[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379670)

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

## API Loans

 GET /contracts

| **Campo** | **O que foi feito?** |
| --- | --- |
| data | Adicionando minItems |
| contractId | Alterado pattern  <br>Adicionado minLength |
| brandName | Alterada descrição |
| companyCnpj | Alterado pattern |
| productType | Removido maxLength |
| productSubType | Removido maxLength |
| ipocCode | Adicionado minLength  <br>Adicionado pattern |
| Swagger | Alterado texto em Orientações Gerais |
| Header | Adicionado campo pagination-key |
| Propriedade de extensibilidade | Removida a explicitude do additionalProperties |
| Response code | Alterado response Default |
| Response code | Adicionado status code 422 |
| Response code | Adicionado status code 423 |
| Response code | Adicionado status code 529 |

 GET /contracts/{contractId}

| **Campo** | **O que foi feito?** |
| --- | --- |
| amortizationScheduled | Removido maxLength |
| amortizationScheduledAdditionalInfo | Alterada descrição  <br>Alterado exemplo  <br>Alterado maxLength  <br>Alterada mandatoriedade |
| cnpjConsignee | Alterada descrição  <br>Adicionado Restrição  <br>Alterado pattern  <br>Alterada mandatoriedade |
| instalmentPeriodicity | Removido maxLength |
| instalmentPeriodicityAdditionalInfo | Alterada mandatoriedade  <br>Alterada descrição |
| productType | Removido maxLength |
| productSubType | Removido maxLength |
| contractAmount | Alterado para string  <br>Alterada descrição  <br>Alterado exemplo  <br>Alterado minLength  <br>Removido nullable   <br>Alterado pattern  <br>Alterada mandatoriedade |
| settlementDate | Alterado pattern  <br>Alterada descrição  <br>Alterada mandatoriedade |
| currency | Alterada mandatoriedade |
| dueDate | Alterada mandatoriedade  <br>Adicionado minLength  <br>Alterada descrição |
| firstInstalmentDueDate | Alterada descrição  <br>Alterada mandatoriedade |
| CET | Alterado para string com format double  <br>Alterada descrição  <br>Alterado exemplo  <br>Alterado maxLength  <br>Adicionado minLength  <br>Removido nullable  <br>Adicionado pattern  <br>Alterada mandatoriedade |
| contractNumber | Alterado pattern  <br>Adicionado minLength |
| ipocCode | Adicionado minLength  <br>Adicionado pattern |
| disbursementDates | Alterado nome para o plural  <br>Alterado para lista  <br>Alterada descrição |
| interestRates | Adicionado minItems  <br>Adicionada descrição |
| interestRates/calculation | Removido maxLength |
| interestRates/preFixedRate | Alterado para string com fotmat double  <br>Alterada descrição  <br>Alterado exemplo  <br>Alterado maxLength  <br>Adicionado minLength  <br>Removido nullable  <br>Adicionado pattern |
| interestRates/postFixedRate | Alterado para string com fotmat double  <br>Alterada descrição  <br>Alterado exemplo  <br>Alterado maxLength  <br>Adicionado minLength  <br>Removido nullable  <br>Adicionado pattern |
| interestRates/taxPeriodicity | Removido maxLength |
| interestRates/taxType | Removido maxLength |
| interestRates/interestRateType | Removido maxLength |
| interestRates/additionalInfo | Alterada mandatoriedade  <br>Adicionada restrição |
| interestRates/referentialRateIndexerType | Removido maxLength |
| interestRates/referentialRateIndexerSubType | Removido maxLength |
| contractedFees/feeAmount | Alterado para string com fotmat double  <br>Adicionada restrição  <br>Alterado exemplo  <br>Adicionado minLength  <br>Removido nullable  <br>Alterado pattern  <br>Alterada mandatoriedade |
| contractedFees/feeRate | Alterado para string  <br>Alterada descrição  <br>Alterado exemplo  <br>Alterado maxLength  <br>Adicionado minLength  <br>Removido nullable  <br>Adicionado pattern  <br>Alterada mandatoriedade |
| contractedFees/feeCharge | Removido maxLength |
| contractedFees/feeChargeType | Removido maxLength |
| contractedFees | Alterada descrição |
| contractedFinanceCharges/chargeRate | Alterado para string com fotmat double  <br>Alterada descrição  <br>Alterado exemplo  <br>Alterado maxLength  <br>Adicionado minLength  <br>Adicionado pattern |
| contractedFinanceCharges/chargeType | Removido maxLength |
| contractedFinanceCharges/chargeAdditionalInfo | Alterada descrição  <br>Adicionado maxLength  <br>Alterada mandatoriedade  <br>Alterado pattern |
| Header | Adicionado campo pagination-key |
| Propriedade de extensibilidade | Removida a explicitude do additionalProperties |
| Response code | Alterado Response Default |
| Response code | Adicionado status code 422 |
| Response code | Adicionado status code 423 |
| Response code | Adicionado status code 529 |

 GET /contracts/{contractId}/warranties

