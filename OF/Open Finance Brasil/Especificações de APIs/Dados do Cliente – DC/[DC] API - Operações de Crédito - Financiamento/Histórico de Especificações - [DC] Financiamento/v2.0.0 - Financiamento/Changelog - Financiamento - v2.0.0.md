[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379592)

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

## API Financings

 GET /contracts

| **Campo** | **O que foi feito?** |
| --- | --- |
| data | Adicionado minItems |
| contractId | Alterado pattern |
| brandName | Alterada descrição |
| companyCnpj | Alterado pattern |
| productType | Removido maxLength |
| productSubType | Removido maxLength |
| ipocCode | Adicionado minLength  <br>Adicionado pattern |
| Swagger | Alterado texto em Orientações Gerais |
| Header | Adicionado campo pagination-key |
| Propriedade de extensibilidade | Removida a explicitude do additionalProperties |
| Response code | Alterado response Default |
| Response code | Adicionado o status code 422 |
| Response code | Adicionado o status code 423 |
| Response code | Adicionado o status code 529 |

 GET /contracts/{contractId}

| **Campo** | **O que foi feito?** |
| --- | --- |
| amortizationScheduled | Removido maxLength |
| contractNumber | Adicionado do pattern |
| ipocCode | Adicionado minLength  <br>Adicionado pattern |
| productType | Removido maxLength |
| productSubType | Removido maxLength |
| disbursementDates | Alterado nome para o plural  <br>Alterado para lista  <br>Alterada descrição |
| settlementDate | Alterada descrição   <br>Alterado pattern  <br>Alterada mandatoriedade |
| contractAmount | Alterado para string com format double  <br>Alterada mandatoriedade  <br>Alterada descrição   <br>Alterado pattern  <br>Alterado minLength  <br>Alterado exemplo   <br>Removido nullable |
| currency | Alterada mandatoriedade |
| dueDate | Alterada mandatoriedade |
| instalmentPeriodicity | Removido maxLength |
| instalmentPeriodicityAdditionalInfo | Alterada a descrição  <br>Alterada mandatoriedade  <br>Adicionada restrição |
| firstInstalmentDueDate | Alterada mandatoriedade |
| CET | Alterado para string com format double  <br>Alterada descrição   <br>Alterada mandatoriedade  <br>Alterado maxLength  <br>Adicionado minLength  <br>Removido nullable  <br>Adicionado pattern  <br>Alterado exemplo |
| amortizationScheduled | Removido maxLength |
| amortizationScheduledAdditionalInfo | Alterada mandatoriedade  <br>Alterado maxLength  <br>Alterado exemplo  <br>Alterada descrição |
| interestRates | Adicionado minItems  <br>Removido maxLength  <br>Adicionada descrição |
| interestRates/taxType | Removido maxLength |
| interestRates/interestRateType | Removido maxLength |
| interestRates/taxPeriodicity | Removido maxLength |
| interestRates/calculation | Removido maxLength |
| interestRates/referentialRateIndexerType | Removido maxLength |
| interestRates/referentialRateIndexerSubType | Removido maxLength |
| interestRates/preFixedRate | Alterado para string com format double  <br>Alterada a descrição  <br>Alterado exemplo  <br>Alterado maxLength  <br>Adicionado minLength  <br>Removido nullable  <br>Adicionado pattern  <br>Alterada mandatoriedade |
| interestRates/postFixedRate | Alterado para string com format double  <br>Alterada a descrição  <br>Alterado exemplo  <br>Alterado maxLength  <br>Adicionado minLength  <br>Removido nullable  <br>Adicionado pattern  <br>Alterada mandatoriedade |
| interestRates/additionalInfo | Alterada descrição  <br>Alterada mandatoriedade  <br>Adicionada restrição |
| contractedFees | Adicionada descrição |
| contractedFees/feeChargeType | Removido maxLength |
| contractedFees/feeCharge | Removido maxLength |
| contractedFees/feeAmount | Alterado para string com format double  <br>Alterada a descrição  <br>Alterado exemplo  <br>Alterado minLength  <br>Removido maxLength  <br>Removido nullable  <br>Alterado pattern  <br>Alterada mandatoriedade |
| contractedFees/feeRate | Alterado para string com format double  <br>Alterada a descrição  <br>Alterado exemplo  <br>Alterado maxLength  <br>Adicionado minLength  <br>Removido nullable  <br>Adicionado pattern  <br>Alterada mandatoriedade |
| contractedFinanceCharges/chargeType | Removido maxLength |
| contractedFinanceCharges/chargeAdditionalInfo | Alterada mandatoriedade  <br>Adicionado maxLength  <br>Alterada descrição  <br>Alterado pattern |
| contractedFinanceCharges/chargeRate | Alterado para string com format double  <br>Alterada a descrição  <br>Alterado exemplo  <br>Alterado maxLength  <br>Adicionado minLength  <br>Adicionado pattern |
| Propriedade de extensibilidade | Removida a explicitude do additionalProperties |
| Response code | Alterado response Default |
| Response code | Adicionado o status code 422 |
| Response code | Adicionado o status code 423 |
| Response code | Adicionado o status code 529 |

 GET /contracts/{contractId}/warranties

