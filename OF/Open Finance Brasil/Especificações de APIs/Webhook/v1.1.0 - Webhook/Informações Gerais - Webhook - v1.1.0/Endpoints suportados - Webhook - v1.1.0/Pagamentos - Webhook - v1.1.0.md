[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/161448172)

## API - Pagamentos 

/payments/

Na **API de Pagamentos**, a instituição (**detentora **de contas e/ou transmissora de dados) envia uma notificação à **iniciadora **de pagamento e/ou receptora de dados informando que ocorreu uma **mudança no estado** do recurso e ela deverá consultar o recurso para obter mais informações.

A implementação da funcionalidade do **Webhook **será incluída nas **máquinas de estado de Pagamentos**, com o objetivo de notificar as alterações dos **status dos pagementos**.

### Máquinas de estados  

**Arranjo PIX** - POST /pix/payments

**Consentimento** - POST /consents

### Obrigatoriedade

A deliberação sobre a obrigatoriedade de implementação do Webhook pelas detentoras se teve através de discursões realizadas no GT Especificação, pelo fato em que as iniciadoras precisam se comunicar com todas as detentoras do ecossistema para realizar a iniciação de pagamentos, enquanto a opcionalidade para iniciadora implementar o Webhook se deve pelo fato em querer melhorar a sua experiência na apresentação das informações ao seu cliente, desse modo os recursos existentes seriam o suficiente para a sua implementação.  

**Iniciadora - Opcional**

**Detentora - Obrigatório**

## Casos de Uso

Os casos de uso fornecem uma **visão clara** e **estruturada** de quando o **Webhook **será **acionado **e o **fluxo geral** de das **máquinas de estado**.

### Notificação sobre consentimento

POST /payments/[Versão da API]/consents/{consentId}

Os **eventos **que **acionarão notificações** via Webhook na máquina de estados do **consentimento **do pagamento serão os status **REJECTED **e **CONSUMED**.
![att161448189](Pagamentos%20-%20Webhook%20-%20v1.1.0/attachments/EventosConsentimento.png)
### Notificação sobre pagamento: Arranjo PIX

POST /payments/[Versão da API]/pix/payments/{paymentId}

Os **eventos **que **acionarão as notificações** via Webhook na máquina de estados do **pagamento**: Arranjo Pix da API de Iniciação de Pagamentos serão: **ACSC**, **RJCT**, **CANC**, **PATC**, **PDNG **e **SCHD**.
![att161448192](Pagamentos%20-%20Webhook%20-%20v1.1.0/attachments/EventosPagamento.png)
### Cenários de notificações

Cenários que podem ocorrer como resultado da convivência entre as chamadas assíncronas do Webhook e as chamadas síncronas do POST/payments ou POST/consents:

- **Cenário 1:** Notificação de Webhook pode chegar antes da resposta do POST. Neste caso, a iniciadora seria notificada de uma alteração de estado de pagamento ou consentimento, cujo o id ela ainda não conhece;
- **Cenário 2:** Não há qualquer ordem ou vínculo garantido entre notificações de Webhook de máquinas de estados diferentes, por exemplo, consentimento e pagamento. Neste caso, a iniciadora seria notificada de um estado final da máquina de consentimento após a notificação do primeiro estado da máquina de pagamento, por exemplo, CONSUMED da máquina de estados do consentimento depois do PDNG da máquina de estados do pagamento

As iniciadoras e/ou detentoras poderão criar mecanismos para tratar os cenários apresentados. Por exemplo, para o Cenário 1, a iniciadora pode optar por guardar a notificação por alguns segundos na espera da finalização do POST ou pode descartar a mensagem de imediato e utilizar o polling.

## Diagramas de Sequência

No diagrama de exemplo abaixo, é possível identificar como será o **comportamento da Iniciadora** de pagamentos no processo de **consulta de um pagamento**.

A **detentora** de contas **envia uma notificação** à instituição **iniciadora **de pagamento informando que ocorreu uma **mudança significativa** da máquina de estados da API e que a mesma deverá **consultar** o pagamento para obter mais informações.

### Consulta de Consentimento
![att161448195](Pagamentos%20-%20Webhook%20-%20v1.1.0/attachments/DiagramaSequenciaConsentimento.png)
### Consulta de Pagamento
![att161448198](Pagamentos%20-%20Webhook%20-%20v1.1.0/attachments/DiagramaSequenciaPagamento.png)

## Conteúdo do Payload/ URL

O **payload **será composto pela informação do ***timestamp ***do momento da **alteração da situação do pagamento**;

- timestamp

### Payload

    {
      "data": {
        "timestamp": "2021-05-21T08:30:00Z"
      }
    }

### URL

As **URLs **do ecossistema são formadas com a **configuração **abaixo:  
&lt;host&gt; / &lt;string&gt; / &lt;api&gt; / &lt;versão&gt; / &lt;recurso&gt;

