[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17377516)

Os padrões de Open Finance podem não cobrir todas as possibilidades de objetos retornados ou APIs que os participantes desejam expor. Os participantes podem ter o desejo de realizar inovações sobre os padrões definidos oferecendo mais dados afim de atender demandas específicas de mercado. É nossa intenção que os padrões definidos não apenas permitam estas extensões como também sirvam como base para futuras alterações na própria definição dos padrões.

No entanto, é importante que um participante que esteja querendo estender as APIs não impeça um consumidor que foi projetado para consumir apenas o *endpoint* padrão funcione corretamente.

Para atender tanto as demandas de quem deseja estender as APIs (participantes) quanto as demandas de quem irá realizar o consumo (consumidor das APIs), foram definidos os critérios abaixo.

É possível estender os padrões nos seguintes aspectos:

- O participante pode oferecer **uma API** completamente nova que não está coberta nos padrões definidos
- O participante pode oferecer **novos endpoints** em uma API que já foi definida no padrão
- O participante pode oferecer **campos de entrada e retorno opcionais** para um endpoint que já foi definido no padrão

## **ID dos participantes**

Participantes que desejam estender os padrões devem adicionar seu prefixo para identificar todas as extensões. Campos adicionais no retorno de *endpoints* existentes ou em novos *endpoints* devem usar o prefixo do participante. O prefixo deve ser no formato exposto ao lado (4 letras) e não devem haver prefixos duplicados entre os participantes.

Nesta documentação, quando tivermos que nos referir ao prefixo do participante, o termo `<PID>` será utilizado.  
  
**Exemplos de Código**

Cada participantes terá um ID que representa a sua instituição. Os participantes da atual versão estão listados abaixo:

- BBAS - Banco do Brasil
- BBCD - Bradesco
- BTGP - BTG Pactual
- CAIX - Caixa Econônica Federal
- ITAU - Itau
- STDR - Santander
- BRGS - Banrisul
- BNBR - Banco do Nordeste do Brasil
- BNDS - BNDES
- CITI - Citibank
- SAFR - Safra
- BABV - Votorantim

## **Novas APIs**

Quando a extensão for a criação de uma nova API, o participante deve adicionar seu prefixo a URI antes do nome da nova API, conforme exemplo abaixo.

Por exemplo, uma API definida pelo padrão seguirá o seguinte formato: `<host> / open-banking / <api> / <versão> / <recurso>`

Uma API estendida por um participante deverá estar no formato abaixo: `<host> / open-banking / <PID> / <api> / <versão> / <recurso>`

Para os *endpoints* definidos dentro da estrutura acima, os atributos dos *payloads* não precisam conter o prefixo do participante, pois entende-se que todos os recursos da API estendida não conflitam de nenhum modo com as definidas pelo padrão.

| **Importante:**<br><ul><li><p>Este método <strong>não deve</strong> ser usado para criar duplicações modificadas dos *endpoints* já definidos no padrão.</p></li><li><p>Os novos *endpoints* <strong>devem</strong> atender às convenções e princípios do padrão, incluindo convenções de nomes e tipos de dados.</p></li></ul> |
| --- |

## **Novos endpoints em APIs existentes**

Quando o participante desejar adicionar um novo *endpoint* em uma API já especificada no padrão, o participante deve incluir seu `<PID>` como prefixo do recurso que será implementado.

Por exemplo, assumindo a existência do *endpoint* abaixo para consulta das transações de uma conta: `<host>/open-banking/accounts/v1/accounts/{account ID}/transactions`

Se o participante deseja adicionar um novo *endpoint* que resume as transações por um período, então este *endpoint* poderia ser definido como: `<host>/open-banking/accounts/v1/accounts/{account ID}/<PID>-balance-movement`

| **Importante:**<br><ul><li><p>O prefixo deve ser adicionado antes do nome do recurso seguido por um hífen. (-)</p></li><li><p>Como o *endpoint* é novo, os atributos do *payload* de requisição e resposta não precisam conter o prefixo do participante.</p></li><li><p>Se um *endpoint* possuir múltiplos níveis na URI do recurso, apenas o recurso mais a direita deverá possuir o prefixo do participante.</p></li><li><p>Os novos *endpoints* <strong>devem</strong> atender às convenções e princípios do padrão, incluindo convenções de nomes e tipos de dados.</p></li></ul> |
| --- |

## **Campos de retorno adicionais em um endpoint existente**

Quando o participante desejar adicionar um novo campo ao *payload* de resposta, o atributo deverá receber o prefixo do participante seguido por um hífen `<PID>-`.

Se um objeto estiver sendo adicionado ao *payload* de resposta, apenas o nome do objeto precisa receber o prefixo. Qualquer atributo dentro do novo objeto pode ser nomeado normalmente.

| **Importante:**<br><ul><li><p>Campos existentes <strong>não devem</strong> ser modificados. Isto inclui adicionar novas opções em campos do tipo Enum.</p></li><li><p>Um campo obrigatório <strong>não deve</strong> se tornar opcional como resultado de uma extensão.</p></li><li><p>*Payloads* de requisição também podem ser estendidos, porém o resultado ainda deve respeitar os padrões definidos caso o campo de extensão não tenha sido utilizado (por definição, campos adicionais no *payload* de *request* devem ser opcionais).</p></li><li><p>Parâmetros de *query* <strong>podem</strong> ser adicionados desde que seguidas as mesmas premissas de um novo campo no *payload* de requisição (com prefixo, não obrigatório e sem efeitos colaterais caso não seja informado).</p></li><li><p>Parâmetros por *header* <strong>podem</strong> ser adicionados desde que seguidas as mesmas premissas de um novo campo no *payload* de requisição. No entanto, seu prefixo deve estar no formato `x--`.</p></li><li><p>Novos campos <strong>devem</strong> atender os padrões definidos de nomenclatura e tipos de dados.</p></li></ul> |
| --- |

## **Parâmetros query adicionais**

Quando for adicionado um novo parâmetro de *query* a um *endpoint* existente, o novo parâmetro deve ter o prefixo `<PID>-`, evitando assim colisões com parâmetros já existentes.

## **Filtro de Dados**

Opcionalmente, a entidade transmissora de dados poderá realizar filtro de dados através de *query* de entrada, baseado em campos que julgue relevante para a melhor experiência do cliente.  
A informação de quais possibilidades estarão disponíveis (*query parameter*) deverá constar em documentação adicional disponibilizada pela entidade transmissora.

## **Extensão do versionamento**

Como descrito na seção versionamento, o versionamento existe apenas no nível das APIs e não no nível dos *endpoints*, no entanto caso seja necessário realizar versionamento de um *endpoint* customizado, o participante poderá utilizar o *header* `x-<PID>-v` para que o consumidor possa especificar qual versão do *endpoint* está requisitando.

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17377516)