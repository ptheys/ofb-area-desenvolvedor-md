[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/37879861)

O Reporte é o dado que as instituições participantes enviam para a Plataforma de Coleta de Métricas para catalogar a interação entre elas. 

**Nota sobre segurança**

Consulte o [Manual de Integração](../../../../../../OF/Open%20Finance%20Brasil/Especifica%c3%a7%c3%b5es%20de%20Integra%c3%a7%c3%a3o/Plataforma%20de%20Coleta%20de%20M%c3%a9tricas/Manual%20de%20Integra%c3%a7%c3%a3o)  para maiores informações sobre como se autenticar na plataforma.

## Fluxo

Considerando:

- Uma interação entre "Instituição A" e "Instituição B" onde a Instituição A vai solicitar a lista de contas de um determinado responsável pelo objeto de negócio para a Instituição B;
- A parte que realiza a chamada já tem o consentimento do responsável pelo objeto de negócio para recuperar os dados;

O esquema abaixo mostra a interação entre as duas instituições.
![att38371400](Reporte/attachments/Open%20Banking%20-%20PCM%20-%20Copy%20of%20Interaction%20Base.jpg)

1. Instituição A faz uma chamada para `/accounts/v1/accounts` na Instituição B. Essa chamada contém o header `x-fapi-interaction-id`, conforme documentação do endpoint[^1];
2. Instituição B registra essa chamada e processa o pedido e retorna resposta à instituição A;
3. Instituição B envia o reporte para Plataforma Coleta de Métricas ;
4. Instituição A recebe a resposta da instituição B e envia o reporte para Plataforma Coleta de Métricas.

**Cabeçalho **`x-fapi-interaction-id`

O cabeçalho `x-fapi-interaction-id` é um cabeçalho obrigatório para o client e deve ser repetido pelo server em sua resposta conforme especificação do Open Finance Brasil. Esse cabeçalho identifica uma requisição (e sua devida resposta) em específico, e não deve ser utilizado para identificar sequências de chamadas (jornadas, paginação, etc). Cada par requisição-resposta deverá conter seu próprio valor nesse cabeçalho.

## Modelos dos reportes

As APIs da PCM são divididas em duas categorias:

**Reportes private:** representam os reportes sobre transações feitas entre duas instituições participantes do Open Finance. Se tratam de transações protegidas pelos mecanismos de segurança vigentes no OFB, e portanto são considerados reportes de APIs privadas.

**Reportes opendata:** se referem aos reportes feitos em APIs da fase 1 específicas para dados abertos. Como se referem à endpoints que são disponíveis a público em geral, são considerados reportes abertos.

### Modelos para reportes Private

O reporte contém dados que se referem à uma transação em específico entre dois participantes, e é a informação que cada papel (server ou client) tem que enviar para a Plataforma de Coleta de Métricas.  
Uma instituição é identificada pelo seu `organisationId` (com "s").

No contexto de uma chamada, os dados enviados para a Plataforma de Coleta de Métricas pelo client e pelo server são diferentes, uma vez que essa diferença reflete os contextos de execução da transação de cada um dos lados.

**Importante**

Além dos campos que são obrigatórios exclusivamente para o client (`clientSSId`, `endpointUriPrefix`, e `additionalInfo`), os campos `timestamp` e `processTimespan` possuem significado diferente para cada papel, bem como o campo `role` que possui valor fixo dependendo do papel.

Os campos abaixo são comuns tanto para o client quanto para o server:

