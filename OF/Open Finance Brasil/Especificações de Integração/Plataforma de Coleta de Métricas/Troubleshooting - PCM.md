[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/46170119)

# Solução de erros na PCM 

Os erros enviados pelas APIs da PCM seguem um padrão de mensagem conforme o template abaixo:

`<tipo do erro>: <detalhe do erro>`

Quando múltiplos erros são enviados, eles são separados por ponto-e-vírgula (`;`).

A [documentação da API](../../../../OF/Open%20Finance%20Brasil/Especifica%c3%a7%c3%b5es%20de%20Integra%c3%a7%c3%a3o/Plataforma%20de%20Coleta%20de%20M%c3%a9tricas/Documenta%c3%a7%c3%a3o%20da%20API) contém a especificação detalhada sobre cada um dos campos.

Abaixo os tipos de erro, seus significados e princípios para investigação da solução.

## Missing property 

**Quando ocorre:** quando uma das propriedades do JSON está faltando. O detalhe contém o atributo. 

**Investigação para Solução: **Verifique o Swagger da PCM e observe se está enviando todos os campos que são requeridos em cada papel (role). 

## Invalid field value 

**Quando ocorre:** quando um valor pré estabelecido para um determinado campo não é respeitado. Exemplo: enviar o valor “OPTIONS” no campo `httpMethod` gera esse erro, uma vez que essa opção não está disponível dentre as previstas. O detalhamento informa o campo que tem o valor errado.

**Investigação para Solução: **Verifique o Swagger da PCM e observe se está enviando todos os campos conforme especificados.

## Unlisted endpoint 

**Quando ocorre:** quando um endpoint que não está na lista de *enums* é enviado. O detalhe possui o nome do atributo que foi enviado pelo client. É uma especialização do tipo *Invalid Field Value* para o campo `endpoint`. 

**Investigação para Solução:** verifique a planilha com lista de endpoint e observe se o endpoint que se está enviando está na lista. Um erro comum é o envio do path que foi chamado ao invés da entrada no enum de valores permitidos. Consulte a [documentação do campo endpoint](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/37879861/Reporte#endpoint) para maiores informações. 

## Invalid payload format 

**Quando ocorre:** quando o payload não é um array.

**Investigação para solução:** envie os payloads sempre em formato de array, mesmo quando exista apenas um elemento.

## Requester id mismatch with 

**Quando ocorre:** quando o organisationId de quem está enviando não é exatamente o mesmo do organisationId do contexto em questão: se a role for client, tem que bater com o clientOrgId, se for server, com serverOrgId. O detalhamento informa com qual role ele não coincidiu.

**Investigação para solução:** verifique se o certificado utilizado para se recuperar o token de acesso possui as informações da organização que está enviando o reporte. O organisationId utilizado para essa checagem é o que foi recuperado do atributo OU/OrganizationIdentifier do certificado no momento da geração do token.

## Field type mismatch 

**Quando ocorre:** quando há divergência no tipo de dados esperado para um determinado campo. O detalhamento informa o campo que contém o erro, bem como o tipo de dados esperado.

**Investigação para solução:** verifique o tipo do dado de acordo com a documentação da API (swagger).

## Additional property not allowed 

**Quando ocorre:** quando uma propriedade adicional que não está na especificação da API é enviada. O detalhamento informa o campo adicional.

**Investigação para solução:** remova os campos que não estejam definidos na API. Um erro comum é a escrita errada de um campo existente.

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/46170119)