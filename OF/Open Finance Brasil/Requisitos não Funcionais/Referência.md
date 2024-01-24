[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17957025)

## [Relatórios e Métricas](../../../OF/Open%20Finance%20Brasil/Especifica%c3%a7%c3%b5es%20de%20APIs/Relat%c3%b3rios%20e%20M%c3%a9tricas/index)

| [API Admin](../../../OF/Open%20Finance%20Brasil/Especifica%c3%a7%c3%b5es%20de%20APIs/Relat%c3%b3rios%20e%20M%c3%a9tricas/API%20Admin/index) |
| --- |
| **Endpoint** | **Frequência** | **SLA (ms)\*** | **Timeout (s)** | **TPM** | **TPS** | **Limite Operacional**<br><br>**(consultas/mês)** |
| GET /metrics | Alta | 1500 | 15 | NA | NA | NA |

| [API Comum (Discovery)](../../../OF/Open%20Finance%20Brasil/Especifica%c3%a7%c3%b5es%20de%20APIs/Relat%c3%b3rios%20e%20M%c3%a9tricas/API%20Comum%20%28Discovery%29/index) |
| --- |
| **Endpoint** | **Frequência** | **SLA (ms)\*** | **Timeout (s)** | **TPM** | **TPS** | **Limite Operacional**<br><br>**(consultas/mês)** |
| GET /status | Alta | 1500 | 15 | NA | NA | NA |
| GET /outages | Alta | 1500 | 15 | NA | NA | NA |

## [Dados Abertos](../../../OF/Open%20Finance%20Brasil/Especifica%c3%a7%c3%b5es%20de%20APIs/Dados%20Abertos%20-%20DA/index)

| [\[DA\] API Produtos e Serviços](../../../OF/Open%20Finance%20Brasil/Especifica%c3%a7%c3%b5es%20de%20APIs/Dados%20Abertos%20-%20DA/[DA]%20API%20-%20Produtos%20e%20Servi%c3%a7os/index) |
| --- |
| **Endpoint** | **Frequência** | **SLA (ms)\*** | **Timeout (s)** | **TPM** | **TPS** | **Limite Operacional**<br><br>**(consultas/mês)** |
| GET /personal-accounts | Baixa | 4000 | 15 | 500 | 300 | NA |
| GET /business-accounts | Baixa | 4000 | 15 | 500 | 300 | NA |
| GET /personal-loans | Baixa | 4000 | 15 | 500 | 300 | NA |
| GET /business-loans | Baixa | 4000 | 15 | 500 | 300 | NA |
| GET /personal-credit-cards | Baixa | 4000 | 15 | 500 | 300 | NA |
| GET /business-credit-cards | Baixa | 4000 | 15 | 500 | 300 | NA |
| GET /personal-financings | Baixa | 4000 | 15 | 500 | 300 | NA |
| GET /business-financings | Baixa | 4000 | 15 | 500 | 300 | NA |
| GET /personal-invoice-financings | Baixa | 4000 | 15 | 500 | 300 | NA |
| GET /business-invoice-financings | Baixa | 4000 | 15 | 500 | 300 | NA |
| GET /personal-unarranged-account-overdraft | Baixa | 4000 | 15 | 500 | 300 | NA |
| GET /business-unarranged-account-overdraft | Baixa | 4000 | 15 | 500 | 300 | NA |

| [DA] API Canais de Atendimento |
| --- |
| **Endpoint** | **Frequência** | **SLA (ms)\*** | **Timeout (s)** | **TPM** | **TPS** | **Limite Operacional**<br><br>**(consultas/mês)** |
| GET /banking-agents | Baixa | 4000 | 15 | 500 | 300 | NA |
| GET /branches | Baixa | 4000 | 15 | 500 | 300 | NA |
| GET /electronic-channels | Baixa | 4000 | 15 | 500 | 300 | NA |
| GET /phone-channels | Baixa | 4000 | 15 | 500 | 300 | NA |
| GET /shared-automated-teller-machines | Baixa | 4000 | 15 | 500 | 300 | NA |