- **Detentoras **de contas e/ou Transmissora de dados: Precisam construir a **URI **de notificação da seguinte forma:

![att161448201](Pagamentos%20-%20Webhook%20-%20v1.1.0/attachments/webhook_consent.png)

![att161448204](Pagamentos%20-%20Webhook%20-%20v1.1.0/attachments/webhook_payment.png)

- Quando **habilitar **a **funcionalidade **de **Webhook **para a **API de Pagamentos**, a **iniciadora **de pagamentos deverá estar **apta a receber** notificações nos seguintes endereços:

    - `https://itp.com/kong3/open-banking/webhook/[Versão do Webhook]/payments/[Versão da API]/consents/{consentId}`
    - `https://itp.com/kong3/open-banking/webhook/[Versão do Webhook]/payments/[Versão da API]/pix/payments/{paymentId}`

## Header das Requests / Responses

A Fim de **permitir **o **monitoramento **e facilitar a **identificação** dos **tickets bilaterais**, foi necessário a **criação **de um **novo parâmetro** de cabeçalho de **requests e responses **na utilização do Webhook.

Parâmetro: **x-webhook-interaction-i**

**Detentora**: No header do request, deverá conter o parâmetro, contendo a seguinte descrição:

“Identificador único para cada tentativa de notificação realizada. O identificador deverá seguir o padrão UID RFC4122”

***\*O Campo é obrigatório***

**Iniciadora**: No header do response, deverá conter o parâmetro, contendo a seguinte descrição:

“Identificador único recebido da detentora de conta na notificação enviada pelo Webhook”

***\*O Campo é obrigatório para a instituição que optar pela utilização da funcionalidade***

O **Parâmetro** foi **incluso **nas **tabelas **abaixo:

- [https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17377351/Cabe+alhos+HTTP#Cabe%C3%A7alho-de-requisi%C3%A7%C3%A3o](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17377351/Cabe+alhos+HTTP#Cabe%C3%A7alho-de-requisi%C3%A7%C3%A3o)
- [https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17377351/Cabe+alhos+HTTP#Cabe%C3%A7alho-de-resposta](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17377351/Cabe+alhos+HTTP#Cabe%C3%A7alho-de-resposta)

## Código de Resposta HTTP

Foi definido código de resposta HTTP específico para o Webhook, que pode ser consultado no link abaixo:

[https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17377374/C+digos+de+Resposta+HTTP#C%C3%B3digos-de-resposta-HTTP](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17377374/C+digos+de+Resposta+HTTP#C%C3%B3digos-de-resposta-HTTP) 

## Segurança

Todos os **endpoints **do **Webhook **utilizam-se de **mTLS **para **autenticação**, não possuem scopes e permissions específicos de segurança. **<u>Toda a segurança é feita via certificado(mTLS – BRCAC).</u>**

**\****** Não será necessário a assinatura do webhook, pois não vai haver dados sensíveis no conteúdo do Payload.***

## Orientação em caso de falha

- Em caso de **falha **de **notificação**

A iniciadora de pagamentos, ao perceber que não está recebendo as notificações oriundas da detentora de contas, poderá utilizar os endpoints de consulta para obter informações sobre o andamento de uma determinada transação do consentimento e/ou pagamento.

Endpoints de Consulta: 

| **Consulta de Consentimento** | **Consulta de Pagamento** |
| --- | --- |
| GET /consents/{consentId} | GET /pix/payments/{paymentId} |

## Requisitos Não Funcionais

- Foram **definidos **os seguintes **requisitos não funcionais**, que podem ser** consultados no seguinte link:** [Referência](../../../../../../../OF/Open%20Finance%20Brasil/Requisitos%20n%c3%a3o%20Funcionais/Refer%c3%aancia) 

    - Frequência;
    - SLA;
    - Timeout;
    - TPS;

### Orientações para as Iniciadoras e Detentoras

- **Orientações **para as **Iniciadoras **de Pagamento:

    - Não deverá ser feito nenhum processamento ou validação síncrona para resposta da notificação
    - As regras de cálculo de SLA devem utilizar as especificações definidas no Portal do Open Finance para todas as APIs
- **Orientações **para as **Detentoras **de Pagamento:

    - A **detentora **de conta fará no **máximo 3 tentativas de notificação**:
    - A **segunda **e a **terceira **tentativas **só ocorrerão em caso de falha**;
    - A **primeira** tentativa de notificação do evento, pela detentora de conta, **deverá ocorrer** em até **1,5 segundo após o evento**;
    - A **segunda **tentativa deverá ocorrer **10 segundos** **após a falha** da **primeira **tentativa;
    - A **terceira **tentativa deverá ocorrer **60 segundos após a falha** da **segunda **tentativa;
- A API de Webhook **não deverá sofrer redirecionamentos de sua URL cadastrada** (HTTP 3XX), caso isso ocorra, deverá ser **considerado como erro**.

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/161448172)