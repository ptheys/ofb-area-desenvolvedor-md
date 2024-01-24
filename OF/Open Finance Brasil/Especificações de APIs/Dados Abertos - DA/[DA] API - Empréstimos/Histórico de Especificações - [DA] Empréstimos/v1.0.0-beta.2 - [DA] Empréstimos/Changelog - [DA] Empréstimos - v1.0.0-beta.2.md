[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/223805702)

Alteração na parte de orientações dentro do swagger

| **Campo** | **O que foi alterado?** |
| --- | --- |
| tags/description | Adicionado - Description |

 GET /personals-loans

| **Campo** | **O que foi alterado?** |
| --- | --- |
| get/responses/200/data | Adicionado - "minItems" |
| get/responses/200/data/items/fees/services | description |
| get/responses/200/data/items/fees/services/items/chargingTriggerInfo | pattern |
| get/responses/200/data/items/fees/services/items/code | pattern |
| get/responses/200/data/items/fees/services/items/maximum/currency | Adicionado - "minLength" |
| get/responses/200/data/items/fees/services/items/maximum/value | Adicionado - "minLength" |
| get/responses/200/data/items/fees/services/items/minimum/currency | Adicionado - "minLength" |
| get/responses/200/data/items/fees/services/items/minimum/value | Adicionado - "minLength" |
| get/responses/200/data/items/fees/services/items/name | pattern |
| get/responses/200/data/items/fees/services/items/prices/items/currency | Adicionado - "minLength" |
| get/responses/200/data/items/fees/services/items/prices/items/value | Adicionado - "minLength" |
| get/responses/200/data/items/participant/brand | pattern |
| get/responses/200/data/items/participant/cnpjNumber | Adicionado - "minLength" |
| get/responses/200/data/items/participant/name | pattern |
| get/responses/200/data/items/participant/urlComplementaryList | pattern |
| get/responses/200/data/items/termsConditions | pattern |
| get/responses/200/links/first | Adicionado - "minLength" |
| get/responses/200/links/last | Adicionado - "minLength" |
| get/responses/200/links/next | Adicionado - "minLength" |
| get/responses/200/links/prev | Adicionado - "minLength" |
| get/responses/200/links/self | Adicionado - "minLength" |
| get/responses/400//errors/items/code | pattern |
| get/responses/400//errors/items/detail | pattern |
| get/responses/400//errors/items/title | pattern |
| get/responses/404//errors/items/code | pattern |
| get/responses/404//errors/items/detail | pattern |
| get/responses/404//errors/items/title | pattern |
| get/responses/405//errors/items/code | pattern |
| get/responses/405//errors/items/detail | pattern |
| get/responses/405//errors/items/title | pattern |
| get/responses/429//errors/items/code | pattern |
| get/responses/429//errors/items/detail | pattern |
| get/responses/429//errors/items/title | pattern |
| get/responses/500//errors/items/code | pattern |
| get/responses/500//errors/items/detail | pattern |
| get/responses/500//errors/items/title | pattern |
| get/responses/504//errors/items/code | pattern |
| get/responses/504//errors/items/detail | pattern |
| get/responses/504//errors/items/title | pattern |
| get/responses/529//errors/items/code | pattern |
| get/responses/529//errors/items/detail | pattern |
| get/responses/529//errors/items/title | pattern |
| get/responses/default//errors/items/code | pattern |
| get/responses/default//errors/items/detail | pattern |
| get/responses/default//errors/items/title | pattern |
| get/responses/200/data/items/participant/brand | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/participant/name | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/participant/cnpjNumber | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/participant/urlComplementaryList | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/type | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/fees/services/items/name | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/fees/services/items/code | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/fees/services/items/chargingTriggerInfo | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/fees/services/items/prices/items/interval | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/fees/services/items/prices/items/value | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/fees/services/items/prices/items/currency | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/fees/services/items/prices/items/customers | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/fees/services/items/prices/items/customers/rate | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/fees/services/items/minimum/value | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/fees/services/items/minimum/currency | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/fees/services/items/maximum/value | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/fees/services/items/maximum/currency | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/interestRates/items/referentialRateIndexer | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/interestRates/items/rate | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/interestRates/items/applications/items/interval | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/interestRates/items/applications/items/indexer | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/interestRates/items/applications/items/indexer/rate | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/interestRates/items/applications/items/customers | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/interestRates/items/applications/items/customers/rate | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/interestRates/items/minimumRate | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/interestRates/items/maximumRate | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/requiredWarranties | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/termsConditions | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/interestRates/items/applications/items/interval | Adicionado - "example" |
| get/responses/200/links/next | Adicionado - "example" |
| get/responses/200/links/prev | Adicionado - "example" |
| get/responses/200/data | Adicionado - "description" |
| get/responses/200/data/items/fees | description |
| get/responses/200/data/items/fees/services/items/prices/items/customers | Adicionado - "description" |
| get/responses/200/data/items/interestRates/items/applications/items/customers | Adicionado - "description" |
| get/responses/200/data/items/participant | Adicionado - "description" |
| get/responses/400/meta | removido - totalPages e totalRecords |
| get/responses/404/meta | removido - totalPages e totalRecords |
| get/responses/405/meta | removido - totalPages e totalRecords |
| get/responses/429/meta | removido - totalPages e totalRecords |
| get/responses/500/meta | removido - totalPages e totalRecords |
| get/responses/504/meta | removido - totalPages e totalRecords |
| get/responses/529/meta | removido - totalPages e totalRecords |
| get/responses/default/meta | removido - totalPages e totalRecords |

 GET /business-loans

