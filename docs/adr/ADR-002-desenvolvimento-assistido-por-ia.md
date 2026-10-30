# ADR-002: Adoção do Desenvolvimento Assistido por Inteligência Artificial com Governança Técnica

- **Status:** APROVADO
- **Data:** 30/10/2026
- **Autora:** Heviane
- **Contexto:** Definição do paradigma de desenvolvimento de software assistido por modelos generativos e agentes autônomos na organização `heviane-learning`.

---

## 🎯 1. Contexto do Problema

O avanço dos Modelos de Linguagem de Grande Porte (LLMs) e ferramentas de pair programming com agentes autônomos (Antigravity, Claude, ChatGPT, GitHub Copilot) alterou drasticamente a dinâmica da engenharia de software. 

A abordagem comum de mercado ("Vibe Coding") introduz riscos severos:
- Proliferação de débitos técnicos sintéticos e abstrações desnecessárias.
- Insegurança de supply chain via alucinação de dependências (*Slopsquatting*).
- Falsos positivos em testes unitários tautológicos que mascaram falhas de negócio.
- Degradação da manutenibilidade por falta de contexto arquitetural.

A organização necessitava decidir se — e sob quais condições — incorporaria assistentes generativos ao seu fluxo de desenvolvimento diário.

---

## ⚖️ 2. Alternativas Consideradas

### Alternativa A: Desenvolvimento Tradicional 100% Manual (Sem IA)
- **Prós:** Controle total linha a linha, ausência de alucinações sintéticas.
- **Contras:** Gargalo cognitivo em tarefas mecânicas/boilerplate, menor velocidade de prototipagem e perda de competitividade frente ao estado da arte da indústria.

### Alternativa B: Adoção Desgovernada de IA ("Vibe Coding")
- **Prós:** Velocidade imediata de digitação na fase inicial de novos projetos.
- **Contras:** Custo exponencial de depuração, assimetria cognitiva severa no code review, risco de alucinação de pacotes em produção e perda de rastreabilidade técnica.

### Alternativa C: Desenvolvimento Assistido por IA com Governança e Spec-Driven Development (SDD)
- **Prós:**
  - Multiplicação da produtividade técnica canalizada por contratos formais de software.
  - Mitigação de alucinações através de *Spec-Driven Prompting* e *Test-Driven Prompting*.
  - Governança estrita via `AGENTS.md` (System Prompt do repositório com regras de autorização prévia).
  - Soberania humana preservada (*Human-in-the-Loop*).
- **Contras:** Exige disciplina e maior esforço inicial na escrita das especificações antes do código.

---

## 🏆 3. Decisão Arquitetural

Adotar a **Alternativa C**: Incorporar o desenvolvimento assistido por IA como padrão operacional na organização `heviane-learning`, subordinado obrigatoriamente às seguintes diretrizes:

1. **Metodologia Spec-Driven Development (SDD):**
   - Nenhum artefato relevante é gerado sem uma especificação prévia (`specs/SPEC-XXX.md`) contendo contratos estritos e *Definition of Done (DoD)*.
2. **Governança via System Prompt (`AGENTS.md`):**
   - Agentes e copilotos devem operar com escopo delimitado, aprovação prévia mandatória e reanálise contínua da documentação.
3. **Padrão "Anti-Fake Natty" (Zero Fluff):**
   - Código e documentação gerados devem priorizar tipagem estrita, invariantes de negócio, manutenibilidade e ausência de jargão superficial.
4. **Soberania Humana Irrevogável:**
   - O aceite final de qualquer código, teste ou documentação em branch principal é responsabilidade exclusiva da engenheira de software humana.

---

## 📈 4. Consequências e Resultados Esperados

- **Positivas:** Aceleração do ciclo de vida de desenvolvimento, aumento da cobertura de testes com foco em invariantes reais, documentação rica gerada em paralelo e consolidação do papel do *Desenvolvedor Centauro*.
- **Riscos Monitorados:** Atenção constante à assimetria cognitiva em code review, aplicando sempre o *Checklist de Revisão para PRs com IA* (definido no projeto 01).

