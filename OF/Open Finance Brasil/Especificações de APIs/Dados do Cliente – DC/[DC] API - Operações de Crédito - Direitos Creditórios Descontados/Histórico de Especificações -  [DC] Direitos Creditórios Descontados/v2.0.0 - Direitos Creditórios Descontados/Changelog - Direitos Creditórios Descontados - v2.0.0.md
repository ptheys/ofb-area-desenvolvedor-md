[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379631)

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

## API Invoice-financings

 GET /contracts

| **Campo** | **O que foi feito?** |
| --- | --- |
| data | Adicionado minItems |
| contractId | Alterado pattern  <br>Adicionado minLength |
| brandName | Alterada descrição |
| companyCnpj | Alterado pattern |
| productType | Removido maxLength |
| productSubType | Removido maxLength |
| ipocCode | Adicionado minLength  <br>Adicionado pattern |
| Swagger | Alterado texto em Orientações Gerais |
| Header | Adicionado campo pagination-key |
| Propriedade de extensibilidade | Removida a explicitude do additionalProperties |
| Response code | Alterado Response Default |
| Response code | Adicionado status code 422 |
| Response code | Adicionado status code 423 |
| Response code | Adicionado status code 529 |

 GET /contracts/{contractId}

| **Campo** | **O que foi feito?** |
| --- | --- |
| amortizationScheduled | Removido maxLength |
| amortizationScheduledAdditionalInfo | Alterada mandatoriedade  <br>Alterado maxLength  <br>Removida restrição  <br>Alterado exemplo |
| calculation | Removido maxLength |
| CET | Alterada mandatoriedade  <br>Alterado para string  <br>Alterado maxLength  <br>Adicionado minLength  <br>Alterado exemplo  <br>Adicionado pattern  <br>Alterada descrição  <br>Removido Nullable |
| contractAmount | Alterado minLength  <br>Alterado maxLength  <br>Alterado pattern  <br>Alterada mandatoriedade  <br>Alterada descrição  <br>Removido nullable  <br>Alterado exemplo  <br>Alterado para string |
| contractedFees/feeAmount | Alterada mandatoriedade  <br>Adicionada restrição  <br>Alterado maxLength  <br>Adicionado minLength  <br>Alterado exemplo  <br>Alterado para string  <br>Alterado pattern  <br>Removido Nullable |
| contractedFees/feeCharge | Removido maxLength |
| contractedFees/feeChargeType | Removido maxLength |
| contractedFees/feeName | Alterado pattern  <br>Adicionado minLength  <br>Alterada descrição |
| contractedFees/feeCode | Alterado pattern  <br>Adicionado minLength  <br>Alterada descrição |
| contractedFees/feeRate | Alterado para string  <br>Adicionado pattern  <br>Adicionado minLength  <br>Alterado maxLength  <br>Alterado exemplo  <br>Alterada descrição  <br>Alterada mandatoriedade  <br>Removido Nullable |
| contractedFinanceCharges/chargeAdditionalInfo | Alterada mandatoriedade  <br>Adicionado maxLength  <br>Alterada descrição |
| contractedFinanceCharges/chargeRate | Alterado para string  <br>Adicionado pattern  <br>Adicionado minLength  <br>Alterado maxLength  <br>Alterado exemplo  <br>Alterada descrição |
| contractedFinanceCharges/chargeType | Removido maxLength |
| contractNumber | Adicionado pattern |
| currency | Alterada mandatoriedade |
| disbursementDates | Alterado nome para o plural  <br>Alterado para lista  <br>Alterada descrição |
| dueDate | Alterada mandatoriedade  <br>Alterado maxLength  <br>Adicionado minLength |
| firstInstalmentDueDate | Alterada mandatoriedade  <br>Adicionado minLength  <br>Alterada descrição |
| instalmentPeriodicity | Removido maxLength |
| instalmentPeriodicityAdditionalInfo | Alterada mandatoriedade  <br>Removido restrição |
| interestRates | Adicionado minItems  <br>Adicionada descrição |
| interestRates/additionalInfo | Alterada mandatoriedade  <br>Adicionada restrição |
| interestRates/calculation | Removido maxLength |
| interestRates/interestRateType | Removido maxLength |
| interestRates/postFixedRate | Alterada mandatoriedade  <br>Alterado para string  <br>Alterado maxLength  <br>Adicionado minLength  <br>Alterado exemplo  <br>Alterada descrição  <br>Removido Nullable  <br>Adicionado pattern |
| interestRates/preFixedRate | Alterada mandatoriedade  <br>Alterado para string  <br>Alterado maxLength  <br>Adicionado minLength  <br>Alterado exemplo  <br>Alterada descrição  <br>Removido Nullable  <br>Adicionado pattern |
| interestRates/referentialRateIndexerType | Removido maxLength |
| interestRates/referentialRateIndexerSubType | Removido maxLength |
| interestRates/taxPeriodicity | Removido maxLength |
| interestRates/taxType | Removido maxLength |
| ipocCode | Adicionado minLength  <br>Adicionado pattern |
| productType | Removido maxLength |
| productSubType | Removido maxLength |
| settlementDate | Alterada mandatoriedade  <br>Alterado pattern |
| Propriedade de extensibilidade | Removida a explicitude do additionalProperties |
| Response code | Alterado Response Default |
| Response code | Adicionado status code 422 |
| Response code | Adicionado status code 423 |
| Response code | Adicionado status code 529 |

 GET /contracts/{contractId}/warranties

