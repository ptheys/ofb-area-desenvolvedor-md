[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/125370389)

Nessa sessão será possível encontrar orientações sobre quais eventos de resposta que a detentoras de conta devem repassar para iniciadora de pagamentos referente ao processamento de um pagamento na máquina de estado do pagamento: Consentimento e na máquina de estado do pagamento: Arranjo Pix na adoção do Webhook.

## **Obrigatoriedade do Webhook**

Adoção do Webhook pelas instituições e para o ecossistema geram diversos benefícios, quando relacionados ao número de chamadas gerando otimização do ecossistema do Open Finance Brasil. 

A implementação da funcionalidade das notificações por Webhook é: 

- Obrigatória para as detentoras de conta
- Opcional para as iniciadoras de pagamento. Quando a iniciadora optar por implementar as notificações por Webhook deverá realizar o cadastro da URL no diretório central e demais procedimentos detalhados no guia do diretório.

### **Notificação sobre consentimento: **POST /payments/[Versão da API]/consents/{consentId}

Os eventos que acionarão notificações na máquina de estados do consentimento do pagamento serão os status REJECTED e CONSUMED.
![att125370412](Informa%c3%a7%c3%b5es%20Gerais%20-%20Webhook%20-%20v1.0.0-beta.3/attachments/EventosConsentimento.png)
### **Notificação sobre pagamento:** POST /payments/[Versão da API]/pix/payments/{paymentId}

Os eventos que acionarão as notificações via Webhook na máquina de estados pagamento: Arranjo Pix da API de Iniciação de Pagamentos serão: ACSC, RJCT, CANC, PATC, PDNG e SCHD.
![att125370409](Informa%c3%a7%c3%b5es%20Gerais%20-%20Webhook%20-%20v1.0.0-beta.3/attachments/EventosPagamento.png)
## **Notificações do Webhook **

O consumo de informações pelos participantes do Open Finance Brasil é feito através de diversas consultas (polling), onde um participante busca avaliar se houve alguma atualização no estado de um recurso, dessa maneira eleva-se de forma significativa o consumo da infraestrutura das instituições participantes do Open Finance Brasil.

No diagrama de exemplo abaixo, é possível identificar como será o comportamento da Iniciadora de pagamentos no processo de consulta de um pagamento. 

A detentora de contas envia uma notificação à instituição iniciadora de pagamento informando que ocorreu uma mudança significativa da máquina de status da API e que a mesma deverá consultar o pagamento para obter mais informações.

*Exemplo*:
![att125370415](Informa%c3%a7%c3%b5es%20Gerais%20-%20Webhook%20-%20v1.0.0-beta.3/attachments/DiagramaSequenciaConsentimento.png)![att125370418](Informa%c3%a7%c3%b5es%20Gerais%20-%20Webhook%20-%20v1.0.0-beta.3/attachments/DiagramaSequenciaPagamento.png)
### **Premissas**

- O payload será composto pela informação do timestamp do momento da alteração da situação do pagamento;
- A detentora de conta deve encaminhar o paymentId para iniciadora pela URL.

### **Em caso de falha de notificação**

A iniciadora de pagamentos, ao perceber que não está recebendo as  notificações oriundas da detentora de contas, poderá utilizar os endpoints de consulta para obter informações sobre o andamento de uma determinada transação do consentimento e/ou pagamento.

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/125370389)