| **Campo** | **O que foi feito?** |
| --- | --- |
| data | Adicionado minItems |
| warrantyAmount | Alterado para string com format double  <br>Adicionado minLength  <br>Alterado pattern  <br>Alterada a descrição  <br>Alterada mandatoriedade |
| warrantySubType | Removido maxLength  <br> Adicionadas as opções:   <br>ACORDOS\_COMPENSACAO\_LIQUIDACAO\_OBRIGACOES”,   <br>”PROAGRO”, e   <br>“SEM\_SUB\_TIPO\_GARANTIA” |
| warrantyType | Removido maxLength   <br>Removida a opção doenum: “SEM\_TIPO\_GARANTIA” |
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
| balloonPayments | Alterada mandatoriedade  <br>Alterado mimItems  <br>Removido nullable |
| balloonPayments/amount | Convertido em objeto com os atributos amount e currency |
| balloonPayments/amount/amount | Atualizada a descrição |
| balloonPayments/dueDate | Adicionado minLength  <br>Removida mandatoriedade |
| contractRemainingNumber | Removido nullable  <br>Removido maxLength  <br>Adicionado maximum  <br>Alterada mandatoriedade  <br>Adicionada restrição |
| dueInstalments | Removido nullable  <br>Removido maxLength  <br>Maximum adicionado |
| paidInstalments | Removido nullable  <br>Removido maxLength  <br>Adicionado maximum |
| pastDueInstalments | Removido nullable  <br>Removido maxLength  <br>Maximum adicionado |
| totalNumberOfInstalments | Removido nullable  <br>Removido maxLength  <br>Adicionado maximum  <br>Alterada mandatoriedade  <br>Adicionada restrição |
| typeContractRemaining | Removido maxLength |
| typeNumberOfInstalments | Removido maxLength |
| pagination-key | Adicionado o campo no header. |
| Propriedade de extensibilidade | Removida a explicitude do additionalProperties |
| Response code | Alterado Response Default |
| Response code | Adicionado status code 422 |
| Response code | Adicionado status code 423 |
| Response code | Adicionado status code 529 |

 GET /contracts/{contractId}/payments

| **Campo** | **O que foi feito?** |
| --- | --- |
| chargeType | Removido maxLength |
| contractOutstandingBalance | Alterado para string com format double  <br>Alterado exemplo  <br>Alterado minLength  <br>Alterado pattern |
| paidInstalments | Removido maxLength  <br>Adicionado maximum  <br>Removido nullable  <br>Alterada mandatoriedade |
| releases | Adicionado minItems |
| releases/instalmentId | Alterado pattern  <br>Adicionado minLength |
| releases/overParcel | Adicionada restrição  <br>Alterada mandatoriedade |
| releases/overParcel/charges | Adicionado minItems |
| releases/overParcel/charges/chargeAdditionalInfo | Alterada mandatoriedade |
| releases/overParcel/charges/chargeAmount | Alterado para string com format double  <br>Alterado exemplo  <br>Alterado minLength  <br>Removido nullable  <br>Alterado pattern  <br>Alterada descrição |
| releases/overParcel/charges/chargeType | Removido maxLength |
| releases/overParcel/fees | Adicionado minItems |
| releases/overParcel/fees/feeAmount | Alterado para string  <br>Alterado format  <br>Alterado exemplo  <br>Alterado maxLength  <br>Alterado minLength  <br>Removido nullable  <br>Alterada descrição |
| releases/paidAmount | Alterado para string  <br>Alterada descrição  <br>Alterado exemplo  <br>Alterado minLength  <br>Alterado pattern |
| releases/overParcel/fees/feeCode | Alterada descrição |
| releases/overParcel/fees/feeName | Alterada descrição |
| releases/paymentId | Alterado pattern  <br>Adicionado minLength |
| Propriedade de extensibilidade | Removida a explicitude do additionalProperties |
| Header | Adicionado campo pagination-key |
| Response code | Alterado Response Default |
| Response code | Adicionado status code 422 |
| Response code | Adicionado status code 423 |
| Response code | Adicionado status code 529 |

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379670)