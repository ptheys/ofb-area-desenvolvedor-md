[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17377105)

## **API de status**: (GET /discovery/v1/status)

### Visão geral

Obtém a descrição referente ao código de status retornado pelas APIs.

## **API de outages**: (GET /discovery/v1/outages)

### **Visão geral**

Obtêm a lista de indisponibilidade agendada para os serviços.

### **Exemplo de código**

Na estrutura de retorno exemplificada abaixo, no caso em que o parâmetro isPartial devolvido seja true, o array unavailableEndpoints deve conter a lista de endpoints indisponíveis:

    {
      "data": {
        "outages": [
          {
            "outageTime": "2020-07-21T08:30:00Z",
            "duration": "PT2H30M",
            "isPartial": false,
            "explanation": "Atualização do API Gateway",
            "unavailableEndpoints": [
              "https://api.banco.com.br/open-banking/discovery/v1/outages"
            ]
          }
        ]
      },
      "links": {
        "self": "https://api.banco.com.br/open-banking/discovery/v1/outages"
      },
      "meta": {
        "totalRecords": 1,
        "totalPages": 1
      }
    }

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17377105)