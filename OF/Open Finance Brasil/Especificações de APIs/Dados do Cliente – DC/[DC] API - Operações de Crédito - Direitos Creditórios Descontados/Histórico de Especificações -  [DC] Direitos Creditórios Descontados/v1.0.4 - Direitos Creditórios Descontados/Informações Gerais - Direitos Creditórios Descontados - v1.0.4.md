[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17375570)

Visão Geral

A API Invoice-financings viabiliza o compartilhamento de informações das Operações de Crédito do tipo Direitos Creditórios Descontados.

## **Direitos Creditórios Descontados**: (GET /invoice-financings/v1/contracts)

**Visão Geral**

Conjunto de informações de contratos de direitos creditórios descontados mantidos pelo cliente na instituição transmissora e para os quais ele tenha fornecido consentimento

Tags: [Direito Creditório Descontado (Invoice Financing)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioDireitoCreditorioDescontado) e[Identificador padronizado da operação de crédito – Ipoc Code](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioIPOC).

**Visão de alto de nível das estruturas de dados**
![att17375665](Informa%c3%a7%c3%b5es%20Gerais%20-%20Direitos%20Credit%c3%b3rios%20Descontados%20-%20v1.0.4/attachments/TLD_InvoiceFinancings_List-36daf724.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att17375662](Informa%c3%a7%c3%b5es%20Gerais%20-%20Direitos%20Credit%c3%b3rios%20Descontados%20-%20v1.0.4/attachments/DER_InvoiceFinancings_List_Conceitual-cbb2adbb.png)

- DER Lógico

![att17375659](Informa%c3%a7%c3%b5es%20Gerais%20-%20Direitos%20Credit%c3%b3rios%20Descontados%20-%20v1.0.4/attachments/DER_InvoiceFinancings_List-c771a67f.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/invoiceFinancingsGetContracts_v1.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/example/examples_invoice_financings_contract_list.csv)

## **Direitos Creditórios Descontados - Contrato**: (GET /invoice-financings/v1/contracts/{contractId})

**Visão Geral**

Obtém dados referentes à identificação da operação de crédito de Direitos Creditórios Descontados

Tags: [Custo Efetivo Total (CET)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioCET), [Direito Creditório Descontado (Invoice Financing)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioDireitoCreditorioDescontado), [Encargo (Charge)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioEncargo), [Ente Consignante (CnpjConsignee)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioEnteConsignante), [Identificador padronizado da operação de crédito – Ipoc Code](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioIPOC), [Indexador (Indexer)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioIndexador), [Tarifa (Fee)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioTarifa), [Taxa Efetiva (EffectiveTax)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioTaxaEfetiva) e [Taxa nominal (NominalTax)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioTaxaNominal).

**Visão de alto de nível das estruturas de dados**
![att17375656](Informa%c3%a7%c3%b5es%20Gerais%20-%20Direitos%20Credit%c3%b3rios%20Descontados%20-%20v1.0.4/attachments/TLD_InvoiceFinancings_Contract-c63c2a6b.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att17375635](Informa%c3%a7%c3%b5es%20Gerais%20-%20Direitos%20Credit%c3%b3rios%20Descontados%20-%20v1.0.4/attachments/DER_InvoiceFinancings-11ff0d5b.png)

- DER Lógico

![att17375653](Informa%c3%a7%c3%b5es%20Gerais%20-%20Direitos%20Credit%c3%b3rios%20Descontados%20-%20v1.0.4/attachments/DER_InvoiceFinancings_Contract-c0c084b4.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/invoiceFinancingsGetContractsContractId_v1.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/example/examples_invoice_financings_contract.csv)

## **Direitos Creditórios Descontados - Garantias do Contrato**: (GET /invoice-financings/v1/contracts/{contractId}/warranties)

**Visão Geral**

Obtém dados referentes às garantias que avalizam a operação de crédito de Direitos Creditórios Descontados contratada

