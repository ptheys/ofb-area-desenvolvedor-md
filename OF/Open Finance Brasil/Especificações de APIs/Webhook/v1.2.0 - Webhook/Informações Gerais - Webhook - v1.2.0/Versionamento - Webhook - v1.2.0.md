[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/200736854)

O **Versionamento ocorrerá de forma desacoplada** de qualquer API presente no ecossistema. Tal decisão tem por objetivo **possibilitar **o **reaproveitamento **da **especificação **quando o **Webhook **for adotado para outras APIs no ecossistema do Open Finance, sendo assim:

- A **versão **do **Webhook não fará parte da URL base** do serviço, a URL base representa apenas o &lt;host&gt; da iniciadora que receberá as notificações;
- O restante da URL será formada da seguinte maneira: uma string "/open-banking/webhook", versão do Webhook, nome da API, sua versão e qual endpoint dentro da API que este Webhook notificará, por exemplo:

    - `/open-banking/webhook/[Versão do Webhook]/[nome_da_API]/[Versão_da_API]/[endpoint_da_API]`
- Utilizando a API de Iniciação de Pagamentos como exemplo, ficaria da seguinte forma:

    - `/open-banking/webhook/[Versão do Webhook]/payments/[Versão_da_API]/consents/{consentId}`
    - `/open-banking/webhook/[Versão do Webhook]/payments/[Versão_da_API]/pix/payments/{paymentId}`

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/200736854)