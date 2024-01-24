[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/242188949)

**Visão Geral**

API de informações de operações de Renda Variável Open Finance Brasil – Fase 4. API que retorna informações de operações de investimento do tipo Renda Variável mantidas nas instituições transmissoras por seus clientes, incluindo dados como informações do produto, quantidade, saldos em posição do cliente, movimentações financeiras e detalhes da nota de negociação.

## **Product List:** (GET /variable-incomes/v1/investments)

**Visão Geral**

Obtém a lista de operações de Renda Variável mantidas pelo cliente na instituição transmissora e para as quais ele tenha fornecido consentimento.

**Visão de alto de nível das estruturas de dados**
![att242254210](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Renda%20Vari%c3%a1vel%20-%20v1.1.0/attachments/image-20230405-201406.png)

**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att242254216](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Renda%20Vari%c3%a1vel%20-%20v1.1.0/attachments/image-20230405-195433.png)

- DER Lógico

![att242254222](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Renda%20Vari%c3%a1vel%20-%20v1.1.0/attachments/image-20230405-195537.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/variableIncomesGetInvestments_v1.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_variableIncomesGetInvestments_v1.csv)

## **Product Identification:** (GET /variable-incomes/v1/investments/{investmentId})

**Visão Geral**

Obtém os dados da operação de Renda Variável identificada por investmentId.

**Visão de alto de nível das estruturas de dados**
![att242254228](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Renda%20Vari%c3%a1vel%20-%20v1.1.0/attachments/image-20230405-195642.png)

**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att242254234](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Renda%20Vari%c3%a1vel%20-%20v1.1.0/attachments/New%20Draw.png)

- DER Lógico

![att242254240](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Renda%20Vari%c3%a1vel%20-%20v1.1.0/attachments/image-20230405-195801.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/variableIncomesGetInvestmentsInvestmentId_v1.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_variableIncomesGetInvestmentsInvestmentId_v1.csv)

## **Balances:** (GET /variable-incomes/v1/investments/{investmentId}/balances)

**Visão Geral**

Obtém a posição da operação de Renda Variável identificada por investmentId.

**Visão de alto de nível das estruturas de dados**
![att242254246](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Renda%20Vari%c3%a1vel%20-%20v1.1.0/attachments/image-20230405-201254.png)

**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att242254234](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Renda%20Vari%c3%a1vel%20-%20v1.1.0/attachments/New%20Draw.png)

- DER Lógico

![att242254263](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Renda%20Vari%c3%a1vel%20-%20v1.1.0/attachments/image-20230405-195959.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/variableIncomesGetInvestmentsInvestmentIdBalances_v1.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_variableIncomesGetInvestmentsInvestmentIdBalances_v1.csv)

## **Transactions:** (GET /variable-incomes/v1/investments/{investmentId}/transactions)

**Visão Geral**

Obtém as movimentações históricas (últimos 12 meses) da operação de Renda Variável identificada por investmentId.

**Visão de alto de nível das estruturas de dados**
![att242254269](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Renda%20Vari%c3%a1vel%20-%20v1.1.0/attachments/image-20230405-200434.png)

**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att242254234](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Renda%20Vari%c3%a1vel%20-%20v1.1.0/attachments/New%20Draw.png)

- DER Lógico

![att242254286](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Renda%20Vari%c3%a1vel%20-%20v1.1.0/attachments/image-20230427-163323.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/variableIncomesGetInvestmentsInvestmentIdTransactions_v1.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_variableIncomesGetInvestmentsInvestmentIdTransactions_v1.csv)

## **Transactions Current:** (GET /variable-incomes/v1/investments/{investmentId}/transactions-current)

**Visão Geral**

Obtém as movimentações recentes da operação de Renda Variável identificada por investmentId. O período a ser considerado para apresentação de movimentações será de até 7 dias - 7 dias anteriores da consulta, incluindo o dia da consulta (D-6).

**Visão de alto de nível das estruturas de dados**
![att242254292](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Renda%20Vari%c3%a1vel%20-%20v1.1.0/attachments/image-20230405-200359.png)

**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att242254234](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Renda%20Vari%c3%a1vel%20-%20v1.1.0/attachments/New%20Draw.png)

- DER Lógico

![att242254309](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Renda%20Vari%c3%a1vel%20-%20v1.1.0/attachments/image-20230427-163404.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/variableIncomesGetInvestmentsInvestmentIdTransactionsCurrent_v1.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_variableIncomesGetInvestmentsInvestmentIdTransactionsCurrent_v1.csv)

## **Broker Note Details:** (GET /variable-incomes/v1/investments/{investmentId}/broker-notes/{brokerNoteId})

**Visão Geral**

Obtém as informações da nota de negociação identificado nas movimentações de compra e venda de ativos em bolsa.

**Visão de alto de nível das estruturas de dados**
![att242254315](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Renda%20Vari%c3%a1vel%20-%20v1.1.0/attachments/image-20230405-200931.png)

**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att242254234](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Renda%20Vari%c3%a1vel%20-%20v1.1.0/attachments/New%20Draw.png)

- DER Lógico

![att242254332](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Renda%20Vari%c3%a1vel%20-%20v1.1.0/attachments/image-20230427-163441.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/variableIncomesGetInvestmentsInvestmentIdBrokerNotesBrokerNoteId_v1.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_variableIncomesGetInvestmentsInvestmentIdBrokerNotesBrokerNoteId_v1.csv)

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/242188949)