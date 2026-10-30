# 🧪 Natty or Not Lab — Engenharia de Software Assistida por IA

> 📌 **Origem do Projeto:** Este laboratório monorepo foi criado a partir do desafio original *[Natural ou Fake Natty](https://github.com/digitalinnovationone/lab-natty-or-not)* da [Digital Innovation One (DIO)](https://www.dio.me/), evoluído para demonstrar práticas avançadas de engenharia de software assistida por inteligência artificial, governança de agentes autônomos e desenvolvimento orientado a especificações (SDD).

Um ecossistema técnico focado na fronteira entre a automação generativa acelerada e a manutenção do rigor arquitetural, segurança e autenticidade ("Natty") do software em produção.

---

## 🏛️ Metodologia & Governança do Laboratório

Diferente de abordagens baseadas em tentativa e erro (*vibe prompting*), este laboratório opera sob princípios formais de engenharia de software:

- **Spec-Driven Development (SDD):** Nenhum artefato é sintetizado sem um contrato prévio formalizado em `specs/` com critérios de aceite objetivos (*Definition of Done*).
- **Governança de Agentes ([AGENTS.md](AGENTS.md)):** Regras operacionais estritas que delimitam o escopo de atuação de copilotos e agentes, exigindo aprovação prévia humana e verificação contínua da documentação.
- **Soberania Técnica (*Human-in-the-Loop*):** A IA atua como força de trabalho executiva, mas a arquitetura, curadoria crítica e responsabilidade do aceite final de código são estritamente humanas.
- **Rastreabilidade Técnica:** Cada iteração, prompt calibrado e avaliação humana é registrado em logs unificados na pasta `prompts/` de cada projeto.

---

## 📂 Catálogo de Projetos do Laboratório

| ID / Projeto | Tema Central | Formatos | Status | Entregáveis & Documentação |
| :---: | :--- | :---: | :---: | :--- |
| **01** | **[Engenharia de Software Natty](projetos/01-eng-software-natty/)**<br>*Boas Práticas, Limites e Antipatterns com IA* | E-book, Vídeo, Podcast | 🟡 Em andamento | 📖 [E-book Completo](projetos/01-eng-software-natty/entregaveis/ebook/ebook-completo.md)<br>📐 [SPEC-001 (E-book)](projetos/01-eng-software-natty/specs/SPEC-001-ebook.md)<br>🔬 [Logs de Prompts](projetos/01-eng-software-natty/prompts/) |
| **02** | **RAG em Produção**<br>*Arquitetura, Chunking e Mitigação de Alucinações* | E-book, Infográfico | ⚪ *Planejado* | [Acompanhar no Backlog](backlog.md) |
| **03** | **Prompt Engineering para Testes**<br>*Test-Driven Prompting e Cobertura de Mutação* | Guia, Código, Lab | ⚪ *Planejado* | [Acompanhar no Backlog](backlog.md) |

---

## 🤖 Stack de Tecnologias Multimodais

- **Engenharia de Prompt & Raciocínio Lógico:** Gemini 1.5 Pro, Claude 3.5 Sonnet, GPT-4o.
- **Assistência in-Editor & Pair Programming:** [Antigravity](https://antigravity.google/), GitHub Copilot.
- **Pesquisa e Prototipagem Centralizada:** [Gemini Notebook do Projeto](https://notebook.google.com/notebook/346205c8-d30f-4f12-8092-de71b7856727).
- **Geração Visual & Identidade:** Midjourney v6.1, Ideogram v2, Canva.
- **Síntese de Vídeo e Áudio:** HeyGen / D-ID, ElevenLabs, CapCut, Audacity.

---

## 🧭 Estrutura do Monorepo

```text
natty-or-not-lab/
├── AGENTS.md                  # System prompt do repositório e regras de governança para IAs
├── README.md                  # Este portal executivo e catálogo de projetos
├── backlog.md                 # Roadmap macro de novos desafios
│
├── docs/                      # Governança global, templates e decisões arquiteturais
│   ├── template-spec.md       # Template de especificação formal (SDD)
│   ├── template-prompt.md     # Template unificado de log de prompt
│   └── prompts/               # Logs das decisões de arquitetura do laboratório
│
└── projetos/                  # Desafios modulares autocontidos
    └── 01-eng-software-natty/ # Projeto ativo: Engenharia de Software Natty
        ├── specs/             # Especificações técnicas formais dos entregáveis
        ├── prompts/           # Histórico calibrado de prompts do projeto
        ├── entregaveis/       # Artefatos prontos (ebook/, video/, podcast/)
        └── backlog.md         # Gestão de tarefas específica do projeto
```

---

## 👤 Autora & Licença

- **Autora:** Heviane ([GitHub Profile](https://github.com/heviane-learning))
- **Licença:** Distribuído sob a licença MIT. Consulte [LICENSE](LICENSE) para mais informações.
