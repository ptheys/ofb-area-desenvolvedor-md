[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17378798)

## **Retorno para pedidos fora da janela de funcionamento**

Chamadas às interfaces de compartilhamento de dados, fora dos horários estipulados de cada ciclo, conforme IN 136, deve retornar *HTTP Status Code* 425.

## **Clientes para o cálculo do número de consentimentos**

O cálculo percentual seria feito sobre o total de clientes (considerando pessoas naturais e jurídicas), seguindo a mesma regra do envio da base de clientes ao BCB.

## **Base de clientes elegíveis**

Para o cálculo do percentual de clientes elegíveis em cada ciclo do lançamento escalonado, a instituição participante deve considerar a base total de clientes, a qual já é comunicada mensalmente ao Banco Central.

Deve ser considerada a última data disponível de referência para o levantamento do número total de clientes, com base nos números comunicados ao BCB. (Utilizar 30/05 como base para cálculo dos percentuais de todos os 4 ciclos do lançamento escalonado da Fase 2).

## **Código de retorno para pedidos de consentimento para a transmissora que já atingiu o limite de consentimentos**

Caso a transmissora já tenha atingido o limite de consentimentos permitidos no ciclo, a solicitação do consentimento deve retornar erro *HTTP Status Code* 429.

## **Devolução de mensagem padronizada**

Quando a receptora receber o erro da transmissora, de que o limite de consentimentos do ciclo foi atingido, deve ser exibida ao cliente uma mensagem padronizada:

*No momento, a instituição de origem dos dados não poderá atender esta solicitação, pois atingiu os limites de compartilhamentos estabelecidos. O Open Finance está sendo disponibilizado gradualmente para garantir um sistema seguro e estável. (Recomendação para que a Instituição Receptora sugira o que fazer, ex.: call to action).*

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17378798)