| [\[DA\] API Títulos de Capitalização](../../../OF/Open%20Finance%20Brasil/Especifica%c3%a7%c3%b5es%20de%20APIs/Dados%20Abertos%20-%20DA/[DA]%20API%20-%20T%c3%adtulos%20de%20Capitaliza%c3%a7%c3%a3o/index) |
| --- |
| **Endpoint** | **Frequência** | **SLA (ms)\*** | **Timeout (s)** | **TPM** | **TPS** | **Limite Operacional**<br><br>**(consultas/mês)** |
| GET /bonds | Baixa | 4000 | 15 | 500 | 300 | NA |

| [\[DA\] API Investimentos](../../../OF/Open%20Finance%20Brasil/Especifica%c3%a7%c3%b5es%20de%20APIs/Dados%20Abertos%20-%20DA/[DA]%20API%20-%20Investimentos/index) |
| --- |
| **Endpoint** | **Frequência** | **SLA (ms)\*** | **Timeout (s)** | **TPM** | **TPS** | **Limite Operacional**<br><br>**(consultas/mês)** |
| GET /funds | Baixa | 4000 | 15 | 500 | 300 | NA |
| GET /bank-fixed-incomes | Baixa | 4000 | 15 | 500 | 300 | NA |
| GET /credit-fixed-incomes | Baixa | 4000 | 15 | 500 | 300 | NA |
| GET /variable-incomes | Baixa | 4000 | 15 | 500 | 300 | NA |
| GET /treasure-titles | Baixa | 4000 | 15 | 500 | 300 | NA |

| [\[DA\] API Câmbio](../../../OF/Open%20Finance%20Brasil/Especifica%c3%a7%c3%b5es%20de%20APIs/Dados%20Abertos%20-%20DA/[DA]%20API%20-%20C%c3%a2mbio/index) |
| --- |
| **Endpoint** | **Frequência** | **SLA (ms)\*** | **Timeout (s)** | **TPM** | **TPS** | **Limite Operacional**<br><br>**(consultas/mês)** |
| GET /online-rates | Alta | 1500 | 15 | 500 | 300 | NA |
| GET /vet-values | Baixa | 4000 | 15 | 500 | 300 | NA |

| [\[DA\] API Credenciamento](../../../OF/Open%20Finance%20Brasil/Especifica%c3%a7%c3%b5es%20de%20APIs/Dados%20Abertos%20-%20DA/[DA]%20API%20-%20Credenciamento/index) |
| --- |
| **Endpoint** | **Frequência** | **SLA (ms)\*** | **Timeout (s)** | **TPM** | **TPS** | **Limite Operacional**<br><br>**(consultas/mês)** |
| GET /businesses | Baixa | 4000 | 15 | 500 | 300 | NA |
| GET /personals | Baixa | 4000 | 15 | 500 | 300 | NA |

| [\[DA\] API Previdência](../../../OF/Open%20Finance%20Brasil/Especifica%c3%a7%c3%b5es%20de%20APIs/Dados%20Abertos%20-%20DA/[DA]%20API%20-%20Previd%c3%aancia/index) |
| --- |
| **Endpoint** | **Frequência** | **SLA (ms)\*** | **Timeout (s)** | **TPM** | **TPS** | **Limite Operacional**<br><br>**(consultas/mês)** |
| GET /risk-coverages | Baixa | 4000 | 15 | 500 | 300 | NA |
| GET /survival-coverages | Baixa | 4000 | 15 | 500 | 300 | NA |

| [\[DA\] API Seguros](../../../OF/Open%20Finance%20Brasil/Especifica%c3%a7%c3%b5es%20de%20APIs/Dados%20Abertos%20-%20DA/[DA]%20API%20-%20Seguros/index) |
| --- |
| **Endpoint** | **Frequência** | **SLA (ms)\*** | **Timeout (s)** | **TPM** | **TPS** | **Limite Operacional**<br><br>**(consultas/mês)** |
| GET /automotives | Baixa | 4000 | 15 | 500 | 300 | NA |
| GET /homes | Baixa | 4000 | 15 | 500 | 300 | NA |
| GET /personals | Baixa | 4000 | 15 | 500 | 300 | NA |

