[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/193953813)

Visão Geral

A API Invoice-financings viabiliza o compartilhamento de informações das Operações de Crédito do tipo Direitos Creditórios Descontados.

## **Direitos Creditórios Descontados**: (GET /invoice-financings/v2/contracts)

**Visão Geral**

Conjunto de informações de contratos de direitos creditórios descontados mantidos pelo cliente na instituição transmissora e para os quais ele tenha fornecido consentimento

Tags: [Direito Creditório Descontado (Invoice Financing)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Direito-Credit%C3%B3rio-Descontado-%28Invoice-Financing%29) e [Identificador padronizado da operação de crédito – Ipoc Code](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Identificador-Padronizado-da-Opera%C3%A7%C3%A3o-de-Cr%C3%A9dito-%E2%80%93-Ipoc-Code).

**Visão de alto de nível das estruturas de dados**
![att193953910](Informa%c3%a7%c3%b5es%20Gerais%20-%20Direitos%20Credit%c3%b3rios%20Descontados%20-%20v2.1.1-rc.2/attachments/TLD_InvoiceFinancings_List-36daf724.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att193953907](Informa%c3%a7%c3%b5es%20Gerais%20-%20Direitos%20Credit%c3%b3rios%20Descontados%20-%20v2.1.1-rc.2/attachments/DER_InvoiceFinancings_List_Conceitual-cbb2adbb.png)

- DER Lógico

![att193953904](Informa%c3%a7%c3%b5es%20Gerais%20-%20Direitos%20Credit%c3%b3rios%20Descontados%20-%20v2.1.1-rc.2/attachments/DER_InvoiceFinancings_List-c771a67f.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/invoiceFinancingsGetContracts_v2.csv)

[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/10059965/invoiceFinancingsGetContracts.csv?api=v2&amp;download=true)

## **Direitos Creditórios Descontados - Contrato**: (GET /invoice-financings/v2/contracts/{contractId})

**Visão Geral**

Obtém dados referentes à identificação da operação de crédito de Direitos Creditórios Descontados

Tags: [Custo Efetivo Total (CET)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Custo-Efetivo-Total-%28CET%29), [<u>Direito Creditório Descontado (Invoice Financing)</u>](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Direito-Credit%C3%B3rio-Descontado-%28Invoice-Financing%29), [Encargo (Charge)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Encargo-%28Charge%29), [Ente Consignante (CnpjConsignee)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Ente-Consignante-%28CnpjConsignee%29), [Identificador padronizado da operação de crédito – Ipoc Code](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Identificador-Padronizado-da-Opera%C3%A7%C3%A3o-de-Cr%C3%A9dito-%E2%80%93-Ipoc-Code), [Indexador (Indexer)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Indexador-%28Indexer%29), [Tarifa (Fee)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Tarifa-%28Fee%29), [Taxa Efetiva (EffectiveTax)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Taxa-Efetiva-%28EffectiveTax%29) e [Taxa nominal (NominalTax)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Taxa-nominal-%28NominalTax%29).

**Visão de alto de nível das estruturas de dados**
![att193953901](Informa%c3%a7%c3%b5es%20Gerais%20-%20Direitos%20Credit%c3%b3rios%20Descontados%20-%20v2.1.1-rc.2/attachments/TLD_InvoiceFinancings_Contract-c63c2a6b.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att193953883](Informa%c3%a7%c3%b5es%20Gerais%20-%20Direitos%20Credit%c3%b3rios%20Descontados%20-%20v2.1.1-rc.2/attachments/DER_InvoiceFinancings-11ff0d5b.png)

- DER Lógico

![att193953898](Informa%c3%a7%c3%b5es%20Gerais%20-%20Direitos%20Credit%c3%b3rios%20Descontados%20-%20v2.1.1-rc.2/attachments/DER_InvoiceFinancings_Contract-c0c084b4.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/invoiceFinancingsGetContractsContractId_v2.csv)

[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/10059965/invoiceFinancingsGetContractsContractId.csv?api=v2&amp;download=true)

## **Direitos Creditórios Descontados - Garantias do Contrato**: (GET /invoice-financings/v2/contracts/{contractId}/warranties)

**Visão Geral**

Obtém dados referentes às garantias que avalizam a operação de crédito de Direitos Creditórios Descontados contratada