| **Campo** | **O que foi alterado?** |
| --- | --- |
| get/responses/200/data | Adicionado - "minItems" |
| get/responses/200/data/items/fees/services | description |
| get/responses/200/data/items/fees/services/items/chargingTriggerInfo | pattern |
| get/responses/200/data/items/fees/services/items/code | pattern |
| get/responses/200/data/items/fees/services/items/maximum/currency | Adicionado - "minLength" |
| get/responses/200/data/items/fees/services/items/maximum/value | Adicionado - "minLength" |
| get/responses/200/data/items/fees/services/items/minimum/currency | Adicionado - "minLength" |
| get/responses/200/data/items/fees/services/items/minimum/value | Adicionado - "minLength" |
| get/responses/200/data/items/fees/services/items/name | pattern |
| get/responses/200/data/items/fees/services/items/prices/items/currency | Adicionado - "minLength" |
| get/responses/200/data/items/fees/services/items/prices/items/value | Adicionado - "minLength" |
| get/responses/200/data/items/participant/brand | pattern |
| get/responses/200/data/items/participant/cnpjNumber | Adicionado - "minLength" |
| get/responses/200/data/items/participant/name | pattern |
| get/responses/200/data/items/participant/urlComplementaryList | pattern |
| get/responses/200/data/items/termsConditions | pattern |
| get/responses/200/links/first | Adicionado - "minLength" |
| get/responses/200/links/last | Adicionado - "minLength" |
| get/responses/200/links/next | Adicionado - "minLength" |
| get/responses/200/links/prev | Adicionado - "minLength" |
| get/responses/200/links/self | Adicionado - "minLength" |
| get/responses/400//errors/items/code | pattern |
| get/responses/400//errors/items/detail | pattern |
| get/responses/400//errors/items/title | pattern |
| get/responses/404//errors/items/code | pattern |
| get/responses/404//errors/items/detail | pattern |
| get/responses/404//errors/items/title | pattern |
| get/responses/405//errors/items/code | pattern |
| get/responses/405//errors/items/detail | pattern |
| get/responses/405//errors/items/title | pattern |
| get/responses/429//errors/items/code | pattern |
| get/responses/429//errors/items/detail | pattern |
| get/responses/429//errors/items/title | pattern |
| get/responses/500//errors/items/code | pattern |
| get/responses/500//errors/items/detail | pattern |
| get/responses/500//errors/items/title | pattern |
| get/responses/504//errors/items/code | pattern |
| get/responses/504//errors/items/detail | pattern |
| get/responses/504//errors/items/title | pattern |
| get/responses/529//errors/items/code | pattern |
| get/responses/529//errors/items/detail | pattern |
| get/responses/529//errors/items/title | pattern |
| get/responses/default//errors/items/code | pattern |
| get/responses/default//errors/items/detail | pattern |
| get/responses/default//errors/items/title | pattern |
| get/responses/200/data/items/participant/brand | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/participant/name | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/participant/cnpjNumber | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/participant/urlComplementaryList | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/type | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/fees/services/items/name | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/fees/services/items/code | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/fees/services/items/chargingTriggerInfo | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/fees/services/items/prices/items/interval | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/fees/services/items/prices/items/value | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/fees/services/items/prices/items/currency | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/fees/services/items/prices/items/customers | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/fees/services/items/prices/items/customers/rate | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/fees/services/items/minimum/value | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/fees/services/items/minimum/currency | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/interestRates/items/referentialRateIndexer | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/interestRates/items/rate | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/interestRates/items/applications/items/interval | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/interestRates/items/applications/items/indexer | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/interestRates/items/applications/items/indexer/rate | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/interestRates/items/applications/items/customers | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/interestRates/items/applications/items/customers/rate | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/interestRates/items/minimumRate | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/interestRates/items/maximumRate | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/requiredWarranties | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/termsConditions | Adicionado - "x-regulatory-required" |
| get/responses/200/data/items/interestRates/items/applications/items/interval | Adicionado - "example" |
| get/responses/200/links/next | Adicionado - "example" |
| get/responses/200/links/prev | Adicionado - "example" |
| get/responses/200/data | Adicionado - "description" |
| get/responses/200/data/items/fees | description |
| get/responses/200/data/items/fees/services/items/prices/items/customers | Adicionado - "description" |
| get/responses/200/data/items/interestRates/items/applications/items/customers | Adicionado - "description" |
| get/responses/200/data/items/participant | Adicionado - "description" |
| get/responses/400/meta | removido - totalPages e totalRecords |
| get/responses/404/meta | removido - totalPages e totalRecords |
| get/responses/405/meta | removido - totalPages e totalRecords |
| get/responses/429/meta | removido - totalPages e totalRecords |
| get/responses/500/meta | removido - totalPages e totalRecords |
| get/responses/504/meta | removido - totalPages e totalRecords |
| get/responses/529/meta | removido - totalPages e totalRecords |
| get/responses/default/meta | removido - totalPages e totalRecords |

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/223805702)