## [Dados do Cliente](../../../OF/Open%20Finance%20Brasil/Especifica%c3%a7%c3%b5es%20de%20APIs/Dados%20do%20Cliente%20%e2%80%93%20DC/index)

| [\[DC\] API Consentimento](../../../OF/Open%20Finance%20Brasil/Especifica%c3%a7%c3%b5es%20de%20APIs/Dados%20do%20Cliente%20%e2%80%93%20DC/[DC]%20API%20-%20Consentimento/index) |
| --- |
| **Endpoint** | **Frequência** | **SLA (ms)\*** | **Timeout (s)** | **TPM** | **TPS** | **Limite Operacional**<br><br>**(consultas/mês)** |
| POST /consents | Alta | 1500 | 15 | NA | 300 | NA |
| GET /consents​/{consentId} | Alta | 1500 | 15 | NA | 300 | NA |
| DELETE /consents​/{consentId} | Alta | 1500 | 15 | NA | 300 | NA |
| POST /consents/{consentId}/extends​ | Baixa | 4000 | 15 | NA | 300 | NA |
| GET /consents/​{consentId}/extensions​ | Baixa | 4000 | 15 | NA | 300 | NA |

| [\[DC\] API Recursos](../../../OF/Open%20Finance%20Brasil/Especifica%c3%a7%c3%b5es%20de%20APIs/Dados%20do%20Cliente%20%e2%80%93%20DC/[DC]%20API%20-%20Recursos/index) |
| --- |
| **Endpoint** | **Frequência** | **SLA (ms)\*** | **Timeout (s)** | **TPM** | **TPS** | **Limite Operacional**<br><br>**(consultas/mês)** |
| GET /resources | Alta | 1500 | 15 | NA | 300 | NA |

| [\[DC\] API Dados Cadastrais](../../../OF/Open%20Finance%20Brasil/Especifica%c3%a7%c3%b5es%20de%20APIs/Dados%20do%20Cliente%20%e2%80%93%20DC/[DC]%20API%20-%20Dados%20Cadastrais/index) |
| --- |
| **Endpoint** | **Frequência** | **SLA (ms)\*** | **Timeout (s)** | **TPM** | **TPS** | **Limite Operacional**<br><br>**(consultas/mês)** |
| GET ​/personal​/identifications | Baixa | 4000 | 15 | 500 | 300 | 4 |
| GET ​/personal​/qualifications | Baixa | 4000 | 15 | 500 | 300 | 4 |
| GET ​/personal​/financial-relations | Baixa | 4000 | 15 | 500 | 300 | 4 |
| GET ​/business​/identifications | Baixa | 4000 | 15 | 500 | 300 | 4 |
| GET ​/business​/qualifications | Baixa | 4000 | 15 | 500 | 300 | 4 |
| GET ​/business​/financial-relations | Baixa | 4000 | 15 | 500 | 300 | 4 |

| [\[DC\] API Cartão de Crédito](../../../OF/Open%20Finance%20Brasil/Especifica%c3%a7%c3%b5es%20de%20APIs/Dados%20do%20Cliente%20%e2%80%93%20DC/[DC]%20API%20-%20Cart%c3%a3o%20de%20Cr%c3%a9dito/index) |
| --- |
| **Endpoint** | **Frequência** | **SLA (ms)\*** | **Timeout (s)** | **TPM** | **TPS** | **Limite Operacional**<br><br>**(consultas/mês)** |
| GET ​/accounts | Baixa | 4000 | 15 | 500 | 300 | 4 |
| GET ​/accounts​/{creditCardAccountId} | Baixa | 4000 | 15 | 500 | 300 | 4 |
| GET ​/accounts​/{creditCardAccountId}​/bills | Média | 2000 | 15 | 1000 | 300 | 30 |
| GET ​/accounts​/{creditCardAccountId}​/bills​/{billId}​/transactions | Média | 2000 | 15 | 1000 | 300 | 30 |
| GET ​/accounts​/{creditCardAccountId}​/limits | Alta | 1500 | 15 | 2000 | 300 | 240 |
| GET ​/accounts​/{creditCardAccountId}​/transactions | Baixa | 4000 | 15 | 500 | 300 | 4 |
| GET ​/accounts​/{creditCardAccountId}​/transactions-current | Alta | 1500 | 15 | 2000 | 300 | 240 |

