[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/193658890)

### Obrigatoriedade de informações de contraparte

Com a IN BCB nº 371, a partir de 02/05/23, o envio das informações de identificação de contraparte (CPF ou CNPJ) tornou-se obrigatória para transações de pagamento conforme os tipos de transações da tabela abaixo. 

| **#** | **Tipo de transação** | **Envio da informação da contraparte pagador (S/N) -creditDebitType= CRÉDITO** | **Envio da informação da contraparte recebedor (S/N) -creditDebitType= DÉBITO** | **Observação** |
| --- | --- | --- | --- | --- |
| 1- | TED | S | S | Existem transações em bloco onde as informações únicas de contraparte não são identificadas para o cliente |
| 2- | DOC | N | N |  |
| 3- | PIX | S | S |  |
| 4- | TRANSFERÊNCIA MESMA INSTITUIÇÃO | S | S |  |
| 5- | BOLETO | R | S | No caso de transações em bloco, as informações únicas de contraparte não são identificadas para o cliente |
| 6- | CONVÊNIO ARRECADAÇÃO | R | S | No caso de transações em bloco, as informações únicas de contraparte não são identificadas para o cliente. Caso a instituição possuam a contraparte recebedor, poderá ser enviado |
| 7- | PACOTE TARIFA SERVIÇOS | N | N | O beneficiário é a própria instituição financeira onde o cliente detém a conta |
| 8- | TARIFA SERVIÇOS AVULSOS | N | N | O beneficiário é a própria instituição financeira onde o cliente detém a conta |
| 9- | FOLHA DE PAGAMENTO | S | R | No caso de transações em bloco, as informações únicas de contraparte não são identificadas para o cliente |
| 10- | DEPOSITO | S | N | Pagador existe informação de contraparte apenas em transações acima de R$2.000 (Circular 3978 de 2020) |
| 11- | SAQUE | N | N | Estas operações não entram na classificação de transação de pagamento |
| 12- | CARTÃO | S e N\* | N | \*Para pagamento de fatura: há informação da contraparte. Para cartão de débito e pré-pago: não há informação de contraparte por parte da bandeira (protocolo das bandeiras) |
| 13- | ENCARGOS JUROS CHEQUE ESPECIAL | N | N | O beneficiário é a própria instituição financeira onde o cliente detém a conta |
| 14- | RENDIMENTO\_APLIC\_FINANCEIRA | N | N | Estas operações não entram na classificação de transação de pagamento |
| 15- | PORTABILIDADE SALÁRIO | N | N | O beneficiário é o próprio portador. Observar a forma de transferência do recurso |
| 16- | RESGATE APLICAÇÃO FINANCEIRA | N | N | Estas operações não entram na classificação de transação de pagamento |
| 17- | OPERAÇÃO DE CRÉDITO | N | N | Existe uma API dedicada às operações de crédito |
| 18- | OUTROS | N | N | Preencher em casos que houver informação de contraparte |

**Legenda:** N –Envio não obrigatório; S –Envio obrigatório; R –Em avaliação pelo Banco Central

Abaixo encontramos os casos de exceções à obrigatoriedade de envio da contraparte: ​

- Tipo de transação TED quando se tratar de Transferência entre Reservas (STR0004); ​
- Recebimento de recursos judiciais (STR0051R2);
- Pagamento decorrente de Convênio de Arrecadação na qual a contraparte é um banco correspondente (Neste caso o pagador não necessita enviar a contraparte);
- Transferência para depósito judicial (STR0025);
- Depósito em cheque, e compra e venda de cheque (Neste caso não é necessário envio de contraparte do pagador e recebedor).

### Orientações sobre o transactionId

- As instituições que tiverem transações que ocorreram anteriormente a 13/11/2023 (go-live da v2.1.0) e não possuírem transactionId único, estável e imutável, recomenda-se preenchimento de valor “0000000000” (dummy);

### Identificador de transações

O envio do campo transactionId nos endpoints de transações é obrigatório no Open Finance Brasil. O identificador de transação é obrigatório em D0 para todos os tipos de transação. Já a imutabilidade se dá de acordo com a tabela abaixo:

