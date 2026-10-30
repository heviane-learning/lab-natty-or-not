# Capítulo 1: O Efeito "Fake Natty" no Código

A métrica mais perigosa na engenharia de software moderna é a velocidade bruta de digitação. Um modelo de linguagem avançado consegue gerar 300 linhas de código sintaticamente impecáveis, documentadas com JSDoc e formatadas com Prettier em menos de 10 segundos. No entanto, em sistemas distribuídos e de missão crítica, a digitação de sintaxe nunca foi o gargalo da entrega. O verdadeiro custo de engenharia reside na **modelagem mental**, na **prevenção de falhas ocultas** e na **manutenibilidade a longo prazo**.

Quando copilotos e assistentes autônomos são utilizados sem supervisão rigorosa, surge o que chamamos de **Código "Fake Natty"**: uma implementação que tem aparência estética profissional, nomes de variáveis expressivos e tipagem aparentemente robusta, mas que, sob estresse de produção, desmorona devido a premissas lógicas frágeis, ausência de idempotência ou falsos positivos em suítes de testes.

---

## 1. A Ilusão da Produtividade Sintética

A produtividade assistida por IA frequentemente opera sob uma miragem de aceleração. Durante a fase inicial de desenvolvimento (*greenfield*), gerar código a partir do zero produz uma sensação imediata de fluxo. Funcionalidades inteiras parecem nascer prontas em minutos.

O débito técnico gerado por IA, contudo, é assíncrono. Diferente do desenvolvedor júnior que comete erros visíveis de sintaxe ou estrutura, o modelo generativo gera código com **alta fluência formal e baixa densidade semântica**. Ele reproduz padrões estatísticos comuns encontrados na internet aberta, ignorando as particularidades do domínio de negócio, regras de concorrência ou o ciclo de vida dos recursos da aplicação.

> [!WARNING]
> **A Armadilha do Débito Sintético:** Código gerado por IA tende a inflar a base com abstrações prematuras e tratamentos de exceção genéricos (`try/catch` vazios ou re-lançamentos sem contexto). Essa proliferação superficial mascara lacunas arquiteturais que só se manifestam sob carga ou em falhas de rede parciais.

---

## 2. A Assimetria Cognitiva no Code Review

Na engenharia tradicional, o processo de revisão de código (*code review*) baseia-se na leitura crítica de uma solução construída por outro ser humano que pensou sobre o problema. Existe uma linha de raciocínio contextual que orienta as decisões.

Ao revisar código gerado por IA, o revisor humano enfrenta uma severa **assimetria cognitiva**:

1. **Viés da Autoridade Estética:** O código parece correto à primeira vista. A identação é perfeita, o padrão de nomenclatura segue convenções idiomáticas e o código compila sem avisos do linter.
2. **Esforço Desproporcional de Depuração:** Ler e identificar uma falha sutil de lógica em um código que "parece pronto" consome significativamente mais energia mental do que escrever a lógica do zero com intenção clara.
3. **Fadiga de Contexto:** Como o volume de linhas submetidas em cada Pull Request aumenta drasticamente, os revisores tendem a relaxar o escrutínio sobre casos de borda (*edge cases*), confiando no visual limpo do código.

---

## 3. Estudo de Caso: O Teste Tautológico (Falso Positivo)

O sintoma mais comum do efeito *Fake Natty* ocorre na geração automatizada de testes unitários. Modelos de IA são excelentes em maximizar métricas quantitativas de cobertura de código (*code coverage*), mas frequentemente falham em validar invariantes de negócio.

Considere o cenário de processamento de pagamento idempotente. Abaixo, comparamos a abordagem gerada roboticamente versus a abordagem com rigor de engenharia:

### ❌ Versão Fake Natty: Teste Tautológico

Neste exemplo gerado sem calibragem, a IA gera um teste que atinge 100% de cobertura de linhas, mas é conceitualmente inútil.

```typescript
describe('PaymentService (Fake Natty)', () => {
  it('deve processar o pagamento com sucesso', async () => {
    // A IA cria mocks circulares onde o próprio mock valida o resultado
    const mockRepo = { findByIdempotencyKey: jest.fn().mockResolvedValue(null), save: jest.fn() };
    const mockGateway = { charge: jest.fn().mockResolvedValue({ status: 'PAID', txId: '123' }) };
    
    const service = new PaymentService(mockRepo, mockGateway);
    const result = await service.processPayment({ key: 'order-1', amount: 100 });

    // Assertivas tautológicas: apenas conferem se os mocks chamaram a si mesmos
    expect(mockGateway.charge).toHaveBeenCalledTimes(1);
    expect(result.status).toBe('PAID');
    // SE alguém remover a verificação de duplicidade no service, este teste AINDA PASSA!
  });
});
```

### ✅ Versão Natty: Validação de Invariante e Idempotência Real

A abordagem de engenharia madura foca no comportamento do sistema sob condições concorrentes e falhas de negócio:

```typescript
describe('PaymentService (Natty Real)', () => {
  it('deve garantir idempotência estrita rejeitando transações duplicadas em voo', async () => {
    const existingTransaction = { id: 'tx-existing', key: 'order-1', status: 'PROCESSING' };
    const mockRepo = {
      findByIdempotencyKey: jest.fn().mockResolvedValue(existingTransaction),
      save: jest.fn(),
    };
    const mockGateway = { charge: jest.fn() };

    const service = new PaymentService(mockRepo, mockGateway);

    // O teste valida o invariante: NUNCA acionar o gateway se a transação já existir
    await expect(service.processPayment({ key: 'order-1', amount: 100 }))
      .rejects
      .toThrow(ConflictException);

    // Assertiva defensiva crítica: o dinheiro do cliente não foi cobrado duas vezes
    expect(mockGateway.charge).not.toHaveBeenCalled();
    expect(mockRepo.save).not.toHaveBeenCalled();
  });
});
```

> [!NOTE]
> No teste *Fake Natty*, o modelo satisfez a métrica superficial de cobertura, mas ignorou o risco financeiro da operação. No teste *Natty*, a engenheira impôs a validação da integridade transacional.

---

## 4. Lição de Engenharia: Como Manter o Código Autêntico

Para combater a degradação de bases de código assistidas por IA, algumas práticas são inegociáveis:

- **Não terceirize o design de contratos:** A definição de interfaces, esquemas de validação e tipos primitivos deve ser concebida pelo arquiteto humano antes da solicitação de implementações.
- **Auditoria de asserções negativas:** Ao receber testes gerados por IA, force o código de produção a quebrar intencionalmente (*mutation testing* manual) para verificar se o teste realmente acusa a falha.
- **A regra da legibilidade humana:** Se você não consegue explicar linha por linha como aquele trecho gerado funciona em uma sessão de pair programming, esse código não está pronto para a branch `main`.

No próximo capítulo, dissecaremos os **Antipatterns mais Comuns no Desenvolvimento Assistido por IA**, desde a alucinação de pacotes em gerenciadores de dependência até a intoxicação de contexto em agentes de código.

