[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379748)

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

## API Unarranged-accounts-overdraft

 GET /contracts

| **Campo** | **O que foi feito?** |
| --- | --- |
| data | Alterado minItems |
| contractId | Alterado pattern  <br>Adicionado minLength |
| brandName | Alterada descrição |
| companyCnpj | Alterado pattern |
| productType | Removido maxLength |
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
| amortizationScheduledAdditionalInfo | Alterado maxLength  <br>Alterado exemplo  <br>Alterada descrição |
| contractNumber | Adicionado pattern  <br>Adicionado minLength |
| ipocCode | Adicionado minLength  <br>Adicionado pattern  <br>Alterada descrição |
| productName | Alterada descrição |
| productType | Removido maxLength |
| disbursementDates | Alterado nome para o plural  <br>Alterado para lista  <br>Alterada descrição |
| settlementDate | Alterada mandatoriedade  <br>Removido restrição  <br>Alterado pattern |
| instalmentPeriodicity | Removido maxLength |
| instalmentPeriodicityAdditionalInfo | Alterada descrição |
| contractAmount | Alterada mandatoriedade  <br>Atualizada descrição  <br>Alterado para string  <br>Removido format  <br>Alterado maxLength  <br>Alterado minLength  <br>Alterado exemplo  <br>Removido nullable |
| currency | Alterada mandatoriedade |
| dueDate | Alterada mandatoriedade  <br>Adicionado minLength |
| firstInstalmentDueDate | Alterada mandatoriedade  <br>Adicionado minLength |
| CET | Adicionado pattern  <br>Alterado maxLength   <br>Adicionado minLength  <br>Alterada mandatoriedade  <br>Alterado para string  <br>Alterada descrição  <br>Removido nullable  <br>Adicionado format  <br>Alterado exemplo |
| interestRates | Adicionado minItems  <br>Adicionada descrição |
| interestRates/taxType | Removido maxLength |
| interestRates/interestRateType | Removido maxLength |
| interestRates/taxPeriodicity | Removido maxLength |
| interestRates/calculation | Removido maxLength |
| interestRates/referentialRateIndexerType | Removido maxLength |
| interestRates/referentialRateIndexerSubType | Removido maxLength |
| interestRates/preFixedRate | Alterado para string  <br>Alterado maxLength  <br>Alterado minLength  <br>Alterado exemplo  <br>Adicionado format  <br>Alterada descrição  <br>Removido nullable |
| interestRates/postFixedRate | Alterado para string  <br>Alterado maxLength  <br>Alterado minLength   <br>Alterado exemplo  <br>Adicionado format  <br>Alterada descrição |
| interestRates/additionalInfo | Alterada mandatoriedade<br><br>Adicionada restrição |
| contractedFees/feeChargeType | Removido maxLength |
| contractedFees/feeCharge | Removido maxLength |
| contractedFees/feeAmount | Alterada mandatoriedade  <br>Adicionada restrição  <br>Alterado para string  <br>Alterada descrição  <br>Alterado pattern  <br>Removido nullable  <br>Alterado exemplo  <br>Adicionado minLength |
| contractedFees/feeRate | Alterado para string  <br>Alterado pattern  <br>Alterado maxLength   <br>Alterado minLength   <br>Alterado exemplo  <br>Atualizada descrição  <br>Alterada mandatoriedade  <br>Removido nullable |
| contractedFinanceCharges/chargeType | Removido maxLength |
| contractedFinanceCharges/chargeAdditionalInfo | Alterada mandatoriedade<br><br>Adicionada restrição |
| contractedFinanceCharges/chargeRate | Alterado tipo para: string com format double  <br>Adicionado pattern  <br>Alterado maxLength  <br>Adicionado minLength  <br>Alterado exemplo  <br>Atualizada descrição |
| Propriedade de extensibilidade | Removida a explicitude do additionalProperties |
| Response code | Alterado Response Default |
| Response code | Adicionado status code 422 |
| Response code | Adicionado status code 423 |
| Response code | Adicionado status code 529 |

 GET /contracts/{contractId}/warranties

