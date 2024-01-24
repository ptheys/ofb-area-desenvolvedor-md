[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/142671991)

## **Consentimento**

**Os possíveis status do consentimento são:**

- AWAITING\_AUTHORISATION - Aguardando autorização
- AUTHORISED - Autorizado
- REJECTED - Rejeitado
- CONSUMED - Consumido

![att142672017](M%c3%a1quina%20de%20Estados%20-%20v3.0.0-beta.2%20-%20Pagamentos/attachments/state-machine_phase3-45e80638.png)
Algumas definições são importantes para tratar a transição dos estados do consentimento em diferentes momentos do fluxo:

#### AWAITING\_AUTHORISATION

- O consentimento é sempre criado com o status AWAITING\_AUTHORISATION. Ele pode ser aprovado somente antes do tempo de expiração de 5 minutos, assumindo o status AUTHORISED. Se não, deve assumir o status REJECTED caso expire ou seja cancelado pelo usuário.

Lembrando que o usuário pode cancelar o consentimento no lado da detentora de conta e por sua vez ela deve mudar o status do consentimento para REJECTED.

#### AUTHORISED

- Para o cenário em que o status assumiu AUTHORISED, o tempo máximo do expirationDateTime do consentimento deve assumir "now + 60 minutos". Este é o tempo para consumir o consentimento autorizado, mudando seu status para CONSUMED. Não é possível prorrogar este tempo e a criação de um novo consentimento será necessária para os cenários de insucesso.

O tempo do expirationDateTime é garantido com os 15 minutos do access token, sendo possível utilizar mais três refresh tokens até totalizar 60 minutos.

#### REJECTED

- Em caso de consentimento expirado a Detentora deverá retornar o status REJECTED.
- Em caso de consentimento rejeitado pelo usuário ou por regra de negócio da Detentora, o status deverá ser retornado como REJECTED.

#### CONSUMED

- O consentimento assume o status CONSUMED após ocorrer o processamento da iniciação do pagamento, seja ele com sucesso (HTTP 201) ou ainda em casos de insucesso (HTTP 422) retornados pela Detentora. Para os demais códigos HTTP não há mudança de status do consentimento, o mesmo permanecerá AUTHORISED, respeitando o tempo máximo de expiração do consentimento (60 minutos).

### Recomendação uso de polling

A consulta via GET, para verificar o processamento da transação, pode ser efetuada a qualquer momento desde que se respeite o rate limit definido na página [Recomendação Uso de Polling e Controle de Acesso](../../../../../../../../../OF/Open%20Finance%20Brasil/Especifica%c3%a7%c3%b5es%20de%20APIs/Servi%c3%a7os%20-%20SV/[SV]%20Inicia%c3%a7%c3%a3o%20de%20Pagamentos/[SV]%20API%20-%20Pagamentos/Hist%c3%b3rico%20de%20Especifica%c3%a7%c3%b5es%20-%20Pagamentos/v3.0.0-beta.2%20-%20Pagamentos/Informa%c3%a7%c3%b5es%20Gerais%20-%20Pagamentos%20-%20v3.0.0-beta.2/Recomenda%c3%a7%c3%a3o%20Uso%20de%20Polling%20e%20Controle%20de%20Acesso%20-%20%20v3.0.0-beta.2%20-%20Pagamentos).

## **Pagamento: Arranjo Pix**

**Os possíveis status do pagamento Pix, são:**

- RCVD
- PATC
- CANC
- ACCP
- ACPD
- RJCT
- ACSC
- PDNG
- SCHD

![att142672011](M%c3%a1quina%20de%20Estados%20-%20v3.0.0-beta.2%20-%20Pagamentos/attachments/diagrama-de-status-SB03.png)
Abaixo segue a descrição dos status relacionados a máquina de estados pertinente aos tipos de pagamento Pix:

#### RCVD (Received)

- O status indica que a requisição de pagamento foi recebida com sucesso pela detentora, mas ainda há validações a serem feitas antes de ser submetida para liquidação.

#### PATC (Partially Accepted Technical Correct)

- O status indica que a transação precisa da confirmação de mais autorizadores para que o processamento do pagamento possa prosseguir.

#### CANC (Cancelled)

- O status indica que a transação Pix pendente foi cancelada com sucesso pelo usuário antes que fosse confirmada (ACCP) ou rejeitada (RJCT) pela detentora.

#### ACCP( Accepted Customer Profile)

- O status indica que todas as verificações necessárias já foram realizadas pela detentora e que a transação está pronta para ser enviada para liquidação (no SPI se for Pix para outra instituição ou internamente se for para outra conta na mesma instituição).

#### ACPD (Accepted Clearing Processed)

- O status indica que a detentora já submeteu a transação para liquidação, mas ainda não tem a confirmação se foi liquidada ou rejeitada.

#### RJCT (Rejected)

- O status indica que a transação foi rejeitada pela detentora ou pelo SPI.

#### ACSC (Accepted Settlement Completed Debtor Account)

- O status indica que a transação foi efetivada pela detentora ou pelo SPI.

#### PDNG (Pending)

- O status indica que a detentora reteve temporariamente a transação Pix para análise.

#### SCHD (Scheduled)

- O status indica que a transação Pix foi agendada com sucesso na detentora.

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/142671991)