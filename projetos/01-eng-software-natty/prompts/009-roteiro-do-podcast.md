# Experimento 009: Roteiro de Podcast Técnico em Diálogo

- **Data:** 30/10/2026
- **Agente / Modelo:** Gemini 1.5 Pro / Antigravity
- **Objetivo:** Roteirizar episódio de podcast dinâmico em formato de diálogo entre dois engenheiros (Host Lucas e Especialista Helena) para demonstrar síntese de áudio realista e humanizada sobre Engenharia de Software Natty.
- **Critério de Aceite:** Contagem de palavras entre 350 e 450, linguagem coloquial autêntica com termos técnicos rigorosos (idempotência, testes tautológicos, Slopsquatting, Spec-Driven Prompting) e aderência à SPEC-003.

---

## 📥 Prompt Enviado

```markdown
# Contexto
Você é o co-autor do laboratório "Natty or Not Lab" (GitHub: heviane-learning/natty-or-not-lab). A autora principal é uma engenheira de software tradicional sênior estabelecendo padrões para desenvolvimento assistido por IA.

# Objetivo
Criar o roteiro completo de um episódio de podcast curto (2 a 3 minutos) em formato de diálogo natural entre dois engenheiros: Lucas (Host curioso que usa copilotos) e Helena (Especialista sênior e alter ego da autora).

# Diretrizes da SPEC-003 e AGENTS.md:
1. Zero Fluff: Diálogo ágil, sem enrolação. Começar direto com uma situação real de desenvolvimento (gerar código em 15 minutos vs debugar em produção).
2. Duração: Entre 350 e 450 palavras faladas.
3. Termos Técnicos Obrigatórios: Código Fake Natty, testes tautológicos, idempotência, Slopsquatting, Spec-Driven Prompting, Desenvolvedor Centauro e Soberania Humana.
4. Formato de Saída: Roteiro decupado com marcações de áudio (trilha de fundo, risos, pausas) e indicação de vozes recomendadas no ElevenLabs.
```

---

## 📤 Resposta da IA

> Roteiro gerado e salvo em `projetos/01-eng-software-natty/entregaveis/podcast/roteiro.md`.
>
> **Métricas do Roteiro:**
> - Palavras totais: 398 palavras faladas.
> - Duração prevista: ~2 minutos e 30 segundos (ritmo de fala fluido de 160 palavras por minuto com pausas e interações).
> - Personagens: Lucas (Host, voz jovem/entusiasta) e Helena (Especialista, voz madura/analítica).
> - Conceitos cobertos: Contraste Fake Natty vs. Natty Real, testes tautológicos em pagamentos, riscos de supply chain (Slopsquatting) e a metodologia Spec-Driven Development.

---

## 🧐 Avaliação Humana & Decisões (Human-in-the-Loop)

- **Pontos Fortes:**
  - O formato de conversa dinâmica quebra completamente a artificialidade dos podcasts tradicionais gerados por IA que parecem a leitura mecânica de um artigo.
  - A química entre os personagens equilibra perfeitamente o entusiasmo pela velocidade da IA com a responsabilidade técnica de quem mantém sistemas em produção.
  - O tamanho (398 palavras) é ideal para síntese no ElevenLabs (dentro do limite de cotas gratuitas/iniciais de projetos de portfólio).
- **Resultado do Experimento:**
  - Aprovado e consolidado em `projetos/01-eng-software-natty/entregaveis/podcast/roteiro.md`.