| **Tipo de Transação** | **Data da Obrigatoriedade** | **Data da Imutabilidade** |
| --- | --- | --- |
| TED | D0 | D0 |
| PIX | D0 | D0 |
| TRANSFERENCIA MESMA INSTITUIÇÃO (TEF) | D0 | D0 |
| TARIFA SERVIÇOS AVULSOS | D0 | D0 |
| FOLHA DE PAGAMENTO | D0 | D0 |
| DOC | D0 | D+1 |
| BOLETO | D0 | D+1 |
| CONVÊNIO ARRECADAÇÃO | D0 | D+1 |
| PACOTE TARIFA SERVIÇOS | D0 | D+1 |
| DEPÓSITO | D0 | D+1 |
| SAQUE | D0 | D+1 |
| CARTÃO | D0 | D+1 |
| ENCARGOS JUROS CHEQUE ESPECIAL | D0 | D+1 |
| RENDIMENTO APLICAÇÃO FINANCEIRA | D0 | D+1 |
| PORTABILIDADE SALÁRIO | D0 | D+1 |
| RESGATE APLICAÇÃO FINANCEIRA | D0 | D+1 |
| OPERAÇÃO DE CRÉDITO | D0 | D+1 |
| OUTROS | D0 | D+1 |

*Data de imutabilidade por tipo de transação*

Abaixo a descrição dos possíveis status que uma transação pode ter:​

- TRANSACAO\_EFETIVADA - corresponde a data de processamento/efetivação da transação​
- LANCAMENTO\_FUTURO - corresponde a data prevista de efetivação da transação​
- TRANSACAO\_PROCESSANDO – corresponde a data de lançamento da transação

Para as transações que podem ter seu identificador alterado, conforme regras delimitadas, os comportamento abaixo devem ser seguidos: ​

- <u>O identificador “provisório” compartilhado em D0 deve ser alterado para o identificador definitivo em D+1</u>:​

    - Importante considerar que as instituições financeiras tem diferentes formas de tratar feriados ao processar transações. Umas consideram apenas feriados nacionais e outras consideram feriados regionais. ​
    - Para transações em D+1 com status TRANSACAO\_EFETIVADA entende-se que D+1 diz respeito a dias úteis.

- Não devem ser compartilhados ao mesmo tempo o identificador provisório e o identificador definitivo, ou seja, após a alteração do status da transação para TRANSACAO\_EFETIVADA, somente a transação com o identificador definitivo deve ser exposta.​
- A data e o valor da transação podem ser alterados na mudança do status para TRANSACAO\_EFETIVADA, de acordo com os processos internos existentes nas instituições. Por exemplo: Resgates de investimentos sem liquidez, e Compra e Venda de ações. ​
- A propriedade de identificador de transação único, estável e  imutável passa a vigorar a partir do momento em que o status da transação passa a ser TRANSACAO\_EFETIVADA. Entretanto:​

    - Não se deve ter o mesmo identificador entre transações em diferentes status. Por exemplo, não é possível se ter ao mesmo tempo o identificador 123 sendo utilizado para transações no status TRANSACAO\_PROCESSANDO e TRANSACAO\_EFETIVADA, mesmo que os valores e datas sejam distintos.​
- Especificamente nos casos de transações no status LANÇAMENTO\_FUTURO a data do campo transactionDateTime deve ser enviado com as informações de dia/mês/ano prevista para o processamento da transação e os demais campos de precisão da data/hora podem ser enviados como 0 (00:00:00.000).​
- O identificador de transação pode se repetir apenas para transações em status TRANSACAO\_PROCESSANDO e LANCAMENTO\_FUTURO. Ou seja, uma instituição pode utilizar, por exemplo, o identificador 9999999 para identificar todas as transações que ainda serão confirmadas (status TRANSACAO\_PROCESSANDO).
- Para as transações que não podem ter seu identificador alterado, conforme regras delimitadas, há exceções mapeadas:  ​

    - Existem situações, principalmente para clientes Pessoa Jurídica, nas quais as transações são lançadas de forma individual (múltiplas transações) em D0 e em D+1 são consolidadas em um único lançamento. Também podemos ter o cenário oposto, no qual a transação é lançada de forma consolidada em D0 e em D+1 “abertas” em múltiplos lançamentos individuais. É importante que não haja duplicidade de informações na exposição, ou seja, as transações individuais e a transação consolidada não sejam expostas ao mesmo tempo. ​

        - Por exemplo, para transações de boleto, pix ou folha de pagamento, em D0 são feitos lançamentos individuais com TransactionId individuais, e em D+1 é efetuado lançamento único com um novo transactionID. ​
    - Existem situação de exceção nas quais um lançamento com identificador estável em D0 pode ser eliminado em D+1. ​

        - Por exemplo, para situações de cobrança de tarifa avulsa nas quais existe acordo negocial ou insuficiência de saldo.

### QUANTO AO ERRO 422

Na especificação técnica existe a possibilidade de retornar o código HTTP Status Code 422 - accepted. Este código de retorno deve ser utilizado quando algum parâmetro da consulta for enviado semanticamente incorreto, ou seja, desrespeitando uma regra de negócio, para os seguintes *endpoints*:

- /accounts/{accountId}/transactions;
- /accounts/{accountId}/transactions-current.

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/193658890)