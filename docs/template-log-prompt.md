# 🔬 TEMPLATE de Log de Experimentos de Prompt (Prompt Engineering)

Cada projeto conterá um diretório chamado `prompts`, que conterá um arquivo para cada registro
com o ciclo de iteração, testes e refinamento de prompts utilizados ao longo do projeto.

Para manter o rigor de engenharia de software e garantir a rastreabilidade técnica, utilizamos o modelo **unificado por experimento**: cada arquivo `.md` reúne o prompt enviado, a resposta gerada pela IA e a análise crítica humana (*Human-in-the-Loop*).

---

## 📝 Template Padrão para Novos Experimentos

Ao registrar uma nova iteração com a IA, use a estrutura abaixo:

```markdown
# Experimento 00X: [Título Curto do Experimento]

- **Data:** DD/MM/AAAA
- **Agente / Modelo:** [ex: Claude 3.5 Sonnet / GPT-4o / Gemini 1.5 Pro]
- **Objetivo:** [O que a IA deveria gerar ou resolver]
- **Critério de Aceite:** [O que define o sucesso da saída: clareza, ausência de jargão oco, profundidade técnica, etc.]

---

## 📥 Prompt Enviado

\`\`\`markdown
[Texto exato enviado para a IA]
\`\`\`

---

## 📤 Resposta da IA

[Resposta gerada pela IA, destacando os pontos relevantes]

---

## 🧐 Avaliação Humana & Decisões (Human-in-the-Loop)

- **Pontos Fortes:** [O que a IA acertou]
- **Alucinações / Pontos Fracos:** [O que precisou ser corrigido ou descartado]
- **Ajustes Realizados:** [Decisões manuais e edição feitas pela engenheira]
- **Resultado:** [Aprovado / Rejeitado / Refinado no Experimento 00Y]
```
