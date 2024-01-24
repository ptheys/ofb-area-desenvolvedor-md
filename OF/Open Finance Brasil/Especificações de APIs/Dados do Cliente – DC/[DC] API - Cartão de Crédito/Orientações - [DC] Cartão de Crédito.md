[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/157417473)

| **Consentimento**​ |
| --- |
| **Modelo:**​ | Compartilha todos os recursos <u>selecionados pelo cliente</u>​ |
| **Recursos passíveis de confirmação pelo cliente**​ | <ul><li><p>Conta Cartão ativa em um período de até 12 meses anterior ao início da vigência do consentimento;​</p></li><li><p>Conta cartão cancelada/encerrada em um período de até 12 meses anterior ao início da vigência do consentimento;​</p></li></ul> |
| **Recursos que não devem ser escopo de confirmação pelo cliente**​ | <ul><li><p>Conta cartão que não está efetivamente ativa e visível nos canais eletrônicos​</p></li><li><p>Conta cartão cancelada/encerrada em um período maior que 12 meses anterior ao início da vigência do consentimento;​</p></li><li><p>Conta cartão que pertence a clientes que estão sob algum tipo de bloqueio que implique em indisponibilidade do produto no canal eletrônico conforme políticas internas das instituições​</p></li></ul> |

### Recomendações do uso de *polling*

É recomendado que a instituição receptora implemente um retry exponencial (o tempo de espera entre a última chamada e a próxima chamada da API deve crescer exponencialmente), de forma a não sobrecarregar a API Recursos.

### Diagrama representacional do status da API Recursos

|  | **Consentimento (ex. 4 meses)** |
| --- | --- |
| **Cenários** | **DIA D** | **D+1M** | **D+2M** | **D+3M** | **D+4M** | **D+5M** |
| Produto cancelado/encerrado em D -13M | Não é escopo de compartilhamento |  |  |  |  |  |
| Produto cancelado/encerrado em D -11M | AVAILABLE | AVAILABLE | UNAVAILABLE | UNAVAILABLE | UNAVAILABLE | Acesso a API não autorizado |
| Produto cancelado/encerrado em D +2M | AVAILABLE | AVAILABLE | AVAILABLE | AVAILABLE | AVAILABLE | Acesso a API não autorizado |

**Glossário:**

- **Dia D** – dia do consentimento.
- **Eixo X** - representa o tempo em meses.
- **Eixo em Y** – representa o cenários que são produtos e suas vigências. Ex.: conta cartão cancelada/encerrada a 13 meses • O encontro dos eixos representa o status da API Recursos naquele tempo para aquele produto.

### Regras para o retorno das API Cartão de Crédito de acordo com o status do Recurso (PENDING\_AUTHORISATION, AVAILABLE, UNAVAILABLE e TEMPORARILY\_UNAVAILABLE) e a transição entre status

**PENDING\_AUTHORISATION**: indica a existência de pendências para o compartilhamento do recurso, em caso de múltiplas alçadas, quando é necessário o consentimento de mais de um titular. Neste caso a Transmissora deve retornar um erro HTTP Status Code 403 - Forbidden com o conteúdo abaixo:

{

“code”: “STATUS\_RESOURCE\_PENDING\_AUTHORISATION”,

“title”: “Aguardando autorização de múltiplas alçadas”,

“detail”: “(uso a critério do transmissor)”

}

**AVAILABLE**: indica que o recurso do produto conta cartão escolhido encontra-se disponível para consulta nas API Cartão de Crédito através do identificador creditCardAccountId compartilhado. A Transmissora retorna os dados com status HTTP 200

**UNAVAILABLE**: indica que o recurso (conta cartão) se encontra indisponível para consulta na API Cartão de Crédito. Neste caso a Transmissora deve retornar um erro HTTP Status Code 403 - Forbidden com o conteúdo abaixo:

{

“code”: “STATUS\_RESOURCE\_UNAVAILABLE”,

“title”: “Recurso indisponível”,

“detail”: “(uso a critério do transmissor)”

}

**TEMPORARILY\_UNAVAILABLE**: indica que o recurso (conta cartão) se encontra temporariamente indisponível para consulta na API Cartão de Crédito do produto em questão. Neste caso a Transmissora deve retornar um erro HTTP Status Code 403 - Forbidden com o conteúdo abaixo:

{

“code”: “STATUS\_RESOURCE\_TEMPORARILY\_UNAVAILABLE”,

“title”: “Recurso temporariamente indisponível”,

“detail”: “(uso a critério do transmissor)”

}

### Casos de uso de contas cartões e o respectivo status a ser informado pela API Recursos