| **Campo** | **O que foi feito?** |
| --- | --- |
| data | Adicionado minItems |
| warrantyAmount | Alterada mandatoriedade  <br>Alterado para string  <br>Alterado pattern  <br>Alterado minLength  <br>Alterada descrição  <br>Alterado exemplo |
| warrantyType | Removido maxLength  <br>Removido o seguinte itens no enum:  <br>SEM\_TIPO\_GARANTIA |
| warrantySubType | Removido maxLength  <br>Adicionado os seguintes itens no enum: ACORDOS\_COMPENSACAO\_LIQUIDACAO\_OBRIGACOES, PROAGRO, SEM\_SUB\_TIPO\_GARANTIA |
| currency | Alterada mandatoriedade |
| Header | Adicionado campo pagination-key |
| Propriedade de extensibilidade | Removida a explicitude do additionalProperties |
| Response code | Alterado Response Default |
| Response code | Adicionado status code 422 |
| Response code | Adicionado status code 423 |
| Response code | Adicionado status code 529 |

 GET /contracts/{contractId}/scheduled-instalments

| **Campo** | **O que foi feito?** |
| --- | --- |
| balloonPayments | Alterada mandatoriedade  <br>Alterado minItems  <br>Removido Nullable |
| balloonPayments/amount | Convertido em objeto com os atributos amount e currency  <br>Alterada descrição |
| balloonPayments/amount/currency | Movido para dentro do objeto balloonPayments/amount |
| balloonPayments/dueDate | Alterada mandatoriedade  <br>Adicionado minLength |
| contractRemainingNumber | Alterada mandatoriedade  <br>Adicionada restrição  <br>Removido maxLength  <br>Adicionado maximum  <br>Adicionada descrição  <br>Removido Nullable |
| dueInstalments | Removido Nullable  <br>Removido maxLength  <br>Adicionado maximum |
| paidInstalments | Removido Nullable  <br>Removido maxLength  <br>Adicionado maximum |
| pastDueInstalments | Removido Nullable  <br>Removido maxLength  <br>Adicionado maximum |
| totalNumberOfInstalments | Alterada mandatoriedade  <br>Adicionada restrição  <br>Removido maxLength  <br>Adicionado maximum  <br>Removido Nullable |
| typeContractRemaining | Removido maxLength |
| typeNumberOfInstalments | Removido maxLength |
| Header | Adicionado campo pagination-key |
| Propriedade de extensibilidade | Removida a explicitude do additionalProperties |
| Response code | Alterado Response Default |
| Response code | Adicionado status code 422 |
| Response code | Adicionado status code 423 |
| Response code | Adicionado status code 529 |

 GET /contracts/{contractId}/payments

| **Campo** | **O que foi feito?** |
| --- | --- |
| contractOutstandingBalance | Alterado para string  <br>Alterado pattern  <br>Alterado minLength  <br>Alterado exemplo |
| paidInstalments | Removido maxLength  <br>Adicionado maximum  <br>Nullable removido  <br>Alterada mandatoriedade |
| releases | Adicionado minItems |
| releases/overParcel | Alterada mandatoriedade  <br>Adicionada restrição |
| releases/overParcel/charges/ | Adicionado minItems |
| releases/overParcel/charges/chargeAdditionalInfo | Alterada mandatoriedade  <br>Alterada descrição  <br>Adicionado Restrição |
| releases/overParcel/charges/chargeAmount | Alterado para string  <br>Alterado pattern  <br>Alterado minLength  <br>Alterado exemplo  <br>Alterada descrição  <br>Removido Nullable |
| releases/overParcel/charges/chargeType | Removido maxLength  <br>Alterada descrição |
| releases/overParcel/fees | Adicionado minItems |
| releases/overParcel/fees/feeAmount | Alterado minLength  <br>Alterada  descrição  <br>Alterado para string  <br>Alterado pattern  <br>Removido Nullable  <br>Alterado exemplo |
| releases/overParcel/fees/feeCode | Adicionado minLength  <br>Alterado pattern |
| releases/overParcel/fees/feeName | Adicionado minLength  <br>Alterado pattern |
| releases/paidAmount | Alterado para string  <br>Alterado pattern  <br>Alterado minLength  <br>Alterada descrição  <br>Alterado exemplo |
| Header | Adicionado campo pagination-key |
| Propriedade de extensibilidade | Removida a explicitude do additionalProperties |
| Response code | Alterado Response Default |
| Response code | Adicionado status code 422 |
| Response code | Adicionado status code 423 |
| Response code | Adicionado status code 529 |

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379631)