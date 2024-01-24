[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/124256453)

## **Product List:** (GET /credit-fixed-incomes/v1/investments)

**Visão Geral**

Obtém a lista de operações de Renda Fixa Crédito mantidas pelo cliente na instituição transmissora e para as quais ele tenha fornecido consentimento.

**Visão de alto de nível das estruturas de dados**
![att124256556](Informa%c3%a7%c3%b5es%20Gerais%20-%20Renda%20Fixa%20Cr%c3%a9dito%20-%20v1.0.0-rc2.0/attachments/GET_ProductList_visaoAltoNivel.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att124256559](Informa%c3%a7%c3%b5es%20Gerais%20-%20Renda%20Fixa%20Cr%c3%a9dito%20-%20v1.0.0-rc2.0/attachments/GET_ProductList_DER_conceitual.png)
- DER Lógico

![att124256562](Informa%c3%a7%c3%b5es%20Gerais%20-%20Renda%20Fixa%20Cr%c3%a9dito%20-%20v1.0.0-rc2.0/attachments/GET_ProductList_DER_logico.png)
**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/creditFixedIncomesGetInvestments_v1.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_creditFixedIncomesGetInvestments_v1.csv)

## **Product Identification:** (GET /credit-fixed-incomes/v1/investments/{investmentId})

**Visão Geral**

Obtém os dados da operação de Renda Fixa Crédito identificada por investmentId.

**Visão de alto de nível das estruturas de dados**
![att124256565](Informa%c3%a7%c3%b5es%20Gerais%20-%20Renda%20Fixa%20Cr%c3%a9dito%20-%20v1.0.0-rc2.0/attachments/GET_ProductIdentification_visaoAltoNivel.png)

**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att124256610](Informa%c3%a7%c3%b5es%20Gerais%20-%20Renda%20Fixa%20Cr%c3%a9dito%20-%20v1.0.0-rc2.0/attachments/DER_conceitual_credito-v4.png)
- DER Lógico

![att124256568](Informa%c3%a7%c3%b5es%20Gerais%20-%20Renda%20Fixa%20Cr%c3%a9dito%20-%20v1.0.0-rc2.0/attachments/GET_ProductIdentification_DER_logico.png)
**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/creditFixedIncomesGetInvestmentsInvestmentId_v1.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_creditFixedIncomesGetInvestmentsInvestmentId_v1.csv)

## **Balances:** (GET /credit-fixed-incomes/v1/investments/{investmentId}/balances)

**Visão Geral**

Obtém a posição da operação de Renda Fixa Crédito identificada por investmentId.

**Visão de alto de nível das estruturas de dados**
![att124256580](Informa%c3%a7%c3%b5es%20Gerais%20-%20Renda%20Fixa%20Cr%c3%a9dito%20-%20v1.0.0-rc2.0/attachments/GET_Balances_visaoAltoNivel.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att124256610](Informa%c3%a7%c3%b5es%20Gerais%20-%20Renda%20Fixa%20Cr%c3%a9dito%20-%20v1.0.0-rc2.0/attachments/DER_conceitual_credito-v4.png)
- DER Lógico

![att124256574](Informa%c3%a7%c3%b5es%20Gerais%20-%20Renda%20Fixa%20Cr%c3%a9dito%20-%20v1.0.0-rc2.0/attachments/GET_Balances_DER_logico.png)
**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/creditFixedIncomesGetInvestmentsInvestmentIdBalances_v1.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_creditFixedIncomesGetInvestmentsInvestmentIdBalances_v1.csv)

## **Transactions:** (GET /credit-fixed-incomes/v1/investments/{investmentId}/transactions)

**Visão Geral**

Obtém as movimentações da operação de Renda Fixa Crédito identificada por investmentId.

**Visão de alto de nível das estruturas de dados**
![att124256583](Informa%c3%a7%c3%b5es%20Gerais%20-%20Renda%20Fixa%20Cr%c3%a9dito%20-%20v1.0.0-rc2.0/attachments/GET_Transactions_visaoAltoNivel.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att124256610](Informa%c3%a7%c3%b5es%20Gerais%20-%20Renda%20Fixa%20Cr%c3%a9dito%20-%20v1.0.0-rc2.0/attachments/DER_conceitual_credito-v4.png)

- DER Lógico

![att124256493](Informa%c3%a7%c3%b5es%20Gerais%20-%20Renda%20Fixa%20Cr%c3%a9dito%20-%20v1.0.0-rc2.0/attachments/image-20230427-164630.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/creditFixedIncomesGetInvestmentsInvestmentIdTransactions_v1.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_creditFixedIncomesGetInvestmentsInvestmentIdTransactions_v1.csv)

## **Transactions Current:** (GET /credit-fixed-incomes/v1/investments/{investmentId}/transactions-current)

**Visão Geral**

Obtém as movimentações recentes da operação de Fundos de Investimento identificada por investmentId. O período a ser considerado para apresentação de movimentações será de até 7 dias - 7 dias anteriores da consulta, incluindo o dia da consulta (D-6).

**Visão de alto de nível das estruturas de dados**
![att124256583](Informa%c3%a7%c3%b5es%20Gerais%20-%20Renda%20Fixa%20Cr%c3%a9dito%20-%20v1.0.0-rc2.0/attachments/GET_Transactions_visaoAltoNivel.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att124256610](Informa%c3%a7%c3%b5es%20Gerais%20-%20Renda%20Fixa%20Cr%c3%a9dito%20-%20v1.0.0-rc2.0/attachments/DER_conceitual_credito-v4.png)

- DER Lógico

![att124256490](Informa%c3%a7%c3%b5es%20Gerais%20-%20Renda%20Fixa%20Cr%c3%a9dito%20-%20v1.0.0-rc2.0/attachments/image-20230427-164720.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/creditFixedIncomesGetInvestmentsInvestmentIdTransactionsCurrent_v1.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_creditFixedIncomesGetInvestmentsInvestmentIdTransactionsCurrent_v1.csv)

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/124256453)