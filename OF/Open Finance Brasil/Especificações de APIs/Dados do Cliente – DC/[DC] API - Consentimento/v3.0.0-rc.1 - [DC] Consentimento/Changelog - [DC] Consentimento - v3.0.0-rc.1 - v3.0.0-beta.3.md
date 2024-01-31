[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/277413986)

[![](https://openfinancebrasil.atlassian.net/wiki/download/thumbnails/277413986/Changelog%20-%20%5BDC%5D%20Consentimento%20-%20v3.0.0-rc.1%20-%20v3.0.0-beta.3.csv?version=1&amp;modificationDate=1706726299781&amp;cacheVersion=1&amp;api=v2&amp;viewType=fileMacro)](/wiki/download/attachments/277413986/Changelog%20-%20%5BDC%5D%20Consentimento%20-%20v3.0.0-rc.1%20-%20v3.0.0-beta.3.csv?version=1&amp;modificationDate=1706726299781&amp;cacheVersion=1&amp;api=v2) 

## GET /consents/{consentId}/extensions

### Request

| **Campo** | **O que foi alterado?** | **Tipo da Alteração** | **Antes** | **Depois** |
| --- | --- | --- | --- | --- |
| get/parameters | Adicionado - "page" | Adição |  |  |
| get/parameters | Adicionado - "page-size" | Adição |  |  |

### Response

| **Campo** | **O que foi alterado?** | **Tipo da Alteração** | **Antes** | **Depois** |
| --- | --- | --- | --- | --- |
| get/responses/200/meta/properties | Mandatoriedade | Adição |  | required |
| get/responses/200/meta/properties | Adicionado - "totalPages" | Adição |  |  |
| get/responses/200/meta/properties | Mandatoriedade | Adição |  | required |
| get/responses/200/meta/properties | Adicionado - "totalRecords" | Adição |  |  |

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/277413986)