| [\[DC\] API Contas](../../../OF/Open%20Finance%20Brasil/Especifica%c3%a7%c3%b5es%20de%20APIs/Dados%20do%20Cliente%20%e2%80%93%20DC/[DC]%20API%20-%20Contas/index) |
| --- |
| **Endpoint** | **Frequência** | **SLA (ms)\*** | **Timeout (s)** | **TPM** | **TPS** | **Limite Operacional**<br><br>**(consultas/mês)** |
| GET ​/accounts | Baixa | 4000 | 15 | 500 | 300 | 4 |
| GET ​/accounts​/{accountId} | Baixa | 4000 | 15 | 500 | 300 | 4 |
| GET ​/accounts​/{accountId}​/balances | Alta | 1500 | 15 | 2000 | 300 | 420 |
| GET ​/accounts​/{accountId}​/transactions | Baixa | 4000 | 15 | 500 | 300 | 4 |
| GET ​/accounts​/{accountId}​/transactions-current | Alta | 1500 | 15 | 2000 | 300 | 240 |
| GET ​/accounts​/{accountId}​/overdraft-limits | Alta | 1500 | 15 | 2000 | 300 | 420 |

| [\[DC\] API Operações de Crédito - Empréstimo](../../../OF/Open%20Finance%20Brasil/Especifica%c3%a7%c3%b5es%20de%20APIs/Dados%20do%20Cliente%20%e2%80%93%20DC/[DC]%20API%20-%20Opera%c3%a7%c3%b5es%20de%20Cr%c3%a9dito%20-%20%20Empr%c3%a9stimos/index) |
| --- |
| **Endpoint** | **Frequência** | **SLA (ms)\*** | **Timeout (s)** | **TPM** | **TPS** | **Limite Operacional**<br><br>**(consultas/mês)** |
| GET ​/contracts | Média | 2000 | 15 | 1000 | 300 | 30 |
| GET ​/contracts​/{contractId} | Baixa | 4000 | 15 | 500 | 300 | 4 |
| GET ​/contracts​/{contractId}​/warranties | Baixa | 4000 | 15 | 500 | 300 | 4 |
| GET ​/contracts​/{contractId}​/scheduled-instalments | Média | 2000 | 15 | 1000 | 300 | 30 |
| GET ​/contracts​/{contractId}​/payments | Média | 2000 | 15 | 1000 | 300 | 30 |

| [\[DC\] API Operações de Crédito - Financiamento](../../../OF/Open%20Finance%20Brasil/Especifica%c3%a7%c3%b5es%20de%20APIs/Dados%20do%20Cliente%20%e2%80%93%20DC/[DC]%20API%20-%20Opera%c3%a7%c3%b5es%20de%20Cr%c3%a9dito%20-%20Financiamento/index) |
| --- |
| **Endpoint** | **Frequência** | **SLA (ms)\*** | **Timeout (s)** | **TPM** | **TPS** | **Limite Operacional**<br><br>**(consultas/mês)** |
| GET ​/contracts​ | Média​ | 2000​ | 15​ | 1000​ | 300​ | 30​ |
| GET ​/contracts​/{contractId}​ | Baixa​ | 4000​ | 15​ | 500​ | 300​ | 4​ |
| GET ​/contracts​/{contractId}​/warranties​ | Baixa​ | 4000​ | 15​ | 500​ | 300​ | 4​ |
| GET ​/contracts​/{contractId}​/scheduled-instalments​ | Média​ | 2000​ | 15​ | 1000​ | 300​ | 30​ |
| GET ​/contracts​/{contractId}​/payments​ | Média​ | 2000​ | 15​ | 1000​ | 300​ | 30​ |

