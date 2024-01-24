[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17377445)

### Propriedades

| Tipo | Descrição | Exemplos válidos |
| --- | --- | --- |
| AmountString | <ul><li><p>Uma <em>string</em> que representa um valor monetário.</p></li><li><p>Um número positivo, zero ou negativo.</p></li><li><p>Sem o símbolo da moeda.</p></li><li><p>Com pelo menos 1 e no máximo 16 dígitos antes do ponto decimal.</p></li><li><p>Com no mínimo 2 dígitos (mais dígitos são permitidos, porém não obrigatórios).</p></li><li><p>Sem formatação adicional. Ex: Separador de milhar.</p></li></ul> | "1.37"  <br>"54.85"  <br>"3456928.98"  <br>"-2387.02" |
| Boolean | <ul><li><p>Valor booleano padrão.</p></li></ul> | true  <br>false |
| CurrencyString | <ul><li><p>Uma <em>string</em> que representa a abreviação da moeda conforme especificação ISO-4217.</p></li></ul> | "BRL"  <br>"USD"  <br>"EUR" |
| DateTimeString | <ul><li><p>Campos onde o tipo é string ($date-time), o formato utilizado é AAAA-MM-DDTHH:MM:SSZ, onde T e Z são marcações, representando T a divisão entre data e horário e Z o timezone UTC.</p></li><li><p>Seu fuso horário atual é o UTC e eventuais validações necessárias devem seguir essas definições.</p></li></ul> | 2022-12-01T08:30:00Z, esse formato é especificado pela RFC-3339 |
| DurationString | <ul><li><p>Uma <em>string</em> que representa um período de duração conforme especificação ISO-8601.</p></li></ul> | "P23DT23H"  <br>"PT2H30M" |
| Enum | <ul><li><p>Uma <em>string</em> que representa um domínio de valores</p></li><li><p>Todos os possíveis valores são definidos.</p></li><li><p>Os valores devem estar em letras maiúsculas.</p></li><li><p>Espaços em branco devem ser substituídos por _.</p></li><li><p>Artigos e preposições devem ser removidos.</p></li><li><p>Não devem possuir caracteres acentuados.</p></li></ul> | "PRIMEIRA\_OPCAO"  <br>"OUTRA\_OPCAO\_EXISTENTE" |
| *Integer* | <ul><li><p>Números inteiros.</p></li></ul> | -1  <br>0  <br>1 |
| RateString | <ul><li><p>Uma string que representa um valor percentual, tendo como referência que 100% é igual ao valor 1.</p></li><li><p>Com pelo menos 1 e no máximo 16 dígitos antes do ponto decimal.</p></li><li><p>Com no máximo 16 dígitos após o ponto decimal.</p></li><li><p>Sem formatação adicional. Ex: Separador de milhar.</p></li></ul> | "0.01"  <br>"0.1"  <br>"-0.05"  <br>"-0.98365"  <br>"0.1023" |
| *String* | <ul><li><p>Padrão de texto UTF-8 sem restrição de conteúdo.</p></li></ul> | "Uma *string* qualquer." |
| TimeString | <ul><li><p>Uma <em>string</em> que representa a hora conforme especificação RFC-3339,sempre com a utilização de timezone UTC(UTC time format).</p></li></ul> | "00:39:57Z" |
| URIString | <ul><li><p>Uma <em>string</em> que representa URI válida.</p></li></ul> | "[http://www.google.com.br](http://www.google.com.br) " |
| CountryCode | <ul><li><p>Código do pais de acordo com o código “alpha3” do ISO-3166.</p></li></ul> | "BRA" |
| IbgeCode | <ul><li><p>Código IBGE de Município. A Tabela de Códigos de Municípios do IBGE apresenta a lista dos municípios brasileiros associados a um código composto de 7 dígitos, sendo os dois primeiros referentes ao código da Unidade da Federação.</p></li></ul> | "3550308" |
| DateString | <ul><li><p>Campos onde o tipo é string ($date), o formato utilizado é AAAA-MM-DD.</p></li><li><p>Seu fuso horário atual é o horário de Brasília UTC-3 e eventuais validações necessárias devem seguir essas definições.</p></li></ul> | 2022-12-01, esse formato é especificado pela RFC-3339 |
| DateTimeMillesecond | <ul><li><p>Campos onde o tipo é string ($date-time) com precisão de milissegundos, o formato utilizado é  AAAA-MM-DDTHH:MM:SS.sssZ, onde T e Z são marcações, representando T a divisão entre data e horário e Z o timezone UTC.</p></li><li><p>Seu fuso horário atual é o UTC e eventuais validações necessárias devem seguir essas definições. </p></li></ul> | 2016-01-29T12:29:03.374Z |
| TimeStampMillesecond | <ul><li><p>Campos onde o tipo é interger ($int64) com precisão de milissegundos representa o número de milessegundos desde 1º de janeiro de 1970 a 00:00 no horário UTC.</p></li><li><p>Seu fuso horário atual é o UTC e eventuais validações necessárias devem seguir essas definições.</p></li></ul> | 1454070543374 |

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17377445)