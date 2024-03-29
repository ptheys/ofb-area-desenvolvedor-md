[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17371584)

**Visão Geral**

A API Credit-cards-accounts viabiliza o compartilhamento dos dados de conta pós-paga(cartão de crédito), tais como limites, transações e faturas.

## **Lista de cartões de crédito:** (GET /credit-cards-accounts/v2/accounts)

**Visão Geral**

Método para obter a lista de contas de pagamento pós-paga mantidas pelo cliente na instituição transmissora e para as quais ele tenha fornecido consentimento

Tags: [Bandeira (Credit Card Network)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioBandeira), [Cartão Múltiplo (Multiple CreditCard)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioCartaoMultiplo), [CNPJ (CNPJ Number)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioCNPJ) e [Conta de pagamento pós-paga (Credit Card)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioContaPagamentoPosPaga).

**Visão de alto de nível das estruturas de dados**
![att17371643](Informa%c3%a7%c3%b5es%20Gerais%20-%20Cart%c3%a3o%20de%20Cr%c3%a9dito%20-%20v2.0.0/attachments/TLD_CreditCardAccount_List-f5ed7649.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att17371646](Informa%c3%a7%c3%b5es%20Gerais%20-%20Cart%c3%a3o%20de%20Cr%c3%a9dito%20-%20v2.0.0/attachments/DER_CreditCardAccount_List_Conceitual-0e6048e1.png)

- DER Lógico

![att17371649](Informa%c3%a7%c3%b5es%20Gerais%20-%20Cart%c3%a3o%20de%20Cr%c3%a9dito%20-%20v2.0.0/attachments/DER_CreditCardAccount_List_Logico-e2ca0183.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/creditCardsGetAccounts_v2.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/example/examples_credit_cards_accounts_list.csv)

## **Identificação de cartão de crédito**: (GET /credit-cards-accounts/v2/accounts/{creditCardAccountId})

**Visão Geral**

Obtém dados relativos ao conjunto de informações referentes à identificação da conta de pagamento pós-paga

Tags: [Bandeira (Credit Card Network)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioBandeira), [Cartão Múltiplo (Multiple CreditCard)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioCartaoMultiplo), [CNPJ (CNPJ Number)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioCNPJ) e [Conta de pagamento pós-paga (Credit Card)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioContaPagamentoPosPaga).

Visão de alto de nível das estruturas de dados
![att17371652](Informa%c3%a7%c3%b5es%20Gerais%20-%20Cart%c3%a3o%20de%20Cr%c3%a9dito%20-%20v2.0.0/attachments/TLD_CreditCardAccount_Identification-a9737a16.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att17371673](Informa%c3%a7%c3%b5es%20Gerais%20-%20Cart%c3%a3o%20de%20Cr%c3%a9dito%20-%20v2.0.0/attachments/DER_CreditCardAccount-62b49dec.png)

- DER Lógico

![att17371655](Informa%c3%a7%c3%b5es%20Gerais%20-%20Cart%c3%a3o%20de%20Cr%c3%a9dito%20-%20v2.0.0/attachments/DER_CreditCardAccount_Identification-c203839a.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/creditCardsGetAccountsCreditCardAccountId_v2.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/example/examples_credit_cards_accounts_identification.csv)

##   
**Limites de cartão de crédito**: ( GET /credit-cards-accounts/v2/accounts/{creditCardAccountId}/limits)

**Visão Geral**

Obtém dados dos limites: de Crédito Total e por Modalidade de Crédito relativos à conta de pagamento pós-paga.

Tags: [CNPJ (CNPJ Number)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioCNPJ), [Conta de pagamento pós-paga (Credit Card)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioContaPagamentoPosPaga), [Empréstimo Cartão Consignado (Payroll Loan)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioEmprestimoCartaoConsignado) e [Limite Flexível (Flexible Limit)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioLimiteFlexivel).

**Visão de alto de nível das estruturas de dados**
![att17371658](Informa%c3%a7%c3%b5es%20Gerais%20-%20Cart%c3%a3o%20de%20Cr%c3%a9dito%20-%20v2.0.0/attachments/TLD_CreditCardAccount_Limits-da0b15b9.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att17371673](Informa%c3%a7%c3%b5es%20Gerais%20-%20Cart%c3%a3o%20de%20Cr%c3%a9dito%20-%20v2.0.0/attachments/DER_CreditCardAccount-62b49dec.png)

- DER Lógico

![att17371661](Informa%c3%a7%c3%b5es%20Gerais%20-%20Cart%c3%a3o%20de%20Cr%c3%a9dito%20-%20v2.0.0/attachments/DER_CreditCardAccount_Limits-a61a5c76.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/creditCardsGetAccountsCreditCardAccountIdLimits_v2.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/example/examples_credit_cards_accounts_limits.csv)

## **Transações de cartão de crédito**: (GET /credit-cards-accounts/v2/accounts/{creditCardAccountId}/transactions)

**Visão Geral**

Obtém dados das transações relativas à conta de pagamento pós-paga.

Tags: [CNPJ (CNPJ Number)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioCNPJ), [Conta de pagamento pós-paga (Credit Card)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioContaPagamentoPosPaga), [Crédito Rotativo (Overdraft)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioCreditoRotativo) e [MCC (Merchant Category Code)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioMCC).

