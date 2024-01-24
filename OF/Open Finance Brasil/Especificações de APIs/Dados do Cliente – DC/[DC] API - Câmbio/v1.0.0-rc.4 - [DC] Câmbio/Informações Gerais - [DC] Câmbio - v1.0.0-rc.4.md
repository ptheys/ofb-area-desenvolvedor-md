[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/262144419)

**Visão Geral**

API de informações de operações de Câmbio Open Finance Brasil – Fase 4. API que retorna informações de operações de Câmbio realizadas nas instituições transmissoras por seus clientes, incluindo dados como informações da operação contratada, valor da operação em moeda nacional e moeda estrangeira, classificação da operação, forma de entrega, VET e, quando aplicável, valor a liquidar.

## **Product List:** (GET /exchanges/v1/operations)

**Visão Geral**

Obtém a lista de operações de Câmbio mantidas pelo cliente na instituição transmissora e para as quais ele tenha fornecido consentimento.

**Visão de alto de nível das estruturas de dados**
![att262144582](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20C%c3%a2mbio%20-%20v1.0.0-rc.4/attachments/image-20230530-162058.png)

**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att262144585](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20C%c3%a2mbio%20-%20v1.0.0-rc.4/attachments/image-20230530-162148.png)

- DER Lógico

![att262144588](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20C%c3%a2mbio%20-%20v1.0.0-rc.4/attachments/image-20230530-162216.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/exchangesGetOperations_v1.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_exchangesGetOperations_v1.csv)

## **Product Identification:** (GET /exchanges/v1/operations/{operationId})

**Visão Geral**

Obtém os dados da operação de Câmbio identificada por operationId.

**Visão de alto de nível das estruturas de dados**
![att262144594](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20C%c3%a2mbio%20-%20v1.0.0-rc.4/attachments/image-20230530-162300.png)

**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att262144597](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20C%c3%a2mbio%20-%20v1.0.0-rc.4/attachments/image-20230530-162323.png)

- DER Lógico

![att262144600](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20C%c3%a2mbio%20-%20v1.0.0-rc.4/attachments/image-20230530-162413.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/exchangesGetOperationsOperationId_v1.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_exchangesGetOperationsOperationId_v1.csv)

## **Events:** (GET /exchanges/v1/operations/{operationId}/events)

**Visão Geral**

Obtém os dados dos eventos da operação de Câmbio identificada por operationId.

**Visão de alto de nível das estruturas de dados**
![att262144603](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20C%c3%a2mbio%20-%20v1.0.0-rc.4/attachments/image-20230530-162447.png)

**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att262144606](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20C%c3%a2mbio%20-%20v1.0.0-rc.4/attachments/image-20230530-162509.png)

- DER Lógico

![att262144609](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20C%c3%a2mbio%20-%20v1.0.0-rc.4/attachments/image-20230530-162605.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/exchangesGetOperationsOperationIdEvents_v1.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_exchangesGetOperationsOperationIdEvents_v1.csv)

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/262144419)