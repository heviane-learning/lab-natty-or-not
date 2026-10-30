# SPEC-002: Vídeo Promocional com Avatar Virtual

- **Status:** APROVADO PARA EXECUÇÃO
- **Data de Criação:** 30/10/2026
- **Autora:** Heviane
- **Tema:** *Engenharia de Software Natty: Boas Práticas, Limites e Antipatterns com IA*
- **Formato:** Vídeo curto promocional (30 a 60 segundos) com avatar hiper-realista e legendas dinâmicas.

---

## 🎯 1. Objetivo do Artefato

Apresentar de forma magnética, dinâmica e tecnicamente madura o tema do laboratório e o lançamento do e-book. O vídeo tem como objetivo demonstrar domínio de ferramentas generativas de vídeo e áudio, superando os artefatos sintéticos típicos (expressões congeladas, sincronia labial mecânica e narração sem ritmo humano).

---

## 👥 2. Público-Alvo & Tom de Voz

- **Público:** Desenvolvedores de software, tech leads, recrutadores de tecnologia e comunidade tech.
- **Tom de Voz:** Seguro, pragmático, provocativo e profissional (sem tom de vendedor de infoproduto ou clichês vazios).

---

## 📐 3. Estrutura Roteirizada (Cenas e Cronometragem)

O roteiro terá duração estimada entre 45 e 55 segundos (aproximadamente 110 a 130 palavras faladas):

1. **Gancho Visual e Provocação Técnica (00s - 12s):**
   - *Foco:* Questionar a falsa sensação de segurança do código gerado por IA.
   - *Fala Base:* "Seu código gerado por copilotos parece profissional na superfície... Mas você realmente sabe o que ele está entregando para o seu ambiente de produção?"
2. **Apresentação do Problema Real (12s - 25s):**
   - *Foco:* Apontar os débitos invisíveis (alucinações de pacotes, testes tautológicos e supply chain attacks).
   - *Fala Base:* "A velocidade de digitação aumentou, mas o custo de manutenção disparou. Na esteira de desenvolvimento, o verdadeiro diferencial não é gerar código rápido — é garantir que ele seja arquiteturalmente sólido e seguro."
3. **Apresentação da Solução / E-book (25s - 42s):**
   - *Foco:* Apresentar o guia prático e a metodologia SDD.
   - *Fala Base:* "Foi por isso que criei o 'Engenharia de Software Natty': um guia de sobrevivência com boas práticas, antipatterns reais e um checklist prático de code review para manter suas bases limpas na era dos agentes autônomos."
4. **Chamada para Ação / CTA (42s - 50s):**
   - *Foco:* Convidar para leitura do repositório no GitHub.
   - *Fala Base:* "O material completo e toda a governança com Spec-Driven Development já estão disponíveis no meu repositório. O link está na descrição. Valeu!"

---

## 🤖 4. Stack de Ferramentas Recomendada

- **Avatar Virtual & Lipsync:** [HeyGen](https://www.heygen.com/) ou [D-ID](https://www.d-id.com/).
- **Síntese de Voz (TTS Humano):** [ElevenLabs](https://elevenlabs.io/) (modelo Multilingual v2 com respiração e inflexão natural) ou a própria voz integrada do HeyGen.
- **Pós-Produção & Legendas:** [CapCut](https://www.capcut.com/) ou [Canva](https://www.canva.com/) (para cortes dinâmicos de respiração, inserção de b-rolls e legendas sincronizadas).

---

## ✅ 5. Critérios de Aceite (Definition of Done - DoD)

- [ ] **Roteiro Calibrado:** Roteiro entre 110 e 130 palavras, com marcações de pausas e ênfases registradas em `prompts/008-roteiro-do-video.md`.
- [ ] **Sincronia Labial Natural:** Sincronia do avatar sem artefatos visuais bizarros.
- [ ] **Pós-edição Dinâmica:** Vídeo editado com trilha de fundo sutil e legendas dinâmicas em português.
- [ ] **Publicação:** Vídeo exportado e link/ativo documentado em `projetos/01-eng-software-natty/entregaveis/video/`.

