[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/163545108)

**Visão Geral**

A API bank-fixed-incomes viabiliza o compartilhamento dos dados dos produtos de investimentos de renda fixa bancária como; listagem dos produtos, detalhe do produto, posição do produto e movimentações históricas e recentes do produto do cliente.

## **Product List:** (GET /bank-fixed-incomes/v1/investments)

**Visão Geral**

Obtém a lista de operações de Renda Fixa Bancária mantidas pelo cliente na instituição transmissora e para as quais ele tenha fornecido consentimento.

**Visão de alto de nível das estruturas de dados**
![att163545155](Informa%c3%a7%c3%b5es%20Gerais%20-%20Renda%20Fixa%20Banc%c3%a1ria%20-%20v1.0.1/attachments/GET_ProductList_visaoAltoNivel.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att163545158](Informa%c3%a7%c3%b5es%20Gerais%20-%20Renda%20Fixa%20Banc%c3%a1ria%20-%20v1.0.1/attachments/GET_ProductList_DER_conceitual.png)
- DER Lógico

![att163545161](Informa%c3%a7%c3%b5es%20Gerais%20-%20Renda%20Fixa%20Banc%c3%a1ria%20-%20v1.0.1/attachments/GET_ProductList_DER_logico.png)
**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/banktFixedIncomesGetInvestments_v1.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_bankFixedIncomesGetInvestments_v1.csv)

## **Product Identification:** (GET /bank-fixed-incomes/v1/investments/{investmentId})

**Visão Geral**

Obtém os dados da operação de Renda Fixa Bancária identificada por investmentId.

**Visão de alto de nível das estruturas de dados**
![att163545164](Informa%c3%a7%c3%b5es%20Gerais%20-%20Renda%20Fixa%20Banc%c3%a1ria%20-%20v1.0.1/attachments/GET_ProductIdentification_visaoAltoNivel.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att163545182](Informa%c3%a7%c3%b5es%20Gerais%20-%20Renda%20Fixa%20Banc%c3%a1ria%20-%20v1.0.1/attachments/DER_conceitual_bancaria-v4.png)
- DER Lógico

![att163545167](Informa%c3%a7%c3%b5es%20Gerais%20-%20Renda%20Fixa%20Banc%c3%a1ria%20-%20v1.0.1/attachments/GET_ProductIdentification_DER_logica.png)
**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/banktFixedIncomesGetInvestmentsInvestmentId_v1.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_bankFixedIncomesGetInvestmentsInvestmentId_v1.csv)

## **Balances:** (GET /bank-fixed-incomes/v1/investments/{investmentId}/balances)

**Visão Geral**

Obtém a posição da operação de Renda Fixa Bancária identificada por investmentId.

**Visão de alto de nível das estruturas de dados**
![att163545170](Informa%c3%a7%c3%b5es%20Gerais%20-%20Renda%20Fixa%20Banc%c3%a1ria%20-%20v1.0.1/attachments/GET_Balances_visaoAltoNivel.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att163545182](Informa%c3%a7%c3%b5es%20Gerais%20-%20Renda%20Fixa%20Banc%c3%a1ria%20-%20v1.0.1/attachments/DER_conceitual_bancaria-v4.png)
- DER Lógico

![att163545173](Informa%c3%a7%c3%b5es%20Gerais%20-%20Renda%20Fixa%20Banc%c3%a1ria%20-%20v1.0.1/attachments/GET_Balances_DER_logico.png)
**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/banktFixedIncomesGetInvestmentsInvestmentIdBalances_v1.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_bankFixedIncomesGetInvestmentsInvestmentIdBalances_v1.csv)

## **Transactions:** (GET /bank-fixed-incomes/v1/investments/{investmentId}/transactions)

**Visão Geral**

Obtém as movimentações da operação de Renda Fixa Bancária identificada por investmentId.

**Visão de alto de nível das estruturas de dados**
![att163545179](Informa%c3%a7%c3%b5es%20Gerais%20-%20Renda%20Fixa%20Banc%c3%a1ria%20-%20v1.0.1/attachments/GET_Transactions_visaoAltoNivel.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att163545182](Informa%c3%a7%c3%b5es%20Gerais%20-%20Renda%20Fixa%20Banc%c3%a1ria%20-%20v1.0.1/attachments/DER_conceitual_bancaria-v4.png)
- DER Lógico

![att163545176](Informa%c3%a7%c3%b5es%20Gerais%20-%20Renda%20Fixa%20Banc%c3%a1ria%20-%20v1.0.1/attachments/image-20230427-165914.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/banktFixedIncomesGetInvestmentsInvestmentIdTransactions_v1.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_bankFixedIncomesGetInvestmentsInvestmentIdTransactions_v1.csv)

## **Transactions Current:** (GET /bank-fixed-incomes/v1/investments/{investmentId}/transactions-current)

**Visão Geral**

Obtém as movimentações recentes da operação de Fundos de Investimento identificada por investmentId. O período a ser considerado para apresentação de movimentações será de até 7 dias - 7 dias anteriores da consulta, incluindo o dia da consulta (D-6).

**Visão de alto de nível das estruturas de dados**
![att163545179](Informa%c3%a7%c3%b5es%20Gerais%20-%20Renda%20Fixa%20Banc%c3%a1ria%20-%20v1.0.1/attachments/GET_Transactions_visaoAltoNivel.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att163545182](Informa%c3%a7%c3%b5es%20Gerais%20-%20Renda%20Fixa%20Banc%c3%a1ria%20-%20v1.0.1/attachments/DER_conceitual_bancaria-v4.png)

- DER Lógico

![att163545185](Informa%c3%a7%c3%b5es%20Gerais%20-%20Renda%20Fixa%20Banc%c3%a1ria%20-%20v1.0.1/attachments/image-20230427-170009.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/banktFixedIncomesGetInvestmentsInvestmentIdTransactionsCurrent_v1.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_banktFixedIncomesGetInvestmentsInvestmentIdTransactionsCurrent_v1.csv)

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/163545108)