| [\[DC\] API Operações de Crédito - Adiantamento a Depositantes](../../../OF/Open%20Finance%20Brasil/Especifica%c3%a7%c3%b5es%20de%20APIs/Dados%20do%20Cliente%20%e2%80%93%20DC/[DC]%20API%20-%20Opera%c3%a7%c3%b5es%20de%20Cr%c3%a9dito%20-%20%20Adiantamento%20a%20Depositantes/index) |
| --- |
| **Endpoint** | **Frequência** | **SLA (ms)\*** | **Timeout (s)** | **TPM** | **TPS** | **Limite Operacional**<br><br>**(consultas/mês)** |
| GET ​/contracts​ | Média​ | 2000​ | 15​ | 1000​ | 300​ | 30​ |
| GET ​/contracts​/{contractId}​ | Baixa​ | 4000​ | 15​ | 500​ | 300​ | 4​ |
| GET ​/contracts​/{contractId}​/warranties​ | Baixa​ | 4000​ | 15​ | 500​ | 300​ | 4​ |
| GET ​/contracts​/{contractId}​/scheduled-instalments​ | Média​ | 2000​ | 15​ | 1000​ | 300​ | 30​ |
| GET ​/contracts​/{contractId}​/payments​ | Média​ | 2000​ | 15​ | 1000​ | 300​ | 30​ |

| [\[DC\] API Operações de Crédito - Direitos Creditórios Descontados](../../../OF/Open%20Finance%20Brasil/Especifica%c3%a7%c3%b5es%20de%20APIs/Dados%20do%20Cliente%20%e2%80%93%20DC/[DC]%20API%20-%20Opera%c3%a7%c3%b5es%20de%20Cr%c3%a9dito%20-%20Direitos%20Credit%c3%b3rios%20Descontados/index) |
| --- |
| **Endpoint** | **Frequência** | **SLA (ms)\*** | **Timeout (s)** | **TPM** | **TPS** | **Limite Operacional**<br><br>**(consultas/mês)** |
| GET ​/contracts | Média | 2000 | 15 | 1000 | 300 | 30 |
| GET ​/contracts​/{contractId} | Baixa | 4000 | 15 | 500 | 300 | 4 |
| GET ​/contracts​/{contractId}​/warranties | Baixa | 4000 | 15 | 500 | 300 | 4 |
| GET ​/contracts​/{contractId}​/scheduled-instalments | Média | 2000 | 15 | 1000 | 300 | 30 |
| GET ​/contracts​/{contractId}​/payments | Média | 2000 | 15 | 1000 | 300 | 30 |

| [\[DC\] API Investimentos - Renda Fixa Bancária](../../../OF/Open%20Finance%20Brasil/Especifica%c3%a7%c3%b5es%20de%20APIs/Dados%20do%20Cliente%20%e2%80%93%20DC/[DC]%20APIs%20-%20Investimentos/[DC]%20API%20-%20Investimentos%20-%20Renda%20Fixa%20Banc%c3%a1ria/index) |
| --- |
| **Endpoint** | **Frequência** | **SLA (ms)\*** | **Timeout (s)** | **TPM** | **TPS** | **Limite Operacional**<br><br>**(consultas/mês)** |
| GET ​/investments | Média | 2000 | 15 | 1000 | 300 | 30 |
| GET ​/investments​/{investimentId} | Baixa | 4000 | 15 | 500 | 300 | 4 |
| GET /investments​/{investimentId}​/balances | Média-alta | 2000 | 15 | 1500 | 300 | 120 |
| GET /investments​/{investimentId}​/transactions | Baixa | 4000 | 15 | 500 | 300 | 4 |
| GET ​/investments​/{investimentId}​/transactions-current | Média-alta | 2000 | 15 | 1500 | 300 | 120 |

| [\[DC\] API Investimentos - Renda Fixa Crédito](../../../OF/Open%20Finance%20Brasil/Especifica%c3%a7%c3%b5es%20de%20APIs/Dados%20do%20Cliente%20%e2%80%93%20DC/[DC]%20APIs%20-%20Investimentos/[DC]%20API%20-%20Investimentos%20-%20Renda%20Fixa%20Cr%c3%a9dito/index) |
| --- |
| **Endpoint** | **Frequência** | **SLA (ms)\*** | **Timeout (s)** | **TPM** | **TPS** | **Limite Operacional**<br><br>**(consultas/mês)** |
| GET ​/investments | Média | 2000 | 15 | 1000 | 300 | 30 |
| GET ​/investments​/{investimentId} | Baixa | 4000 | 15 | 500 | 300 | 4 |
| GET /investments​/{investimentId}​/balances | Média-alta | 2000 | 15 | 1500 | 300 | 120 |
| GET /investments​/{investimentId}​/transactions | Baixa | 4000 | 15 | 500 | 300 | 4 |
| GET ​/investments​/{investimentId}​/transactions-current | Média-alta | 2000 | 15 | 1500 | 300 | 120 |

