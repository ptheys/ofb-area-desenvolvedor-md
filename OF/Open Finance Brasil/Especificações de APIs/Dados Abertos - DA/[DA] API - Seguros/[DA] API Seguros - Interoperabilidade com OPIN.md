[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/101941249)

## Tabela de correspondência das APIs de Seguros do Open Finance e Open Insurance

Essa especificação inclui todos artefatos relevantes para a especificação de APIs de Seguros no que toca ao relacionamento entre os diretórios do OPIN e do OFB, apontando a correspondência direta entre cada um dos campos listados nos swaggers. 

- Versões consideradas para esse documento:

| **&gt;&gt;&gt;&gt;&gt; OFB &lt;&lt;&lt;&lt;&lt;** | **&gt;&gt;&gt;&gt;&gt; OPIN &lt;&lt;&lt;&lt;&lt;** |
| --- | --- |
| APIs | APIs |
| API Seguros (v1.0.0) | API Person (v1.3.0) |
| endpoint /personals | endpoint /person |

## De/Para de campos

| **API Seguros (Open Finance)** | **API Person (Open Insurance)** | **Observação** |
| --- | --- | --- |
| ***Endpoint /personals*** | ***Endpoint /person*** |  |
| 200/data/participant/brand | - |  |
| 200/data/participant/name | - |  |
| 200/data/participant/cnpjNumber | - |  |
| 200/data/participant/urlComplementaryList | - |  |
| 200/data/society/name | 200/data/brand/companies/name |  |
| 200/data/society/cnpjNumber | 200/data/brand/companies/cnpjNumber |  |
| 200/data/society/brand | 200/data/brand/name |  |
| 200/data/name | 200/data/brand/companies/products/name |  |
| 200/data/code | 200/data/brand/companies/products/code |  |
| 200/data/category | 200/data/brand/companies/products/category |  |
| 200/data/category/MICROSSEGURO | 200/data/brand/companies/products/category/MICROSEGURO |  |
| 200/data/modality | 200/data/brand/companies/products/insuranceModality |  |
| 200/data/coverages | 200/data/brand/companies/products/coverages |  |
| 200/data/coverages/type | 200/data/brand/companies/products/coverages/coverage |  |
| 200/data/coverages/type/CANCELAMENTO\_VIAGEM | 200/data/brand/companies/products/coverages/coverage/CANCELAMENTO\_DE\_VIAGEM |  |
| 200/data/coverages/type/COBERTURA\_HERNIA | 200/data/brand/companies/products/coverages/coverage/COBERTURA\_PARA\_HERNIA |  |
| 200/data/coverages/type/COBERTURA\_LER\_DORT | 200/data/brand/companies/products/coverages/coverage/COBERTURA\_PARA\_LER\_DORT |  |
| 200/data/coverages/type/DESEMPREGO\_PERDA\_RENDA | 200/data/brand/companies/products/coverages/coverage/DESEMPREGO\_PERDA\_DE\_RENDA |  |
| 200/data/coverages/type/PERDA\_AUTONOMIA\_PESSOAL | 200/data/brand/companies/products/coverages/coverage/PERDA\_DA\_AUTONOMIA\_PESSOAL |  |
| 200/data/coverages/type/TRASLADO | 200/data/brand/companies/products/coverages/coverage/TRANSLADO |  |
| 200/data/coverages/type/OUTROS | 200/data/brand/companies/products/coverages/coverage/OUTRAS |  |
| 200/data/coverages/typeAdditionalInfos | 200/data/brand/companies/products/coverages/coverageOthers |  |
| 200/data/coverages/attributes | 200/data/brand/companies/products/coverages/coverageAttributes |  |
| 200/data/coverages/attributes/indemnityPaymentMethods | 200/data/brand/companies/products/coverages/coverageAttributes/indemnityPaymentMethod |  |
| 200/data/coverages/attributes/indemnityPaymentFrequencies | 200/data/brand/companies/products/coverages/coverageAttributes/indemnityPaymentFrequency |  |
| 200/data/coverages/attributes/minValue | 200/data/brand/companies/products/coverages/coverageAttributes/minValue |  |
| 200/data/coverages/attributes/minValue/amount | 200/data/brand/companies/products/coverages/coverageAttributes/minValue/amount | Os campos possuem tipos de dado diferentes. É necessário converter Number(Open Insurance)~String(Open Finance), respeitando os padrões de apresentação de valores monetários no Open Finance |
| 200/data/coverages/attributes/minValue/currency | 200/data/brand/companies/products/coverages/coverageAttributes/minValue/unit/code | Os ecossistemas de Open Insurance e Open Finance usam diferentes formas de representar moedas, exigindo conversão para apresentar as informações corretamente. Neste campo, "R$" no OPIN é equivalente a "BRL" no Open Finance. |
| - | 200/data/brand/companies/products/coverages/coverageAttributes/minValue/unit/description |  |
| 200/data/coverages/attributes/maxValue | 200/data/brand/companies/products/coverages/coverageAttributes/maxValue |  |
| 200/data/coverages/attributes/maxValue/amount | 200/data/brand/companies/products/coverages/coverageAttributes/maxValue/amount | Os campos possuem tipos de dado diferentes. É necessário converter Number(Open Insurance)~String(Open Finance), respeitando os padrões de apresentação de valores monetários no Open Finance |
| 200/data/coverages/attributes/maxValue/currency | 200/data/brand/companies/products/coverages/coverageAttributes/maxValue/unit/code | Os ecossistemas de Open Insurance e Open Finance usam diferentes formas de representar moedas, exigindo conversão para apresentar as informações corretamente. Neste campo, "R$" no OPIN é equivalente a "BRL" no Open Finance. |
| - | 200/data/brand/companies/products/coverages/coverageAttributes/maxValue/unit/description |  |
| 200/data/coverages/attributes/indemnifiablePeriods | 200/data/brand/companies/products/coverages/coverageAttributes/indemnifiablePeriod |  |
| 200/data/coverages/attributes/maximumQtyIndemnifiableInstallments | 200/data/brand/companies/products/coverages/coverageAttributes/maximumQtyIndemnifiableInstallments |  |
| 200/data/coverages/attributes/gracePeriod | 200/data/brand/companies/products/coverages/coverageAttributes/gracePeriod |  |
| 200/data/coverages/attributes/gracePeriod/details | 200/data/brand/companies/products/coverages/coverageAttributes/gracePeriod/details |  |
| 200/data/coverages/attributes/gracePeriod/amount | 200/data/brand/companies/products/coverages/coverageAttributes/gracePeriod/amount |  |
| 200/data/coverages/attributes/gracePeriod/unit | 200/data/brand/companies/products/coverages/coverageAttributes/gracePeriod/unit |  |
| 200/data/coverages/attributes/gracePeriod/unit/NAO\_APLICA | 200/data/brand/companies/products/coverages/coverageAttributes/gracePeriod/unit/NAO\_SE\_APLICA |  |
| 200/data/coverages/attributes/differentiatedGracePeriod | 200/data/brand/companies/products/coverages/coverageAttributes/differentiatedGracePeriod |  |
| 200/data/coverages/attributes/deductibleDays | 200/data/brand/companies/products/coverages/coverageAttributes/deductibleDays |  |
| 200/data/coverages/attributes/differentiatedDeductibleDays | 200/data/brand/companies/products/coverages/coverageAttributes/differentiatedDeductibleDays |  |
| 200/data/coverages/attributes/deductible/amount | 200/data/brand/companies/products/coverages/coverageAttributes/deductibleBRL | Os campos possuem tipos de dado diferentes. É necessário converter Number(Open Insurance)~String(Open Finance), respeitando os padrões de apresentação de valores monetários no Open Finance |
| 200/data/coverages/attributes/deductible/currency | - | No campo currency deverá ser fixado o conteúdo "BRL" |
| 200/data/coverages/attributes/differentiatedDeductible/amount | 200/data/brand/companies/products/coverages/coverageAttributes/differentiatedDeductibleBRL | Os campos possuem tipos de dado diferentes. É necessário converter Number(Open Insurance)~String(Open Finance), respeitando os padrões de apresentação de valores monetários no Open Finance |
| 200/data/coverages/attributes/differentiatedDeductible/currency | - | No campo currency deverá ser fixado o conteúdo "BRL" |
| 200/data/coverages/attributes/excludedRisks | 200/data/brand/companies/products/coverages/coverageAttributes/excludedRisks |  |
| 200/data/coverages/attributes/excludedRisksURL | 200/data/brand/companies/products/coverages/coverageAttributes/excludedRisksURL |  |
| 200/data/coverages/attributes/allowApartPurchase | 200/data/brand/companies/products/coverages/coverageAttributes/allowApartPurchase |  |
| 200/data/assistanceTypes | 200/data/brand/companies/products/assistanceType |  |
| 200/data/assistanceTypes/MAIS\_VIDA | 200/data/brand/companies/products/assistanceType/MAIS\_EM\_VIDA |  |
| 200/data/assistanceTypesAdditionalInfos | 200/data/brand/companies/products/assistanceTypeOthers |  |
| 200/data/additionals | 200/data/brand/companies/products/additional |  |
| 200/data/termsAndConditions | 200/data/brand/companies/products/termsAndConditions |  |
| 200/data/termsAndConditions/susepProcessNumber | 200/data/brand/companies/products/termsAndConditions/susepProcessNumber |  |
| 200/data/termsAndConditions/detail | 200/data/brand/companies/products/termsAndConditions/definition |  |
| 200/data/globalCapital | 200/data/brand/companies/products/globalCapital |  |
| 200/data/terms | 200/data/brand/companies/products/validity |  |
| 200/data/pmbacRemuneration | 200/data/brand/companies/products/pmbacRemuneration |  |
| 200/data/pmbacRemuneration/interestRate | 200/data/brand/companies/products/pmbacRemuneration/interestRate | Os campos possuem tipos de dado diferentes. É necessário converter Number(Open Insurance)~String(Open Finance), respeitando os padrões de apresentação de valores monetários no Open Finance |
| 200/data/pmbacRemuneration/updateIndexes | 200/data/brand/companies/products/pmbacRemuneration/pmbacUpdateIndex |  |
| 200/data/pmbacRemuneration/updateIndexes/IGP\_M | 200/data/brand/companies/products/pmbacRemuneration/pmbacUpdateIndex/IGP-M |  |
| 200/data/benefitRecalculation | 200/data/brand/companies/products/benefitRecalculation |  |
| 200/data/benefitRecalculation/criterias | 200/data/brand/companies/products/benefitRecalculation/benefitRecalculationCriteria |  |
| 200/data/benefitRecalculation/updateIndexes | 200/data/brand/companies/products/benefitRecalculation/benefitUpdateIndex |  |
| 200/data/benefitRecalculation/updateIndexes/IGP\_M | 200/data/brand/companies/products/benefitRecalculation/benefitUpdateIndex/IGP-M |  |
| 200/data/ageAdjustment | 200/data/brand/companies/products/ageAdjustment |  |
| 200/data/ageAdjustment/criterias | 200/data/brand/companies/products/ageAdjustment/criterion |  |
| 200/data/ageAdjustment/criterias/APOS\_PERIODO\_ANOS | 200/data/brand/companies/products/ageAdjustment/criterion/APOS\_PERIODO\_EM\_ANOS |  |
| 200/data/ageAdjustment/criterias/CADA\_PERIODO\_ANOS | 200/data/brand/companies/products/ageAdjustment/criterion/A\_CADA\_PERIODO\_EM\_ANOS |  |
| 200/data/ageAdjustment/criterias/MUDANCA\_FAIXA\_ETARIA | 200/data/brand/companies/products/ageAdjustment/criterion/POR\_MUDANCA\_DE\_FAIXA\_ETARIA |  |
| 200/data/ageAdjustment/frequency | 200/data/brand/companies/products/ageAdjustment/frequency |  |
| 200/data/financialRegimes | 200/data/brand/companies/products/contractType |  |
| 200/data/reclaim | 200/data/brand/companies/products/reclaim |  |
| 200/data/reclaim/table | 200/data/brand/companies/products/reclaim/reclaimTable |  |
| 200/data/reclaim/table/initialMonthRange | 200/data/brand/companies/products/reclaim/reclaimTable/initialMonthRange |  |
| 200/data/reclaim/table/finalMonthRange | 200/data/brand/companies/products/reclaim/reclaimTable/finalMonthRange |  |
| 200/data/reclaim/table/percentage | 200/data/brand/companies/products/reclaim/reclaimTable/percentage | Os campos possuem tipos de dado diferentes. É necessário converter Number(Open Insurance)~String(Open Finance), respeitando os padrões de apresentação de valores monetários no Open Finance |
| 200/data/reclaim/gracePeriod | 200/data/brand/companies/products/reclaim/gracePeriod |  |
| 200/data/reclaim/gracePeriod/amount | 200/data/brand/companies/products/reclaim/gracePeriod/amount |  |
| 200/data/reclaim/gracePeriod/unit | 200/data/brand/companies/products/reclaim/gracePeriod/unit |  |
| 200/data/reclaim/gracePeriod/unit/NAO\_APLICA | 200/data/brand/companies/products/reclaim/gracePeriod/unit/NAO\_SE\_APLICA |  |
| 200/data/reclaim/gracePeriod/details | 200/data/brand/companies/products/reclaim/gracePeriod/details |  |
| 200/data/reclaim/differenciatedPercentage | 200/data/brand/companies/products/reclaim/diferentiatedPercentage |  |
| 200/data/otherGuaranteedValues | 200/data/brand/companies/products/otherGuaranteedValues |  |
| 200/data/otherGuaranteedValues/NAO\_APLICA | 200/data/brand/companies/products/otherGuaranteedValues/NAO\_SE\_APLICA |  |
| 200/data/allowPortability | 200/data/brand/companies/products/allowPortability |  |
| 200/data/portabilityGraceTime/amount | 200/data/brand/companies/products/portabilityGraceTime |  |
| 200/data/portabilityGraceTime/unit | - | No campo unit deverá ser fixado a opção "DIAS" |
| 200/data/indemnityPaymentMethods | 200/data/brand/companies/products/indemnityPaymentMethod |  |
| 200/data/indemnityPaymentMethods/SOB\_FORMA\_RENDA | 200/data/brand/companies/products/indemnityPaymentMethod/SOB\_FORMA\_DE\_RENDA |  |
| 200/data/indemnityPaymentIncomes | 200/data/brand/companies/products/indemnityPaymentIncome |  |
| 200/data/premiumPayment | 200/data/brand/companies/products/premiumPayment |  |
| 200/data/premiumPayment/paymentMethods | 200/data/brand/companies/products/premiumPayment/paymentMethod |  |
| 200/data/premiumPayment/paymentMethods/DEBITO\_CONTA\_CORRENTE | 200/data/brand/companies/products/premiumPayment/paymentMethod/DEBITO\_CONTA |  |
| 200/data/premiumPayment/frequencies | 200/data/brand/companies/products/premiumPayment/frequency |  |
| 200/data/premiumPayment/contributionTax | 200/data/brand/companies/products/premiumPayment/premiumTax |  |
| 200/data/minimumRequirement | 200/data/brand/companies/products/minimunRequirements |  |
| 200/data/minimumRequirement/contractType | 200/data/brand/companies/products/minimunRequirements/contractingType |  |
| 200/data/minimumRequirement/contractingMinRequirement | 200/data/brand/companies/products/minimunRequirements/contractingMinRequirement |  |
| 200/data/targetAudience | 200/data/brand/companies/products/targetAudience |  |
| 200/links/self | 200/links/self |  |
| 200/links/first | 200/links/first |  |
| 200/links/prev | 200/links/prev |  |
| 200/links/next | 200/links/next |  |
| 200/links/last | 200/links/last |  |
| meta/totalRecords | meta/totalRecords |  |
| meta/totalPages | meta/totalPages |  |

| **API Insurances (Open Finance)** | **API Person (Open Insurance)** | **Observação** |
| --- | --- | --- |
| **Endpoint /personals - Parâmetros** | **Endpoint /person - Parâmetros** |  |
| parameters/page | parameters/page |  |
| parameters/page-size | parameters/page-size |  |
| - | parameters/cache-control | [<u>Utilizar o padrão do endereço: https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Cache-Control#cache_directives Ex: Cache-Control: no-cache Cache-Control: private</u>](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Cache-Control) |
| - | parameters/x-fapi-auth-date |  |
| - | parameters/x-fapi-customer-ip-address |  |
| - | parameters/x-fapi-interaction-id |  |
| - | parameters/x-customer-user-agent |  |

| **API Insurances (Open Finance)** | **API Person (Open Insurance)** | **Observação** |
| --- | --- | --- |
| **Endpoint /personals - Responses** | **Endpoint /person - Responses** |  |
| - | Status code 204 |  |
| - | Status code 401 |  |
| - | Status code 403 |  |
| - | Status code 406 |  |
| - | Status code 422 |  |
| - | Status code default |  |
| 400 404 405 429 500 /meta/requestDateTime | 400 404 405 429 500 /erros/requestDateTime |  |

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/101941249)