| Campo | Descritivo |
| --- | --- |
| `fapiInteractionId`**   ** | UUID que identifica uma transação específica entre dois participantes. Esse dado pode ser encontrado no header x-fapi-interaction-id que é informado pelo Client e devolvido pelo Server. Mais informações em [https://openbanking-brasil.github.io/areadesenvolvedor/#cabecalhos-http](https://openbanking-brasil.github.io/areadesenvolvedor/#cabecalhos-http)  na documentação do Open Finance Brasil. |
| `endpoint` | Identificação do endpoint que foi utilizado na transação reportada. A identificação do endpoint deve estar entre as entradas desse enum para ser considerado válido. Nesse campo não deve ser utilizado o path da requisição original, uma vez que ao comparar com os valores dessa enum, ele não será considerado válido.<br><br>**Exemplo:**<br><br>Caso uma chamada à um endpoint com o path `/open-banking/credit-cards-accounts/v1/accounts/123456789/transactions` tenha sido feita, o valor a ser enviado no reporte é `/open-banking/credit-cards-accounts/v1/accounts/{creditCardAccountId}/transactions`, que é o identificador desse endpoint no enum. Nesse caso, o dado real da parte variável do path não deverá ser enviado.<br><br>A seção *endpoint* em *Campos Especiais* abaixo possui uma lista dos valores válidos. |
| `statusCode` | Status de retorno HTTP da solicitação, conforme descrito na documentação de cada endpoint. |
| `httpMethod` | Método HTTP da solicitação. |
| `clientOrgId` | Identificador da organização **de onde** a chamada foi disparada |
| `serverOrgId` | Identificador da organização **para onde** a chamada foi feita |
| `correlationId` (opcional) | ID de correlação que identifica uma sequência de chamadas inter-relacionadas. Diferente do `fapiInteractionId` que serve para identificar cada par request-response (interação), o identificador de correlação serve para ligar diferentes reportes quando estes representam uma jornada ou uma sequência de chamadas. |

**statusCode e timeout**

Quando o client não receber uma resposta do server em tempo hábil, ele deve enviar no reporte o status `408` no campo `statusCode`, e o tempo que aguardou até o evento de timeout ocorrer  no campo `processTimespan` do modelo do client.

**Timeout e divergências**

Em casos onde o client não receber a resposta em tempo hábil e reportar um timeout, o server ainda poderá responder e reportar a resposta. O motor de conciliação vai buscar a contraparte.

#### Modelo do Client

Além dos campos padrão do reporte, o *client* necessita enviar os campos abaixo. Note que todos eles são obrigatórios:

| Campo | Descritivo |
| --- | --- |
| `timestamp` | Data/Hora UTC no formato ISO8601 com milissegundos (YYYY-MM-DDTHH:mm:ss.sssZ) do momento em que a chamada foi disparada, imediatamente antes do primeiro byte enviado na requisição. |
| `processTimespan` | Tempo em milissegundos inteiros decorrido desde o registro do timestamp até a chegada do primeiro byte da resposta do server. |
| `clientSSId` | Identificador do software statement **de onde** a chamada foi disparada. |
| `endpointUriPrefix` | Endereço do servidor de destino da chamada incluindo o prefixo quando houver. O formato do campo deverá ser o seguinte: `https://{host}/{prefixo}`, sendo:<br><ul><li><p><code>host</code>: endereço FQDN do servidor de destino</p></li><li><p><code>prefixo</code>: toda a parte do path que vem antes da string <code>/open-banking</code></p></li></ul><br>  <br>**Exemplos:**<br><ol start="1"><li><p>Para uma requisição em <code>https://openbanking.instituicao-1.com.br/opbk/open-banking/products-services/v1/business-accounts</code><a class="external-link" href="https://openbanking.instituicao-1.com.br/opbk/open-banking/products-services/v1/business-accounts," rel="nofollow">,</a> o dado a ser enviado é <code>https://openbanking.instituicao-1.com.br/opbk</code><a class="external-link" href="https://openbanking.instituicao-1.com.br/opbk." rel="nofollow">.</a></p></li><li><p><code>Para uma requisição em https://openbanking.instituicao-2.com.br/open-banking/products-services/v1/business-accounts</code><a class="external-link" href="https://openbanking.instituicao-2.com.br/open-banking/products-services/v1/business-accounts," rel="nofollow">,</a> o dado a ser enviado é <code>https://openbanking.instituicao-1.com.br/</code><a class="external-link" href="https://openbanking.instituicao-1.com.br/." rel="nofollow">.</a></p></li></ol> |
| `additionalInfo.personType` | Identifica se a transação aconteceu em nome de uma pessoa física ou jurídica. |
| `additionalInfo.consentId` | Deve ser preenchido com a mesma string obtida no campo `data.consentId` retornado após a chamada inicial na API `POST /consent`. |
| `additionalInfo.localInstrument` | Deve ser preenchido com a mesma string informada no payload "data.localInstrument" |
| `additionalInfo.status` | Deve ser preenchido com a mesma string obtida no "data.status" |
| `additionalInfo.rejectReason` | Deve ser preenchido com a mesma string obtida no "data.rejectionReason" |
| `role` | ENUM indicando se o reporte que está sendo enviado apresenta a visão do server ou do client. Obrigatório valor "CLIENT" |

**Importante:** Os atributos do campo `additionalInfo` deverão ser preenchidos de maneira contextual conforme valor do campo `endpoint`. Informações adicionais [na planilha em anexo (download aqui)](https://openfinancebrasil.atlassian.net/wiki/download/attachments/37879861/Tabela%20additionalInfo%20%E2%80%93%20campos%20contexto%20e%20obrigatoriedade%20%28cliente%20server%29v12__20231004134608.xlsx?api=v2).

Além dos campos padrão do reporte, o *server* necessita enviar os seguintes campos:

| Campo | Descritivo |
| --- | --- |
| `timestamp` | Data/Hora UTC no formato ISO8601 com milissegundos (YYYY-MM-DDTHH:mm:ss.sssZ) do momento em que a chamada foi disparada, imediatamente antes do primeiro byte enviado na requisição. |
| `processTimespan` | Tempo em milissegundos inteiros decorrido desde o registro do timestamp até a chegada do primeiro byte da resposta do server. |
| `role` | ENUM indicando se o reporte que está sendo enviado apresenta a visão do server ou do client. Obrigatório valor "SERVER". |

Para informações detalhadas, bem como exemplos de utilização, consulte a documentação da API.

### Reportes OpenData

Quando o envio for para um reporte de chamadas em endpoints da fase 1 (dados abertos), o modelo a ser enviado segue o padrão de dados a seguir. Como as APIs da fase 1 não se referem à transações entre duas instituições participantes, não existe processo de conciliação. 

| Campo | Descritivo |
| --- | --- |
| `endpoint` | Identificação do endpoint que foi utilizado na chamada da api de dados abertos. A identificação do endpoint deve estar entre as entradas desse enum para ser considerado válido. |
| `statusCode` | Tempo em milissegundos inteiros decorrido desde o registro do timestamp até a chegada do primeiro byte da resposta do server. |
| `httpMethod` | Método HTTP da solicitação. |
| `timestamp` | Data/Hora UTC no formato ISO8601 com milissegundos (YYYY-MM-DDTHH:mm:ss.sssZ) do momento em que a chamada foi recebida |
| `processTimespan` | Tempo em milissegundos inteiros decorrido desde o recebimento do request até o momento imediato ao envido do primeiro byte da resposta |
| `additionalInfo.clientIp` | Endereço IP do cliente que efetuou a chamada |

Para detalhes sobre o campo `additionalInfo`, consulte o [tópico específico](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/37879861/Reporte#additionalInfo) abaixo.

### Campos especiais

#### **fapiInteractionId**

O `fapiInteractionId` é um dado que precisa ser conhecido pelas duas partes. Ele trafega no header `x-fapi-interaction-id` e identifica uma chamada e resposta em específico. Quando o client enviar essa informação para o server, ambos enviam o dado que foi gerado pelo client. Caso essa informação não seja enviada pelo client, ela deve ser gerada e devolvida pelo server, e nesse caso, ambos enviam o dado gerado pelo server. 

Essa informação é obrigatória para a Plataforma de Coleta de Métricas, uma vez que é o principal dado utilizado na conciliação das chamadas mas, de acordo com a documentação dos headers do Open Finance[1], não é obrigatória no momento da solicitação.

#### **endpoint**

O campo `endpoint` registra o identificador do endpoint envolvido na transação. O dado faz parte do conjunto (ENUM) previamente listado na [Documentação da API](../../../../../../OF/Open%20Finance%20Brasil/Especifica%c3%a7%c3%b5es%20de%20Integra%c3%a7%c3%a3o/Plataforma%20de%20Coleta%20de%20M%c3%a9tricas/Documenta%c3%a7%c3%a3o%20da%20API) e reproduzido abaixo, a qual refletirá os endpoints previstos na documentação do Open Finance. Por se tratar da identificação do endpoint, o valor do *path* efetivamente trafegado na transação será considerado inválido pela plataforma, caso ele seja diferente das entradas do ENUM.

O envio do campo endpoint difere para reportes privados e para reportes de dados abertos. A lista de endpoints para cada tipo de envio pode ser encontrada [aqui](../../../../../../OF/Open%20Finance%20Brasil/Especifica%c3%a7%c3%b5es%20de%20Integra%c3%a7%c3%a3o/Plataforma%20de%20Coleta%20de%20M%c3%a9tricas/Tabela%20de%20endpoints%20aceitos%20pela%20PCM).

Existem dois casos especiais que são os endpoints `/token` e `/register`. Esses endpoints não possuem padrão pré definido, uma vez que cada participante decide suas próprias URLs e informam dentro dos seus respectivos catálogos. Portanto, para o preenchimento do reporte no papel de client, é necessário que cada participante identifique o endpoint através das URL’s de .well-known e inclua esse valor no campo `endpointUriPrefix`. Sob a perspectiva do server, o report deverá ser feito como `/token` e `/register` de acordo com o endereço que foi chamado.

Esse procedimento é obrigatório para participantes que estejam enviando reportes no papel de client. Em versões futuras, esse processo também deverá ser feito para os participantes que reportarem no papel de server. A lista de endpoints válidos será atualizada quinzenalmente dentro da PCM.

#### **additionalInfo**

O campo `additionalInfo` tem por objetivo concentrar informações adicionais dentro de um determinado contexto da transação. Ele tem uma ligação estrita com o campo `endpoint`, ou seja, as informações que deverão ser repassadas no `additionalInfo` dependem do valor informado no campo `endpoint`. 

A planilha em anexo ([download aqui](https://openfinancebrasil.atlassian.net/wiki/download/attachments/258277703/Tabela%20additionalInfo%20%E2%80%93%20campos%20contexto%20e%20obrigatoriedade%20%28cliente%20server%29v15.xlsx?api=v2)) contém o detalhamento das regras de envio de cada informação no campo `additionalInfo` conforme o contexto.

**Nota sobre** `consentId` **no endpoint** `/token`

Ao reportar o uso de um endpoint `/token`, o identificador único de consentimento só será reportado nos casos em que o "grant\_type" é do tipo "authorization\_code" ou do tipo "refresh\_token", uma vez que esta informação de consentId é inexistente quando o "grant\_type" é do tipo "client\_credentials".

Exemplos de uso e detalhamento dos campos e das operações podem ser encontradas na [Documentação da API](../../../../../../OF/Open%20Finance%20Brasil/Especifica%c3%a7%c3%b5es%20de%20Integra%c3%a7%c3%a3o/Plataforma%20de%20Coleta%20de%20M%c3%a9tricas/Documenta%c3%a7%c3%a3o%20da%20API).

## Formas de Envio

Os reportes deverão ser enviados através de seus respectivos endpoints seguindo sua natureza (reportes ou opendata). Todos os reportes devem ser enviados em lotes, ainda que sejam poucos reportes por lote. É permitido enviar reportes de client e server no mesmo lote. 

O limite operacional estabelecido para o envio é de no máximo 5.000 reportes por requisição.

Em todos os casos, o processamento dos dados é feito de forma assíncrona.

## Recepção e retorno

Quando um reporte chega nos endpoints da API, ele recebe um atributo `reportId`, que o identifica unicamente na plataforma. A partir daí é feita a validação de campos obrigatórios. Caso o formato do reporte esteja inválido, aquele `reportId` em particular será marcado com o status `DISCARDED`, acrescido de uma descrição. Caso não haja erro no formato, o report ganha o status `ACCEPTED`. Depois dessa validação, são retornados os campos `reportId`, `status` e `correlationId` (quando aplicável) para o chamador. Todos os reportes são então inseridos em uma fila de processamento, feito sempre de maneira **assíncrona**, e portanto se utiliza da premissa da consistência posterior[2].

O detalhamento dos status e o ciclo de vida do reporte são detalhados no tópico sobre [processamento](../../../../../../OF/Open%20Finance%20Brasil/Especifica%c3%a7%c3%b5es%20de%20Integra%c3%a7%c3%a3o/Plataforma%20de%20Coleta%20de%20M%c3%a9tricas/Especifica%c3%a7%c3%a3o%20T%c3%a9cnica/Reporte,%20Processamento%20e%20Diverg%c3%aancias/Processamento).

* * *

[1]: A documentação das APIs do Open Finance Brasil define os cabeçalhos padrão para uma chamada. O detalhamento de cada cabeçalho pode ser encontrado em [Cabeçalhos HTTP](https://openbanking-brasil.github.io/areadesenvolvedor/#cabecalhos-http)

[2]: Definição de Consistência Tardia ou Posterior - [Inglês](https://en.wikipedia.org/wiki/Eventual_consistency)/[Português](https://pt.wikipedia.org/wiki/Consist%C3%AAncia_posterior)

* * *

Próximo: [Processamento](../../../../../../OF/Open%20Finance%20Brasil/Especifica%c3%a7%c3%b5es%20de%20Integra%c3%a7%c3%a3o/Plataforma%20de%20Coleta%20de%20M%c3%a9tricas/Especifica%c3%a7%c3%a3o%20T%c3%a9cnica/Reporte,%20Processamento%20e%20Diverg%c3%aancias/Processamento)

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/37879861)