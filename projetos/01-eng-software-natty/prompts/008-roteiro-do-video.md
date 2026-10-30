# Experimento 008: Calibração do Roteiro para Vídeo Promocional com Avatar

- **Data:** 30/10/2026
- **Agente / Modelo:** Gemini 1.5 Pro / Antigravity
- **Objetivo:** Roteirizar vídeo de 45 a 55 segundos para avatar virtual com gancho de autoridade técnica, problemas reais de engenharia de software e CTA para o repositório, com marcações de prosódia e decupagem de cenas.
- **Critério de Aceite:** Entre 110 e 130 palavras, tom pragmático e maduro, sem clichês de marketing sensacionalista, atendendo à SPEC-002.

---

## 📥 Prompt Enviado

```markdown
# Contexto
Você é o co-autor técnico do laboratório "Natty or Not Lab" (GitHub: heviane-learning/natty-or-not-lab). A autora é uma engenheira de software tradicional sênior estabelecendo padrões para desenvolvimento com IA.

# Objetivo
Criar o roteiro técnico e decupado para um vídeo curto (45 a 55 segundos) com Avatar Virtual e síntese de voz (HeyGen / ElevenLabs), divulgando o lançamento do e-book "Engenharia de Software Natty".

# Diretrizes da SPEC-002 e AGENTS.md:
1. Zero Fluff: Sem introduções de vendedor de infoproduto. Começar com uma provocação técnica sobre a falsa segurança de código gerado por IA.
2. Tamanho: Entre 110 e 130 palavras faladas.
3. Formato de Entrega: Tabela de decupagem (tempo, visual/b-roll, texto falado com pausas) + bloco contínuo pronto para TTS (ElevenLabs/HeyGen) + dicas de produção anti-artefatos sintéticos.
```

---

## 📤 Resposta da IA

> Roteiro gerado e salvo em `projetos/01-eng-software-natty/entregaveis/video/roteiro.md`.
>
> **Métricas do Roteiro:**
> - Palavras totais: 122 palavras.
> - Duração prevista: ~48 segundos (em velocidade de fala natural de 150 wpm com pausas respiratórias).
> - Estrutura: 4 cenas (Gancho ➔ Problema Real ➔ Apresentação do E-book ➔ CTA).
> - Decupagem com sugestão de cortes e b-rolls para disfarçar microexpressões estáticas do avatar.

---

## 🧐 Avaliação Humana & Decisões (Human-in-the-Loop)

- **Pontos Fortes:**
  - O gancho *"Seu código gerado por copilotos parece profissional na superfície... Mas você realmente sabe o que ele está entregando para o seu ambiente de produção?"* é direto e captura imediatamente a atenção de qualquer desenvolvedor.
  - A contagem de 122 palavras encaixa com precisão cirúrgica na janela de 45 a 55 segundos.
  - A inclusão de dicas práticas de pós-edição para disfarçar o aspecto "robótico" do avatar reforça a proposta "Natty".
- **Resultado do Experimento:**
  - Aprovado e consolidado em `projetos/01-eng-software-natty/entregaveis/video/roteiro.md`.