| **Campo** | **O que foi feito?** |
| --- | --- |
| data | Adicionado minItems |
| warrantyType | Removido maxLength  <br>Removida opção do enum: 'SEM\_TIPO\_GARANTIA' |
| currency | Alterada mandatoriedade |
| warrantySubType | Removido maxLength  <br>Adicionadas opções no enum:  <br>'ACORDOS\_COMPENSACAO\_LIQUIDACAO\_OBRIGACOES', 'PROAGRO' e 'SEM\_SUB\_TIPO\_GARANTIA' |
| warrantyAmount | Alterado para string com format double  <br>Alterada descrição  <br>Alterado exemplo   <br>Adicionado minLength  <br>Alterado pattern |
| Propriedade de extensibilidade | Removida a explicitude do additionalProperties |
| Response code | Alterado response Default |
| Response code | Adicionado o status code 422 |
| Response code | Adicionado o status code 423 |
| Response code | Adicionado o status code 529 |

 GET /contracts/{contractId}/scheduled-instalments

| **Campo** | **O que foi feito?** |
| --- | --- |
| typeNumberOfInstalments | Removido maxLength |
| totalNumberOfInstalments | Alterada descrição   <br>Removido maxLength  <br>Adicionado maximum  <br>Removido nullable  <br>Alterada mandatoriedade |
| typeContractRemaining | Removido maxLength |
| contractRemainingNumber | Alterada descrição   <br>Removido maxLength  <br>Adicionado maximum  <br>Removido nullable  <br>Alterada mandatoriedade |
| paidInstalments | Removido nullable  <br>Removido maxLength  <br>Adicionado maximum  <br>Alterada mandatoriedade |
| dueInstalments | Alterada descrição   <br>Removido maxLength  <br>Adicionado maximum  <br>Removido nullable  <br>Alterada mandatoriedade |
| pastDueInstalments | Removido nullable  <br>Removido maxLength  <br>Adicionado maximum  <br>Alterada mandatoriedade  <br>Adicionada restrição |
| balloonPayments | Alterado minItems  <br>Removido nullable  <br>Alterada mandatoriedade |
| balloonPayments/dueDate | Alterada mandatoriedade |
| balloonPayments/amount | Convertido em objeto com os atributos amount e currency  <br>Alterada descrição  <br>Alterada mandatoriedade |
| balloonPayments/amount/amount | Alterado para string  <br>Alterada descrição  <br>Alterado pattern  <br>Removido nullable  <br>Alterado minLength  <br>Alterado maxLength |
| balloonPayments/amount/currency | Removido "NA" do pattern  <br>Alterada descrição |
| Header | Adicionado campo pagination-key |
| Propriedade de extensibilidade | Removida a explicitude do additionalProperties |
| Response code | Alterado response Default |
| Response code | Adicionado o status code 422 |
| Response code | Adicionado o status code 423 |
| Response code | Adicionado o status code 529 |

 GET /contracts/{contractId}/payments

| **Campo** | **O que foi feito?** |
| --- | --- |
| paidInstalments | Alterada descrição  <br>Removido maxLength  <br>Adicionado maximum  <br>Removido nullable  <br>Alterada mandatoriedade |
| contractOutstandingBalance | Alterado para string  <br>Alterado exemplo  <br>Alterado minLength  <br>Alterado pattern |
| releases | Adicionado minItems |
| releases/paidAmount | Alterado para string  <br>Alterada descrição  <br>Alterado exemplo  <br>Alterado minLength  <br>Alterado pattern |
| releases/overParcel | Alterada mandatoriedade |
| releases/overParcel/fees | Adicionado minItems |
| releases/overParcel/fees/feeName | Alterada descrição |
| releases/overParcel/fees/feeAmount | Alterado para string  <br>Atualizada descrição  <br>Alterado exemplo  <br>Alterado minLength  <br>Removido nullable  <br>Alterado pattern |
| releases/overParcel/fees/feeCode | Alterada descrição |
| releases/overParcel/charges | Adicionado minItems |
| releases/overParcel/charges/chargeType | Removido maxLength |
| releases/overParcel/charges/chargeAmount | Alterado para string  <br>Atualizada descrição  <br>Alterado exemplo  <br>Alterado minLength  <br>Removido nullable  <br>Removido maxLength  <br>Alterado pattern |
| releases/overParcel/charges/chargeAdditionalInfo | Alterada mandatoriedade |
| releases/paymentId | Alterado pattern  <br>Adicionado minLength |
| releases/instalmentId | Alterado pattern  <br>Adicionado minLength |
| Swagger | Alterado texto em Orientações Gerais |
| Header | Adicionado campo pagination-key |
| Propriedade de extensibilidade | Removida a explicitude do additionalProperties |
| Response code | Alterado response Default |
| Response code | Adicionado o status code 422 |
| Response code | Adicionado o status code 423 |
| Response code | Adicionado o status code 529 |

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379592)