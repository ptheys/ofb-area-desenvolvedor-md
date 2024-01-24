[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/110166017)

Legenda:

O caractere "-" indica que não existe correspondência do campo na API.

## **De/Para dos campos**

| **API Capitalization Bonds (Open Finance)** | **API Capitalization Title (Open Insurance)** | **Observação** |
| --- | --- | --- |
| **Endpoint /bonds** | **Endpoint /capitalization-title** |  |
| - | requestTime |  |
| data/participant | brand/companies[]/products[]/ |  |
| data | brand |  |
| data/participant/brand | - |  |
| data/society/name | brand/companies[] |  |
| data/participant/name | brand/companies[]/name |  |
| data/participant/cnpjNumber | brand/companies[]/cnpjNumber |  |
| data/participant/urlComplementaryList | brand/companies[]/products[]/ |  |
| data | brand/companies[]/products[] |  |
| data/society | brand/companies[]/products[]/ |  |
| data/name | brand/companies[]/products[]/name |  |
| data/code | brand/companies[]/products[]/code |  |
| data/modality | brand/companies[]/products[]/modality |  |
| data/costType | brand/companies[]/products[]/costType |  |
| data/termsAndConditions/susepProcessNumber | brand/companies[]/products[]/termsAndConditions/susepProcessNumber |  |
| data/termsAndConditions/detail | brand/companies[]/products[]/termsAndConditions/termsRegulations |  |
| data/quotas[]/capitalizationQuota | brand/companies[]/products[]/quotas[]/capitalizationQuota[] |  |
| data/quotas[]/raffleQuota | brand/companies[]/products[]/quotas[]/raffleQuota[] |  |
| data/quotas[]/chargingQuota | brand/companies[]/products[]/quotas[]/chargingQuota[] |  |
| data/validity | brand/companies[]/products[]/validity |  |
| data/capitalizationPeriod | brand/companies[]/products[]/capitalizationPeriod |  |
| data/capitalizationPeriod/interestRate | brand/companies[]/products[]/capitalizationPeriod/interestRate |  |
| data/capitalizationPeriod/updateIndex | brand/companies[]/products[]/capitalizationPeriod/updateIndex[] |  |
| data/capitalizationPeriod/updateIndexAdditionalInfo | brand/companies[]/products[]/capitalizationPeriod/updateIndexOthers[] |  |
| data/capitalizationPeriod/contributionAmount[] | brand/companies[]/products[]/capitalizationPeriod/contributionAmount | Array vs Objeto.   <br>(Está em tratamento no GT Especificações de OPF) |
| data/capitalizationPeriod/contributionAmount[]/periodicity | brand/companies[]/products[]/capitalizationPeriod/contributionAmount/frequency | Enum diferente entre OPF e OPIN. (Está em tratamento no GT Especificações de OPF) |
| data/capitalizationPeriod/contributionAmount[]/periodicityAdditionalInfo | brand/companies[]/products[]/capitalizationPeriod/contributionAmount |  |
| data/capitalizationPeriod/contributionAmount[]/minimum | brand/companies[]/products[]/capitalizationPeriod/contributionAmount/minValue |  |
| data/capitalizationPeriod/contributionAmount[]/maximum | brand/companies[]/products[]/capitalizationPeriod/contributionAmount/maxValue |  |
| data/capitalizationPeriod/contributionAmount[]/allowedValue | brand/companies[]/products[]/capitalizationPeriod/contributionAmount/value |  |
| data/capitalizationPeriod/earlyRedemptions[]/quota | brand/companies[]/products[]/capitalizationPeriod/earlyRedemptions[]/quota |  |
| data/capitalizationPeriod/earlyRedemptions[]/rate | brand/companies[]/products[]/capitalizationPeriod/earlyRedemptions[]/percentage |  |
| data/capitalizationPeriod/redemptionPercentageEndTerm | brand/companies[]/products[]/capitalizationPeriod/redemptionPercentageEndTerm |  |
| data/latePayment/suspensionMonths | brand/companies[]/products[]/latePayment/suspensionPeriod |  |
| data/latePayment/periodExtensionOption | brand/companies[]/products[]/latePayment/termExtensionOption |  |
| data/contributionPayment/paymentMethod | brand/companies[]/products[]/contributionPayment/paymentMethod | Correspondência de domínios diferentes:  <br>Open Finance: PAGAMENTO\_PONTOS  <br>Open Insurance: PAGAMENTO\_COM\_PONTOS |
| data/contributionPayment/paymentMethodAdditionalInfo | - |  |
| data/contributionPayment/updateIndex | brand/companies[]/products[]/contributionPayment/updateIndex |  |
| data/contributionPayment/updateIndexAdditionalInfo | brand/companies[]/products[]/contributionPayment/updateIndexOthers |  |
| data/redemptionPercentageEndTerm | brand/companies[]/products[]/capitalizationPeriod/redemptionPercentageEndTerm |  |
| data/finalRedemptionRate | brand/companies[]/products[]/redemption/redemption |  |
| data/draws[] | brand/companies[]/products[]/raffle |  |
| data/draws[]/quantity | brand/companies[]/products[]/raffle/raffleQty |  |
| data/draws[]/timeInterval | brand/companies[]/products[]/raffle/timeInterval |  |
| data/draws[]/prizeMultiplier | brand/companies[]/products[]/raffle/raffleValue |  |
| data/draws[]/earlySettlementRaffle | brand/companies[]/products[]/raffle/earlySettlementRaffle |  |
| data/draws[]/mandatoryContemplation | brand/companies[]/products[]/raffle/mandatoryContemplation |  |
| data/draws[]/ruleDescription | brand/companies[]/products[]/raffle/ruleDescription |  |
| data/draws[]/minimumContemplationProbability | brand/companies[]/products[]/raffle/minimumContemplationProbability |  |
| data/draws[]/timeIntervalAdditionalInfo | - |  |
| data/additionalInfo | brand/companies[]/products[]/additionalDetails/additionalDetails |  |
| data/minimumRequirementDetails | brand/companies[]/products[]/minimumRequirements/minimumRequirementDetails |  |
| data/targetAudience | brand/companies[]/products[]/minimumRequirements/targetAudiences |  |

## **De/Para dos Parâmetros**

| **API Capitalization Bonds** | **API Capitalization Title** |
| --- | --- |
| **Endpoint: /bonds ** | **Endpoint: /capitalization-title ** |
| - | parameters/cache-Control |
| - | parameters/cnpjNumber |
| - | parameters/content-Security-Policy |
| - | parameters/content-Type |
| - | parameters/strict-Transport-Security |
| - | parameters/x-Content-Type-Options |
| - | parameters/x-Frame-Options |

## **De/Para dos status code**

| **API Capitalization Bonds** | **API Capitalization Title** |
| --- | --- |
| **Endpoint /bonds - Parâmetros** | **Endpoint /capitalization-title - Parâmetros** |
| - | Status code: 401 |
| - | Status code: 403 |
| - | Status code: 406 |
| - | Status code: default |
| 400 404 405 429 500 /meta/requestDateTime | 400 401 403 404 405 406 422 429 500 /erros/requestDateTime |

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/110166017)