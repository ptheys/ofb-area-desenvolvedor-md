[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/207716940)

**Visão Geral**

A API Loans viabiliza o compartilhamento de informações das Operações de Crédito do tipo Empréstimo.

## **Empréstimos**: (GET /loans/v2/contracts)

**Visão Geral**

Obtém a lista de contratos de empréstimos mantidos pelos clientes da instituição transmissora.

Tags: [CNPJ (CNPJ Number)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#CNPJ-%28CNPJ-Number%29), [Custo Efetivo Total (CET)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Custo-Efetivo-Total-%28CET%29), [Empréstimo (Loan)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Empr%C3%A9stimo-%28Loan%29), [Encargo (Charge)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Encargo-%28Charge%29), [Ente Consignante (CnpjConsignee)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Ente-Consignante-%28CnpjConsignee%29), [Identificador padronizado da operação de crédito – Ipoc Code](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Identificador-Padronizado-da-Opera%C3%A7%C3%A3o-de-Cr%C3%A9dito-%E2%80%93-Ipoc-Code), [Indexador (Indexer)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Indexador-%28Indexer%29), [Sistema de Amortização Constante (SAC)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Sistema-de-Amortiza%C3%A7%C3%A3o-Constante-%28SAC%29), [Sistema Francês de Amortização (Price)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Sistema-Franc%C3%AAs-de-Amortiza%C3%A7%C3%A3o-%28Price%29), [Tarifa (Fee)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Tarifa-%28Fee%29), [Taxa Efetiva (EffectiveTax)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Taxa-Efetiva-%28EffectiveTax%29) e [Taxa nominal (NominalTax)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Taxa-nominal-%28NominalTax%29).

**Visão de alto de nível das estruturas de dados**
![att207717004](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Empr%c3%a9stimos%20-%20v2.1.0/attachments/TLD_Loans_List-2dca2a73.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att207717007](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Empr%c3%a9stimos%20-%20v2.1.0/attachments/DER_Loans_List_Conceitual-1a77830e.png)

- DER Lógico

![att207717010](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Empr%c3%a9stimos%20-%20v2.1.0/attachments/DER_Loans_List_Logico-b44dc150.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/loansGetContracts_v2.csv)

[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/9961490/loansGetContracts.csv?api=v2&amp;download=true)

##   
**Empréstimos - Contrato**: (GET /loans/v2/contracts/{contractId})

**Visão Geral**

Obtém dados referentes à identificação da operação de crédito de Empréstimos

Tags: [CNPJ (CNPJ Number)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#CNPJ-%28CNPJ-Number%29), [Custo Efetivo Total (CET)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Custo-Efetivo-Total-%28CET%29), [Empréstimo (Loan)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Empr%C3%A9stimo-%28Loan%29), [Encargo (Charge)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Encargo-%28Charge%29), [Ente Consignante (CnpjConsignee)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Ente-Consignante-%28CnpjConsignee%29), [Identificador padronizado da operação de crédito – Ipoc Code](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Identificador-Padronizado-da-Opera%C3%A7%C3%A3o-de-Cr%C3%A9dito-%E2%80%93-Ipoc-Code), [Indexador (Indexer)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Indexador-%28Indexer%29), [Sistema de Amortização Constante (SAC)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Sistema-de-Amortiza%C3%A7%C3%A3o-Constante-%28SAC%29), [Sistema Francês de Amortização (Price)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Sistema-Franc%C3%AAs-de-Amortiza%C3%A7%C3%A3o-%28Price%29), [Tarifa (Fee)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Tarifa-%28Fee%29), [Taxa Efetiva (EffectiveTax)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Taxa-Efetiva-%28EffectiveTax%29) e [Taxa nominal (NominalTax)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Taxa-nominal-%28NominalTax%29).

**Visão de alto de nível das estruturas de dados**
![att207717013](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Empr%c3%a9stimos%20-%20v2.1.0/attachments/TLD_Loans_Contract-fad2d027.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att207717043](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Empr%c3%a9stimos%20-%20v2.1.0/attachments/DER_Loans-14b4a0b8.png)

- DER Lógico

![att207717016](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Empr%c3%a9stimos%20-%20v2.1.0/attachments/DER_Loans_Contract-a02d96d4.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/loansGetContractsContractId_v2.csv)

[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/9961490/loansGetContractsContractId.csv?api=v2&amp;download=true)

## **Empréstimos - Garantias do Contrato**: (GET /loans/v2/contracts/{contractId}/warranties)

**Visão Geral**

Obtém dados referentes às garantias que avalizam a operação de crédito de Empréstimos contratada

Tags: [Empréstimo (Loan)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Empr%C3%A9stimo-%28Loan%29) e [Garantia (Warranty)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Garantia-%28Warranty%29).

**Visão de alto de nível das estruturas de dados**
![att207717019](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Empr%c3%a9stimos%20-%20v2.1.0/attachments/TLD_Loans_Warranties-9d79de56.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att207717043](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Empr%c3%a9stimos%20-%20v2.1.0/attachments/DER_Loans-14b4a0b8.png)

- DER Lógico

![att207717022](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Empr%c3%a9stimos%20-%20v2.1.0/attachments/DER_Loans_Warranties-fa9fed2b.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/loansGetContractsContractIdWarranties_v2.csv)

[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/9961490/loansGetContractsContractIdWarranties.csv?api=v2&amp;download=true)

## **Empréstimos - Pagamentos do Contrato**: (GET /loans/v2/contracts/{contractId}/payments)

**Visão Geral**

Obtém dados dos pagamentos referentes às operações de crédito de Empréstimos contratadas

Tags: [Empréstimo (Loan)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Empr%C3%A9stimo-%28Loan%29), [Encargo (Charge)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Encargo-%28Charge%29), [Saldo Devedor (Outstanding Balance)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Saldo-Devedor-%28Outstanding-Balance%29) e [Tarifa (Fee)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Tarifa-%28Fee%29).

**Visão de alto de nível das estruturas de dados**
![att207717025](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Empr%c3%a9stimos%20-%20v2.1.0/attachments/TLD_Loans_Payments-d4bed1ea.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att207717043](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Empr%c3%a9stimos%20-%20v2.1.0/attachments/DER_Loans-14b4a0b8.png)

- DER Lógico

![att207717001](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Empr%c3%a9stimos%20-%20v2.1.0/attachments/123.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/loansGetContractsContractIdPayments_v2.csv)

[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/9961490/loansGetContractsContractIdPayments.csv?api=v2&amp;download=true)

## **Empréstimos - Parcelas do Contrato**: (GET /loans/v2/contracts/{contractId}/scheduled-instalments)

**Visão Geral**

Obtém dados referentes às parcelas / prestações da operação de crédito de Empréstimos contratadas

Tags: [Empréstimo (Loan)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Empr%C3%A9stimo-%28Loan%29) e [Prestação Regular (Instalment)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Presta%C3%A7%C3%A3o-Regular-%28Instalment%29).

**Visão de alto de nível das estruturas de dados**
![att207717040](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Empr%c3%a9stimos%20-%20v2.1.0/attachments/TLD_Loans_Instalments-6076accf.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att207717043](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Empr%c3%a9stimos%20-%20v2.1.0/attachments/DER_Loans-14b4a0b8.png)
- DER Lógico

![att207717046](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Empr%c3%a9stimos%20-%20v2.1.0/attachments/DER_Loans_Instalments-a5bde7e6.png)
**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/loansGetContractsContractIdScheduledInstalments_v2.csv)

[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/9961490/loansGetContractsContractIdScheduledInstalments.csv?api=v2&amp;download=true)

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/207716940)