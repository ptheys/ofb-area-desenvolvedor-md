[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/213909872)

Alteração na parte de orientações dentro do swagger

| **Campo** | **O que foi feito?** |
| --- | --- |

 POST /consents

| **Campo** | **O que foi feito?** |
| --- | --- |
| resquest/data/payment/detail/localInstrument | Adicionado - Restrição |
| response/data/payment/detail/localInstrument | Adicionado - Restrição |

 GET /consents/{consentId}

| **Campo** | **O que foi feito?** |
| --- | --- |
| get/responses/200/data/payment/detail/localInstrument | Adicionado - Restrição |

 POST /pix/payments

| **Campo** | **O que foi feito?** |
| --- | --- |
| resquest/data/localInstrument | Adicionado - Restrição |
| response/data/localInstrument | Adicionado - Restrição |

 GET /pix/payments/{paymentId}

| **Campo** | **O que foi feito?** |
| --- | --- |
| get/responses/200/data | Alterado - “type“ |
| get/responses/200/data/**localInstrument** | Adicionado - Restrição |

 PATCH pix/payments/{paymentId}/

| **Campo** | **O que foi feito?** |
| --- | --- |
| response/data/**localInstrument** | Adicionado - Restrição |

 PATCH pix/payments/consents/{consentId}

| **Campo** | **O que foi feito?** |
| --- | --- |

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/213909872)