**Visão de alto de nível das estruturas de dados**
![att17371670](Informa%c3%a7%c3%b5es%20Gerais%20-%20Cart%c3%a3o%20de%20Cr%c3%a9dito%20-%20v2.0.0/attachments/TLD_CreditCardAccount_Transactions-30cd2d1e.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att17371673](Informa%c3%a7%c3%b5es%20Gerais%20-%20Cart%c3%a3o%20de%20Cr%c3%a9dito%20-%20v2.0.0/attachments/DER_CreditCardAccount-62b49dec.png)

- DER Lógico

![att17371676](Informa%c3%a7%c3%b5es%20Gerais%20-%20Cart%c3%a3o%20de%20Cr%c3%a9dito%20-%20v2.0.0/attachments/DER_CreditCardAccount_Transactions-3ec790c3.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/creditCardsGetAccountsCreditCardAccountIdTransactions_v2.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/example/examples_credit_cards_accounts_transactions.csv)

## **Transações de cartão de crédito**: (GET /credit-cards-accounts/v2/accounts/{creditCardAccountId}/transactions-current)

**Visão Geral**

Obtém dados das transações relativas à conta de pagamento pós-paga.

Tags: [CNPJ (CNPJ Number)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioCNPJ), [Conta de pagamento pós-paga (Credit Card)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioContaPagamentoPosPaga), [Crédito Rotativo (Overdraft)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioCreditoRotativo) e [MCC (Merchant Category Code)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioMCC).

**Visão de alto de nível das estruturas de dados**
![att17371670](Informa%c3%a7%c3%b5es%20Gerais%20-%20Cart%c3%a3o%20de%20Cr%c3%a9dito%20-%20v2.0.0/attachments/TLD_CreditCardAccount_Transactions-30cd2d1e.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att17371673](Informa%c3%a7%c3%b5es%20Gerais%20-%20Cart%c3%a3o%20de%20Cr%c3%a9dito%20-%20v2.0.0/attachments/DER_CreditCardAccount-62b49dec.png)

- DER Lógico

![att17371676](Informa%c3%a7%c3%b5es%20Gerais%20-%20Cart%c3%a3o%20de%20Cr%c3%a9dito%20-%20v2.0.0/attachments/DER_CreditCardAccount_Transactions-3ec790c3.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/accountsGetAccountsAccountIdTransactionsCurrent_v2.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/example/examples_credit_cards_accounts_transactions.csv)

##   
**Fatura de Cartão de Crédito**: (GET /credit-cards-accounts/v2/accounts/{creditCardAccountId}/bills)

**Visão Geral**

Obtém dados referentes à fatura da conta de pagamento pós-paga.

Tags: [CNPJ (CNPJ Number)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioCNPJ), [Conta de pagamento pós-paga (Credit Card)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioContaPagamentoPosPaga), [Crédito Rotativo (Overdraft)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioCreditoRotativo) e [Fatura (Bill)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioFatura).

Visão de alto de nível das estruturas de dados
![att17371664](Informa%c3%a7%c3%b5es%20Gerais%20-%20Cart%c3%a3o%20de%20Cr%c3%a9dito%20-%20v2.0.0/attachments/TLD_CreditCardAccount_Bill-18fa37a9.png)
DER - Diagramas de Entidade e Relacionamento

- DER Conceitual

![att17371673](Informa%c3%a7%c3%b5es%20Gerais%20-%20Cart%c3%a3o%20de%20Cr%c3%a9dito%20-%20v2.0.0/attachments/DER_CreditCardAccount-62b49dec.png)

- DER Lógico

![att17371667](Informa%c3%a7%c3%b5es%20Gerais%20-%20Cart%c3%a3o%20de%20Cr%c3%a9dito%20-%20v2.0.0/attachments/DER_CreditCardAccount_Bill-eafe4a52.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/creditCardsGetAccountsCreditCardAccountIdBills_v2.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/example/examples_credit_cards_accounts_bill.csv)

## **Transações de cartão de crédito por fatura**: (GET /credit-cards-accounts/v2/accounts/{creditCardAccountId}/bills/{billId}/transactions)

**Visão Geral**

Obtém a lista de transações da conta identificada por creditCardAccountId e billId.

Tags: [CNPJ (CNPJ Number)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioCNPJ), [Conta de pagamento pós-paga (Credit Card)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioContaPagamentoPosPaga), [Crédito Rotativo (Overdraft)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioCreditoRotativo) e [MCC (Merchant Category Code)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioMCC).

**Visão de alto de nível das estruturas de dados**
![att17371670](Informa%c3%a7%c3%b5es%20Gerais%20-%20Cart%c3%a3o%20de%20Cr%c3%a9dito%20-%20v2.0.0/attachments/TLD_CreditCardAccount_Transactions-30cd2d1e.png)
**DER - Diagramas de Entidade e Relacionamento**

- DER Conceitual

![att17371673](Informa%c3%a7%c3%b5es%20Gerais%20-%20Cart%c3%a3o%20de%20Cr%c3%a9dito%20-%20v2.0.0/attachments/DER_CreditCardAccount-62b49dec.png)

- DER Lógico

![att17371676](Informa%c3%a7%c3%b5es%20Gerais%20-%20Cart%c3%a3o%20de%20Cr%c3%a9dito%20-%20v2.0.0/attachments/DER_CreditCardAccount_Transactions-3ec790c3.png)

**Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/creditCardsGetAccountsCreditCardAccountIdBillsBillIdTransactions_v2.csv)

[Fazer download dos exemplos](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/example/examples_credit_cards_accounts_transactions.csv)

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17371584)