[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/75006428)

**Visão Geral**

A API bank-fixed-incomes viabiliza o compartilhamento dos dados dos produtos de investimentos de renda fixa bancária como; listagem dos produtos, detalhe do produto, posição do produto e movimentações históricas e recentes do produto do cliente.

## **Product List:** (GET /bank-fixed-incomes/v1/investments)

**Visão Geral**

Obtém a lista de operações de Renda Fixa Bancária mantidas pelo cliente na instituição transmissora e para as quais ele tenha fornecido consentimento.

**Visão de alto de nível das estruturas de dados**
![att75006507](Informa%c3%a7%c3%b5es%20Gerais%20-%20Renda%20Fixa%20Banc%c3%a1ria%20-%20v1.0.0-rc1.0/attachments/GET_ProductList_visaoAltoNivel.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att75006504](Informa%c3%a7%c3%b5es%20Gerais%20-%20Renda%20Fixa%20Banc%c3%a1ria%20-%20v1.0.0-rc1.0/attachments/GET_ProductList_DER_conceitual.png)
- DER Lógico

![att75006501](Informa%c3%a7%c3%b5es%20Gerais%20-%20Renda%20Fixa%20Banc%c3%a1ria%20-%20v1.0.0-rc1.0/attachments/GET_ProductList_DER_logico.png)
**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/banktFixedIncomesGetInvestments_v1.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_bankFixedIncomesGetInvestments_v1.csv)

## **Product Identification:** (GET /bank-fixed-incomes/v1/investments/{investmentId})

**Visão Geral**

Obtém os dados da operação de Renda Fixa Bancária identificada por investmentId.

**Visão de alto de nível das estruturas de dados**
![att75006498](Informa%c3%a7%c3%b5es%20Gerais%20-%20Renda%20Fixa%20Banc%c3%a1ria%20-%20v1.0.0-rc1.0/attachments/GET_ProductIdentification_visaoAltoNivel.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att75006471](Informa%c3%a7%c3%b5es%20Gerais%20-%20Renda%20Fixa%20Banc%c3%a1ria%20-%20v1.0.0-rc1.0/attachments/DER_conceitual_bancaria-v4.png)
- DER Lógico

![att75006492](Informa%c3%a7%c3%b5es%20Gerais%20-%20Renda%20Fixa%20Banc%c3%a1ria%20-%20v1.0.0-rc1.0/attachments/GET_ProductIdentification_DER_logica.png)
**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/banktFixedIncomesGetInvestmentsInvestmentId_v1.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_bankFixedIncomesGetInvestmentsInvestmentId_v1.csv)

## **Balances:** (GET /bank-fixed-incomes/v1/investments/{investmentId}/balances)

**Visão Geral**

Obtém a posição da operação de Renda Fixa Bancária identificada por investmentId.

**Visão de alto de nível das estruturas de dados**
![att75006489](Informa%c3%a7%c3%b5es%20Gerais%20-%20Renda%20Fixa%20Banc%c3%a1ria%20-%20v1.0.0-rc1.0/attachments/GET_Balances_visaoAltoNivel.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att75006471](Informa%c3%a7%c3%b5es%20Gerais%20-%20Renda%20Fixa%20Banc%c3%a1ria%20-%20v1.0.0-rc1.0/attachments/DER_conceitual_bancaria-v4.png)
- DER Lógico

![att75006483](Informa%c3%a7%c3%b5es%20Gerais%20-%20Renda%20Fixa%20Banc%c3%a1ria%20-%20v1.0.0-rc1.0/attachments/GET_Balances_DER_logico.png)
**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/banktFixedIncomesGetInvestmentsInvestmentIdBalances_v1.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_bankFixedIncomesGetInvestmentsInvestmentIdBalances_v1.csv)

## **Transactions:** (GET /bank-fixed-incomes/v1/investments/{investmentId}/transactions)

**Visão Geral**

Obtém as movimentações da operação de Renda Fixa Bancária identificada por investmentId.

**Visão de alto de nível das estruturas de dados**
![att75006480](Informa%c3%a7%c3%b5es%20Gerais%20-%20Renda%20Fixa%20Banc%c3%a1ria%20-%20v1.0.0-rc1.0/attachments/GET_Transactions_visaoAltoNivel.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att75006471](Informa%c3%a7%c3%b5es%20Gerais%20-%20Renda%20Fixa%20Banc%c3%a1ria%20-%20v1.0.0-rc1.0/attachments/DER_conceitual_bancaria-v4.png)
- DER Lógico

![att75006465](Informa%c3%a7%c3%b5es%20Gerais%20-%20Renda%20Fixa%20Banc%c3%a1ria%20-%20v1.0.0-rc1.0/attachments/DER_logico_Mov_Hist_bancaria-v4.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/banktFixedIncomesGetInvestmentsInvestmentIdTransactions_v1.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_bankFixedIncomesGetInvestmentsInvestmentIdTransactions_v1.csv)

## **Transactions Current:** (GET /bank-fixed-incomes/v1/investments/{investmentId}/transactions-current)

**Visão Geral**

Obtém as movimentações recentes da operação de Fundos de Investimento identificada por investmentId. O período a ser considerado para apresentação de movimentações será de até 7 dias - 7 dias anteriores da consulta, incluindo o dia da consulta (D-6).

**Visão de alto de nível das estruturas de dados**
![att75006480](Informa%c3%a7%c3%b5es%20Gerais%20-%20Renda%20Fixa%20Banc%c3%a1ria%20-%20v1.0.0-rc1.0/attachments/GET_Transactions_visaoAltoNivel.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att75006471](Informa%c3%a7%c3%b5es%20Gerais%20-%20Renda%20Fixa%20Banc%c3%a1ria%20-%20v1.0.0-rc1.0/attachments/DER_conceitual_bancaria-v4.png)

- DER Lógico

![att75006468](Informa%c3%a7%c3%b5es%20Gerais%20-%20Renda%20Fixa%20Banc%c3%a1ria%20-%20v1.0.0-rc1.0/attachments/DER_logico_Mov_Rec_bancaria-v4.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/banktFixedIncomesGetInvestmentsInvestmentIdTransactionsCurrent_v1.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_banktFixedIncomesGetInvestmentsInvestmentIdTransactionsCurrent_v1.csv)

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/75006428)