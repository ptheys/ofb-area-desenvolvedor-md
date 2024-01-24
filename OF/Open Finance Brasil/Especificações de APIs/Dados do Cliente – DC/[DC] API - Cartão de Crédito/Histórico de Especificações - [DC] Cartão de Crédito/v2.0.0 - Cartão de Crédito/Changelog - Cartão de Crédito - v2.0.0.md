[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379514)

#### **Descrição macro das alterações aplicadas às APIs de Dados Cadastrais e Transacionais em relação aos payloads:**

- Nenhum campo poderá receber o valor NA. Seguem regras de acordo com os casos:

    - Obrigatórios: foram revistas as mandatoriedades a fim de atender as regras de negócios de cada um dos produtos;
    - Opcionais: para estes casos basta não enviar o campo;
    - Condicionais: se comportam como opcionais, exceto quando o cenário se encaixar na restrição incluída na descrição;
    - Enums: Retiradas as opções com valor NAO\_APLICA e similares;
    - Removidos todos os atributos Nullable dos campos, que foram analisados obedecendo critérios de mandatoriedade e cenários de negócio.
- Com o objetivo de normalizar o formato dos dados entre as pontas, foram acrescentados patterns em todos os campos elegíveis.
- Foram normalizados os atributos dos campos de acordo com o seu tipo de dado.
- Todas as ocorrências de campos *additionalInfo *foram alteradas para opcional ou condicional de acordo com suas características de negócio. Para os campos condicionais foram acrescentadas restrições de cenário de uso.
- Foram alterados todos os campos numéricos do tipo double para string com format double, com isso garantimos que exista um formato de dados padrão, tornando possível que todas as casas, considerando suas peculiaridades sistêmicas, consigam realizar o tráfego das informações.
- Revista a mandatoriedade dos arrays, considerando os seguintes cenários:

    - Obrigatórios, passam a receber minItems: 0. Considerando que caso as informações não existam, o array precisa ser enviado vazio. Nesse cenário atendemos ao conjunto de informações relativas a um produto, onde um cenário específico não pode ser atendido mesmo existindo como característica do produto, é como quem está enviando dizer “não tenho essa informação para este produto”.
    - Opcionais e condicionais, passam a receber minItems: 1. Caso não exista a informação basta não enviar o array, existindo, deve ser preenchido pelo menos 1.
- Inserção e remoção de campos atendendo às especificidades de cada produto (API).
- Removidos os campos totalPages e totalRecords dos exemplos de response codes de exceção.
- Adicionados novos response codes.

 GET /accounts

| **Campo** | **O que foi feito?** |
| --- | --- |
| brandName | Alterada descrição do campo |
| companyCnpj | Alterado pattern |
| productType | Removido maxLength |
| creditCardNetwork | Removido maxLength |
| networkAdditionalInfo | Alterado exemplo |
| networkAdditionalInfo | Alterado o exemplo |
| creditCardAccountId | Alterado o pattern<br><br>Adicionado minLength |
| Header | Adicionado campo pagination-key |
| Propriedade de extensibilidade | Removida a explicitude do additionalProperties |
| Response code | Alterado response Default |
| Response code | Adicionado o status code 422 |
| Response code | Adicionado o status code 423 |
| Response code | Adicionado o status code 529 |

 GET /accounts/{creditCardAccountId}

| **Campo** | **O que foi feito?** |
| --- | --- |
| productType | Removido maxLength |
| creditCardNetwork | Removido maxLength |
| networkAdditionalInfo | Alterado o exemplo |
| identificationNumber | Alterado o pattern  <br>Adicionado minLength |
| paymentMethod | Adicionada descrição |
| Propriedade de extensibilidade | Removida a explicitude do additionalProperties |
| Response code | Alterado response Default |
| Response code | Adicionado o status code 422 |
| Response code | Adicionado o status code 423 |
| Response code | Adicionado o status code 529 |

 GET /accounts/{creditCardAccountId}/bills

