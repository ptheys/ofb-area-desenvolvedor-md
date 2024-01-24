**Visão Geral**

API de informações de operações de Câmbio Open Finance Brasil – Fase 4. API que retorna informações de operações de Câmbio realizadas nas instituições transmissoras por seus clientes, incluindo dados como informações da operação contratada, valor da operação em moeda nacional e moeda estrangeira, classificação da operação, forma de entrega, VET e, quando aplicável, valor a liquidar.

## **Product List:** (GET /exchanges/v1/operations)

**Visão Geral**

Obtém a lista de operações de Câmbio mantidas pelo cliente na instituição transmissora e para as quais ele tenha fornecido consentimento.

**Visão de alto de nível das estruturas de dados**
![att114425904](Informa%c3%a7%c3%b5es%20Gerais%20-%20C%c3%a2mbio/attachments/image-20230530-162058.png)

**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att114425901](Informa%c3%a7%c3%b5es%20Gerais%20-%20C%c3%a2mbio/attachments/image-20230530-162148.png)

- DER Lógico

![att114425898](Informa%c3%a7%c3%b5es%20Gerais%20-%20C%c3%a2mbio/attachments/image-20230530-162216.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/exchangesGetOperations_v1.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_exchangesGetOperations_v1.csv)

## **Product Identification:** (GET /exchanges/v1/operations/{operationId})

**Visão Geral**

Obtém os dados da operação de Câmbio identificada por operationId.

**Visão de alto de nível das estruturas de dados**
![att114425892](Informa%c3%a7%c3%b5es%20Gerais%20-%20C%c3%a2mbio/attachments/image-20230530-162300.png)

**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att114425889](Informa%c3%a7%c3%b5es%20Gerais%20-%20C%c3%a2mbio/attachments/image-20230530-162323.png)

- DER Lógico

![att114425886](Informa%c3%a7%c3%b5es%20Gerais%20-%20C%c3%a2mbio/attachments/image-20230530-162413.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/exchangesGetOperationsOperationId_v1.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_exchangesGetOperationsOperationId_v1.csv)

## **Events:** (GET /exchanges/v1/operations/{operationId}/events)

**Visão Geral**

Obtém os dados dos eventos da operação de Câmbio identificada por operationId.

**Visão de alto de nível das estruturas de dados**
![att114425883](Informa%c3%a7%c3%b5es%20Gerais%20-%20C%c3%a2mbio/attachments/image-20230530-162447.png)

**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att114425880](Informa%c3%a7%c3%b5es%20Gerais%20-%20C%c3%a2mbio/attachments/image-20230530-162509.png)

- DER Lógico

![att114425877](Informa%c3%a7%c3%b5es%20Gerais%20-%20C%c3%a2mbio/attachments/image-20230530-162605.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/exchangesGetOperationsOperationIdEvents_v1.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_exchangesGetOperationsOperationIdEvents_v1.csv)