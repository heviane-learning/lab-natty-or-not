# Capítulo 2: Antipatterns no Desenvolvimento Assistido por IA

Assistentes de código baseados em Modelos de Linguagem de Grande Porte (LLMs) operam calculando probabilidades estatísticas de tokens subsequentes. Eles não possuem um compilador interno, não realizam resolução de dependências em tempo real e não compreendem o ciclo de vida da infraestrutura onde o código será executado.

Quando a equipe de engenharia adota copilotos sem governança e sem diretrizes claras de revisão, padrões arquiteturais degenerativos começam a se infiltrar silenciosamente nos repositórios. A seguir, dissecamos os quatro antipatterns mais críticos identificados em bases de código assistidas por IA, seus impactos operacionais e como neutralizá-los.

---

## 1. Dependency Hallucination (Alucinação de Pacotes)

A alucinação de dependências ocorre quando o modelo sugere a importação de uma biblioteca que não existe, mas cujo nome parece perfeitamente razoável e idiomático para a tarefa solicitada (ex.: `express-jwt-permissions-guard` ou `py-crypto-vault-validator`).

O perigo imediato não é apenas a falha de build (`ModuleNotFoundError`), mas sim a vulnerabilidade de segurança conhecida como **Slopsquatting** (ou *AI Package Typosquatting*):

> [!CAUTION]
> **Ataque à Cadeia de Suprimentos via IA:** Atacantes monitoram alucinações recorrentes de LLMs e registram intencionalmente esses nomes de pacotes fantasmas nos repositórios públicos (npm, PyPI, Maven Central). Se um desenvolvedor aceita a sugestão da IA e roda `npm install` sem verificar a autenticidade do pacote, instala código malicioso diretamente na esteira de integração contínua (CI/CD) da organização.

---

## 2. Blind Acceptance ("Síndrome do Tab-Tab-Tab")

A facilidade dos atalhos de autocompletion cria um hábito perigoso: o desenvolvedor aperta `Tab` sucessivamente para blocos inteiros de código sem realizar a leitura analítica linha por linha.

### Sintomas em Produção:
- **Vazamento de Recursos:** Código gerado frequentemente instancia conexões com bancos de dados, buffers ou streams sem fechá-los em cláusulas seguras (`try/finally`, context managers `with` ou blocos `using`).
- **Explosão de Complexidade Ciclomática:** O modelo tende a resolver problemas de fluxo encadeando múltiplos blocos `if/else` aninhados e `switch/case` redundantes, em vez de aplicar polimorfismo ou estratégias de design patterns.
- **Tratamento Genérico de Falhas:** Capturas cegas do tipo `catch (Exception e) { return null; }` que silenciam erros críticos e tornam a rastreabilidade via logs impossível em ambiente de produção.

---

## 3. Context Starvation (Inanição de Contexto)

Ocorre quando o desenvolvedor fornece ao copiloto apenas o trecho isolado onde está trabalhando, esperando que ele deduza regras arquiteturais globais, padrões de concorrência e modelos de domínio da empresa.

Modelos de IA sofrem do viés de localidade: sem a visão do sistema, eles resolvem o problema imediato violando as fronteiras arquiteturais do projeto. O resultado é a criação de acoplamentos indevidos (ex.: camadas de controle acessando bancos diretamente sem passar pelos repositórios de domínio).

---

## 4. Boilerplate Inflation

Como a IA não "sente dor" ao digitar, ela tende a gerar dezenas de linhas de lógica imperativa verbosa para tarefas que bibliotecas padrão ou funções de ordem superior resolveriam de forma declarativa e concisa.

### Exemplo Comparativo:

#### ❌ Boilerplate Inflation Gerado por IA (Fake Natty)
```typescript
// 35 linhas de lógica manual imperativa, suscetível a erros de mutação e referências nulas
export function aggregateUserTransactions(transactions: any[]): any {
  let result: any = {};
  if (!transactions || transactions.length === 0) {
    return result;
  }
  for (let i = 0; i < transactions.length; i++) {
    let t = transactions[i];
    if (t && t.status === 'COMPLETED' && t.userId) {
      if (!result[t.userId]) {
        result[t.userId] = { total: 0, count: 0, items: [] };
      }
      result[t.userId].total = result[t.userId].total + (t.amount || 0);
      result[t.userId].count = result[t.userId].count + 1;
      result[t.userId].items.push(t.id);
    }
  }
  return result;
}
```

#### ✅ Solução Idiomática, Tipada e Declarativa (Natty Real)
```typescript
// Solução imutável, fortemente tipada e com complexidade ciclomática mínima
interface Transaction {
  id: string;
  userId: string;
  amount: number;
  status: 'PENDING' | 'COMPLETED' | 'FAILED';
}

interface UserSummary {
  total: number;
  count: number;
  items: readonly string[];
}

export function aggregateUserTransactions(
  transactions: readonly Transaction[]
): ReadonlyMap<string, UserSummary> {
  return transactions
    .filter((t): t is Transaction & { status: 'COMPLETED' } => t.status === 'COMPLETED')
    .reduce((acc, t) => {
      const current = acc.get(t.userId) ?? { total: 0, count: 0, items: [] };
      return acc.set(t.userId, {
        total: current.total + t.amount,
        count: current.count + 1,
        items: [...current.items, t.id],
      });
    }, new Map<string, UserSummary>());
}
```

---

## 📊 Matriz Comparativa de Antipatterns

A tabela abaixo resume os sintomas visíveis em Pull Requests e os planos de ação preventiva:

| Antipattern | Sintoma no Pull Request | Impacto Técnico Oculto | Ação de Mitigação |
| :--- | :--- | :--- | :--- |
| **Dependency Hallucination** | Novos pacotes adicionados ao `package.json` sem justificativa. | Risco de supply chain attack (*Slopsquatting*) e quebra de build. | Uso obrigatório de lockfiles e verificação manual em registros oficiais antes de aceitar dependências. |
| **Blind Acceptance** | PRs gigantescos (+500 linhas) gerados em poucos minutos. | Falhas de concorrência, memory leaks e tratamento cego de erros. | Limitar PRs por escopo e exigir leitura linha a linha antes do commit. |
| **Context Starvation** | Código funcional, mas que ignora os padrões do repositório. | Corrosão arquitetural e quebra de bounded contexts. | Uso de regras de contexto (`AGENTS.md`, `.cursorrules`, system prompts). |
| **Boilerplate Inflation** | Funções excessivamente longas com loops manuais e mutabilidade. | Degradação de legibilidade e alta densidade de manutenção. | Priorizar soluções funcionais e exigir linters estritos de complexidade ciclomática. |

---

## 🛠️ Conclusão do Capítulo

Evitar antipatterns gerados por IA exige que o engenheiro assuma a postura de **Auditor Técnico**, e não de mero operador de teclado. A presença de um copiloto não diminui a responsabilidade sobre o código entregue; ao contrário, exige maior atenção aos detalhes arquiteturais e de segurança.

No **Capítulo 3**, apresentaremos o outro lado da moeda: as **Boas Práticas da Engenharia de Software Natty**, explorando como técnicas como *Spec-Driven Prompting* e *Test-Driven Prompting* transformam assistentes em multiplicadores reais de qualidade técnica.

