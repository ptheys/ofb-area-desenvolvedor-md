[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17377564)

## **Especificações da Fase 1 do Open Finance Brasil**

Apresentamos neste item orientações para problemas conhecidos da Fase 1 do Open Finance Brasil. Na tabela a seguir, listamos a versão de problemas identificados e seu direcionamento.

| API/Menu | Endpoint/Submenu | Campo/detalhe | Problema | Orientação |
| --- | --- | --- | --- | --- |
| API Admin | GET /metrics | schema AverageMetrics - currentDay e previousDays | O swagger não detalha a necessidade de fornecer resposta nesses campos em milissegundos, causando erros de apropriação no dashboard para algumas instituições. | Publicada orientação na página principal do portal, os campos são do tipo inteiro (e não number) e deve-se considerar milissegundos até o ajuste explícito no swagger. |

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17377564)