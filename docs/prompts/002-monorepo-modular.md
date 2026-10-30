# Repositório para multiplos projetos

## 📥 Prompt Enviado

```markdown

```

## 📤 Resposta da IA

Essa visão é **excelente e arquiteturalmente muito superior**.

Na engenharia de software tradicional, o que você está propondo é a transição de um "monolito acoplado" para um **Monorepo Modular (ou Bounded Contexts)**. Em vez de o repositório ser descartável (um único trabalho de curso), ele se torna o seu **Laboratório Permanente de Casos de Estudo de IA** (*AI Engineering Lab*).

## 🎯 Por que essa abordagem é muito melhor?

### 1. Alta Coesão e Baixo Acoplamento

Se mantivéssemos tudo na raiz (`prompts/`, `specs/`, `docs/`), quando você criasse o segundo ou terceiro projeto, a pasta `prompts/` viraria uma lista confusa com dezenas de arquivos de temas completamente diferentes.  
Com pastas dedicadas, cada desafio tem seu próprio ciclo de vida fechado.

### 2. Otimização Brutal de Contexto para Agentes de IA

Modelos de linguagem têm limite de janela de contexto e sofrem de "atenção dispersa" quando há arquivos demais no projeto.  
Ao isolar cada tema em sua própria pasta, podemos instruir o agente: *"Atue apenas dentro de `labs/01-engenharia-de-software-natty/`"*. O agente lerá apenas as specs e prompts daquele tema, sem alucinar misturando referências de projetos anteriores.

### 3. O README da Raiz vira um "Portal / Catálogo de Portfólio"

O `README.md` principal deixa de ser a explicação de um único e-book e passa a ser o seu **Showcase Executivo**, listando os cases já concluídos e os em andamento:

| Lab | Tema | Formatos | Status | Link |
| :---: | :--- | :---: | :---: | :---: |
| **01** | Engenharia de Software Natty: Boas Práticas e Antipatterns | E-book, Vídeo, Podcast | 🟡 Em andamento | [Ver Lab](file:///e:/Projects/GitHub/heviane-learning/natty-or-not-lab/labs/01-eng-software-natty) |
| **02** | RAG em Produção: Arquitetura e Mitigação de Alucinações | E-book, Infográfico | ⚪ Planejado | — |

---

## 📂 Como ficaria a arquitetura do repositório?

```text
natty-or-not-lab/
├── .gitignore
├── LICENSE
├── AGENTS.md                  # Regras globais de governança para qualquer IA
├── README.md                  # Hub central / Portfólio com catálogo de projetos
├── backlog.md                 # Roadmap macro de novos desafios
│
├── templates/                 # Padrões reutilizáveis para novos labs
│   ├── spec-template.md       # Template de SDD para novos artefatos
│   └── prompt-template.md     # Template unificado de prompt
│
└── labs/                      # (ou projetos/ / cases/)
    │
    └── 01-eng-software-natty/ # 👈 Nosso projeto atual isolado
        ├── README.md          # Resumo executivo específico deste lab
        ├── specs/             # Specs formais (SPEC-001 E-book, SPEC-002 Vídeo...)
        │   └── SPEC-001-ebook.md
        ├── prompts/           # Logs de prompts exclusivos deste tema
        │   └── 001-concepcao.md
        └── entregaveis/       # Artefatos finais prontos
            ├── ebook/         # E-book consolidado (Markdown / PDF / Capa)
            ├── video/         # Roteiro e links do avatar
            └── podcast/       # Roteiro e áudio gerado
```

---

## 💡 Recomendação de Design: Modular por Tema (e não por formato)

Manter **E-book + Vídeo + Podcast dentro da mesma pasta do tema** (como no exemplo acima) é o ideal, porque eles compartilham o mesmo domínio de conhecimento, as mesmas fontes de pesquisa e a mesma identidade visual.

### Qual nome você prefere para a pasta-mãe dos projetos?

- **`labs/`** (Combina perfeitamente com o nome do repositório `natty-or-not-lab`)
- **`projetos/`**
- **`cases/`**

Se você aprovar, podemos reorganizar a estrutura atual para dentro de `labs/01-eng-software-natty/` e atualizar o `README.md` e o `AGENTS.md` para refletir esse modelo monorepo. O que acha?

---

## 🧐 Avaliação Humana & Decisões (Human-in-the-Loop)
