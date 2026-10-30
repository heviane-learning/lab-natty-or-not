# Experimento 005: Geração do Capítulo 3 do E-book

- **Data:** 30/10/2026
- **Agente / Modelo:** Gemini 1.5 Pro / Antigravity
- **Objetivo:** Escrever o texto completo do Capítulo 3 do E-book ("Engenharia de Software Natty: Boas Práticas e Padrões"), abordando Spec-Driven Prompting, Test-Driven Prompting, Modularização Estrita e Governança de Contexto, com diagrama Mermaid e código em TypeScript com Zod.
- **Critério de Aceite:** Ausência de introduções genéricas ("zero fluff"), foco metodológico e arquitetural, presença de diagrama Mermaid funcional e exemplo de código com contrato estrito e função pura.

---

## 📥 Prompt Enviado

```markdown
# Contexto
Você é o co-autor técnico de um e-book de engenharia de software para o laboratório "Natty or Not Lab" (GitHub: heviane-learning/natty-or-not-lab). A autora principal é uma engenheira de software tradicional sênior focada em metodologias determinísticas para guiar agentes e copilotos.

# Objetivo
Escrever o texto completo do **Capítulo 3: Engenharia de Software Natty (Boas Práticas e Padrões)**, focado em metodologias práticas de engenharia de software aplicadas ao desenvolvimento assistido por IA.

# Diretrizes Mandatórias da SPEC-001 e AGENTS.md:
1. Zero Fluff / Anti-Clichês: Sem introduções genéricas. Entrar direto nos métodos e na fundamentação técnica.
2. Extensão: Entre 800 e 1.100 palavras.
3. Tom de Voz: Pragmático, arquitetural, centrado em contratos e testes.

# Tópicos Obrigatórios:
1. Spec-Driven Prompting:
   - A prática de estabelecer esquemas e contratos estritos (ex: Zod, Pydantic, TypeScript types ou OpenAPI) antes de solicitar a implementação à IA.
2. Test-Driven Prompting (TDP):
   - Inversão de dependência na esteira de IA: fornecer ou gerar a suíte de testes de invariantes antes do código de produção, criando uma barreira determinística contra alucinações.
3. Redução do Espaço de Hipóteses (Modularização Estrita):
   - Por que funções puras, arquiteturas hexagonais/ports-and-adapters e baixo acoplamento aumentam drasticamente a precisão estatística dos LLMs.
4. Governança de Contexto Operacional:
   - O papel de arquivos como `AGENTS.md`, `.cursorrules` e system prompts para ancorar o comportamento de agentes autônomos.
5. Diagrama Mermaid:
   - Fluxograma conceitual (`flowchart LR` ou `flowchart TD`) representando a esteira "Natty" (Spec ➔ Testes de Contrato ➔ Geração com Agente ➔ Verificação Automatizada ➔ Aceite Humano).
6. Exemplo Prático de Código:
   - Demonstração de Spec-Driven Prompting com um contrato explícito (ex: validação com esquema estrito) gerando uma função pura determinística.

# Formato de Saída:
Markdown pronto para publicação, com diagrama Mermaid funcional, caixas de alerta `> [!TIP]` e `> [!NOTE]` e código devidamente tipado.
```

---

## 📤 Resposta da IA

> Texto completo gerado e salvo em `projetos/01-eng-software-natty/entregaveis/ebook/capitulo-3.md`.
>
> **Estrutura entregue:**
> - Seção 1: O Pipeline de Entrega Natty com diagrama Mermaid (`flowchart LR`).
> - Seção 2: Spec-Driven Prompting (redução do espaço estatístico com contratos) e exemplo prático em TypeScript utilizando validação com Zod para entrada e saída imutáveis.
> - Seção 3: Test-Driven Prompting (TDP) e inversão de fluxo de geração.
> - Seção 4: Redução do Espaço de Hipóteses via Arquitetura Hexagonal, funções puras e SRP.
> - Seção 5: Governança de Contexto Operacional com `AGENTS.md` e regras de repositório.

---

## 🧐 Avaliação Humana & Decisões (Human-in-the-Loop)

- **Pontos Fortes:**
  - O diagrama Mermaid estruturou perfeitamente o pipeline de engenharia com verificação automatizada e soberania humana.
  - O exemplo de código com Zod demonstrou de forma contundente o conceito de "contrato antes da sintaxe", validando invariantes numéricos e regras de negócio sem efeito colateral.
  - O capítulo oferece um contraste claro e prático contra o "vibe coding".
- **Resultado do Experimento:**
  - Aprovado e consolidado em `projetos/01-eng-software-natty/entregaveis/ebook/capitulo-3.md`.

