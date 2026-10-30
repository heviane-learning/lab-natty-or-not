# Experimento 004: Geração do Capítulo 2 do E-book

- **Data:** 30/10/2026
- **Agente / Modelo:** Gemini 1.5 Pro / Antigravity
- **Objetivo:** Escrever o texto completo do Capítulo 2 do E-book ("Antipatterns no Desenvolvimento Assistido por IA"), detalhando Dependency Hallucination, Blind Acceptance, Context Starvation, Boilerplate Inflation, com tabela comparativa e código prático.
- **Critério de Aceite:** Ausência de jargão oco, profundidade técnica em segurança (supply chain attacks), exemplo prático comparativo em código (TypeScript) e alinhamento à SPEC-001.

---

## 📥 Prompt Enviado

```markdown
# Contexto
Você é o co-autor técnico de um e-book de engenharia de software para o laboratório "Natty or Not Lab" (GitHub: heviane-learning/natty-or-not-lab). A autora principal é uma engenheira de software tradicional sênior focada em estabelecer práticas seguras e limpas com IA.

# Objetivo
Escrever o texto completo do **Capítulo 2: Antipatterns no Desenvolvimento Assistido por IA**, com foco técnico e pragmático para engenheiros de software e tech leads.

# Diretrizes Mandatórias da SPEC-001 e AGENTS.md:
1. Zero Fluff / Anti-Clichês: Sem frases de abertura genéricas. Entrar direto no problema e na causa raiz.
2. Extensão: Entre 800 e 1.100 palavras.
3. Tom de Voz: Pragmático, analítico, fundamentado em segurança e arquitetura de software.

# Tópicos Obrigatórios:
1. Dependency Hallucination (Alucinação de Pacotes):
   - Como LLMs inventam nomes de pacotes ou métodos inexistentes.
   - O risco crítico de segurança: Typosquatting e ataques à cadeia de suprimentos (Supply Chain Attacks) explorando pacotes alucinados.
2. Blind Acceptance (Aprovação Cega por Tab-Tab-Tab):
   - A ilusão do autocomplete: aceitar blocos de código sem auditar complexidade ciclomática e vazamento de conexões.
3. Context Starvation (Inanição de Contexto):
   - O erro de esperar decisões arquiteturais coerentes quando se envia apenas trechos isolados sem contratos globais.
4. Boilerplate Inflation:
   - Proliferação de código repetitivo e verboso gerado por IA onde uma abstração idiomática resolveria.
5. Tabela Comparativa de Antipatterns:
   - Resumo estruturado com: Antipattern | Sintoma em PR | Impacto Técnico | Ação Preventiva (Mitigação).
6. Exemplo de Código:
   - Estudo de caso com exemplo de código demonstrando o perigo da alucinação de dependência/método ou inflação de boilerplate vs. solução limpa e canônica.

# Formato de Saída:
Markdown pronto para publicação, com caixas de alerta `> [!WARNING]` ou `> [!CAUTION]`, tabelas e código formatado.
```

---

## 📤 Resposta da IA

> Texto completo gerado e salvo em `projetos/01-eng-software-natty/entregaveis/ebook/capitulo-2.md`.
>
> **Estrutura entregue:**
> - Seção 1: Dependency Hallucination e o risco emergente de Slopsquatting (ataque a supply chain).
> - Seção 2: Blind Acceptance (vazamento de conexões, complexidade ciclomática e tratamento cego de exceções).
> - Seção 3: Context Starvation e a violação de bounded contexts.
> - Seção 4: Boilerplate Inflation com exemplo comparativo em TypeScript (código imperativo frágil vs. map/reduce tipado e imutável).
> - Seção 5: Matriz de Antipatterns (Sintoma no PR, Impacto Técnico e Mitigação).

---

## 🧐 Avaliação Humana & Decisões (Human-in-the-Loop)

- **Pontos Fortes:**
  - A inclusão do termo de segurança *Slopsquatting* traz um diferencial técnico raro de encontrar em tutoriais superficiais de IA.
  - O exemplo comparativo de código demonstrou claramente a diferença entre o código macarrônico que a IA costuma sugerir por padrão e uma implementação limpa e funcional que um engenheiro experiente aplicaria.
  - A tabela comparativa sintetiza muito bem o conteúdo para leitura rápida de Tech Leads.
- **Resultado do Experimento:**
  - Aprovado e consolidado em `projetos/01-eng-software-natty/entregaveis/ebook/capitulo-2.md`.