Tags: [Direito Creditório Descontado (Invoice Financing)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Direito-Credit%C3%B3rio-Descontado-%28Invoice-Financing%29) e [Garantia (Warranty)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Garantia-%28Warranty%29).

**Visão de alto de nível das estruturas de dados**
![att193953895](Informa%c3%a7%c3%b5es%20Gerais%20-%20Direitos%20Credit%c3%b3rios%20Descontados%20-%20v2.1.1-rc.2/attachments/TLD_InvoiceFinancings_Warranties-09b45d1c.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att193953883](Informa%c3%a7%c3%b5es%20Gerais%20-%20Direitos%20Credit%c3%b3rios%20Descontados%20-%20v2.1.1-rc.2/attachments/DER_InvoiceFinancings-11ff0d5b.png)

- DER Lógico

![att193953892](Informa%c3%a7%c3%b5es%20Gerais%20-%20Direitos%20Credit%c3%b3rios%20Descontados%20-%20v2.1.1-rc.2/attachments/DER_InvoiceFinancings_Warranties-f69e122e.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/invoiceFinancingsGetContractsContractIdWarranties_v2.csv)

[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/10059965/invoiceFinancingsGetContractsContractIdWarranties.csv?api=v2&amp;download=true)

## **Direitos Creditórios Descontados - Pagamentos do Contrato**: (GET /invoice-financings/v2/contracts/{contractId}/payments)

**Visão Geral**

Obtém dados dos pagamentos referentes às operações de crédito de Direitos Creditórios Descontados contratadas

Tags: [Direito Creditório Descontado (Invoice Financing)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Direito-Credit%C3%B3rio-Descontado-%28Invoice-Financing%29), [Encargo (Charge)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Encargo-%28Charge%29), [Saldo Devedor (Outstanding Balance)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Saldo-Devedor-%28Outstanding-Balance%29) e [Tarifa (Fee)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Tarifa-%28Fee%29).

**Visão de alto de nível das estruturas de dados**
![att193953889](Informa%c3%a7%c3%b5es%20Gerais%20-%20Direitos%20Credit%c3%b3rios%20Descontados%20-%20v2.1.1-rc.2/attachments/TLD_InvoiceFinancings_Payments-b8984bfa.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att193953883](Informa%c3%a7%c3%b5es%20Gerais%20-%20Direitos%20Credit%c3%b3rios%20Descontados%20-%20v2.1.1-rc.2/attachments/DER_InvoiceFinancings-11ff0d5b.png)

- DER Lógico

![att193953913](Informa%c3%a7%c3%b5es%20Gerais%20-%20Direitos%20Credit%c3%b3rios%20Descontados%20-%20v2.1.1-rc.2/attachments/DER_InvoiceFinancings_Payments-98fc0ede.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/invoiceFinancingsGetContractsContractIdPayments_v2.csv)

[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/10059965/invoiceFinancingsGetContractsContractIdPayments.csv?api=v2&amp;download=true)

##   
**Direitos Creditórios Descontados - Parcelas do Contrato**: (GET /invoice-financings/v2/contracts/{contractId}/scheduled-instalments)

**Visão Geral**

Obtém dados referentes às parcelas / prestações da operação de crédito de Direitos Creditórios Descontados contratadas

Tags: [Direito Creditório Descontado (Invoice Financing)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Direito-Credit%C3%B3rio-Descontado-%28Invoice-Financing%29).

**Visão de alto de nível das estruturas de dados**
![att193953886](Informa%c3%a7%c3%b5es%20Gerais%20-%20Direitos%20Credit%c3%b3rios%20Descontados%20-%20v2.1.1-rc.2/attachments/TLD_InvoiceFinancings_Instalments-77a8dcb2.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att193953883](Informa%c3%a7%c3%b5es%20Gerais%20-%20Direitos%20Credit%c3%b3rios%20Descontados%20-%20v2.1.1-rc.2/attachments/DER_InvoiceFinancings-11ff0d5b.png)

- DER Lógico

![att193953880](Informa%c3%a7%c3%b5es%20Gerais%20-%20Direitos%20Credit%c3%b3rios%20Descontados%20-%20v2.1.1-rc.2/attachments/DER_InvoiceFinancings_Instalments-cfaf8413.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/invoiceFinancingsGetContractsContractIdScheduledInstalments_v2.csv)

[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/10059965/invoiceFinancingsGetContractsContractIdScheduledInstalments.csv?api=v2&amp;download=true)

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/193953813)