| **Campo** | **O que foi feito?** |
| --- | --- |
| data | Adicionado minItems |
| billTotalAmount | Convertido em objeto com os atributos amount e currency  <br>Alterada descrição |
| billTotalAmountCurrency | Removido campo |
| billMinimumAmountCurrency | Removido campo |
| billTotalAmount/amount | Alterada descrição   <br>Alterado pattern |
| data/billMinimumAmount | Convertido em objeto com os atributos amount e currency  <br>MaxLength alterado |
| financeCharges | Alterada mandatoriedade |
| data/financeCharges/type | Removido maxLength  <br>Removida opção “SEM\_ENCARGO“ |
| data/financeCharges/amount | Alterado pattern  <br>Alterado descrição   <br>Nullable removido  <br>Alterado para string  <br>Alterado exemplo  <br>Alterado minLength  <br>Alterado maxLength |
| payments/amount | Alterado pattern  <br>Alterada a descrição  <br>Alterado para string  <br>Alterado exemplo  <br>Alterado minLength |
| data/payments/valueType | Removido maxLength  <br>Alterada descrição |
| data/payments/paymentMode | Removido maxLength |
| billId | Alterado o pattern  <br>Adicionado minLength |
| Swagger | Alterado texto em Orientações Gerais |
| Swagger | Alterada descrição do endpoint |
| Header | Adicionado campo pagination-key |
| Propriedade de extensibilidade | Removida a explicitude do additionalProperties |
| Response code | Alterado response Default |
| Response code | Adicionado o status code 422 |
| Response code | Adicionado o status code 423 |
| Response code | Adicionado o status code 529 |

 GET /accounts/{creditCardAccountId}/bills/{billId}/transactions

| **Campo** | **O que foi feito?** |
| --- | --- |
| data | Adicionado minItems |
| lineName | Removido campo |
| creditDebitType | Removido maxLength |
| transactionType | Removido maxLength |
| transactionalAdditionalInfo | Pattern adicionado |
| transactionDate | Alterado pattern |
| paymentType | Removido maxLength  <br>Alterada descrição |
| feeType | Removido maxLength  <br>Alterada mandatoriedade  <br>Adicionada restrição |
| feeTypeAdditionalInfo | Alterada mandatoriedade  <br>Pattern adicionado |
| otherCreditsType | Removido maxLength  <br>Alterada mandatoriedade |
| otherCreditsAdditionalInfo | Pattern adicionado  <br>Alterada mandatoriedade  <br>Adicionado restrição |
| chargeNumber | Removido maxLength  <br>Nullable removido  <br>Alterada mandatoriedade  <br>Adicionada restrição  <br>Alterado exemplo  <br>Adicionado maximum |
| brazilianAmount | Convertido em objeto com os atributos amount e currency  <br>Alterada descrição  <br>Alterada mandatoriedade |
| brazilianAmount/amount | Alterado maxLength  <br>Alterado minLength  <br>Alterado exemplo  <br>Alterado format para double |
| amount | Convertido em objeto com os atributos amount e currency  <br>Alterada descrição  <br>Alterada mandatoriedade |
| amount/amount | Alterado maxLength  <br>Alterado minLength  <br>Alterado example  <br>Alterado format para double |
| currency | Removido campo |
| billPostDate | Alterado pattern |
| payeeMCC | Removido nullable  <br>Removido maxLength  <br>Adicionado maximum  <br>Alterada mandatoriedade |
| links/last | Removido campo |
| transactionId | Alterado pattern<br><br>Adicionado minLength |
| identificationNumber | Alterado pattern<br><br>Adicionado minLength |
| billId | Alterado pattern<br><br>Adicionado minLength |
| Swagger | Alterado texto em Orientações Gerais |
| Swagger | Alterada descrição do endpoint |
| Header | Adicionado campo pagination-key |
| Propriedade de extensibilidade | Removida a explicitude do additionalProperties |
| Response code | Alterado response Default |
| Response code | Adicionado o status code 422 |
| Response code | Adicionado o status code 423 |
| Response code | Adicionado o status code 529 |

 GET /accounts/{creditCardAccountId}/limits

