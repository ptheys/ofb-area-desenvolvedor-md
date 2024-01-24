[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17376243)

## **Visão Geral**

A API tem como objetivo coletar o consentimento e realizar a iniciação de pagamento entre bancos e instituições financeiras e acessível também à estabelecimentos comerciais participantes do Open Finance Brasil.

Os recursos estão disponíveis para pagadores que possuem vínculo com uma instituição detentora de conta participante do Open Finance, independentemente de serem pessoa física ou jurídica.

## **Criar consentimento para iniciação de pagamento: **(POST /payments/v1/consents)

Método para a criação do consentimento para iniciação de pagamento.

Para consultar os payloads correspondentes ao tipo do pagamento PIX, [acesse aqui.](../../../../../../../../../OF/Open%20Finance%20Brasil/Especifica%c3%a7%c3%b5es%20de%20APIs/Servi%c3%a7os%20-%20SV/[SV]%20Inicia%c3%a7%c3%a3o%20de%20Pagamentos/[SV]%20API%20-%20Pagamentos/Hist%c3%b3rico%20de%20Especifica%c3%a7%c3%b5es%20-%20Pagamentos/v1.1.0-rc1.0%20-%20Pagamentos/Informa%c3%a7%c3%b5es%20Gerais%20-%20Pagamentos%20-%20v1.1.0-rc1.0/Orienta%c3%a7%c3%b5es%20-%20v1.1.0-rc1.0)

### **Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/paymentsPostConsents_v1.csv)

## **Consultar consentimento para iniciação de pagamento**: (GET /payments/v1/consents/{consentId})

Método para consultar o consentimento para iniciação de pagamento.

### **Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/paymentsGetConsentsConsentId_v1.csv)

## **Revogar consentimento de pagamento**: (PATCH /payments/v1/consents/{consentId})

Método para revogação do consentimento.

### **Dicionário de dados**

Campos de resposta do endpoint de `/consents`

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/paymentsPatchPixPayments_v1.csv)

## **Pix - Criar iniciação de pagamento**: (POST /payments/v1/pix/payments)

Método para a criação de uma iniciação de pagamento.

### **Dicionário de dados**

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/paymentsPostPixPayments_v1.csv)  

## **Pix - Consultar iniciação de pagamento**: (GET /payments/v1/pix/payments/{paymentId})

Método para consultar uma iniciação de pagamento.

### **Dicionário de dados**

Campos de resposta do endpoint de `/pix/payments`.

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/paymentsGetPixPaymentsPaymentId_v1.csv)

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17376243)