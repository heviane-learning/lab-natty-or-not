# 📋 Backlog do Projeto: Engenharia de Software Natty

Acompanhamento de tarefas, ciclo de vida e status dos entregáveis do projeto `projetos/01-eng-software-natty`.

---

## 📊 Dashboard de Status do Projeto

| Entregável / Dimensão | Especificação (SDD) | Roteiro / Conteúdo | Ativo Final de Mídia | Status Geral |
| :--- | :---: | :---: | :---: | :---: |
| 📖 **E-book Técnico** | [SPEC-001](specs/SPEC-001-ebook.md) ✅ | [ebook-completo.md](entregaveis/ebook/ebook-completo.md) ✅ | Capa (Em geração) ⏳ | 🟡 90% |
| 🎬 **Vídeo Promocional** | [SPEC-002](specs/SPEC-002-video.md) ✅ | [roteiro.md](entregaveis/video/roteiro.md) ✅ | Vídeo renderizado ⏳ | 🟡 60% |
| 🎙️ **Podcast Técnico** | [SPEC-003](specs/SPEC-003-podcast.md) ✅ | [roteiro.md](entregaveis/podcast/roteiro.md) ✅ | Áudio sintetizado ⏳ | 🟡 60% |

---

## ⏳ 1. A Fazer (To Do)

Tarefas planejadas aguardando execução:

- [ ] **Vídeo:** Renderizar o vídeo promocional com Avatar Virtual (HeyGen / D-ID).
- [ ] **Vídeo:** Realizar pós-produção e cortes dinâmicos no CapCut.
- [ ] **Podcast:** Sintetizar o áudio das vozes de Lucas e Helena no ElevenLabs (ou NotebookLM).
- [ ] **Podcast:** Aplicar equalização e trilha de fundo sutil no Audacity.
- [ ] **Fechamento:** Adicionar links finais dos arquivos de mídia no [README.md da raiz](../../README.md).

---

## 🚧 2. Em Andamento (In Progress / WIP)

Tarefas com etapas intermediárias em desenvolvimento:

- [ ] **Capa do E-book:** Prompts calibrados gerados ([Experimento 007](prompts/007-capa-do-ebook.md)), aguardando geração visual e upload em `entregaveis/ebook/capa.png`.
- [ ] **Documentação de Vídeo:** Estrutura pronta, aguardando link do vídeo final em `entregaveis/video/README.md`.
- [ ] **Documentação de Podcast:** Estrutura pronta, aguardando link do episódio em `entregaveis/podcast/README.md`.

---

## ✅ 3. Concluído (Done)

### 🏛️ Governança & Especificações Formais (SDD)
- [x] Configuração do Gemini Notebook para fontes e referências.
- [x] Concepção inicial e escopo do projeto ([Experimento 001](prompts/001-concepcao-do-projeto.md)).
- [x] Definição temática do projeto 01 ([Experimento 002](prompts/002-definicao-do-tema.md)).
- [x] Criação da especificação formal do E-book ([SPEC-001](specs/SPEC-001-ebook.md)).
- [x] Criação da especificação formal do Vídeo Promocional ([SPEC-002](specs/SPEC-002-video.md)).
- [x] Criação da especificação formal do Podcast Técnico ([SPEC-003](specs/SPEC-003-podcast.md)).

### 📖 Entregável 1: E-book Técnico
- [x] **Capítulo 1:** O Efeito "Fake Natty" no Código ([capitulo-1.md](entregaveis/ebook/capitulo-1.md) \| [Prompt 003](prompts/003-capitulo-1-fake-natty.md)).
- [x] **Capítulo 2:** Antipatterns no Desenvolvimento com IA ([capitulo-2.md](entregaveis/ebook/capitulo-2.md) \| [Prompt 004](prompts/004-capitulo-2-antipatterns.md)).
- [x] **Capítulo 3:** Engenharia de Software Natty: Boas Práticas ([capitulo-3.md](entregaveis/ebook/capitulo-3.md) \| [Prompt 005](prompts/005-capitulo-3-boas-praticas.md)).
- [x] **Capítulo 4:** O Desenvolvedor Centauro e Checklist de PR ([capitulo-4.md](entregaveis/ebook/capitulo-4.md) \| [Prompt 006](prompts/006-capitulo-4-desenvolvedor-centauro.md)).
- [x] Consolidação final do volume compilado ([ebook-completo.md](entregaveis/ebook/ebook-completo.md)).
- [x] Engenharia de prompt para imagem da capa ([Prompt 007](prompts/007-capa-do-ebook.md)).

### 🎬 Entregável 2: Vídeo Promocional com Avatar
- [x] Roteirização decupada de 50s com marcações de tempo e dicas anti-estatismo ([roteiro.md](entregaveis/video/roteiro.md) \| [Prompt 008](prompts/008-roteiro-do-video.md)).

### 🎙️ Entregável 3: Podcast Técnico
- [x] Roteirização em diálogo dinâmico (Lucas & Helena) cobrindo microsserviços, Slopsquatting e SDD ([roteiro.md](entregaveis/podcast/roteiro.md) \| [Prompt 009](prompts/009-roteiro-do-podcast.md)).
