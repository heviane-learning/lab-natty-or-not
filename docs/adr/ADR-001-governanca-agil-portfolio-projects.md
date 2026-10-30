# ADR-001: Centralização de Governança Ágil com GitHub Projects v2 e Views Especializadas

- **Status:** APROVADO
- **Data:** 30/10/2026
- **Autora:** Heviane
- **Contexto:** Definição do modelo de gestão ágil de projetos e tarefas para a organização `heviane-learning`.

---

## 🎯 1. Contexto do Problema

Com a transição para engenharia de software assistida por IA e a evolução da organização para um ecossistema monorepo/multirrepositório, surgiu a necessidade de estruturar um fluxo de trabalho ágil que atendesse aos seguintes requisitos:
1. Visibilidade executiva de múltiplas iniciativas simultâneas (labs, estudos de caso, aplicações).
2. Limitação efetiva de trabalho em progresso (WIP - *Work in Progress*) para evitar sobrecarga e multitarefa desnecessária.
3. Rastreabilidade técnica bidirecional entre documentação local em repositório (*Docs-as-Code*) e quadros de gestão.
4. Apresentação profissional para avaliação de portfólio técnico por pares e lideranças de engenharia.

---

## ⚖️ 2. Alternativas Consideradas

### Alternativa A: Um GitHub Project por Repositório (Descentralizado)
- **Prós:** Isolamento de contexto estrito por repositório.
- **Contras:**
  - Fragmentação da visibilidade (necessidade de alternar entre múltiplos boards).
  - Impossibilidade de priorização global e controle de WIP cross-repository.
  - Alto custo de manutenção de configurações e campos customizados repetidos.

### Alternativa B: Um GitHub Project Central de Nível Organizacional com Views (Centralizado)
- **Prós:**
  - *Single Pane of Glass:* Visão unificada de todo o portfólio da organização em uma única interface.
  - Alinhamento com frameworks modernos de gestão de portfólio ágil (Flight Levels / Portfolio Kanban).
  - Otimização do uso do GitHub Projects v2 via *Views* customizadas com filtros (`repo:natty-or-not-lab`).
  - Demonstração explícita de maturidade em governança ágil para avaliadores externos.
- **Contras:**
  - Exige disciplina no uso de filtros para evitar poluição visual (mitigado pelas *Views*).

---

## 🏆 3. Decisão Arquitetural

Adotar a **Alternativa B**: Centralizar a gestão de tarefas e iniciativas da organização em um único **GitHub Project v2 de nível organizacional**, utilizando **Views especializadas (Abas)** por repositório e por estado de entrega.

### Diretrizes de Operação:
1. **Fonte de Verdade Técnica:** O arquivo `backlog.md` de cada projeto no repositório atua como contrato local versionado via Git (*Docs-as-Code*).
2. **Camada de Orquestração Visual:** O GitHub Project central atua como o quadro executivo interativo, alimentado por Issues dos repositórios.
3. **Views Obrigatórias:**
   - *Visão Geral:* Tabela agrupada por repositório para acompanhamento de roadmap.
   - *Board do Repositório:* Kanban filtrado pelo repositório específico (`repo:heviane-learning/<nome-repo>`).
   - *Foco da Sprint:* Visualização restrita a itens com `status:"In Progress"`.

---

## 📈 4. Consequências e Resultados Esperados

- **Positivas:** Redução de fricção de contexto, foco no fechamento de ciclos de entrega (*Stop Starting, Start Finishing*), rastreabilidade de ponta a ponta e padrão de engenharia corporativo.
- **Riscos Mitigados:** Acúmulo de débitos técnicos invisíveis e abandono de iniciativas por dispersão de atenção.
