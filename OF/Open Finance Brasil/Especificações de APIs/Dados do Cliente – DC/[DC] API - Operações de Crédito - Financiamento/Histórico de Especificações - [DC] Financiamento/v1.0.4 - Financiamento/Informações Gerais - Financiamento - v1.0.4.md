[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17373895)

**Visão Geral**

A API Financings viabiliza o compartilhamento de informações das Operações de Crédito do tipo Financiamento.

##   
**Financiamentos**: (GET /financings/v1/contracts)

**Visão Geral**

Obtém dados referentes à operação de crédito de Financiamentos

Tags: [CNPJ (CNPJ Number)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioCNPJ), [CPF - Cadastro de Pessoa Física (CPF Number)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioCPF) e [Financiamento (Financing)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioFinanciamento).

**Visão de alto de nível das estruturas de dados**
![att17374002](Informa%c3%a7%c3%b5es%20Gerais%20-%20Financiamento%20-%20v1.0.4/attachments/TLD_Financings_List-317a9f55.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att17373999](Informa%c3%a7%c3%b5es%20Gerais%20-%20Financiamento%20-%20v1.0.4/attachments/DER_Financings_List_Conceitual-78a6e363.png)

- DER Lógico

![att17373996](Informa%c3%a7%c3%b5es%20Gerais%20-%20Financiamento%20-%20v1.0.4/attachments/DER_Financings_List-c771a67f.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/financingsGetContracts_v1.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/example/examples_financings_contract_list.csv)

##   
**Financiamentos - Contrato**: (GET /financings/v1/contracts/{contractId})

**Visão Geral**

Obtém dados referentes à identificação da operação de crédito de Financiamentos

Tags: [CNPJ (CNPJ Number)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioCNPJ), [CPF - Cadastro de Pessoa Física (CPF Number)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioCPF), [Custo Efetivo Total (CET)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioCET), [Encargo (Charge)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioEncargo), [Ente Consignante (CnpjConsignee)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioEnteConsignante), [Financiamento (Financing)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioFinanciamento), [Identificador Padronizado da Operação de Crédito – Ipoc Code](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioIPOC), [Indexador (Indexer)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioIndexador), [Sistema de Amortização Constante (SAC)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioSAC), [Sistema de Amortização Misto (SAM)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioSAM), [Sistema Francês de Amortização (Price)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioPrice), [Tarifa (Fee)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioTarifa), [Taxa Efetiva (EffectiveTax)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioTaxaEfetiva) e [Taxa nominal (NominalTax)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioTaxaNominal).

**Visão de alto de nível das estruturas de dados**
![att17373993](Informa%c3%a7%c3%b5es%20Gerais%20-%20Financiamento%20-%20v1.0.4/attachments/TLD_Financings_Contract-28e66d10.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att17373972](Informa%c3%a7%c3%b5es%20Gerais%20-%20Financiamento%20-%20v1.0.4/attachments/DER_Financings-d24aedd7.png)

- DER Lógico

![att17373990](Informa%c3%a7%c3%b5es%20Gerais%20-%20Financiamento%20-%20v1.0.4/attachments/DER_Financings_Contract-2dad086e.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/financingsGetContractsContractId_v1.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/example/examples_financings_contract.csv)

## **Financiamentos - Garantias do Contrato**: (GET /financings/v1/contracts/{contractId}/warranties)

**Visão Geral**

Obtém dados referentes às garantias que avalizam a operação de crédito de Financiamentos contratada

Tags: [Financiamento (Financing)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioFinanciamento), [Garantia (Warranty)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioGarantia) e [Sistema de Amortização Misto (SAM)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioSAM).

**Visão de alto de nível das estruturas de dados**
![att17373987](Informa%c3%a7%c3%b5es%20Gerais%20-%20Financiamento%20-%20v1.0.4/attachments/TLD_Financings_Warranties-45815cdc.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att17373972](Informa%c3%a7%c3%b5es%20Gerais%20-%20Financiamento%20-%20v1.0.4/attachments/DER_Financings-d24aedd7.png)

- DER Lógico

![att17373984](Informa%c3%a7%c3%b5es%20Gerais%20-%20Financiamento%20-%20v1.0.4/attachments/DER_Financings_Warranties-d85bb514.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/financingsGetContractsContractIdWarranties_v1.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/example/examples_financings_warranties.csv)

##   
**Financiamentos - Pagamentos do Contrato**: (GET /financings/v1/contracts/{contractId}/payments)

**Visão Geral**

Obtém dados dos pagamentos referentes às operações de crédito de Financiamentos contratadas

Tags: [Encargo (Charge)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioEncargo), [Financiamento (Financing)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioFinanciamento), [Identificador Padronizado da Operação de Crédito – Ipoc Code](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioIPOC), [Saldo Devedor (Outstanding Balance)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioSaldoDevedor), [Sistema de Amortização Constante (SAC)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioSAC), [Sistema de Amortização Misto (SAM)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioSAM), [Sistema Francês de Amortização (Price)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioPrice) e [Tarifa (Fee)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioTarifa).

**Visão de alto de nível das estruturas de dados**
![att17373981](Informa%c3%a7%c3%b5es%20Gerais%20-%20Financiamento%20-%20v1.0.4/attachments/TLD_Financings_Payments-38c034e2.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att17373972](Informa%c3%a7%c3%b5es%20Gerais%20-%20Financiamento%20-%20v1.0.4/attachments/DER_Financings-d24aedd7.png)

- DER Lógico

![att17373978](Informa%c3%a7%c3%b5es%20Gerais%20-%20Financiamento%20-%20v1.0.4/attachments/DER_Financings_Payments-e2f69311.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/financingsGetContractsContractIdPayments_v1.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/example/examples_financings_payments.csv)

##   
**Financiamentos - Parcelas do Contrato**: (GET /financings/v1/contracts/{contractId}/scheduled-instalments)

**Visão Geral**

Obtém dados referentes às parcelas / prestações da operação de crédito de Financiamentos contratadas

Tags: [Financiamento (Financing)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioFinanciamento) e [Prestação Regular (Instalment)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioPrestacaoRegular).

**Visão de alto de nível das estruturas de dados**
![att17373975](Informa%c3%a7%c3%b5es%20Gerais%20-%20Financiamento%20-%20v1.0.4/attachments/TLD_Financings_Instalments-aaa0d467.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att17373972](Informa%c3%a7%c3%b5es%20Gerais%20-%20Financiamento%20-%20v1.0.4/attachments/DER_Financings-d24aedd7.png)

- DER Lógico

![att17373969](Informa%c3%a7%c3%b5es%20Gerais%20-%20Financiamento%20-%20v1.0.4/attachments/DER_Financings_Instalments-f7eb2f57.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/financingsGetContractsContractIdScheduledInstalments_v1.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/example/examples_financings_scheduled_instalments.csv)

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17373895)