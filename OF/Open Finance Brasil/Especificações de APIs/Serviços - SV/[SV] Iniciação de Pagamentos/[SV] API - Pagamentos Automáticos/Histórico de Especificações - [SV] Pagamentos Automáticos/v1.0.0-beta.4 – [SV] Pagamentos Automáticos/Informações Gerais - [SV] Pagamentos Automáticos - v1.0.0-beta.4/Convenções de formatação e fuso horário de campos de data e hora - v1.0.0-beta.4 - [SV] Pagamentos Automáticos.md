[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/234258678)

**Date**  
Campos onde o tipo é string($date), o formato utilizado é AAAA-MM-DD.  
Exemplo: 2022-12-01, esse formato é especificado pela RFC-3339.  
Seu fuso horário atual é o horário de Brasília UTC-3.

**DateTime**  
Campos onde o tipo é string($date-time), o formato utilizado é AAAA-MM-DDTHH:MM:SSZ, onde T e Z são marcações, representando T a divisão entre data e horário e Z o timezone UTC.   
Exemplo: 2022-12-01T08:30:00Z, esse formato é especificado pela RFC-3339.  
Seu fuso horário atual é o UTC.

*Existem algumas inconsistências nas descrições de alguns campos no swagger da API de Serviços - Iniciação de Pagamentos, porém ao implementar leve em consideração as informações aqui registradas.*

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/234258678)