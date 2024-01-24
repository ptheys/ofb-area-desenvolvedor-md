[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379430)

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
| brandName | Alterada descrição |
| companyCnpj | Alterado pattern |
| type | Removido maxLength |
| compeCode | Alterado pattern |
| branchCode | Alterada mandatoriedade  <br>Alterado pattern  <br>Adicionada restrição |
| number | Alterado pattern |
| accountId | Alterado pattern  <br>Adicionado minLength |
| Swagger | Alterado texto em Orientações Gerais |
| Header | Adicionado campo pagination-key |
| Propriedade de extensibilidade | Removida a explicitude do additionalProperties |
| Response code | Alterado response Default |
| Response code | Adicionado o status code 422 |
| Response code | Adicionado o status code 423 |
| Response code | Adicionado o status code 529 |

 GET /accounts/{accountId}

| **Campo** | **O que foi feito?** |
| --- | --- |
| compeCode | Alterado pattern |
| number | Alterado pattern |
| type | Removido maxLength |
| branchCode | Alterada mandatoriedade  <br>Adicionada restrição  <br>Alterado pattern |
| subtype | Removido maxLength |
| Propriedade de extensibilidade | Removida a explicitude do additionalProperties |
| Response code | Alterado response Default |
| Response code | Adicionado o status code 422 |
| Response code | Adicionado o status code 423 |
| Response code | Adicionado o status code 529 |

 GET /accounts/{accountId}/balances

| **Campo** | **O que foi feito?** |
| --- | --- |
| data | Alterada estrutura do objeto data:<br><br>"data": {  <br>"availableAmount": {  <br>"amount": "100000.0400",  <br>"currency": "BRL"  <br>},  <br>"blockedAmount": {  <br>"amount": "100000.0400",  <br>"currency": "BRL"  <br>},  <br>"automaticallyInvestedAmount": {  <br>"amount": "100000.0400",  <br>"currency": "BRL"  <br>}  <br>}<br><br>Atributos amount alterados para string |
| availableAmount | Campo convertido em objeto com os atributos amount e current |
| availableAmount/amount | Alterado pattern  <br>Alterado minLength  <br>Alterado maxLength  <br>Adicionada descrição |
| availableAmount/currency | Adicionado campo e suas propriedades |
| availableAmountCurrency | Removido campo |
| blockedAmount | Campo convertido em objeto com os atributos amount e current |
| blockedAmount/amount | Alterado pattern   <br>Alterado minLength  <br>Adicionada descrição |
| blockedAmount/currency | Adicionado campo e suas propriedades |
| blockedAmountCurrency | Removido campo |
| automaticallyInvestedAmount | Campo convertido em objeto com os atributos amount e current |
| automaticallyInvestedAmount/amount | Alterado pattern  <br>Alterado minLength  <br>Adicionada descrição |
| automaticallyInvestedAmount/currency | Adicionado campo e suas propriedades |
| automaticallyInvestedAmountCurrency | Removido campo |
| Propriedade de extensibilidade | Removida a explicitude do additionalProperties |
| Response code | Alterado response Default |
| Response code | Adicionado o status code 422 |
| Response code | Adicionado o status code 423 |
| Response code | Adicionado o status code 529 |

 GET /accounts/{accountId}/transactions

| **Campo** | **O que foi feito?** |
| --- | --- |
| completedAuthorisedPaymentType | Removido maxLength |
| creditDebitType | Removido maxLength |
| type | Removido maxLength  <br>Alterada descrição |
| transaction | Renomeado para transactionAmount  <br>Campo convertido em objeto com os atributos amount e currency |
| transactionAmount | Adicionada descrição |
| transactionCurrency | Removido campo |
| partieCnpjCpf | Alterado pattern  <br>Alterada mandatoriedade |
| partiePersonType | Removido maxLength  <br>Alterada mandatoriedade |
| partieCompeCode | Alterado pattern  <br>Alterada mandatoriedade |
| partieBranchCode | Alterado pattern  <br>Alterada mandatoriedade |
| partieNumber | Alterado pattern  <br>Alterada mandatoriedade |
| partieCheckDigit | Alterada mandatoriedade |
| links/last | Removido campo |
| meta/totalRecords | Removido campo |
| meta/totalPages | Removido campo |
| transactionId | Alterado pattern  <br>Adicionado minLength |
| Header | Adicionado campo pagination-key |
| Propriedade de extensibilidade | Removida a explicitude do additionalProperties |
| Response code | Alterado response Default |
| Response code | Adicionado o status code 422 |
| Response code | Adicionado o status code 423 |
| Response code | Adicionado o status code 529 |

 GET /accounts/{accountId}/transactions-current

| **Campo** | **O que foi feito?** |
| --- | --- |
| endpoint | Inserido novo endpoint para retornar dados dos últimos 7 dias |

 GET /accounts/{accountId}/overdraft-limits

| **Campo** | **O que foi feito?** |
| --- | --- |
| data | "Alterada estrutura do objeto data:<br><br>"data": {   <br>"overdraftContractedLimit": {   <br>"amount": "100000.0400",   <br>"currency": "BRL"   <br>},   <br>"overdraftUsedLimit": {   <br>"amount": "100000.0400",   <br>"currency": "BRL"   <br>},   <br>"unarrangedOverdraftAmount": {   <br>"amount": "100000.0400",   <br>"currency": "BRL"   <br>}   <br>} |
| overdraftContractedLimit | Campo convertido em objeto com os atributos amount e currency |
| overdraftContractedLimit/amount | Alterado pattern  <br>Alterado minLength |
| overdraftContractedLimitCurrency | Removido campo |
| overdraftUsedLimit | Campo convertido em objeto com os atributos amount e currency |
| overdraftUsedLimit/amount | Alterado pattern  <br>Alterado minLength |
| overdraftUsedLimitCurrency | Removido campo |
| unarrangedOverdraftAmount | Alterada mandatoriedade |
| unarrangedOverdraftAmount/amount | Alterado pattern  <br>Alterado minLength |
| unarrangedOverdraftAmountCurrency | Removido campo |
| Propriedade de extensibilidade | Removida a explicitude do additionalProperties |
| Response code | Alterado response Default |
| Response code | Adicionado o status code 422 |
| Response code | Adicionado o status code 423 |
| Response code | Adicionado o status code 529 |

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379430)