[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17373529)

**Visão Geral**

A API Financings viabiliza o compartilhamento de informações das Operações de Crédito do tipo Financiamento.

##   
**Financiamentos**: (GET /financings/v2/contracts)

**Visão Geral**

Obtém dados referentes à operação de crédito de Financiamentos

Tags: [CNPJ (CNPJ Number)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#CNPJ-%28CNPJ-Number%29), [CPF - Cadastro de Pessoa Física (CPF Number)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#CPF---Cadastro-de-Pessoa-F%C3%ADsica-%28CPF-Number%29) e [Financiamento (Financing)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Financiamento-%28Financing%29).

**Visão de alto de nível das estruturas de dados**
![att17373648](Informa%c3%a7%c3%b5es%20Gerais%20-%20Financiamento%20-%20v2.0.1/attachments/TLD_Financings_List-317a9f55.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att17373645](Informa%c3%a7%c3%b5es%20Gerais%20-%20Financiamento%20-%20v2.0.1/attachments/DER_Financings_List_Conceitual-78a6e363.png)

- DER Lógico

![att17373642](Informa%c3%a7%c3%b5es%20Gerais%20-%20Financiamento%20-%20v2.0.1/attachments/DER_Financings_List-c771a67f.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/financingsGetContracts_v2.csv)

[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/10059794/financingsGetContracts.csv?api=v2&amp;download=true)

##   
**Financiamentos - Contrato**: (GET /financings/v2/contracts/{contractId})

**Visão Geral**

Obtém dados referentes à identificação da operação de crédito de Financiamentos

Tags: [CNPJ (CNPJ Number)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#CNPJ-%28CNPJ-Number%29), [CPF - Cadastro de Pessoa Física (CPF Number)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#CPF---Cadastro-de-Pessoa-F%C3%ADsica-%28CPF-Number%29), [Custo Efetivo Total (CET)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Custo-Efetivo-Total-%28CET%29), [Encargo (Charge)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Encargo-%28Charge%29), [Ente Consignante (CnpjConsignee)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Ente-Consignante-%28CnpjConsignee%29), [Financiamento (Financing)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Financiamento-%28Financing%29), [Identificador Padronizado da Operação de Crédito – Ipoc Code](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Identificador-Padronizado-da-Opera%C3%A7%C3%A3o-de-Cr%C3%A9dito-%E2%80%93-Ipoc-Code), [Indexador (Indexer)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Indexador-%28Indexer%29), [Sistema de Amortização Constante (SAC)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Sistema-de-Amortiza%C3%A7%C3%A3o-Constante-%28SAC%29), [Sistema de Amortização Misto (SAM)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Sistema-de-Amortiza%C3%A7%C3%A3o-Misto-%28SAM%29), [Sistema Francês de Amortização (Price)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Sistema-Franc%C3%AAs-de-Amortiza%C3%A7%C3%A3o-%28Price%29), [Tarifa (Fee)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Tarifa-%28Fee%29), [Taxa Efetiva (EffectiveTax)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Taxa-Efetiva-%28EffectiveTax%29) e [Taxa nominal (NominalTax)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Taxa-nominal-%28NominalTax%29).

**Visão de alto de nível das estruturas de dados**
![att17373639](Informa%c3%a7%c3%b5es%20Gerais%20-%20Financiamento%20-%20v2.0.1/attachments/TLD_Financings_Contract-28e66d10.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att17373618](Informa%c3%a7%c3%b5es%20Gerais%20-%20Financiamento%20-%20v2.0.1/attachments/DER_Financings-d24aedd7.png)

- DER Lógico

![att17373636](Informa%c3%a7%c3%b5es%20Gerais%20-%20Financiamento%20-%20v2.0.1/attachments/DER_Financings_Contract-2dad086e.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/financingsGetContractsContractId_v2.csv)

[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/10059794/financingsGetContractsContractId.csv?api=v2&amp;download=true)

## **Financiamentos - Garantias do Contrato**: (GET /financings/v2/contracts/{contractId}/warranties)

**Visão Geral**

Obtém dados referentes às garantias que avalizam a operação de crédito de Financiamentos contratada

Tags: [Financiamento (Financing)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Financiamento-%28Financing%29), [Garantia (Warranty)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Garantia-%28Warranty%29) e [Sistema de Amortização Misto (SAM)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Sistema-de-Amortiza%C3%A7%C3%A3o-Misto-%28SAM%29).

**Visão de alto de nível das estruturas de dados**
![att17373633](Informa%c3%a7%c3%b5es%20Gerais%20-%20Financiamento%20-%20v2.0.1/attachments/TLD_Financings_Warranties-45815cdc.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att17373618](Informa%c3%a7%c3%b5es%20Gerais%20-%20Financiamento%20-%20v2.0.1/attachments/DER_Financings-d24aedd7.png)

- DER Lógico

![att17373630](Informa%c3%a7%c3%b5es%20Gerais%20-%20Financiamento%20-%20v2.0.1/attachments/DER_Financings_Warranties-d85bb514.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/financingsGetContractsContractIdWarranties_v2.csv)

[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/10059794/financingsGetContractsContractIdWarranties.csv?api=v2&amp;download=true)

##   
**Financiamentos - Pagamentos do Contrato**: (GET /financings/v2/contracts/{contractId}/payments)

**Visão Geral**

Obtém dados dos pagamentos referentes às operações de crédito de Financiamentos contratadas

Tags: [Encargo (Charge)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Encargo-%28Charge%29), [Financiamento (Financing)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Financiamento-%28Financing%29), [Identificador Padronizado da Operação de Crédito – Ipoc Code](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Identificador-Padronizado-da-Opera%C3%A7%C3%A3o-de-Cr%C3%A9dito-%E2%80%93-Ipoc-Code), [Saldo Devedor (Outstanding Balance)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Saldo-Devedor-%28Outstanding-Balance%29), [Sistema de Amortização Constante (SAC)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Sistema-de-Amortiza%C3%A7%C3%A3o-Constante-%28SAC%29), [Sistema de Amortização Misto (SAM)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Sistema-de-Amortiza%C3%A7%C3%A3o-Misto-%28SAM%29), [Sistema Francês de Amortização (Price)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Sistema-Franc%C3%AAs-de-Amortiza%C3%A7%C3%A3o-%28Price%29) e [Tarifa (Fee)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Tarifa-%28Fee%29).

**Visão de alto de nível das estruturas de dados**
![att17373627](Informa%c3%a7%c3%b5es%20Gerais%20-%20Financiamento%20-%20v2.0.1/attachments/TLD_Financings_Payments-38c034e2.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att17373618](Informa%c3%a7%c3%b5es%20Gerais%20-%20Financiamento%20-%20v2.0.1/attachments/DER_Financings-d24aedd7.png)

- DER Lógico

![att17373624](Informa%c3%a7%c3%b5es%20Gerais%20-%20Financiamento%20-%20v2.0.1/attachments/DER_Financings_Payments-e2f69311.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/financingsGetContractsContractIdPayments_v2.csv)

[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/10059794/financingsGetContractsContractIdPayments.csv?api=v2&amp;download=true)

##   
**Financiamentos - Parcelas do Contrato**: (GET /financings/v2/contracts/{contractId}/scheduled-instalments)

**Visão Geral**

Obtém dados referentes às parcelas / prestações da operação de crédito de Financiamentos contratadas

Tags: [Financiamento (Financing)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Financiamento-%28Financing%29) e [Prestação Regular (Instalment)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Presta%C3%A7%C3%A3o-Regular-%28Instalment%29).

**Visão de alto de nível das estruturas de dados**
![att17373621](Informa%c3%a7%c3%b5es%20Gerais%20-%20Financiamento%20-%20v2.0.1/attachments/TLD_Financings_Instalments-aaa0d467.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att17373618](Informa%c3%a7%c3%b5es%20Gerais%20-%20Financiamento%20-%20v2.0.1/attachments/DER_Financings-d24aedd7.png)

- DER Lógico

![att17373615](Informa%c3%a7%c3%b5es%20Gerais%20-%20Financiamento%20-%20v2.0.1/attachments/DER_Financings_Instalments-f7eb2f57.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/financingsGetContractsContractIdScheduledInstalments_v2.csv)

[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/10059794/financingsGetContractsContractIdScheduledInstalments.csv?api=v2&amp;download=true)

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17373529)