| **Campo** | **O que foi feito?** |
| --- | --- |
| data | Adicionado minItems |
| currency | Alterada mandatoriedade |
| warrantyType | Removido maxLength  <br>Removido opção SEM\_TIPO\_GARANTIA do enum |
| warrantySubType | Removido maxLength  <br>Adicionadas as opções no enum: ACORDOS\_COMPENSACAO\_LIQUIDACAO\_OBRIGACOES. PROAGRO, SEM\_SUB\_TIPO\_GARANTIA |
| warrantyAmount | Alterado maxLength  <br>Alterado minLength  <br>Alterada descrição  <br>Alterada mandatoriedade  <br>Alterado para string  <br>Removido format  <br>Alterado exemplo |
| Header | Adicionado campo pagination-key |
| Propriedade de extensibilidade | Removida a explicitude do additionalProperties |
| Response code | Alterado Response Default |
| Response code | Adicionado status code 422 |
| Response code | Adicionado status code 423 |
| Response code | Adicionado status code 529 |

 GET /contracts/{contractId}/sheduled-instalments

| **Campo** | **O que foi feito?** |
| --- | --- |
| typeNumberOfInstalments | Removido maxLength |
| totalNumberOfInstalments | Removido maxLength  <br>Adicionado maximum  <br>Removido nullable   <br>Alterada mandatoriedade  <br>Adicionada restrição |
| typeContractRemaining | Removido maxLength |
| contractRemainingNumber | Removido maxLength  <br>Adicionado maximum  <br>Adicionada restrição  <br>Alterada mandatoriedade  <br>Removido nullable  <br>Alterado exemplo |
| paidInstalments | Removido maxLength  <br>Adicionado maximum  <br>Removido nullable |
| dueInstalments | Removido maxLength  <br>Adicionado maximum  <br>Removido nullable |
| pastDueInstalments | Removido maxLength  <br>Adicionado maximum  <br>Removido nullable |
| balloonPayments | Adicionado minItems  <br>Removido nullable  <br>Alterada mandatoriedade |
| balloonPayments/dueDate | Alterada mandatoriedade |
| balloonPayments/amount | Convertido em objeto com os atributos amount e currency  <br>Alterada descrição |
| balloonPayments/currency | Removido campo deste nível |
| Propriedade de extensibilidade | Removida a explicitude do additionalProperties |
| Response code | Alterado Response Default |
| Response code | Adicionado status code 422 |
| Response code | Adicionado status code 423 |
| Response code | Adicionado status code 529 |

 GET /contracts/{contractId}/payments

| **Campo** | **O que foi feito?** |
| --- | --- |
| paidInstalments | Removido maxLength  <br>Adicionado maximum  <br>Removido nullable  <br>Alterada mandatoriedade |
| contractOutstandingBalance | Alterado minLength  <br>Alterado maxLength  <br>Alterado para string  <br>Removido format  <br>Alterado exemplo |
| releases | Adicionado mimItems |
| releases/paidAmount | Alterado para string  <br>Alterado maxLength  <br>Alterado minLength  <br>Alterada descrição  <br>Removido format  <br>Alterado exemplo |
| releases/overParcel | Alterada mandatoriedade  <br>Adicionada restrição |
| releases/overParcel/fees | Adicionado mimItems |
| releases/overParcel/fees/feeCode | Alterada descrição |
| releases/overParcel/fees/feeAmount | Removido Restrição   <br>Alterado maxLength   <br>Alterado minLength  <br>Alterada descrição  <br>Alterado para string  <br>Removido format  <br>Removido nullable  <br>Alterado exemplo |
| releases/overParcel/charges/ | Adicionado mimItems |
| releases/overParcel/charges/chargeType | Removido maxLength |
| releases/overParcel/charges/chargeAdditionalInfo | Alterada mandatoriedade |
| releases/overParcel/charges/chargeAmount | Removido nullable  <br>Alterada descrição  <br>Alterado para string  <br>Alterado maxLength  <br>Alterado minLength  <br>Removido format  <br>Alterado exemplo |
| releases/paymentId | Alterado pattern  <br>Adicionado minLength |
| releases/instalmentId | Alterado pattern  <br>Adicionado minLength |
| Header | Adicionado o campo pagination-key |
| Propriedade de extensibilidade | Removida a explicitude do additionalProperties |
| Response code | Alterado Response Default |
| Response code | Adicionado status code 422 |
| Response code | Adicionado status code 423 |
| Response code | Adicionado status code 529 |

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379748)