[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/207716505)

**Visão Geral**

A API Credit-cards-accounts viabiliza o compartilhamento dos dados de conta pós-paga(cartão de crédito), tais como limites, transações e faturas.

## **Lista de cartões de crédito:** (GET /credit-cards-accounts/v2/accounts)

**Visão Geral**

Método para obter a lista de contas de pagamento pós-paga mantidas pelo cliente na instituição transmissora e para as quais ele tenha fornecido consentimento

Tags: [Bandeira (Credit Card Network)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Bandeira-%28Credit-Card-Network%29), [Cartão Múltiplo (Multiple CreditCard)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Cart%C3%A3o-M%C3%BAltiplo-%28Multiple-CreditCard%29), [CNPJ (CNPJ Number)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#CNPJ-%28CNPJ-Number%29) e [Conta de pagamento pós-paga (Credit Card)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Conta-de-Pagamento-P%C3%B3s-paga-%28Credit-Card%29).

**Visão de alto de nível das estruturas de dados**
![att207716616](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Cart%c3%a3o%20de%20Cr%c3%a9dito%20-%20v2.1.0/attachments/TLD_CreditCardAccount_List-f5ed7649.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att207716613](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Cart%c3%a3o%20de%20Cr%c3%a9dito%20-%20v2.1.0/attachments/DER_CreditCardAccount_List_Conceitual-0e6048e1.png)

- DER Lógico

![att207716610](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Cart%c3%a3o%20de%20Cr%c3%a9dito%20-%20v2.1.0/attachments/DER_CreditCardAccount_List_Logico-e2ca0183.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/creditCardsGetAccounts_v2.csv)

[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/9863186/accounts.csv?api=v2&amp;download=true)

## **Identificação de cartão de crédito**: (GET /credit-cards-accounts/v2/accounts/{creditCardAccountId})

**Visão Geral**

Obtém dados relativos ao conjunto de informações referentes à identificação da conta de pagamento pós-paga

Tags: [Bandeira (Credit Card Network)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Bandeira-%28Credit-Card-Network%29), [Cartão Múltiplo (Multiple CreditCard)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Cart%C3%A3o-M%C3%BAltiplo-%28Multiple-CreditCard%29), [CNPJ (CNPJ Number)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#CNPJ-%28CNPJ-Number%29) e [Conta de pagamento pós-paga (Credit Card)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Conta-de-Pagamento-P%C3%B3s-paga-%28Credit-Card%29).

Visão de alto de nível das estruturas de dados
![att207716607](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Cart%c3%a3o%20de%20Cr%c3%a9dito%20-%20v2.1.0/attachments/TLD_CreditCardAccount_Identification-a9737a16.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att207716586](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Cart%c3%a3o%20de%20Cr%c3%a9dito%20-%20v2.1.0/attachments/DER_CreditCardAccount-62b49dec.png)

- DER Lógico

![att207716604](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Cart%c3%a3o%20de%20Cr%c3%a9dito%20-%20v2.1.0/attachments/DER_CreditCardAccount_Identification-c203839a.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/creditCardsGetAccountsCreditCardAccountId_v2.csv)

[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/9863186/accounts_creditCardAccountId.csv?api=v2&amp;download=true)

##   
**Limites de cartão de crédito**: ( GET /credit-cards-accounts/v2/accounts/{creditCardAccountId}/limits)

**Visão Geral**

Obtém dados dos limites: de Crédito Total e por Modalidade de Crédito relativos à conta de pagamento pós-paga.

Tags: [CNPJ (CNPJ Number)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#CNPJ-%28CNPJ-Number%29) e [Conta de pagamento pós-paga (Credit Card)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Conta-de-Pagamento-P%C3%B3s-paga-%28Credit-Card%29), [Empréstimo Cartão Consignado (Payroll Loan)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Empr%C3%A9stimo-Cart%C3%A3o-Consignado-%28Payroll-Loan%29) e [Limite Flexível (Flexible Limit)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Limite-Flex%C3%ADvel-%28Flexible-Limit%29).

**Visão de alto de nível das estruturas de dados**
![att207716601](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Cart%c3%a3o%20de%20Cr%c3%a9dito%20-%20v2.1.0/attachments/TLD_CreditCardAccount_Limits-da0b15b9.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att207716586](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Cart%c3%a3o%20de%20Cr%c3%a9dito%20-%20v2.1.0/attachments/DER_CreditCardAccount-62b49dec.png)

- DER Lógico

![att207716598](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Cart%c3%a3o%20de%20Cr%c3%a9dito%20-%20v2.1.0/attachments/DER_CreditCardAccount_Limits-a61a5c76.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/creditCardsGetAccountsCreditCardAccountIdLimits_v2.csv)

[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/9863186/accounts_creditCardAccountId_limits.csv?api=v2&amp;download=true)

## **Transações de cartão de crédito**: (GET /credit-cards-accounts/v2/accounts/{creditCardAccountId}/transactions)

**Visão Geral**

Obtém dados das transações relativas à conta de pagamento pós-paga.

Tags: [CNPJ (CNPJ Number)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#CNPJ-%28CNPJ-Number%29) e [Conta de pagamento pós-paga (Credit Card)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Conta-de-Pagamento-P%C3%B3s-paga-%28Credit-Card%29), [Crédito Rotativo (Overdraft)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Cr%C3%A9dito-Rotativo-%28Overdraft%29) e [MCC (Merchant Category Code)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#MCC-%28Merchant-Category-Code%29).

**Visão de alto de nível das estruturas de dados**
![att207716589](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Cart%c3%a3o%20de%20Cr%c3%a9dito%20-%20v2.1.0/attachments/TLD_CreditCardAccount_Transactions-30cd2d1e.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att207716586](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Cart%c3%a3o%20de%20Cr%c3%a9dito%20-%20v2.1.0/attachments/DER_CreditCardAccount-62b49dec.png)

- DER Lógico

![att207716583](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Cart%c3%a3o%20de%20Cr%c3%a9dito%20-%20v2.1.0/attachments/DER_CreditCardAccount_Transactions-3ec790c3.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/creditCardsGetAccountsCreditCardAccountIdTransactions_v2.csv)

[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/9863186/accounts_creditCardAccountId_transactions.csv?api=v2&amp;download=true)

## **Transações de cartão de crédito**: (GET /credit-cards-accounts/v2/accounts/{creditCardAccountId}/transactions-current)

**Visão Geral**

Obtém dados das transações relativas à conta de pagamento pós-paga.

Tags: [CNPJ (CNPJ Number)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#CNPJ-%28CNPJ-Number%29) e [Conta de pagamento pós-paga (Credit Card)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Conta-de-Pagamento-P%C3%B3s-paga-%28Credit-Card%29), [Crédito Rotativo (Overdraft)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Cr%C3%A9dito-Rotativo-%28Overdraft%29) e [MCC (Merchant Category Code)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#MCC-%28Merchant-Category-Code%29).

**Visão de alto de nível das estruturas de dados**
![att207716589](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Cart%c3%a3o%20de%20Cr%c3%a9dito%20-%20v2.1.0/attachments/TLD_CreditCardAccount_Transactions-30cd2d1e.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att207716586](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Cart%c3%a3o%20de%20Cr%c3%a9dito%20-%20v2.1.0/attachments/DER_CreditCardAccount-62b49dec.png)

- DER Lógico

![att207716583](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Cart%c3%a3o%20de%20Cr%c3%a9dito%20-%20v2.1.0/attachments/DER_CreditCardAccount_Transactions-3ec790c3.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/creditCardsGetAccountsCreditCardAccountIdTransactionsCurrent_v2.csv)

[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/9863186/accounts_creditCardAccountId_transactions_current.csv?api=v2&amp;download=true)

##   
**Fatura de Cartão de Crédito**: (GET /credit-cards-accounts/v2/accounts/{creditCardAccountId}/bills)

**Visão Geral**

Obtém dados referentes à fatura da conta de pagamento pós-paga.

Tags:[CNPJ (CNPJ Number)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#CNPJ-%28CNPJ-Number%29) e [Conta de pagamento pós-paga (Credit Card)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Conta-de-Pagamento-P%C3%B3s-paga-%28Credit-Card%29), [Crédito Rotativo (Overdraft)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Cr%C3%A9dito-Rotativo-%28Overdraft%29) e [Fatura (Bill)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Fatura-%28Bill%29).

Visão de alto de nível das estruturas de dados
![att207716595](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Cart%c3%a3o%20de%20Cr%c3%a9dito%20-%20v2.1.0/attachments/TLD_CreditCardAccount_Bill-18fa37a9.png)
DER - Diagramas de Entidade e Relacionamento

- DER Conceitual

![att207716586](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Cart%c3%a3o%20de%20Cr%c3%a9dito%20-%20v2.1.0/attachments/DER_CreditCardAccount-62b49dec.png)

- DER Lógico

![att207716592](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Cart%c3%a3o%20de%20Cr%c3%a9dito%20-%20v2.1.0/attachments/DER_CreditCardAccount_Bill-eafe4a52.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/creditCardsGetAccountsCreditCardAccountIdBills_v2.csv)

[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/9863186/accounts_creditCardAccountId_bills.csv?api=v2&amp;download=true)

## **Transações de cartão de crédito por fatura**: (GET /credit-cards-accounts/v2/accounts/{creditCardAccountId}/bills/{billId}/transactions)

**Visão Geral**

Obtém a lista de transações da conta identificada por creditCardAccountId e billId.

Tags: [CNPJ (CNPJ Number)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#CNPJ-%28CNPJ-Number%29) e [Conta de pagamento pós-paga (Credit Card)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Conta-de-Pagamento-P%C3%B3s-paga-%28Credit-Card%29), [Crédito Rotativo (Overdraft)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Cr%C3%A9dito-Rotativo-%28Overdraft%29) e [MCC (Merchant Category Code)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#MCC-%28Merchant-Category-Code%29).

**Visão de alto de nível das estruturas de dados**
![att207716589](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Cart%c3%a3o%20de%20Cr%c3%a9dito%20-%20v2.1.0/attachments/TLD_CreditCardAccount_Transactions-30cd2d1e.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att207716586](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Cart%c3%a3o%20de%20Cr%c3%a9dito%20-%20v2.1.0/attachments/DER_CreditCardAccount-62b49dec.png)

- DER Lógico

![att207716583](Informa%c3%a7%c3%b5es%20Gerais%20-%20[DC]%20Cart%c3%a3o%20de%20Cr%c3%a9dito%20-%20v2.1.0/attachments/DER_CreditCardAccount_Transactions-3ec790c3.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/creditCardsGetAccountsCreditCardAccountIdBillsBillIdTransactions_v2.csv)

[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/9863186/accounts_creditCardAccountId_bills_billId_transactions.csv?api=v2&amp;download=true)

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/207716505)