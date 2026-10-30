# Roteiro de Podcast — Natty or Not: Engenharia sem Ilusão

- **Formato:** Diálogo entre dois engenheiros (Host & Especialista)
- **Duração Estimada:** 2 minutos e 30 segundos
- **Contagem Total de Palavras:** 398 palavras
- **Público:** Desenvolvedores Plenos/Sêniores, Tech Leads e Arquitetos
- **Metodologia:** Spec-Driven Development ([SPEC-003](file:///e:/Projects/GitHub/heviane-learning/natty-or-not-lab/projetos/01-eng-software-natty/specs/SPEC-003-podcast.md))

---

## 🎙️ Personagens & Vozes Recomendadas (ElevenLabs)

- **Lucas (Host):** Voz masculina jovem, enérgica e curiosa (ex.: voz *Adam* ou *Charlie* com sotaque neutro em português).
- **Helena (Especialista):** Voz feminina madura, calma, confiante e articulada (ex.: voz *Rachel* ou *Nicole* calibrada para tom analítico).

---

## 🎧 Roteiro Decupado com Marcações de Áudio

**[Trilha de abertura sutil estilo lofi / tech beat entra por 4 segundos e reduz para fade under]**

**Lucas:** Fala pessoal, bem-vindos ao *Natty or Not Lab*! Hoje eu tô aqui com a Helena, e eu já quero começar com uma confissão polêmica: ontem eu gerei um microsserviço inteiro de pagamentos em 15 minutos usando um copiloto. Digitei o prompt, apertei Tab, Tab, Tab... e pronto. Código lindo, formatadinho!

**Helena:** *(risos breves)* Pois é, Lucas... Gerar em 15 minutos é fácil. A pergunta que eu sempre faço é: quanto tempo você vai passar debugando isso quando cair em produção na sexta-feira à noite?

**Lucas:** *(pausa)* Poxa, mas ele até gerou os testes unitários com cem por cento de cobertura!

**Helena:** E é exatamente aí que mora o perigo do código que a gente chama de "Fake Natty". A IA adora criar testes tautológicos: mocks circulares que só conferem se o próprio mock foi chamado. O teste passa verde, mas se alguém arrancar a validação de idempotência, o sistema aceita pagamento duplicado sorrindo. Sem falar no risco de alucinação de dependências... você checou se aquele pacote importado existe mesmo no npm?

**Lucas:** Cara... pior que não chequei. Podia ser um caso de *Slopsquatting*, né? 

**Helena:** Exatamente! O atacante registra o nome do pacote que o modelo costuma inventar e injeta malware na sua esteira de CI. Usar IA sem governança é terceirizar o pensamento arquitetural.

**Lucas:** Tá, mas então qual é o caminho pra gente ser realmente "Natty" na engenharia?

**Helena:** O segredo é mudar a postura. Em vez de aceitar código pronto às cegas, você pratica o que chamamos de *Spec-Driven Prompting*. Você define os contratos e os tipos estritos antes — com Zod, Pydantic ou interfaces bem desenhadas. Você escreve o teste que quebra primeiro, e só aí pede pro modelo implementar a regra pura. O desenvolvedor deixa de ser um mero digitador de sintaxe para virar o arquiteto e o orquestrador dos agentes.

**Lucas:** É o conceito do Desenvolvedor Centauro! A IA acelera a digitação, mas o julgamento crítico e a responsabilidade de produção continuam cem por cento humanos.

**Helena:** Perfeito. O aceite final em produção nunca pode ser uma aposta probabilística.

**Lucas:** Sensacional, Helena! Galera, todo esse debate, a matriz de antipatterns e um checklist prático de code review estão detalhados no nosso e-book no GitHub. O link tá na descrição. Até a próxima!

**Helena:** Até mais, pessoal! Mantenham suas bases limpas e natty!

**[Trilha musical sobe em fade in por 3 segundos e encerra com fade out]**

