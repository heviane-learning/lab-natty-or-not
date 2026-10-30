# ADR-003: Padronização de Artefatos de Governança via Templates Formais (Docs-as-Code)

- **Status:** APROVADO
- **Data:** 30/10/2026
- **Autora:** Heviane
- **Contexto:** Padronização e determinismo na criação de novos projetos, especificações, logs de prompts e backlogs no laboratório `natty-or-not-lab`.

---

## 🎯 1. Contexto do Problema

Com a transição para um modelo Monorepo Multiprojeto e a atuação contínua de agentes de IA, identificou-se o risco de fragmentação e heterogeneidade estrutural. Cada novo projeto criado corria o risco de adotar convenções discrepantes de backlog, formatações soltas de prompts ou especificações sem critérios objetivos de aceite (*Definition of Done*).

Para garantir escalabilidade, leitura intuitiva por avaliadores e execução determinística por agentes de IA, era necessário estabelecer um padrão imutável de artefatos.

---

## ⚖️ 2. Alternativas Consideradas

### Alternativa A: Formatação Livre por Projeto ("Ad-hoc")
- **Prós:** Liberdade total em cada novo desafio.
- **Contras:** Caos estrutural, alta carga cognitiva de navegação e forte tendência dos agentes de IA a gerarem estruturas inconsistentes.

### Alternativa B: Templates Formais Reutilizáveis (Docs-as-Code)
- **Prós:**
  - *Determinismo:* Agentes geram novos arquivos instanciando schemas pré-definidos sem alucinações de formato.
  - *Consistência de Portfólio:* Quem visita qualquer projeto encontra a mesma régua de qualidade.
  - *Separação de Abstração:* Distinção nítida entre escopo macro de portfólio (Flight Level 2) e micro de execução (Flight Level 1).
- **Contras:** Pequeno overhead inicial na criação e manutenção dos templates em `docs/`.

---

## 🏆 3. Decisão Arquitetural

Adotar a **Alternativa B**: Estabelecer um **Catálogo Central de Templates** em `docs/` como padrão obrigatório para qualquer novo artefato no repositório:

1. **`docs/template-spec.md`:** Contrato formal de requisitos, escopo e *Definition of Done (DoD)* para entregáveis (SDD).
2. **`docs/template-prompt.md`:** Modelo unificado de experimento de prompt engineering com metadados, prompt, retorno da IA e avaliação *Human-in-the-Loop*.
3. **`docs/template-backlog-projeto.md`:** Modelo Kanban operacional para projetos (Dashboard %, To Do, In Progress, Done clusterizado).
4. **`docs/template-backlog-macro.md`:** Modelo de roadmap executivo para a raiz de novos repositórios monorepo.

---

## 📈 4. Consequências e Resultados Esperados

- **Positivas:** Inicialização instantânea de novos projetos com zero atrito, previsibilidade para agentes de IA e experiência de leitura executiva para tech leads.
- **Governança:** Qualquer agente atuando no repositório deve consultar obrigatoriamente a pasta `docs/` antes de criar novos arquivos estruturais (conforme registrado no `AGENTS.md`).
