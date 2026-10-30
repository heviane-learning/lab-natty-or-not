# SPEC-003: Podcast Técnico — "Natty or Not: Engenharia sem Ilusão"

- **Status:** APROVADO PARA EXECUÇÃO
- **Data de Criação:** 30/10/2026
- **Autora:** Heviane
- **Tema:** *Engenharia de Software Natty: Boas Práticas, Limites e Antipatterns com IA*
- **Formato:** Episódio curto de mesa-redonda / conversa entre dois engenheiros (2 a 3 minutos).

---

## 🎯 1. Objetivo do Artefato

Criar uma experiência imersiva e natural de áudio que discuta a transição da engenharia tradicional para o desenvolvimento assistido por IA. O foco é demonstrar como sintetizar diálogos autênticos, dinâmicos e com química vocal humana (*interrupções sutis, concordâncias coloquiais e tom descontraído, porém tecnicamente rigoroso*).

---

## 👥 2. Personagens do Episódio

- **Host (Lucas):** Desenvolvedor empolgado com a velocidade dos copilotos, que traz os questionamentos comuns do mercado.
- **Especialista (Helena):** Engenheira de software sênior (alter ego da autora), analítica, pragmática e defensora de contratos estritos, arquitetura sólida e soberania técnica.

---

## 📐 3. Estrutura Roteirizada do Episódio (Blocos)

Duração total entre 2 e 3 minutos (aproximadamente 350 a 450 palavras no total):

1. **Abertura & Provocação (00:00 - 00:35):**
   - Lucas comenta sobre ter gerado um microsserviço inteiro em 15 minutos com IA.
   - Helena faz a provocação: "Gerou em 15 minutos, mas quanto tempo você vai passar debugando em produção?"
2. **O Risco do Código Fake Natty (00:35 - 01:20):**
   - Discussão sobre o teste tautológico e a alucinação de pacotes (Slopsquatting).
   - Helena explica por que o código parece perfeito visualmente, mas quebra em concorrência.
3. **A Virada de Chave: Engenharia Natty (01:20 - 02:10):**
   - Apresentação dos pilares: *Spec-Driven Prompting* e *Test-Driven Prompting*.
   - Por que o desenvolvedor agora é um arquiteto e orquestrador de múltiplos agentes.
4. **Fechamento & Recado Prático (02:10 - 02:40):**
   - Convite para conferir o e-book e as especificações no repositório GitHub.

---

## 🤖 4. Stack de Ferramentas Recomendada

- **Síntese de Voz (TTS Multivoz):** [ElevenLabs](https://elevenlabs.io/) (utilizando *Projects* ou geração de duas vozes contrastantes com modelo Multilingual v2) ou [NotebookLM](https://notebooklm.google.com/) Audio Overview.
- **Edição & Pós-Produção:** [Audacity](https://www.audacityteam.org/) (equalização, compressão vocal suave, remoção de ruídos e inserção de trilha de entrada/saída em volume sutil).

---

## ✅ 5. Critérios de Aceite (Definition of Done - DoD)

- [ ] **Roteiro Natural:** Diálogo com marcadores de respiração, risos sutis e linguagem coloquial técnica registrado em `prompts/009-roteiro-do-podcast.md`.
- [ ] **Contagem de Palavras:** Entre 350 e 450 palavras faladas.
- [ ] **Profundidade Técnica:** Menção explícita a invariantes, testes não-tautológicos e Spec-Driven Development.
- [ ] **Documentação:** Roteiro completo salvo em `entregaveis/podcast/roteiro.md`.

