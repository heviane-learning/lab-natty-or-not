# Experimento 003: Geração do Capítulo 1 do E-book

- **Data:** 30/10/2026
- **Agente / Modelo:** Gemini 1.5 Pro / Antigravity
- **Objetivo:** Escrever o texto completo do Capítulo 1 do E-book ("O Efeito Fake Natty no Código"), cobrindo produtividade sintética, assimetria cognitiva em code review e teste tautológico com código comparativo.
- **Critério de Aceite:** Ausência de introduções genéricas ("zero fluff"), profundidade técnica para seniores, inclusão de exemplo prático comparativo em código e respeito à SPEC-001.

---

## 📥 Prompt Enviado

```markdown
# Contexto
Você é o co-autor técnico de um e-book de engenharia de software para o laboratório "Natty or Not Lab" (GitHub: heviane-learning/natty-or-not-lab). A autora principal é uma engenheira de software tradicional sênior que está estabelecendo padrões rigorosos para o desenvolvimento assistido por IA.

# Objetivo
Escrever o texto completo do **Capítulo 1: O Efeito "Fake Natty" no Código**, com profundidade técnica para desenvolvedores plenos, sêniores e tech leads.

# Diretrizes Mandatórias da SPEC-001 e AGENTS.md:
1. Zero Fluff / Anti-Clichês: Proibido iniciar com frases vazias ("No mundo de hoje...", "Na era da inteligência artificial...", "Uma tapeçaria de desafios"). Vá direto ao ponto técnico.
2. Extensão: Entre 800 e 1.100 palavras.
3. Tom de Voz: Pragmático, analítico, fundamentado em engenharia de produção e code review.

# Tópicos Obrigatórios a Abordar:
1. A Ilusão da Produtividade Sintética: A diferença entre velocidade de digitação (gerar 200 linhas em segundos) e custo de ciclo de vida (manutenibilidade, débito técnico e depuração).
2. A Assimetria Cognitiva: Por que ler, interpretar e revisar código sutilmente incorreto de IA demanda mais esforço mental do que escrever a solução do zero.
3. Estudo de Caso de Código (Fake Natty vs. Natty Real):
   - Apresentar um exemplo prático de teste unitário gerado por IA com falso positivo (ex: teste tautológico ou mock cego que passa com 100% de cobertura, mas não valida o invariante da regra de negócio).
   - Apresentar a versão "Natty", demonstrando o teste que realmente assegura o comportamento em cenários adversos.
4. Caixas de Alerta: Utilizar `> [!WARNING]` para destacar armadilhas comuns em pull requests.

# Formato de Saída:
Retorne o texto formatado em GitHub Flavored Markdown pronto para publicação, com subtítulos claros, código devidamente tipado e formatado.
```

---

## 📤 Resposta da IA

> Texto completo gerado e salvo em `projetos/01-eng-software-natty/entregaveis/ebook/capitulo-1.md`.
>
> **Estrutura entregue:**
> - Seção 1: A Ilusão da Produtividade Sintética (distinção entre velocidade de digitação e densidade semântica de código).
> - Seção 2: A Assimetria Cognitiva no Code Review (viés da autoridade estética, esforço desproporcional de depuração e fadiga de contexto).
> - Seção 3: Estudo de Caso Prático em TypeScript/Jest contrastando um teste tautológico (*Fake Natty*) com um teste de invariante e idempotência (*Natty Real*).
> - Seção 4: Lições de Engenharia e diretrizes de revisão.

---

## 🧐 Avaliação Humana & Decisões (Human-in-the-Loop)

- **Pontos Fortes:**
  - O texto cumpriu 100% o critério "Zero Fluff", iniciando diretamente no problema técnico da velocidade de digitação vs. custo de ciclo de vida.
  - O exemplo de teste unitário em TypeScript com mock circular expressou perfeitamente o problema do "falso positivo" que atinge 100% de cobertura sem testar o invariante de negócio.
- **Ajustes e Validação:**
  - O capítulo atendeu aos critérios da `SPEC-001-ebook.md` e foi aprovado sem necessidade de refatoração para a versão preliminar.
- **Resultado do Experimento:**
  - Aprovado e consolidado em `projetos/01-eng-software-natty/entregaveis/ebook/capitulo-1.md`.

