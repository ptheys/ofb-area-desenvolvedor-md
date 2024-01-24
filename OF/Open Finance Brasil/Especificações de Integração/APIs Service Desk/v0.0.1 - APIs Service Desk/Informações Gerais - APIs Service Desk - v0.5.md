[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17377992)

# Especificação API Service Desk Open Finance Brasil

O objetivo desse documento é prover material para publicação das informações referentes a APIs do Service Desk no portal do Open Finance Brasil.

A Documentação completa e também utilizada como fonte deste conteúdo pode ser encontrada em: [https://community.sysaid.com/Sysforums/templates/default/help/files/Guide_REST_API.htm](https://community.sysaid.com/Sysforums/templates/default/help/files/Guide_REST_API.htm) 

# 1. Modelo de Fluxo de atendimento:
![att242483245](Informa%c3%a7%c3%b5es%20Gerais%20-%20APIs%20Service%20Desk%20-%20v0.5/attachments/image-20231219-181124.png)
# 2. URLs de acesso:

[https://servicedesk.openfinancebrasil.org.br/](https://servicedesk.openfinancebrasil.org.br/): Ambiente Produtivo do Service Desk Open Finance.

[https://servicedesksandbox.openfinancebrasil.org.br/](https://servicedesksandbox.openfinancebrasil.org.br/): Ambiente Sandbox (Homologação) do Service Desk Open Finance.

# 3. Tabela DE/PARA front-end para API

| **Nome do Campo** | **API** | **Detalhes** |
| --- | --- | --- |
| Categoria | problem\_type | 1ºNível\_2ºNível\_3ºNível / Na resposta: 1º Nível de Categoria |
| Subcategoria | problem\_sub\_type | Na resposta: 2º Nível de Categoria |
| Categoria de 3º Nível | third\_level\_category | Na resposta: 3º Nível de Categoria |
| Título | title |  |
| Descrição | description |  |
| Anotações | notes | {“userName”:{NOME DO USUÁRIO},”createDate”:{DATA EM MILISEGUNDOS},”text”:{TEXTO}} |
| Solução | solution |  |
| Atividades | activities | Iterações entre N1 e N2 |
| Data de solicitação | insert\_time | Em milisegundos |
| Data de modificação | uptade\_time | Em milisegundos |
| Data de encerramento | close\_time | Em milisegundos |
| Prazo de SLA | due\_date | Em milisegundos |
| Data Prevista para Implementação da<br><br>Correção | CustomColumn82sr | Necessária quando utilizado o status “AGUARDANDO CORREÇÃO N2” em categorias de Incidentes |
| Usuário Solicitante | request\_user |  |
| Equipe de Atendimento | assigned\_group |  |
| Especialista Atribuído | responsibility |  |
| Status | status | Conferir lista de status |
| Contador de Reabertura | reopen\_counter | Número de vezes que o chamado foi reaberto |
| Anexos | attachments |  |
| Tipo de Registro de<br><br>Serviço | sr\_type |  |
| Arquivado | arquive | Tipo Booleano |
| Nível de Suporte Atual | current\_support\_level |  |
| Tipo do Chamado | type | Incidentes = 1; Solicitação de Serviço = 10 |
| Formulário Utilizado | template | Padrão Incidente = 20; Padrão Solicitação de Serviço = 12 |
| O conteúdo da<br><br>reclamação é procedente? | CustomColumn129sr | Necessário o preenchimento ao encaminhar um chamado tipo Incidente para encerramento<br><br>(status: ENCAMINHADO N1 ENCERRAMENTO) |
| Tipo de Erro | CustomColumn119sr | Disponível apenas para consulta nos chamados da categoria “Erro na Jornada ou Dados” |

# **4. APIs**

Tipo de API: REST

Formato dos dados de retorno e envio: JSON Fonte do conteúdo:

[https://community.sysaid.com/Sysforums/templates/default/help/files/Guide_REST_API.htm](https://community.sysaid.com/Sysforums/templates/default/help/files/Guide_REST_API.htm) 

FAQ Service Desk: [<u>https://servicedesk.openfinancebrasil.org.br/KBFAQTree.jsp</u>](https://servicedesk.openfinancebrasil.org.br/KBFAQTree.jsp)

## 4.1 Login

Responsável pela autenticação na API, é pré-requisito para a execução de qualquer requisição. As credenciais devem ser solicitadas via Portal do Service Desk Open Finance.

É necessário um usuário Administrador (Atendimento N2) para a utilização da API.

#### POST - {URL}/api/v1/login

<u>Campos Obrigatórios:</u>

“user\_name” = Nome de usuário de integração “password” = Senha do usuário de integração

<u>Exemplo de Body:</u>

{"user\_name":"{NOME DO USUÁRIO}", "password":"{SENHA}"}

No retorno é necessário armazenar o Cookie JSESSIONID para consumo dos demais métodos.

Nesta requisição de login, também é necessário identificar o <u>ID do Grupo</u> de Atendimento que será utilizado nas requisições de <u>consulta de chamados</u>, para identificar este número na resposta deve ser capturado o valor do "id" na key "user\_groups". De acordo com o exemplo a seguir:

    "key": "user_groups",
    "value": [
    {
    "id": 10,
    "name": "N1 Service Desk", "type": 1,
    "supportLevel": 1, "visible": true
    }

## 4.2 Consulta de Chamados

Retorna todos os chamados, ativos e encerrados, que se encontram na equipe de atendimento do usuário autenticado, com exceção dos chamados que já foram arquivados. Neste tipo de requisição é necessário passar o parâmetro “assigned\_group” para que apenas os tickets pertencentes ao grupo de atendimento do usuário sejam retornados.

#### GET – {URL}/api/v1/sr?assigned\_group={ID do Grupo}

<u>Body:</u> Manter vazio

Para refinar a busca é necessário incluir parâmetros na requisição.

Estes são alguns exemplos de keys comuns a serem utilizadas:

“problem\_type” = Categoria: 1º nível\_2º nível\_3ºnível “status” = Qual status que o chamado se encontra “insert\_time” = Abertura do chamado

“due\_date” = SLA

Consultar a Tabela DE/PARA (Tópico 3.)

<u>Exemplo de requisição:</u>

#### GET – {URL}/api/v1/sr?problem\_type=Incidentes\_APIs\_Erros&assigned\_group=10

<u>Body:</u> Manter vazio

O retorno virá com todas as informações referentes aos chamados que entrarem nos parâmetros estabelecidos. Para retornar campos específicos na reposta é necessário utilizar a key “fields" na requisição e selecionar os parâmetros de retorno.

Estes são alguns exemplos de keys comuns a serem utilizadas:

“id” = ID do chamado

“update\_time” = Data e hora da última modificação “solution” = Solução do chamado

“request\_user” = Usuário Solicitante Consultar a Tabela DE/PARA (Tópico 3.)

<u>Exemplo de requisição:</u>

#### GET – {URL}/api/v1/sr?problem\_type=Incidentes\_APIs\_Erros&fields=id,update\_time&assigned\_group=10

Aplicando os mesmos parâmetros da requisição anterior, os chamados exibidos serão os mesmos, porém agora apenas a informações indicadas em “fields” serão exibidas em cada chamado respectivamente.

Existem outros parâmetros que podem ser consultados na Documentação Completa do SysAid (Tópico 4.)

<u>Exemplo de retorno:</u>

    [ {
    "id": "1273",
    "canUpdate": true, "canDelete": true, "canArchive": true, "hasChildren": false, "info": [
    {
    "key": "update_time", "value": 1646856953697,
    "valueClass": "",
    "keyCaption": "Data de modificação", "valueCaption": "09-03-2022 17:15:53"
    }
    ]
    },
    {
    "id": "1274",
    "canUpdate": true, "canDelete": true, "canArchive": true, "hasChildren": false, "info": [
    {
    "key": "update_time", "value": 1646862779347,
    "valueClass": "",
    "keyCaption": "Data de modificação", "valueCaption": "09-03-2022 18:52:59"
    } ]

## 4.3 Consulta de chamado específico

Traz todas as informações de um chamado específico, possível aplicar parâmetros de busca e de retorno para customizar a consulta.

#### GET – {URL}/api/v1/sr/{ID DO CHAMADO}

## 4.4 Abertura de Chamados

Abre um chamado para o Service Desk. Todos os campos a serem inseridos no chamado devem ser passados no Body da requisição.

Consultar a Tabela DE/PARA (Tópico 3.) para informar o “type” e “template”

Algumas categorias podem possuir formulários customizados, sendo necessário utilizar templates específicos e informar campos customizados. Nestes casos deve-se acessar a FAQ do Service Desk e consultar a categoria específica no seguinte link:

[<u>https://servicedesk.openfinancebrasil.org.br/KBFAQTree.jsp</u>](https://servicedesk.openfinancebrasil.org.br/KBFAQTree.jsp)

#### POST – {URL}/api/v1/sr?type={TIPO DE CHAMADO}&template={ID DO FORMULÁRIO}

<u>Campos Obrigatórios:</u>

“problem\_type” = Categoria (São 3 níveis de categorização, devem ser separados utilizando “\_”) “title” = Título

“description” = Descrição

<u>Exemplo de requisição:</u>

#### POST – {URL}/api/v1/sr?type=1&template=20

<u>Exemplo de Body:</u>

    {
    "info": [{"key":"problem_type", "value":"Incidentes_Diretório_Erro"},
    {"key":"title", "value":"Abertura de Chamado via API"},
    {"key":"description", "value":"Teste de abertura de incidente através de API."}]
    }

## 4.5 Alteração no Chamado

Alterar um chamado, modificando as informações. Todos os campos a serem modificados no chamado devem ser passados no Body da requisição.

(Para consultar a lista com os IDs dos Status, visite a FAQ).

#### PUT - {URL}/api/v1/sr/{ID DO CHAMADO}

<u>Exemplo de Body:</u>

    {
    "id": "1275",
    "info": [
    {"key":"status", "value": "8"},
    {"key":"notes", "value":
    [{"userName":"João Teste","createDate":1647019229000,"text":"Teste Nota"}]}
    ]
    }

## 4.6 Recuperado Anexos

Para consultar os anexos dentro do chamado é necessário a utilização do campo "attachments" na chave "fields", de acordo com o exemplo a seguir:

#### GET - {URL}/api/v1/sr/{ID do CHAMADO}?fields=attachments

<u>Body:</u> Manter vazio

<u>Exemplo de retorno:</u>

    "key": "attachments", "value": [
    {
    "fileId": "{ID do ANEXO}", "fileName": "nome_do_anexo.pdf", "realFileName": null, "chatSessionId": null,
    "fileDate": "22-10-2021 09:35"
    }
    ],

Com o ID do anexo contido no campo "fileId" você vai poder utilizar a URL de Download para obter o arquivo.

URL de download:

#### {URL}/getFile?table=service\_req&id={ID do CHAMADO}&getFile={ID do ANEXO}

## 4.7 Inserindo Atividades

Para utilizar o campo de atividades, deve ser feita a seguinte requisição:

#### POST – {URL}/api/v1/sr/{ID DO CHAMADO}/activity

Campos obrigatórios:

"id" = ID do chamado onde será adicionada a atividade "userId" = ID do usuário que está inserindo a atividade "fromTime" = Data e hora do início da atividade "toTime” = Data e hora do término da atividade "description” = Descrição da Atividade

Obs: A data e hora de início e término da atividade podem ser as mesmas, mas devem indicar o momento em que foi inserida a atividade.

<u>Exemplo do Body</u>:

    {
    "id": "2507",
    "userId":123456, "fromTime":1652904309000, "toTime":1652904309000,
    "description":"Adicionando Atividade via API"
    }

## 4.8 Consulta de chamados como solicitante

Além das consultas que podem ser feitas como Equipe de Atendimento dos chamados, para aqueles chamados que são abertos pelo seu usuário, tanto via API quanto via Portal do Usuário Final, também é possível fazer a consulta dos mesmos via API, para isso deve-se acrescentar um Header na requisição.

<u>Header:</u>

    Key: Referer
    Value: /servicePortal

Portanto ambas as requisições dos tópicos **4.2 **e **4.3 **podem ser executadas adicionando este novo header para efetuar as consultas no papel de usuário <u>solicitante</u>. Lembrando que mesmo efetuando a consulta como solicitante é pré-requisito que o seu usuário seja N2 (Administrador) e tenha as permissões necessárias para o consumo da API.

Caso o usuário seja supervisor, também será possível obter os chamados abertos por outros membros da instituição utilizando um parâmetro adicional no endpoint:

    Key: supervised
    Requests Value: Y

Como no exemplo a seguir:

#### GET - {URL}/v1/sr?status=1&fields=id,insert\_time,status&supervisedRequests=Y

## 4.9 Adição de notas como solicitante

Seguindo o que foi instruído no item **4.8 **além de fazer a consulta das informações, também é possível fazer a adição de notas ao chamado no papel de requisitante via API. Para isso é necessário a utilização do Header e executar o processo descrito no item **4.5 **seguindo os parâmetros para a adição de notas contida na Tabela DE/PARA no item **3.0 **deste documento:

    Key: notes
    Value: {“userName”:{NOME DO USUÁRIO},”createDate”:{DATA EM MILISEGUNDOS},”text”:{TEXTO}}

#### Requisição: **PUT - {URL}/api/v1/sr/{ID DO CHAMADO}**

<u>Exemplo do Body</u>:

    {
    "id": "1234",
    "info": [
    {"key":"notes", "value":
    [{"userName":"João Teste","createDate":1647019229000,"text":"Teste Nota"}]}
    ]
    }

É importante ressaltar que <u>não devem ser alterados os demais campos do chamado</u> incluindo o status, apenas a adição da nota deve ser executada e o chamado já terá o status alterado de forma automática pelo SysAid.

**Em caso de dúvidas ou dificuldades na utilização da API entrar em contato com o Service Desk através do Portal: **[**<u>https://servicedesk.openfinancebrasil.org.br/</u>**](https://servicedesk.openfinancebrasil.org.br/)

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17377992)