| [\[DC\] API Investimentos - Renda Variável](../../../OF/Open%20Finance%20Brasil/Especifica%c3%a7%c3%b5es%20de%20APIs/Dados%20do%20Cliente%20%e2%80%93%20DC/[DC]%20APIs%20-%20Investimentos/[DC]%20API%20-%20Investimentos%20-%20Renda%20Vari%c3%a1vel/index) |
| --- |
| **Endpoint** | **Frequência** | **SLA (ms)\*** | **Timeout (s)** | **TPM** | **TPS** | **Limite Operacional**<br><br>**(consultas/mês)** |
| GET ​/investments | Média | 2000 | 15 | 1000 | 300 | 30 |
| GET ​/investments​/{investimentId} | Baixa | 4000 | 15 | 500 | 300 | 4 |
| GET /investments​/{investimentId}​/balances | Média | 2000 | 15 | 1000 | 300 | 30 |
| GET /investments​/{investimentId}​/transactions | Baixa | 4000 | 15 | 500 | 300 | 4 |
| GET ​/investments​/{investimentId}​/transactions-current | Média | 2000 | 15 | 1000 | 300 | 30 |
| GET ​/investments​/{investimentId}​/broker-notes/{brokerNoteId} | Média | 2000 | 15 | 1000 | 300 | 30 |

| [\[DC\] API Investimentos - Títulos do Tesouro Direto](../../../OF/Open%20Finance%20Brasil/Especifica%c3%a7%c3%b5es%20de%20APIs/Dados%20do%20Cliente%20%e2%80%93%20DC/[DC]%20APIs%20-%20Investimentos/[DC]%20API%20-%20Investimentos%20-%20T%c3%adtulos%20do%20Tesouro%20Direto/index) |
| --- |
| **Endpoint** | **Frequência** | **SLA (ms)\*** | **Timeout (s)** | **TPM** | **TPS** | **Limite Operacional**<br><br>**(consultas/mês)** |
| GET ​/investments | Média | 2000 | 15 | 1000 | 300 | 30 |
| GET ​/investments​/{investimentId} | Baixa | 4000 | 15 | 500 | 300 | 4 |
| GET /investments​/{investimentId}​/balances | Média-alta | 2000 | 15 | 1500 | 300 | 120 |
| GET /investments​/{investimentId}​/transactions | Baixa | 4000 | 15 | 500 | 300 | 4 |
| GET ​/investments​/{investimentId}​/transactions-current | Média-alta | 2000 | 15 | 1500 | 300 | 120 |

| [\[DC\] API Investimentos - Fundos de Investimento](../../../OF/Open%20Finance%20Brasil/Especifica%c3%a7%c3%b5es%20de%20APIs/Dados%20do%20Cliente%20%e2%80%93%20DC/[DC]%20APIs%20-%20Investimentos/[DC]%20API%20-%20Investimentos%20-%20Fundos%20de%20Investimento/index) |
| --- |
| **Endpoint** | **Frequência** | **SLA (ms)\*** | **Timeout (s)** | **TPM** | **TPS** | **Limite Operacional**<br><br>**(consultas/mês)** |
| GET ​/investments | Média | 2000 | 15 | 1000 | 300 | 30 |
| GET ​/investments​/{investimentId} | Baixa | 4000 | 15 | 500 | 300 | 4 |
| GET /investments​/{investimentId}​/balances | Média-alta | 2000 | 15 | 1500 | 300 | 120 |
| GET /investments​/{investimentId}​/transactions | Baixa | 4000 | 15 | 500 | 300 | 4 |
| GET ​/investments​/{investimentId}​/transactions-current | Média-alta | 2000 | 15 | 1500 | 300 | 120 |

