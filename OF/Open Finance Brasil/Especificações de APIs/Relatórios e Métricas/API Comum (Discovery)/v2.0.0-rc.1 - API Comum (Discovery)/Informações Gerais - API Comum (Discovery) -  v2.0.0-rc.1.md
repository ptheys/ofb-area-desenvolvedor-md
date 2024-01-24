[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/266895400)

### Contexto: 

Conforme IN nº 306 de 19/02/2022, o Item 2 do Anexo lista todas as APIs integrantes do Open Finance. Dentre elas, as APIs de Métricas são comum a todos os participantes do Open Finance Brasil, independentemente da fase de adesão.

| Relatórios e Métricas | Situação do Ambiente | Deve dar acesso a dados sobre a disponibilidade atual das implementações das APIs, bem como a dados sobre indisponibilidades programadas. |
| --- | --- | --- |
| Métricas | Deve dar acesso a dados de performance de todas as APIs disponibilizadas. |

Sendo assim: 

1. Todas as instituições devem publicar essas APIs que monitoram a situação do ambiente;
2. API Comum (Discovery) deve reportar os dados de disponibilidade e indisponibilidade programada de** todas as APIs **que a instituição oferece;
3. API Comum (Discovery) deve ser atualizada conforme lançamento de novas APIs pela instituição ou atualização das APIs já existentes.

## GET /discovery/v2/status.

### Visão geral

A instituição deve disponibilizar o código de status de todas as suas APIs nesse endpoint

### Visão de alto nível das estruturas de dados
![att266895414](Informa%c3%a7%c3%b5es%20Gerais%20-%20API%20Comum%20(Discovery)%20-%20%20v2.0.0-rc.1/attachments/comuns%20-%20alto%20nivel.png)

### Dicionário de dados

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/getStatus_v2.csv)

### Exemplo de código

Na estrutura de retorno exemplificada abaixo, o campo "explanation" opcionalmente pode conter os endpoints indisponíveis, além da explicação sobre os motivos:

    {
      "data": {
        "status": [
          {
            "code": "PARTIAL_FAILURE",
            "explanation": "Um ou mais endpoints estão indisponíveis",
            "detectionTime": "2020-07-21T08:30:00Z",
            "expectedResolutionTime": "2020-07-21T08:30:00Z",
            "updateTime": "2020-01-02T01:00:00Z",
            "unavailableEndpoints": [
              "https://api.banco.com.br/open-banking/channels/v2/electronic-channels"
            ]
          }
        ]
      },
      "links": {
        "self":  "https://api.banco.com.br/open-banking/common/v2/resource",
        "first": "https://api.banco.com.br/open-banking/common/v2/resource",
        "prev":  "https://api.banco.com.br/open-banking/common/v2/resource",
        "next":  "https://api.banco.com.br/open-banking/common/v2/resource",
        "last":  "https://api.banco.com.br/open-banking/common/v2/resource"
      },
      "meta": {
        "totalRecords": 1,
        "totalPages": 1
      }
    }

## GET /discovery/v2/outages.

### Visão geral

A instituição deve disponibilizar previamente a previsão de indisponibilidade agendada dos seus serviços através desse endpoint.

### Visão de alto nível das estruturas de dados
![att266895417](Informa%c3%a7%c3%b5es%20Gerais%20-%20API%20Comum%20(Discovery)%20-%20%20v2.0.0-rc.1/attachments/outages-Vis%c3%a3o%20de%20alto%20n%c3%advel%20das%20estruturas%20de%20dados.png)
### Dicionário de dados

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/getOutage_v2.csv)

### Exemplo de código

Na estrutura de retorno exemplificada abaixo, o campo "explanation" opcionalmente pode conter os endpoints indisponíveis, além da explicação sobre os motivos:

    {
      "data": [
        {
          "outageTime": "2020-07-21T08:30:00Z",
          "duration": "PT2H30M",
          "isPartial": false,
          "explanation": "Atualização do API Gateway"
        }
      ],
      "links": {
        "self": "https://api.banco.com.br/open-banking/channels/v2/<resource>",
        "first": "https://api.banco.com.br/open-banking/channels/v2/<resource>",
        "prev": "https://api.banco.com.br/open-banking/channels/v2/<resource>",
        "next": "https://api.banco.com.br/open-banking/channels/v2/<resource>",
        "last": "https://api.banco.com.br/open-banking/channels/v2/<resource>"
      },
      "meta": {
        "totalRecords": 1,
        "totalPages": 1
      }
    }

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/266895400)