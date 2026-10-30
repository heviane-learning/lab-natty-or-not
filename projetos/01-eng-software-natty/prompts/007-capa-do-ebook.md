# Experimento 007: Geração de Prompts para a Capa do E-book

- **Data:** 30/10/2026
- **Agente / Modelo:** Gemini 1.5 Pro / Antigravity
- **Objetivo:** Desenvolver prompts calibrados para modelos de difusão de imagem (Midjourney v6.1, Ideogram v2, DALL-E 3) para gerar a arte de capa do e-book "Engenharia de Software Natty".
- **Critério de Aceite:** Expressar visualmente o contraste entre arquitetura limpa (sólida, blueprint) e alucinações sintéticas (caóticas, fragmentadas), com opções para composição visual pura e tipografia embutida.

---

## 📥 Prompts Calibrados Desenvolvidos

### Opção A: Foco em Visual Cinemático / Arte de Fundo (Midjourney v6.1 / DALL-E 3)

```text
A cinematic book cover design, representing high-level Software Engineering and Generative AI. A stark visual contrast: on the left, a solid, elegant, clean architectural monolith made of glass and precision blue-print grid lines, perfectly structured and stable; on the right, digital holographic code fragments dissolving into chaotic, glowing neon particles and unstable synthetic artifacts. Minimalist dark aesthetic, deep slate gray and navy background with subtle cyan and amber highlights, shot on 35mm lens, f/1.8, editorial style, hyper-detailed, clean composition, zero distorted text --ar 3:4 --v 6.1 --style raw
```

### Opção B: Capa Completa com Tipografia Embutida (Ideogram v2)

```text
Professional technical book cover titled "ENGENHARIA DE SOFTWARE NATTY" in bold, elegant sans-serif typography at the top. Subtitle below in crisp modern font: "Boas Práticas, Limites e Antipatterns com IA". Author name at the bottom: "Heviane". Center graphic: a minimalist isometric split illustration showing on the left a clean, solid, orderly software architecture diagram in deep navy and cyan blueprints, and on the right a chaotic disintegration of glowing neon green and orange synthetic digital code. Dark premium editorial cover, matte finish, balanced layout.
```

---

## 📤 Racional Técnico da Composição Visual

1. **Dualidade Conceitual (Natty vs. Fake Natty):** O lado esquerdo representa a solidez da engenharia tradicional (estruturas que não caem), enquanto o lado direito reflete a ilusão do código gerado sem governança (efeito visual de desintegração).
2. **Paleta de Cores Editorial:** Tons sóbrios de azul marinho e ardósia como base transmitem maturidade corporativa, contrastando com pontos de neon ciano e âmbar para modernidade.
3. **Versatilidade de Execução:** A Opção A permite criar a arte e finalizar a tipografia manualmente no Canva, enquanto a Opção B permite renderização tipográfica direta via Ideogram v2.

---

## 🧐 Avaliação Humana & Decisões (Human-in-the-Loop)

- **Decisão:** Prompts aprovados para teste nas ferramentas de geração visual da autora.
- **Próxima Ação:** Gerar a imagem escolhida e salvar o ativo final no diretório `projetos/01-eng-software-natty/entregaveis/ebook/capa.png` (ou `.jpg`).