| [\[DC\] API Câmbio](../../../OF/Open%20Finance%20Brasil/Especifica%c3%a7%c3%b5es%20de%20APIs/Dados%20do%20Cliente%20%e2%80%93%20DC/[DC]%20API%20-%20C%c3%a2mbio/index) |
| --- |
| **Endpoint** | **Frequência** | **SLA (ms)\*** | **Timeout (s)** | **TPM** | **TPS** | **Limite Operacional**<br><br>**(consultas/mês)** |
| GET ​/operations | Média | 2000 | 15 | 1000 | 300 | 30 |
| GET ​/operations​/{operationId} | Baixa | 4000 | 15 | 500 | 300 | 4 |
| GET ​/operations​/{operationId}/events | Média | 2000 | 15 | 1000 | 300 | 30 |

## [Serviços](../../../OF/Open%20Finance%20Brasil/Especifica%c3%a7%c3%b5es%20de%20APIs/Servi%c3%a7os%20-%20SV/index)

| [\[SV\] API Pagamentos](../../../OF/Open%20Finance%20Brasil/Especifica%c3%a7%c3%b5es%20de%20APIs/Servi%c3%a7os%20-%20SV/[SV]%20Inicia%c3%a7%c3%a3o%20de%20Pagamentos/[SV]%20API%20-%20Pagamentos/index) |
| --- |
| **Endpoint** | **Frequência** | **SLA (ms)\*** | **Timeout (s)** | **TPM** | **TPS** | **Limite Operacional**<br><br>**(consultas/mês)** |
| POST ​/consents | Alta | 1500 | 15 | NA | 300 | NA |
| GET ​/consents​/{consentId} | Alta | 1500 | 15 | NA | 300 | NA |
| POST ​/pix​/payments | Alta | 1500 | 15 | NA | 300 | NA |
| GET ​/pix​/payments​/{paymentId} | Alta | 1500 | 15 | NA | 300 | NA |
| PATCH /pix/payments/{paymentld} | Alta | 1500 | 15 | NA | 300 | NA |

| [\[SV\] API Pagamentos Automáticos](../../../OF/Open%20Finance%20Brasil/Especifica%c3%a7%c3%b5es%20de%20APIs/Servi%c3%a7os%20-%20SV/[SV]%20Inicia%c3%a7%c3%a3o%20de%20Pagamentos/[SV]%20API%20-%20Pagamentos%20Autom%c3%a1ticos/index) |
| --- |
| **Endpoint** | **Frequência** | **SLA (ms)\*** | **Timeout (s)** | **TPM** | **TPS** | **Limite Operacional**<br><br>**(consultas/mês)** |
| POST /recurring-consents | Alta | 1500 | 15 | NA | 300 | NA |
| GET /recurring-consents/{recurringConsentId} | Alta | 1500 | 15 | NA | 300 | NA |
| PATCH /recurring-consents/{recurringConsentId} | Alta | 1500 | 15 | NA | 300 | NA |
| POST /recurring-payments | Alta | 1500 | 15 | NA | 300 | NA |
| GET /recurring-payments/{recurringPaymentId} | Alta | 1500 | 15 | NA | 300 | NA |
| GET /recurring-payments | Alta | 1500 | 15 | NA | 300 | NA |
| PATCH /recurring-payments/{recurringPaymentId} | Alta | 1500 | 15 | NA | 300 | NA |

## [Webhook](../../../OF/Open%20Finance%20Brasil/Especifica%c3%a7%c3%b5es%20de%20APIs/Webhook/index)

| [Webhook - Todas as APIs](../../../OF/Open%20Finance%20Brasil/Especifica%c3%a7%c3%b5es%20de%20APIs/Webhook/index) |
| --- |
| **Endpoint** | **Frequência** | **SLA (ms)\*** | **Timeout (s)** | **TPM** | **TPS** | **Limite Operacional**<br><br>**(consultas/mês)** |
| POST ​/payments/[Versão da API]/consents/{consentId} | Alta | 1500 | 15 | NA | 300 | NA |
| POST ​/payments/[Versão da API]/pix/payments/{paymentId} | Alta | 1500 | 15 | NA | 300 | NA |

**Legenda**  
NA - Não se aplica

- - Percentil 95

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17957025)