Tags: [Direito Creditório Descontado (Invoice Financing)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioDireitoCreditorioDescontado) e [Garantia (Warranty)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioGarantia).

**Visão de alto de nível das estruturas de dados**
![att17375650](Informa%c3%a7%c3%b5es%20Gerais%20-%20Direitos%20Credit%c3%b3rios%20Descontados%20-%20v1.0.4/attachments/TLD_InvoiceFinancings_Warranties-09b45d1c.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att17375635](Informa%c3%a7%c3%b5es%20Gerais%20-%20Direitos%20Credit%c3%b3rios%20Descontados%20-%20v1.0.4/attachments/DER_InvoiceFinancings-11ff0d5b.png)

- DER Lógico

![att17375647](Informa%c3%a7%c3%b5es%20Gerais%20-%20Direitos%20Credit%c3%b3rios%20Descontados%20-%20v1.0.4/attachments/DER_InvoiceFinancings_Warranties-f69e122e.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/invoiceFinancingsGetContractsContractIdWarranties_v1.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/example/examples_invoice_financings_warranties.csv)

## **Direitos Creditórios Descontados - Pagamentos do Contrato**: (GET /invoice-financings/v1/contracts/{contractId}/payments)

**Visão Geral**

Obtém dados dos pagamentos referentes às operações de crédito de Direitos Creditórios Descontados contratadas

Tags: [Direito Creditório Descontado (Invoice Financing)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioDireitoCreditorioDescontado), [Encargo (Charge)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioEncargo), [Saldo Devedor (Outstanding Balance)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioSaldoDevedor) e [Tarifa (Fee)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioTarifa).

**Visão de alto de nível das estruturas de dados**
![att17375644](Informa%c3%a7%c3%b5es%20Gerais%20-%20Direitos%20Credit%c3%b3rios%20Descontados%20-%20v1.0.4/attachments/TLD_InvoiceFinancings_Payments-b8984bfa.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att17375635](Informa%c3%a7%c3%b5es%20Gerais%20-%20Direitos%20Credit%c3%b3rios%20Descontados%20-%20v1.0.4/attachments/DER_InvoiceFinancings-11ff0d5b.png)

- DER Lógico

![att17375641](Informa%c3%a7%c3%b5es%20Gerais%20-%20Direitos%20Credit%c3%b3rios%20Descontados%20-%20v1.0.4/attachments/DER_InvoiceFinancings_Payments-98fc0ede.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/invoiceFinancingsGetContractsContractIdPayments_v1.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/example/examples_invoice_financings_payments.csv)

##   
**Direitos Creditórios Descontados - Parcelas do Contrato**: (GET /invoice-financings/v1/contracts/{contractId}/scheduled-instalments)

**Visão Geral**

Obtém dados referentes às parcelas / prestações da operação de crédito de Direitos Creditórios Descontados contratadas

Tags: [Direito Creditório Descontado (Invoice Financing)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioDireitoCreditorioDescontado).

**Visão de alto de nível das estruturas de dados**
![att17375638](Informa%c3%a7%c3%b5es%20Gerais%20-%20Direitos%20Credit%c3%b3rios%20Descontados%20-%20v1.0.4/attachments/TLD_InvoiceFinancings_Instalments-77a8dcb2.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att17375635](Informa%c3%a7%c3%b5es%20Gerais%20-%20Direitos%20Credit%c3%b3rios%20Descontados%20-%20v1.0.4/attachments/DER_InvoiceFinancings-11ff0d5b.png)

- DER Lógico

![att17375632](Informa%c3%a7%c3%b5es%20Gerais%20-%20Direitos%20Credit%c3%b3rios%20Descontados%20-%20v1.0.4/attachments/DER_InvoiceFinancings_Instalments-cfaf8413.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/invoiceFinancingsGetContractsContractIdScheduledInstalments_v1.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/example/examples_invoice_financings_instalments.csv)

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17375570)