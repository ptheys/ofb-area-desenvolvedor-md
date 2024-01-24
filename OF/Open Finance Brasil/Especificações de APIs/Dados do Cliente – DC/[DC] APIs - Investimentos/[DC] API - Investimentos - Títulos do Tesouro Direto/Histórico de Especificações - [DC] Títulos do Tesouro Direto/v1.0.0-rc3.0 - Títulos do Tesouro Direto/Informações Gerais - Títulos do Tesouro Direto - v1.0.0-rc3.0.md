[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/144900725)

**Visão Geral**

API de informações de operações de Títulos do Tesouro Direto Open Finance Brasil – Fase 4. API que retorna informações de operações de investimento do tipo Títulos do Tesouro Direto mantidas nas instituições transmissoras por seus clientes, incluindo dados como informações do produto, quantidade, saldos em posição do cliente e movimentações financeiras.

## **Product List:** (GET /treasure-titles/v1/investments)

**Visão Geral**

Obtém a lista de operações de Títulos do Tesouro Direto mantidas pelo cliente na instituição transmissora e para as quais ele tenha fornecido consentimento.

**Visão de alto de nível das estruturas de dados**
![att144900795](Informa%c3%a7%c3%b5es%20Gerais%20-%20T%c3%adtulos%20do%20Tesouro%20Direto%20-%20v1.0.0-rc3.0/attachments/image-20230411-183819.png)

**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att144900792](Informa%c3%a7%c3%b5es%20Gerais%20-%20T%c3%adtulos%20do%20Tesouro%20Direto%20-%20v1.0.0-rc3.0/attachments/image-20230411-183852.png)

- DER Lógico

![att144900789](Informa%c3%a7%c3%b5es%20Gerais%20-%20T%c3%adtulos%20do%20Tesouro%20Direto%20-%20v1.0.0-rc3.0/attachments/image-20230411-183940.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/treasureTitlesGetInvestments_v1.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_treasureTitlesGetInvestments_v1.csv)

## **Product Identification:** (GET /treasure-titles/v1/investments/{investmentId})

**Visão Geral**

Obtém os dados da operação de Títulos do Tesouro Direto identificada por investmentId.

**Visão de alto de nível das estruturas de dados**
![att144900780](Informa%c3%a7%c3%b5es%20Gerais%20-%20T%c3%adtulos%20do%20Tesouro%20Direto%20-%20v1.0.0-rc3.0/attachments/image-20230411-184151.png)

**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att144900783](Informa%c3%a7%c3%b5es%20Gerais%20-%20T%c3%adtulos%20do%20Tesouro%20Direto%20-%20v1.0.0-rc3.0/attachments/image-20230411-184122.png)

- DER Lógico

![att144900786](Informa%c3%a7%c3%b5es%20Gerais%20-%20T%c3%adtulos%20do%20Tesouro%20Direto%20-%20v1.0.0-rc3.0/attachments/image-20230411-184035.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/treasureTitlesGetInvestmentsInvestmentId_v1.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_treasureTitlesGetInvestmentsInvestmentId_v1.csv)

## **Balances:** (GET /treasure-titles/v1/investments/{investmentId}/balances)

**Visão Geral**

Obtém a posição da operação de Títulos do Tesouro Direto identificada por investmentId.

**Visão de alto de nível das estruturas de dados**
![att144900777](Informa%c3%a7%c3%b5es%20Gerais%20-%20T%c3%adtulos%20do%20Tesouro%20Direto%20-%20v1.0.0-rc3.0/attachments/image-20230411-184225.png)

**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att144900774](Informa%c3%a7%c3%b5es%20Gerais%20-%20T%c3%adtulos%20do%20Tesouro%20Direto%20-%20v1.0.0-rc3.0/attachments/image-20230411-184248.png)

- DER Lógico

![att144900771](Informa%c3%a7%c3%b5es%20Gerais%20-%20T%c3%adtulos%20do%20Tesouro%20Direto%20-%20v1.0.0-rc3.0/attachments/image-20230411-184317.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/treasureTitlesGetInvestmentsInvestmentIdBalances_v1.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_treasureTitlesGetInvestmentsInvestmentIdBalances_v1.csv)

## **Transactions:** (GET /treasure-titles/v1/investments/{investmentId}/transactions)

**Visão Geral**

Obtém as movimentações da operação (últimos 12 meses) de Títulos do Tesouro Direto identificada por investmentId.

**Visão de alto de nível das estruturas de dados**
![att144900768](Informa%c3%a7%c3%b5es%20Gerais%20-%20T%c3%adtulos%20do%20Tesouro%20Direto%20-%20v1.0.0-rc3.0/attachments/image-20230411-184349.png)

**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att144900765](Informa%c3%a7%c3%b5es%20Gerais%20-%20T%c3%adtulos%20do%20Tesouro%20Direto%20-%20v1.0.0-rc3.0/attachments/image-20230411-184402.png)

- DER Lógico

![att144900762](Informa%c3%a7%c3%b5es%20Gerais%20-%20T%c3%adtulos%20do%20Tesouro%20Direto%20-%20v1.0.0-rc3.0/attachments/image-20230411-184433.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/treasureTitlesGetInvestmentsInvestmentIdTransactions_v1.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_treasureTitlesGetInvestmentsInvestmentIdTransactions_v1.csv)

## **Transactions Current:** (GET /treasure-titles/v1/investments/{investmentId}/transactions-current)

**Visão Geral**

Obtém as movimentações recentes da operação de Títulos do Tesouro Direto identificada por investmentId. O período a ser considerado para apresentação de movimentações será de até 7 dias - 7 dias anteriores da consulta, incluindo o dia da consulta (D-6).

**Visão de alto de nível das estruturas de dados**
![att144900759](Informa%c3%a7%c3%b5es%20Gerais%20-%20T%c3%adtulos%20do%20Tesouro%20Direto%20-%20v1.0.0-rc3.0/attachments/image-20230411-184508.png)

**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att144900756](Informa%c3%a7%c3%b5es%20Gerais%20-%20T%c3%adtulos%20do%20Tesouro%20Direto%20-%20v1.0.0-rc3.0/attachments/image-20230411-184520.png)

- DER Lógico

![att144900753](Informa%c3%a7%c3%b5es%20Gerais%20-%20T%c3%adtulos%20do%20Tesouro%20Direto%20-%20v1.0.0-rc3.0/attachments/image-20230411-184544.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/treasureTitlesGetInvestmentsInvestmentIdTransactionsCurrent_v1.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_treasureTitlesGetInvestmentsInvestmentIdTransactionsCurrent_v1.csv)

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/144900725)