| **Campo** | **O que foi feito?** |
| --- | --- |
| data | Alterada mandatoriedade  <br>Adicionado minItems |
| creditLineLimitType | Alterada descrição  <br>Removido maxLength |
| consolidationType | Alterada descrição  <br>Removido maxLength |
| lineName | Removido maxLength |
| lineNameAdditionalInfo | Adicionado maxLength |
| limitAmount | Convertido em objeto com os atributos amount e currency  <br>Alterada descrição  <br>Alterada mandatoriedade |
| limitAmount/amount | Alterado para string com format double  <br>Alterada descrição  <br>Alterada mandatoriedade  <br>Adicionada restrição  <br>Alterado pattern  <br>Alterado minLength  <br>Alterado exemplo  <br>Removido nullable |
| limitAmount/currency | Alterado pattern  <br>Alterada descrição  <br>Adicionada restrição |
| limitAmountCurrency | Removido campo |
| usedAmount | Convertido em objeto com os atributos amount e currency  <br>Alterada descrição  <br>Alterada mandatoriedade |
| usedAmount/amount | Alterado para string com format double  <br>Alterada descrição  <br>Alterado pattern  <br>Alterado minLength  <br>Alterado maxLength  <br>Alterado exemplo  <br>Removido nullable |
| usedAmount/currency | Alterado pattern |
| usedAmountCurrency | Removido campo |
| availableAmount | Convertido em objeto com os atributos amount e currency  <br>Alterada descrição  <br>Alterada mandatoriedade |
| availableAmount/amount | Alterado para string com format double  <br>Alterada mandatoriedade  <br>Adicionada restrição  <br>Alterado minLength  <br>Alterado maxLength  <br>Alterado exemplo  <br>Removido nullable |
| availableAmount/currency | Alterado pattern  <br>Alterada mandatoriedade  <br>Adicionada restrição |
| availableAmountCurrency | Removido campo |
| identificationNumber | Alterado pattern  <br>Adicionado minLength |
| Propriedade de extensibilidade | Removida a explicitude do additionalProperties |
| Response code | Alterado response Default |
| Response code | Adicionado o status code 422 |
| Response code | Adicionado o status code 423 |
| Response code | Adicionado o status code 529 |

 GET /accounts/{creditCardAccountId}/transactions

| **Campo** | **O que foi feito?** |
| --- | --- |
| data | Alterado minItems |
| lineName | Removido campo |
| creditDebitType | Removido maxLength |
| transactionType | Removido maxLength |
| transactionalAdditionalInfo | Pattern adicionado  <br>Alterada mandatoriedade |
| paymentType | Removido maxLength  <br>Alterada descrição |
| feeType | Removido maxLength  <br>Alterada mandatoriedade  <br>Adicionada restrição |
| feeTypeAdditionalInfo | Pattern adicionado  <br>Alterada mandatoriedade |
| otherCreditsType | Removido maxLength  <br>Alterada mandatoriedade  <br>Adicionada restrição |
| otherCreditsAdditionalInfo | Pattern adicionado  <br>Alterada mandatoriedade  <br>Adicionado restrição  <br>Alterada descrição |
| chargeNumber | Alterada mandatoriedade  <br>Adicionado restrição  <br>Maximum adicionado  <br>Nullable removido   <br>Removido maxLength  <br>Alterado exemplo |
| brazilianAmount | Convertido em objeto com os atributos amount e currency |
| brazilianAmount/amount | Alterada descrição |
| brazilianAmount/currency | Alterada descrição |
| amount | Convertido em objeto com os atributos amount e currency |
| amount/amount | Alterada descrição |
| currency | Removido campo |
| transactionDate | Alterado pattern |
| billPostDate | Alterado pattern |
| payeeMCC | Removido de nullable  <br>Removido maxLength  <br>Adicionado maximum  <br>Alterada mandatoriedade |
| transactionId | Alterado de pattern  <br>Adicionado minLength |
| identificationNumber | Alterado pattern  <br>Adicionado minLength |
| billId | Alterado pattern  <br>Adicionado minLength |
| links/last | Removido campo |
| meta/totalRecords | Removido campo |
| meta/totalPages | Removido campo |
| Swagger | Alterada descrição do endpoint |
| Swagger | Alterado texto em Orientações Gerais |
| Header | Adicionado campo pagination-key |
| Header | Adicionada restrição em fromTransactionDate |
| Header | Adicionada restrição em toTransactionDate |
| Propriedade de extensibilidade | Removida a explicitude do additionalProperties |
| Response code | Alterado response Default |
| Response code | Adicionado o status code 422 |
| Response code | Adicionado o status code 423 |
| Response code | Adicionado o status code 529 |

 GET /accounts/{creditCardAccountId}/transactions-current

| **Campo** | **O que foi feito?** |
| --- | --- |
| Novo endpoint | Novo endpoint |

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379514)