- Contas Cartão que se encontram em plena utilização e disponível nos canais de atendimento eletrônico devem ter seu status como AVAILABLE.
- Conta cartão cancelada/encerrada nos últimos 12 meses anteriores a data consulta – considerando o consentimento vigente - devem ter seus status como AVAILABLE.
- Conta Cartão cancelada/encerrada a mais que 12 meses anteriores a data consulta –considerando o consentimento vigente - devem ter seus status como UNAVAILABLE.
- Conta cartão cancelada/encerrada, em situações nas quais o cliente não mais possua acesso aos canais de atendimento eletrônico da instituição, devem retornar o status UNAVAILABLE.
- Conta cartão que se encontra em bloqueio temporário, onde o cliente não possui acesso aos detalhes por meio dos canais de atendimento eletrônico, devem retornar o status TEMPORARILY\_UNAVAILABLE.
- Conta cartão que se encontra em bloqueio definitivo onde o cliente não possui acesso por meio dos canais de atendimento eletrônico, devem retornar o status UNAVAILABLE.
- Conta cartão ativa com plásticos bloqueados (ex. virtual, adicional ou físico), visualizada pelo cliente nos canais eletrônicos da instituição, deve ter seu status como AVAILABLE.
- Conta cartão ativa para a qual ainda não houve desbloqueio de nenhum plástico - visualizada pelo cliente nos canais eletrônicos da instituição -deve ter seu status como AVAILABLE.
- Conta cartão que não está ativa e não pode ser visualizada pelo cliente no canal, como por exemplo as que são criadas “dormentes”, e dependem de ação do cliente para que se tornem ativas não devem ser compartilhadas.
- Casos de uso que um cliente final efetue um consentimento para conta cartão para o qual um dos recursos (respeitando a RN001) exija a aprovação de múltiplas alçadas (PENDING\_AUTHORISATION) e outro recurso esteja disponível para consulta (AVAILABLE), o comportamento esperado é que cada recurso tenha seu status representado de forma independente, disponibilizando imediatamente os recursos já aprovados.

### Tabela descritiva das possibilidades de interação entre API Recursos e as API Cartão de Crédito:

| **Cenário** | **Status do recurso na detentora** | **API Recursos (.../resources/v1/resources)** | **API de listagem de Produto (/accounts)¹** | **APIs de Identificação da Conta (/accounts/{creditCardAccountId}²** |
| --- | --- | --- | --- | --- |
| Sem consentimento | - | 401 unauthorized | 401 unauthorized | 401 unauthorized |
| Com consentimento não autorizado | - | 401 unauthorized | 401 unauthorized | 401 unauthorized |
| Com consentimento autorizado (pendente múltipla alçada) | - | 200 - Retorna recurso com status PENDING\_ AUTHORISATION | 200 Não retorna | 403 forbidden |
| Com consentimento autorizado (aprovado múltipla alçada) | OK | 200 - Retorna o recurso com status AVAILABLE | 200 retorna o recurso na lista | 200 retorna dados para o recurso |
| Com consentimento autorizado (aprovado múltipla alçada) | Bloqueio Temporário | 200 - Retorna o recurso com status TEMPORARY\_ UNAVAILABLE | 200 Não retorna na lista o recurso “bloqueado” | 403 forbidden |
| Com consentimento autorizado (aprovado múltipla alçada) | Cancelado/Encerrado | 200 - Retorna o recurso como status AVAILABLE | 200 retorna o recurso na lista | 200 retorna o recurso na lista |
| Com consentimento autorizado (aprovado múltipla alçada) | Cancelado/Encerrado a mais de 12 meses (recurso nunca compartilhado na vigência do consentimento) | 200 – Não retorna o recurso | 200 – Não retorna o recurso | 403 forbidden |
| Com consentimento autorizado (aprovado múltipla alçada) | Cancelado/Encerrado a mais de 12 meses (recurso já compartilhado na vigência do consentimento) | 200 - Retorna o recurso como status UNAVAILABLE | 200 – Não retorna o recurso | 403 forbidden |
| Com consentimento autorizado (recusado múltipla alçada) | - | 200 - Retorna recurso com status UNAVAILABLE | 200 - Não retorna recurso recusado na lista | 403 forbidden |
| Com consentimento autorizado (conta inexistente) | - | 200 – Não retorna o recurso | 200 – Não retorna o recurso | 403 forbidden |
| Com consentimento revogado ou expirado¹ | - | 401 unauthorized | 401 unauthorized | 401 unauthorized |

### Regras quanto a interpretação pelas receptoras do status da API Recursos para os recursos de cartões

- **PENDING\_AUTHORISATION**: neste caso a recomendação é que a Receptora aguarde a alteração desse status para um dos demais status executando polling na API Recursos (vide recomendações de polling).
- **AVAILABLE**: indica que o recurso encontra-se disponível para consulta na API Cartão de Crédito através do identificador creditCardAccountId compartilhado.
- **UNAVAILABLE**: neste status a recomendação é que a Receptora não consulte a API Cartão de Crédito em função do dado não estar disponível para esse creditCardAccountId.
- **TEMPORARILY\_UNAVAILABLE**: neste status a recomendação é que a Receptora aguarde a alteração desse status para um dos demais status executando polling na API Recursos (vide recomendações de polling).

### Regras de busca na API Recursos em relação aos recursos da API Cartão de Crédito:

- Recomenda-se que a Receptora consulte a API Recursos logo após identificar que o consentimento se encontra autorizado de modo a obter as contas cartão consentida pelo cliente e seus respectivos identificadores.
- Recomenda-se que a Receptora, caso obtenha um erro HTTP Status Code 403 - Forbidden na API Cartão de Crédito avalie o JSON retornado no body da requisição para identificar as informações adicionais referentes ao erro, como o status específico da API Recursos que impede o consumo da informação.
- Recomenda-se que a Receptora consulte a API Recursos caso obtenha um erro na API Cartão de Crédito, de modo a identificar uma possível alteração de status do recurso.

### Quanto ao erro 422:

Na especificação técnica existe a possibilidade de retornar o código HTTP Status Code 422 - accepted. Este código de retorno deve ser utilizado quando algum parâmetro da consulta for enviado semanticamente incorreto, ou seja, desrespeitando uma regra de negócio, para os seguintes *endpoints*:

- /accounts/{creditCardAccountId}/bills;
- /accounts/{creditCardAccountId}/{billId}/transactions;
- /accounts/{creditCardAccountId}/transactions;
- /accounts/{creditCardAccountId}/transactions-current.

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/157417473)