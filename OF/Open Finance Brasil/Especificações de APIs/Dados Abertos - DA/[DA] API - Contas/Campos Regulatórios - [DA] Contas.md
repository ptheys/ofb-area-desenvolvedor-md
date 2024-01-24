[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/223805546)

### Campos obrigatórios segundo a regulação

Os campos listados abaixo são obrigatórios por regulação de acordo com o Banco Central.

Além disso, ao longo da especificação, o atributo x-regulatory-required indica a obrigatoriedade regulatória de cada campo dentro dos objetos. Para mais informações sobre preenchimento dos campos e relação com a obrigatoriedade técnica, consulte a página "Obrigatoriedade de campos" na seção "Padrões"

| **endpoint** | **campo** | **Regulação** |
| --- | --- | --- |
| personal-accounts | /data[]/participant/brand | IN n° 371 |
| personal-accounts | /data[]/participant/name | IN n° 371 |
| personal-accounts | /data[]/participant/cnpjNumber | IN n° 371 |
| personal-accounts | /data[]/participant/urlComplementaryList | IN n° 371 |
| personal-accounts | /data[]/type | IN n° 371 |
| personal-accounts | /data[]/fees​ | IN n° 371 |
| personal-accounts | /data[]/fees/priorityServices​ | IN n° 371 |
| personal-accounts | /data[]/fees/priorityServices[]/name | IN n° 371 |
| personal-accounts | /data[]/fees/priorityServices[]/code | IN n° 371 |
| personal-accounts | /data[]/fees/priorityServices[]/chargingTriggerInfo | IN n° 371 |
| personal-accounts | /data[]/fees/priorityServices[]/prices | IN n° 371 |
| personal-accounts | /data[]/fees/priorityServices[]/prices[]/interval | IN n° 371 |
| personal-accounts | /data[]/fees/priorityServices[]/prices[]/value | IN n° 371 |
| personal-accounts | /data[]/fees/priorityServices[]/prices[]/currency | IN n° 371 |
| personal-accounts | /data[]/fees/priorityServices[]/prices[]/customers | IN n° 371 |
| personal-accounts | /data[]/fees/priorityServices[]/prices[]/customers/rate | IN n° 371 |
| personal-accounts | /data[]/fees/priorityServices[]/minimum | IN n° 371 |
| personal-accounts | /data[]/fees/priorityServices[]/minimum/value | IN n° 371 |
| personal-accounts | /data[]/fees/priorityServices[]/minimum/currency | IN n° 371 |
| personal-accounts | /data[]/fees/priorityServices[]/maximum | IN n° 371 |
| personal-accounts | /data[]/fees/priorityServices[]/maximum/value | IN n° 371 |
| personal-accounts | /data[]/fees/priorityServices[]/maximum/currency | IN n° 371 |
| personal-accounts | /data[]/fees/otherServices[]/name | IN n° 371 |
| personal-accounts | /data[]/fees/otherServices[]/code | IN n° 371 |
| personal-accounts | /data[]/fees/otherServices[]/chargingTriggerInfo | IN n° 371 |
| business-accounts | /data[]/participant/brand | IN n° 371 |
| business-accounts | /data[]/participant/name | IN n° 371 |
| business-accounts | /data[]/participant/cnpjNumber | IN n° 371 |
| business-accounts | /data[]/participant/urlComplementaryList | IN n° 371 |
| business-accounts | /data[]/type | IN n° 371 |
| business-accounts | /data[]//fees/services[]/name | IN n° 371 |
| business-accounts | /data[]/fees/services[]/code | IN n° 371 |
| business-accounts | /data[]/fees/services[]/chargingTriggerInfo | IN n° 371 |
| business-accounts | /data[]/fees/services[]/prices | IN n° 371 |
| business-accounts | /data[]/fees/services[]/prices[]/interval | IN n° 371 |
| business-accounts | /data[]/fees/services[]/prices[]/value | IN n° 371 |
| business-accounts | /data[]/fees/services[]/prices[]/currency | IN n° 371 |
| business-accounts | /data[]/fees/services[]/prices[]/customers | IN n° 371 |
| business-accounts | /data[]/fees/services[]/prices[]/customers/rate | IN n° 371 |
| business-accounts | /data[]/fees/services[]/minimum | IN n° 371 |
| business-accounts | /data[]/fees/services[]/minimum/value | IN n° 371 |
| business-accounts | /data[]/fees/services[]/minimum/currency | IN n° 371 |
| business-accounts | /data[]/fees/services[]/maximum | IN n° 371 |
| business-accounts | /data[]/fees/services[]/maximum/value | IN n° 371 |
| business-accounts | /data[]/fees/services[]/maximum/currency | IN n° 371 |
| business-accounts | /data[]/serviceBundles[]/name | IN n° 371 |
| business-accounts | /data[]/serviceBundles[]/services[]/code | IN n° 371 |
| business-accounts | /data[]/serviceBundles[]/services[]/chargingTriggerInfo | IN n° 371 |
| business-accounts | /data[]/serviceBundles[]/services[]/eventLimitQuantity | IN n° 371 |
| business-accounts | /data[]/serviceBundles[]/services[]/freeEventQuantity | IN n° 371 |
| business-accounts | /data[]/serviceBundles[]/prices[]/interval | IN n° 371 |
| business-accounts | /data[]/serviceBundles[]/prices[]/monthlyFee | IN n° 371 |
| business-accounts | /data[]/serviceBundles[]/prices[]/currency | IN n° 371 |
| business-accounts | /data[]/serviceBundles[]/prices[]/customers | IN n° 371 |
| business-accounts | /data[]/serviceBundles[]/prices[]/customers/rate | IN n° 371 |
| business-accounts | /data[]/serviceBundles[]/minimum/value | IN n° 371 |
| business-accounts | /data[]/serviceBundles[]/minimum/currency | IN n° 371 |
| business-accounts | /data[]/serviceBundles[]/maximum/value | IN n° 371 |
| business-accounts | /data[]/serviceBundles[]/maximum/currency | IN n° 371 |
| business-accounts | /data[]/openingClosingChannels | IN n° 371 |
| business-accounts | /data[]/openingClosingChannelsAdditionalInfo | IN n° 371 |
| business-accounts | /data[]/transactionMethods | IN n° 371 |
| business-accounts | /data[]/termsConditions/minimumBalance | IN n° 371 |
| business-accounts | /data[]/termsConditions/minimumBalance/value | IN n° 371 |
| business-accounts | /data[]/termsConditions/minimumBalance/currency | IN n° 371 |
| business-accounts | /data[]/termsConditions/elegibilityCriteriaInfo | IN n° 371 |
| business-accounts | /data[]/termsConditions/closingProcessInfo | IN n° 371 |
| business-accounts | /data[]/incomeRate/savingAccount | IN n° 371 |
| business-accounts | /data[]/incomeRate/prepaidPaymentAccount | IN n° 371 |

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/223805546)