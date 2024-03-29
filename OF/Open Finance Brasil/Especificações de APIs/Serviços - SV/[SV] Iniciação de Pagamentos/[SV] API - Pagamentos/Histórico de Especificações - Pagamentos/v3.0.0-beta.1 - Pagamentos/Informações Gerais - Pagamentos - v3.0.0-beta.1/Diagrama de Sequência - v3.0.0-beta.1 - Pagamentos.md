[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/136937537)

![att136937578](Diagrama%20de%20Sequ%c3%aancia%20-%20v3.0.0-beta.1%20-%20Pagamentos/attachments/diagrama-sequencia-SB02.1.jpg)
#### Descrição do Diagrama de Sequência

#### Detalhamento da iniciação de pagamento:

1. Debtor (Usuário) inicia o processo de pagamento na iniciadora.
2. Na iniciadora, o debtor seleciona a detentora e os dados de pagamentos: **Observação**: não serão ofertados, no primeiro momento, **Pix Saque e Pix troco**. Também não será possível agendamentos para **Pix QR Codes Dinâmico com vencimento**. [Aqui referências a regulamentação relacionada ao Pix](https://www.bcb.gov.br/estabilidadefinanceira/pix?modalAberto=regulamentacao_pix).

#### Estabelece TLS

Toda comunicação máquina-a-máquina (m2m) usará mTLS, conforme RFC 8705 e detalhado na especificação de segurança: [Open Finance Brasil Financial-grade API Security Profile 1.0 Implementers Draft 3](https://openbanking-brasil.github.io/specs-seguranca/open-banking-brasil-financial-api-1_ID3.html).

#### POST /tokens - Pedido de access\_token e scope: payments, openid

Antes de começar o fluxo de iniciação de pagamento, a Instituição Iniciadora deverá ter se cadastrado como *client* na Instituição Detentora da Conta, em acordo com o especificado para o Registro Dinâmico de Clientes (Dynamic Client Registration). Os detalhes dessa etapa podem ser encontrados na especificação de segurança:  [Open Finance Brasil Financial-grade API Dynamic Client Registration 1.0 Implementers Draft 2](https://openbanking-brasil.github.io/specs-seguranca/open-banking-brasil-dynamic-client-registration-1_ID2.html). Uma vez cadastrada, a Instituição Iniciadora deverá obter o token de acesso (*access\_token*) pelo fluxo de *client credentials*, conforme especificado pela RFC 6749, com os escopos *payments* e *openid*.

#### Valida certificado SSL e scopes

Ao receber a requisição da Iniciadora, o Servidor de Autorização da Instituição Detentora da Conta deverá validar o certificado SSL e os escopos, se esses estão de acordo com a especificação: *payments* e *openid*.

#### Gera access\_token

Em caso de sucesso da validação, o Servidor de Autorização da Instituição Detentora da Conta deverá gerar o *access\_token*, que será utilizado para a criação de consentimento.

#### Access\_token (scope: payments, openid)

O Servidor de Autorização da Instituição Detentora da Conta deverá responder à requisição com o *access\_token* conforme padrões definidos pelo GT de Segurança.

#### POST /payments/consents

Para a criação de consentimento, considerando o requerido para FAPI - Lodging Intent ([Financial_API_Lodging_Intent.md](https://bitbucket.org/openid/fapi/src/master/Financial_API_Lodging_Intent.md)), após a obtenção do token de acesso, a Instituição Iniciadora deverá usar esse token de acesso para fazer a requisição POST de consentimento. A criação do consentimento encontra-se detalhada na seção das APIs para Pagamentos (Open Finance Brasil).

#### 201 Created

A API de Consentimento deverá responder o Http Status 201 e Payload contendo ***consentId***, e status inicial do consentimento em **AWAITING\_AUTHORISATION** conforme especificado na documentação Open Finance Brasil.

#### Redirecionamento

No caso do consentimento ter sido criado com sucesso, a Instituição Iniciadora deverá fazer o redirecionamento para a Instituição Detentora da Conta. Esse fluxo de redirecionamento deve considerar todos os requisitos definidos para o objeto de requisição OpenID Connect (Seção 4.3 da especificação de segurança - [Third Party Provider End To End User Guide](https://openbanking-brasil.github.io/specs-seguranca/tpp-user-guide.html)). Esse redirecionamento é o passo que permitirá o início da autenticação do usuário na Instituição Detentora da Conta.

#### Validações de negócios (Detentora)

Ao receber `POST /payments/<version>/consents` ou `POST /payments/<version>/pix/payments` é importante observar que a Detentora deverá validar as informações passadas pela Iniciadora nos campos do payload de envio do consentimento e do pagamento (como, por exemplo, valores e dados do creditado), além de caso veja necessidade, decodificar o payload para validar outras informações (atenção para a PACS008 e as [regulamentações do Pix](https://www.bcb.gov.br/estabilidadefinanceira/pix?modalAberto=regulamentacao_pix)). A Detentora deve validar as informações de detalhes do payload com os dados de detalhes do consentimento, de acordo com a forma de pagamento. Caso os dados do detalhe informados no consentimento sejam diferente dos dados enviados na iniciação de pagamento, a Detentora deve retornar erro HTTP 422 Unprocessable Entity, com o code BENEFICIARIO\_INCOMPATIVEL.

#### Efetivação do pagamento&lt;&lt;Async&gt;&gt;

A Detentora de Conta efetua a transação de pagamento entre o Debtor e Creditor através da forma de pagamento escolhida pelo Debtor. A efetivação da transação acontece de maneira assíncrona ao fluxo do Open Finance, seguindo as regras e interfaces do arranjo utilizado (apenas PIX disponível nesse momento).

#### Loop (Polling)

A Iniciadora deverá consultar periodicamente a Instituição Detentora de Conta para verificar o status da transação de iniciação pagamento. Os possíveis status de uma transação de iniciação de pagamento estão detalhados na documentação (Open Finance Brasil). Como sugestão, é indicado que a Instituição Iniciadora do pagamento implemente um retry exponencial e respeite o “rate limit” descriminado na documentação. A recomendação para uso do polling encontra-se detalhada na seção de “Recomendação uso de polling” ([Open Finance Brasil](../../../../../../../../../OF/Open%20Finance%20Brasil/Especifica%c3%a7%c3%b5es%20de%20APIs/Servi%c3%a7os%20-%20SV/[SV]%20Inicia%c3%a7%c3%a3o%20de%20Pagamentos/[SV]%20API%20-%20Pagamentos/Hist%c3%b3rico%20de%20Especifica%c3%a7%c3%b5es%20-%20Pagamentos/v3.0.0-beta.1%20-%20Pagamentos/Informa%c3%a7%c3%b5es%20Gerais%20-%20Pagamentos%20-%20v3.0.0-beta.1/Recomenda%c3%a7%c3%a3o%20Uso%20de%20Polling%20e%20Controle%20de%20Acesso%20-%20%20v3.0.0-beta.1%20-%20Pagamentos)).

#### GET pix/payments/{paymentId}

Durante o período de polling a Iniciadora deverá consultar o status da transação através da rota “Get pix/payments/{paymentId}” informado o respectivo paymentId da transação. A consulta encontra-se detalhada na seção das APIs para Pagamentos (Open Finance Brasil).

#### Exibe comprovante de iniciação de pagamento

Caso a Iniciadora identifique que a transação de pagamento foi aprovada pela Detentora de Conta, poderá ser exibido o comprovante da **efetivação** da Transação de Pagamento. Caso o status do pagamento seja diferente de aprovado ou rejeitado, deverá ser apresentada a efetivação da **solicitação** de Iniciação de Pagamento, apresentando as informações [segundo Guia de Usuário](../../../../../../../../../OF/Open%20Finance%20Brasil/Seguran%c3%a7a/Guia%20do%20Usu%c3%a1rio/index).

Os possíveis status de uma transação de iniciação de pagamento estão detalhados na documentação (Open Finance Brasil).

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/136937537)