[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/33062913)

# Introdução

O CIBA (Client Initiated Backchannel Authentication) é um protocolo de autenticação desacoplado em que Instituições Iniciadoras de Pagamento ou Receptoras de Dados recebem consentimentos dos usuários SEM realizar o fluxo FAPI Hybrid Flow (redirecionamento) em todas as interações.

O usuário é redirecionado via fluxo FAPI Hybrid Flow apenas uma única vez, onde o CIBA é ativado e por consequência os próximos pedidos de autorização serão por meio de um canal secundário - o backchannel - em que as Instituições Iniciadoras de Pagamento ou Receptoras de Dados se comunicam com o Servidor de Autorização da Instituição Detentora da Conta ou Transmissora de Dados para receber o consentimento do usuário.

O uso do FAPI Hybrid Flow para o vínculo inicial foi escolhido porque já é um processo conhecido pelo usuário e permite uma identificação via id\_token em que os Servidores de Autorização já implementam nas Instituições Detentoras de Conta ou Transmissora de Dados.

Após o vínculo, nos próximos pedidos de consentimento, o usuário receberá um push notification, SMS, mensagem via WhatsApp, etc como canal de redirecionamentopara o aceite do consentimento.

Ao habilitar o fluxo CIBA os participantes devem implementar algumas diretrizes:

1. O id\_token é único e representa um cliente e conta;
2. O tempo de aceite do consentimento sobre o pedido de Autorização recebido via CIBA deverá se manter o mesmo definido para o fluxo via Hybrid Flow, de 5 minutos;
3. O payload de pagamento deve conter identificação que foi realizado via CIBA ou FAPI Hybrid Flow.

O fluxo CIBA está descrito em quatro documentos técnicos que se complementam mutuamente, e fazem referências a outras especificações. Recomenda-se a consulta na seguinte ordem:

OpenID Connect Client-Initiated Backchannel Authentication Flow - Core 1.0 -[OpenID Connect Client-Initiated Backchannel Authentication Flow - Core 1.0](https://openid.net/specs/openid-client-initiated-backchannel-authentication-core-1_0.html) - Esta é a principal especificação do fluxo CIBA divulgada pela OpenID Foundation, contendo detalhes de implementação, requisitos e recomendações, e referências a outras especificações basais.

Open Finance Brasil Financial-grade API Security Profile 1.0 Implementers Draft 3 - [Open Finance Brasil Financial-grade API Security Profile 1.0 Implementers Draft 3 -](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/82051180/PT+Open+Finance+Brasil+Financial-grade+API+Security+Profile+1.0+Implementers+Draft+3) Este é o perfil de regras e recomendações de autenticação e segurança proposto pelo GT de Segurança do Open Finance Brasil.

Financial-grade API: Client Initiated Backchannel Authentication Profile -[Draft-02: Financial-grade API: Client Initiated Backchannel Authentication Profile](https://openid.net/specs/openid-financial-api-ciba-ID1.html) - Este é o perfil de regras e recomendações de autenticação e segurança proposto pela OpenID Foundation para implementações genéricas do fluxo CIBA.

Open Finance Brasil Financial-grade API CIBA Security** Profile 1.0 **-[Open Banking Brasil Financial-grade CIBA API Security Profile 1.0 Implementers Draft 3](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/213352480/PT+Open+Banking+Brasil+Financial-grade+CIBA+API+Security+Profile+1.0+Implementers+Draft+3) - Este é o perfil de regras e recomendações de autenticação e segurança proposto pela Squad CIBA do Open Finance Brasil para implementação do fluxo CIBA para Iniciação de Pagamentos no cenário brasileiro.

O protocolo CIBA é abrangente e permite diversos casos de uso. Nas próximas seções estão definidas as opções permitidas e seus detalhes. 

# [SV] CIBA – Decoupled Flow EN

# Introduction

The CIBA (Client Initiated Backchannel Authentication) is a decoupled authentication protocol where Payment Initiator Institutions or Data Receiving Institutions obtain user consents WITHOUT performing the FAPI Hybrid Flow (redirection) in every interaction.

The user is redirected via the FAPI Hybrid Flow only once, where CIBA is activated and consequently, the next authorization requests will be through a secondary channel - the backchannel - where Payment Initiator Institutions or Data Receiving Institutions communicate with the Authorization Server of the Account Holding Institution or Data Transmitting Institution to receive the user's consent.

Using the FAPI Hybrid Flow for the initial link was chosen because it's already a known process by the user and allows identification via an id\_token that Authorization Servers already implement in Account Holding Institutions or Data Transmitting Institutions.

After the link, in subsequent consent requests, the user will receive a push notification, SMS, WhatsApp message, or another channel to redirect and accept the consent.

When enabling the CIBA flow, participants must implement certain guidelines:

1.The id\_token is unique and represents a client and account;

1. The consent acceptance time for the Authorization request received via CIBA should maintain the same defined for the flow via Hybrid Flow, which is 5 minutes;

1. The payment payload must contain identification that it was carried out via CIBA or FAPI Hybrid Flow.

The CIBA flow is described in four complementary technical documents and refers to other specifications. It is recommended to consult them in the following order:

[OpenID Connect Client-Initiated Backchannel Authentication Flow - Core 1.0](https://openid.net/specs/openid-client-initiated-backchannel-authentication-core-1_0.html): This is the primary specification of the CIBA flow released by the OpenID Foundation, containing implementation details, requirements, recommendations, and references to other foundational specifications.

[Open Finance Brasil Financial-grade API Security Profile 1.0 Implementers Draft 3](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/82083996/EN+Open+Finance+Brasil+Financial-grade+API+Security+Profile+1.0+Implementers+Draft+3): This is the rule profile and security authentication recommendations proposed by the Open Finance Brasil Security GT.

[Financial-grade API: Client Initiated Backchannel Authentication Profile - Draft-02](https://openid.net/specs/openid-financial-api-ciba-ID1.html): This is the rule profile and security authentication recommendations proposed by the OpenID Foundation for generic implementations of the CIBA flow.

[Open Finance Brasil Financial-grade API CIBA Security Profile 1.0 - Open Banking Brasil Financial-grade CIBA API Security Profile 1.0 Implementers Draft 3](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/213811213/EN+Open+Banking+Brasil+Financial-grade+CIBA+API+Security+Profile+1.0+Implementers+Draft+3): This is the rule profile and security authentication recommendations proposed by the CIBA Squad of Open Finance Brasil for the CIBA flow implementation for Payment Initiation in the Brazilian scenario.

The CIBA protocol is comprehensive and supports various use cases. The following sections define the currently allowed options and their details.

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/33062913)