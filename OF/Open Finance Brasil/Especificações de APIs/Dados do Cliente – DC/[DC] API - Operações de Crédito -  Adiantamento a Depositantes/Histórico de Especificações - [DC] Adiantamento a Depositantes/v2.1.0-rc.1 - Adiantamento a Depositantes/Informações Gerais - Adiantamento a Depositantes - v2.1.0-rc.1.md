[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/157418188)

**Visão Geral**

A API Unarranged-accounts-overdraft viabiliza o compartilhamento de informações das Operações de Crédito do tipo Adiantamento a Depositantes.

## **Adiantamento a Depositantes**: (GET /unarranged-accounts-overdraft/v2/contracts)

**Visão Geral**

Obtém dados referentes à operação de crédito de Adiantamento a Depositantes

Tags: [Adiantamento a Depositante (Unarranged Account Overdraft)](https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/7996340/Gloss+rio#Adiantamento-a-Depositante-%28Unarranged-Account-Overdraft%29) e [Identificador padronizado da operação de crédito – Ipoc Code](https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/7996340/Gloss+rio#Identificador-Padronizado-da-Opera%C3%A7%C3%A3o-de-Cr%C3%A9dito-%E2%80%93-Ipoc-Code).

**Visão de alto de nível das estruturas de dados**
![att157418244](Informa%c3%a7%c3%b5es%20Gerais%20-%20Adiantamento%20a%20Depositantes%20-%20v2.1.0-rc.1/attachments/TLD_UnarrangedAccountsOverdraft_List-11e82848.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att157418247](Informa%c3%a7%c3%b5es%20Gerais%20-%20Adiantamento%20a%20Depositantes%20-%20v2.1.0-rc.1/attachments/DER_UnarrangedAccOverdraft_List_Conceitual-7cb78532.png)

- DER Lógico

![att157418250](Informa%c3%a7%c3%b5es%20Gerais%20-%20Adiantamento%20a%20Depositantes%20-%20v2.1.0-rc.1/attachments/DER_UnarrangedAccountOverdraft_List-62c962b2.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/unarrangedAccountsOverdraftGetContracts_v2.csv)

[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/9961672/unarrangedAccountsOverdraftGetContracts.csv?api=v2&amp;download=true)

##   
**Adiantamento a Depositantes - Contrato**: (GET /unarranged-accounts-overdraft/v2/contracts/{contractId})

**Visão Geral**

Obtém dados referentes à identificação da operação de crédito de Adiantamento a Depositantes

Tags: [Adiantamento a Depositante (Unarranged Account Overdraft)](https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/7996340/Gloss+rio#Adiantamento-a-Depositante-%28Unarranged-Account-Overdraft%29), [Custo Efetivo Total (CET)](https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/7996340/Gloss+rio#Custo-Efetivo-Total-%28CET%29), [Encargo (Charge)](https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/7996340/Gloss+rio#Encargo-%28Charge%29), [Identificador padronizado da operação de crédito – Ipoc Code](https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/7996340/Gloss+rio#Identificador-Padronizado-da-Opera%C3%A7%C3%A3o-de-Cr%C3%A9dito-%E2%80%93-Ipoc-Code), [Indexador (Indexer)](https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/7996340/Gloss+rio#Indexador-%28Indexer%29), [Sistema de Amortização Constante (SAC)](https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/7996340/Gloss+rio#Sistema-de-Amortiza%C3%A7%C3%A3o-Constante-%28SAC%29), [Sistema Francês de Amortização (Price)](https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/7996340/Gloss+rio#Sistema-Franc%C3%AAs-de-Amortiza%C3%A7%C3%A3o-%28Price%29), [Tarifa (Fee)](https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/7996340/Gloss+rio#Tarifa-%28Fee%29), [Taxa Efetiva (EffectiveTax)](https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/7996340/Gloss+rio#Taxa-Efetiva-%28EffectiveTax%29) e [Taxa nominal (NominalTax)](https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/7996340/Gloss+rio#Taxa-nominal-%28NominalTax%29).

**Visão de alto de nível das estruturas de dados**
![att157418253](Informa%c3%a7%c3%b5es%20Gerais%20-%20Adiantamento%20a%20Depositantes%20-%20v2.1.0-rc.1/attachments/TLD_UnarrangedAccountsOverdraft_Contract-b511db56.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att157418271](Informa%c3%a7%c3%b5es%20Gerais%20-%20Adiantamento%20a%20Depositantes%20-%20v2.1.0-rc.1/attachments/DER_UnarrangedAccountsOverdraft-1f5fe687.png)

- DER Lógico

![att157418256](Informa%c3%a7%c3%b5es%20Gerais%20-%20Adiantamento%20a%20Depositantes%20-%20v2.1.0-rc.1/attachments/DER_UnarrangedAccountsOverdraft_Contract-cf6c3b8d.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/unarrangedAccountsOverdraftGetContractsContractId_v2.csv)

[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/9961672/unarrangedAccountsOverdraftGetContractsContractId.csv?api=v2&amp;download=true)

## **Adiantamento a Depositantes - Garantias do Contrato**: (GET /unarranged-accounts-overdraft/v2/contracts/{contractId}/warranties)

**Visão Geral**

Obtém dados referentes às garantias que avalizam a operação de crédito de Adiantamento a Depositantes contratada

Tags: [Adiantamento a Depositante (Unarranged Account Overdraft)](https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/7996340/Gloss+rio#Adiantamento-a-Depositante-%28Unarranged-Account-Overdraft%29) e [Garantia (Warranty)](https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/7996340/Gloss+rio#Garantia-%28Warranty%29).

**Visão de alto de nível das estruturas de dados**
![att157418259](Informa%c3%a7%c3%b5es%20Gerais%20-%20Adiantamento%20a%20Depositantes%20-%20v2.1.0-rc.1/attachments/TLD_UnarrangedAccountsOverdraft_Warranties-9db6e796.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att157418271](Informa%c3%a7%c3%b5es%20Gerais%20-%20Adiantamento%20a%20Depositantes%20-%20v2.1.0-rc.1/attachments/DER_UnarrangedAccountsOverdraft-1f5fe687.png)

- DER Lógico

![att157418262](Informa%c3%a7%c3%b5es%20Gerais%20-%20Adiantamento%20a%20Depositantes%20-%20v2.1.0-rc.1/attachments/DER_UnarrangedAccountsOverdraft_Warranties-9ff37998.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/unarrangedAccountsOverdraftGetContractsContractIdWarranties_v2.csv)

[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/9961672/unarrangedAccountsOverdraftGetContractsContractIdWarranties.csv?api=v2&amp;download=true)  

## **Adiantamento a Depositantes - Pagamentos do Contrato**: (GET /unarranged-accounts-overdraft/v2/contracts/{contractId}/payments)

**Visão Geral**

Obtém dados dos pagamentos referentes às operações de crédito de Adiantamento a Depositantes contratadas

Tags: [Adiantamento a Depositante (Unarranged Account Overdraft)](https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/7996340/Gloss+rio#Adiantamento-a-Depositante-%28Unarranged-Account-Overdraft%29), [Encargo (Charge)](https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/7996340/Gloss+rio#Encargo-%28Charge%29), [Saldo Devedor (Outstanding Balance)](https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/7996340/Gloss+rio#Saldo-Devedor-%28Outstanding-Balance%29) e [Tarifa (Fee)](https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/7996340/Gloss+rio#Tarifa-%28Fee%29).

**Visão de alto de nível das estruturas de dados**
![att157418265](Informa%c3%a7%c3%b5es%20Gerais%20-%20Adiantamento%20a%20Depositantes%20-%20v2.1.0-rc.1/attachments/TLD_UnarrangedAccountsOverdraft_Payments-19ca5a52.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att157418271](Informa%c3%a7%c3%b5es%20Gerais%20-%20Adiantamento%20a%20Depositantes%20-%20v2.1.0-rc.1/attachments/DER_UnarrangedAccountsOverdraft-1f5fe687.png)

- DER Lógico

![att157418241](Informa%c3%a7%c3%b5es%20Gerais%20-%20Adiantamento%20a%20Depositantes%20-%20v2.1.0-rc.1/attachments/DER_UnarrangedAccountsOverdraft_Payments-f5bdbe9f.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/unarrangedAccountsOverdraftGetContractsContractIdPayments_v2.csv)

[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/9961672/unarrangedAccountsOverdraftGetContractsContractIdPayments.csv?api=v2&amp;download=true)

##   
**Adiantamento a Depositantes - Parcelas do Contrato**: (GET /unarranged-accounts-overdraft/v2/contracts/{contractId}/scheduled-instalments)

**Visão Geral**

Obtém dados referentes às parcelas / prestações da operação de crédito de Adiantamento a Depositantes contratadas

Tags: [Adiantamento a Depositante (Unarranged Account Overdraft)](https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/7996340/Gloss+rio#Adiantamento-a-Depositante-%28Unarranged-Account-Overdraft%29).

**Visão de alto de nível das estruturas de dados**
![att157418268](Informa%c3%a7%c3%b5es%20Gerais%20-%20Adiantamento%20a%20Depositantes%20-%20v2.1.0-rc.1/attachments/TLD_UnarrangedAccountsOverdraft_Instalments-13550441.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att157418271](Informa%c3%a7%c3%b5es%20Gerais%20-%20Adiantamento%20a%20Depositantes%20-%20v2.1.0-rc.1/attachments/DER_UnarrangedAccountsOverdraft-1f5fe687.png)

- DER Lógico

![att157418274](Informa%c3%a7%c3%b5es%20Gerais%20-%20Adiantamento%20a%20Depositantes%20-%20v2.1.0-rc.1/attachments/DER_UnarrangedAccountsOverdraft_Instalments-92c17364.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/unarrangedAccountsOverdraftGetContractsContractIdScheduledInstalments_v2.csv)

[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/9961672/unarrangedAccountsOverdraftGetContractsContractIdScheduledInstalments.csv?api=v2&amp;download=true)

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/157418188)