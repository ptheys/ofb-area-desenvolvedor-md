[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/159318087)

Para as **iniciadoras **de pagamento/receptoras de dados se **habilitarem** a **receber as notificações de Webhook** junto as **detentoras **de conta/transmissoras de dados, foi definido **campos a serem inseridos** no **Software Statement **e **DCR/DCM**.

## Registro

### Diretório

**Iniciadoras **de pagamentos e/ou Receptora de dados: Precisam **cadastrar **a sua** URI base** (&lt;host&gt;) no **diretório de participantes** no campo “**API Webhook**”.

### DCR/DCM

#### Definição do Swagger de DCR/DCM

    	{"webhook_uris": [	"<uri base para o webhook>"],...}

#### Prazo para sincronização

As **detentoras **de conta e transmissoras de dados devem **sincronizar **o seu mecanismo de **notificações por Webhook** com o fluxo **DCR/DCM** de modo que as notificações para as **iniciadoras **de pagamento e receptoras de dados se iniciem em até **10 minutos após a execução do DCR/DCM**.

### Software Statement

#### Definição do campo do Software Statement:

    	{"software_api_webhook_uris": [	"<uri base para o webhook>"],...}

**Para mais detalhes sobre consultas e regras de validações,consultar a página do Dynamic Client Registration no Portal do Desenvolvedor.**

[PT]  Open Finance Brasil Financial-grade API Dynamic Client Registration 1.0 Implementers Draft 3   

- *Itens 18 e 19.*

## URI base

A **URI base** para o **Registro **do **DCR/DCM e Software Statement**, devem ser iguais, conforme exemplo abaixo:

- URL base - https://itp.com/kong3

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/159318087)