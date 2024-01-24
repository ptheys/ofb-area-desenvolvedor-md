[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17375735)

Visão Geral

A API Invoice-financings viabiliza o compartilhamento de informações das Operações de Crédito do tipo Direitos Creditórios Descontados.

## **Direitos Creditórios Descontados**: (GET /invoice-financings/v2/contracts)

**Visão Geral**

Conjunto de informações de contratos de direitos creditórios descontados mantidos pelo cliente na instituição transmissora e para os quais ele tenha fornecido consentimento

Tags: [Direito Creditório Descontado (Invoice Financing)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioDireitoCreditorioDescontado) e[Identificador padronizado da operação de crédito – Ipoc Code](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioIPOC).

**Visão de alto de nível das estruturas de dados**
![att17375794](Informa%c3%a7%c3%b5es%20Gerais%20-%20Direitos%20Credit%c3%b3rios%20Descontados%20-%20v2.0.0/attachments/TLD_InvoiceFinancings_List-36daf724.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att17375797](Informa%c3%a7%c3%b5es%20Gerais%20-%20Direitos%20Credit%c3%b3rios%20Descontados%20-%20v2.0.0/attachments/DER_InvoiceFinancings_List_Conceitual-cbb2adbb.png)

- DER Lógico

![att17375800](Informa%c3%a7%c3%b5es%20Gerais%20-%20Direitos%20Credit%c3%b3rios%20Descontados%20-%20v2.0.0/attachments/DER_InvoiceFinancings_List-c771a67f.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/invoiceFinancingsGetContracts_v2.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/example/examples_invoice_financings_contract_list.csv)

## **Direitos Creditórios Descontados - Contrato**: (GET /invoice-financings/v2/contracts/{contractId})

**Visão Geral**

Obtém dados referentes à identificação da operação de crédito de Direitos Creditórios Descontados

Tags: [Custo Efetivo Total (CET)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioCET), [Direito Creditório Descontado (Invoice Financing)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioDireitoCreditorioDescontado), [Encargo (Charge)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioEncargo), [Ente Consignante (CnpjConsignee)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioEnteConsignante), [Identificador padronizado da operação de crédito – Ipoc Code](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioIPOC), [Indexador (Indexer)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioIndexador), [Tarifa (Fee)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioTarifa), [Taxa Efetiva (EffectiveTax)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioTaxaEfetiva) e [Taxa nominal (NominalTax)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioTaxaNominal).

**Visão de alto de nível das estruturas de dados**
![att17375803](Informa%c3%a7%c3%b5es%20Gerais%20-%20Direitos%20Credit%c3%b3rios%20Descontados%20-%20v2.0.0/attachments/TLD_InvoiceFinancings_Contract-c63c2a6b.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att17375824](Informa%c3%a7%c3%b5es%20Gerais%20-%20Direitos%20Credit%c3%b3rios%20Descontados%20-%20v2.0.0/attachments/DER_InvoiceFinancings-11ff0d5b.png)

- DER Lógico

![att17375806](Informa%c3%a7%c3%b5es%20Gerais%20-%20Direitos%20Credit%c3%b3rios%20Descontados%20-%20v2.0.0/attachments/DER_InvoiceFinancings_Contract-c0c084b4.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/invoiceFinancingsGetContractsContractId_v2.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/example/examples_invoice_financings_contract.csv)

## **Direitos Creditórios Descontados - Garantias do Contrato**: (GET /invoice-financings/v2/contracts/{contractId}/warranties)

**Visão Geral**

Obtém dados referentes às garantias que avalizam a operação de crédito de Direitos Creditórios Descontados contratada

Tags: [Direito Creditório Descontado (Invoice Financing)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioDireitoCreditorioDescontado) e [Garantia (Warranty)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioGarantia).

**Visão de alto de nível das estruturas de dados**
![att17375809](Informa%c3%a7%c3%b5es%20Gerais%20-%20Direitos%20Credit%c3%b3rios%20Descontados%20-%20v2.0.0/attachments/TLD_InvoiceFinancings_Warranties-09b45d1c.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att17375824](Informa%c3%a7%c3%b5es%20Gerais%20-%20Direitos%20Credit%c3%b3rios%20Descontados%20-%20v2.0.0/attachments/DER_InvoiceFinancings-11ff0d5b.png)

- DER Lógico

![att17375812](Informa%c3%a7%c3%b5es%20Gerais%20-%20Direitos%20Credit%c3%b3rios%20Descontados%20-%20v2.0.0/attachments/DER_InvoiceFinancings_Warranties-f69e122e.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/invoiceFinancingsGetContractsContractIdWarranties_v2.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/example/examples_invoice_financings_warranties.csv)

## **Direitos Creditórios Descontados - Pagamentos do Contrato**: (GET /invoice-financings/v2/contracts/{contractId}/payments)

**Visão Geral**

Obtém dados dos pagamentos referentes às operações de crédito de Direitos Creditórios Descontados contratadas

Tags: [Direito Creditório Descontado (Invoice Financing)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioDireitoCreditorioDescontado), [Encargo (Charge)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioEncargo), [Saldo Devedor (Outstanding Balance)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioSaldoDevedor) e [Tarifa (Fee)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioTarifa).

**Visão de alto de nível das estruturas de dados**
![att17375815](Informa%c3%a7%c3%b5es%20Gerais%20-%20Direitos%20Credit%c3%b3rios%20Descontados%20-%20v2.0.0/attachments/TLD_InvoiceFinancings_Payments-b8984bfa.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att17375824](Informa%c3%a7%c3%b5es%20Gerais%20-%20Direitos%20Credit%c3%b3rios%20Descontados%20-%20v2.0.0/attachments/DER_InvoiceFinancings-11ff0d5b.png)

- DER Lógico

![att17375818](Informa%c3%a7%c3%b5es%20Gerais%20-%20Direitos%20Credit%c3%b3rios%20Descontados%20-%20v2.0.0/attachments/DER_InvoiceFinancings_Payments-98fc0ede.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/invoiceFinancingsGetContractsContractIdPayments_v2.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/example/examples_invoice_financings_payments.csv)

##   
**Direitos Creditórios Descontados - Parcelas do Contrato**: (GET /invoice-financings/v2/contracts/{contractId}/scheduled-instalments)

**Visão Geral**

Obtém dados referentes às parcelas / prestações da operação de crédito de Direitos Creditórios Descontados contratadas

Tags: [Direito Creditório Descontado (Invoice Financing)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioDireitoCreditorioDescontado).

**Visão de alto de nível das estruturas de dados**
![att17375821](Informa%c3%a7%c3%b5es%20Gerais%20-%20Direitos%20Credit%c3%b3rios%20Descontados%20-%20v2.0.0/attachments/TLD_InvoiceFinancings_Instalments-77a8dcb2.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att17375824](Informa%c3%a7%c3%b5es%20Gerais%20-%20Direitos%20Credit%c3%b3rios%20Descontados%20-%20v2.0.0/attachments/DER_InvoiceFinancings-11ff0d5b.png)

- DER Lógico

![att17375827](Informa%c3%a7%c3%b5es%20Gerais%20-%20Direitos%20Credit%c3%b3rios%20Descontados%20-%20v2.0.0/attachments/DER_InvoiceFinancings_Instalments-cfaf8413.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/invoiceFinancingsGetContractsContractIdScheduledInstalments_v2.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/example/examples_invoice_financings_instalments.csv)

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17375735)