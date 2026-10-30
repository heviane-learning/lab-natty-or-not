# SPEC-001: E-book Técnico — Engenharia de Software Natty

- **Status:** APROVADO PARA EXECUÇÃO
- **Data de Criação:** 29/10/2026
- **Autora:** Heviane
- **Tema:** *Engenharia de Software Natty: Boas Práticas, Limites e Antipatterns com IA*
- **Subtítulo:** *Guia de sobrevivência para manter bases de código limpas, seguras e humanas em tempos de copilotos autônomos.*

---

## 🎯 1. Objetivo do Artefato

Produzir um e-book técnico denso, prático e autoral que sirva como peça central do portfólio deste projeto. O material deve explorar o limite entre a automação eficiente com inteligência artificial e a introdução de débitos técnicos invisíveis, posicionando a autoria na perspectiva de uma engenheira de software tradicional que aplica rigor aos fluxos modernos de copilotos e agentes.

---

## 👥 2. Público-Alvo & Tom de Voz

- **Público:** Engenheiros de software (júnior a sênior), tech leads e desenvolvedores em processo de transição para desenvolvimento assistido por IA.
- **Tom de Voz:**
  - Técnico, pragmático, analítico e realista.
  - Evitar tanto o ludismo ("IA vai acabar com os programadores amanhã") quanto o oba-oba corporativo ("IA resolve tudo com um clique").
  - Foco em arquitetura, manutenibilidade, segurança e qualidade de software.

---

## 📐 3. Estrutura Modular dos Capítulos

O e-book será composto por 4 capítulos modulares, totalizando entre 3.000 e 4.500 palavras (aproximadamente 800 a 1.100 palavras por capítulo).

### 📖 Capítulo 1: O Efeito "Fake Natty" no Código
- **Foco:** A ilusão da produtividade sintética.
- **Tópicos Obrigatórios:**
  - Código que "parece profissional" na superfície (sintaxe impecável, nomes bonitos), mas quebra em edge cases de produção.
  - A assimetria cognitiva: por que revisar código ruim gerado por IA pode ser mais custoso do que escrever do zero.
  - Estudo de caso: O falso positivo em testes unitários gerados por IA (testes que passam, mas não testam a regra de negócio).

### 📖 Capítulo 2: Antipatterns no Desenvolvimento Assistido por IA
- **Foco:** O que NÃO fazer ao usar copilotos e assistentes.
- **Tópicos Obrigatórios:**
  - *Dependency Hallucination:* Importação de pacotes inexistentes ou obsoletos (risco de supply chain attack e typosquatting).
  - *Blind Acceptance (Aprovação Cega):* Aceitar sugestões de autocompletion sem avaliar complexidade ciclomática.
  - *Context Starvation:* Fornecer contexto insuficiente e esperar soluções arquiteturais consistentes.
  - *Boilerplate Inflation:* Código redundante e prolixo em vez de soluções idiomáticas e reutilizáveis.

### 📖 Capítulo 3: Engenharia de Software Natty (Boas Práticas e Padrões)
- **Foco:** Técnicas avançadas para extrair código de alta qualidade com IA.
- **Tópicos Obrigatórios:**
  - *Spec-Driven Prompting:* Definir contratos de dados e interfaces antes da geração.
  - *Test-Driven Prompting:* Gerar ou fornecer os testes de contrato/integração antes da implementação do código.
  - Modularização estrita: dividir problemas em funções puras e serviços isolados para maximizar a assertividade dos LLMs.
  - Governança de contexto: uso de `AGENTS.md`, `.cursorrules` e system prompts de repositório.

### 📖 Capítulo 4: O Desenvolvedor Centauro e o Futuro da Engenharia
- **Foco:** A evolução do papel do engenheiro de software.
- **Tópicos Obrigatórios:**
  - O desenvolvedor que deixa de ser mero digitador de sintaxe para atuar como arquiteto de sistemas e orquestrador de múltiplos agentes.
  - As habilidades que se tornam ainda mais valiosas: domínio de negócio, raciocínio crítico, segurança e design de sistemas.
  - **Checklist Prático:** Checklist de Code Review para Pull Requests gerados com suporte de IA.

---

## 📊 4. Elementos Visuais e Complementares

- Diagrama conceitual em Mermaid ilustrando o fluxo de desenvolvimento assistido com validação humana.
- Exemplos de código comparativos (Estilo: *Fake Natty vs. Natty Real*).
- Tabela resumo dos principais antipatterns e suas mitigações.

---

## ✅ 5. Critérios de Aceite (Definition of Done - DoD)

Para que o e-book seja considerado concluído e aprovado:

- [ ] **Zero Fluff:** Nenhuma seção ou capítulo pode iniciar com clichês de IA (*"No mundo de hoje..."*, *"Na era da IA..."*).
- [ ] **Profundidade Prática:** Cada capítulo deve conter ao menos um exemplo de código real ou estudo de caso de engenharia.
- [ ] **Estrutura Completa:** Todos os 4 capítulos devem ser desenvolvidos conforme os tópicos da Seção 3.
- [ ] **Checklist Incluso:** O capítulo 4 deve concluir com o checklist acionável de revisão de código.
- [ ] **Rastreabilidade:** Cada capítulo deve ter seu prompt de geração e refinamento documentado na pasta `projetos/01-eng-software-natty/prompts/`.

