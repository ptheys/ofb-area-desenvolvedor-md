[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/136937703)

Na tabela abaixo, é possível observar quais são os possíveis retornos do campo rejectionReason podem ser enviados em cada etapa envolvida com o consentimento, no fluxo de pagamentos:

| **Etapas do funil do consentimento** | **Code** |
| --- | --- |
| (5) Início da autenticação | FALHA\_INFRAESTRUTURA  <br>TEMPO\_EXPIRADO\_AUTORIZAÇAO |
| (6) Conclusão da autenticação | FALHA\_INFRAESTRUTURA  <br>TEMPO\_EXPIRADO\_AUTORIZAÇAO  <br>REJEITADO\_USUARIO |
| (7) Autorização do cliente | FALHA\_INFRAESTRUTURA  <br>CONTAS\_ORIGEM\_DESTINO\_IGUAIS  <br>CONTA\_SALARIO  <br>SALDO\_INSUFICIENTE  <br>VALOR\_ACIMA\_LIMITE  <br>QRCODE\_INVALIDO |
| (8) *Authorisation code *emitido | FALHA\_INFRAESTRUTURA  <br>TEMPO\_EXPIRADO\_CONSUMO |

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/136937703)