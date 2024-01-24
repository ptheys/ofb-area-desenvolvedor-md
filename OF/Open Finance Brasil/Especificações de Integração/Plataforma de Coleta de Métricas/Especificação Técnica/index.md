[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/37945356)

# Introdução

A plataforma de Coleta de Métricas foi idealizada com o objetivo de contabilizar as interações entre as instituições participantes, de modo a promover um ambiente equitativo e não discriminatório. Se trata de uma plataforma localizada no perímetro central, gerida pelo regulador do ecossistema.

## Motivação

Para que o ecossistema do Open Finance Brasil seja saudável para instituições e clientes finais, fez-se necessária a criação de uma plataforma que deverá concentrar dados sobre as chamadas que as instituições fazem umas às outras. Dessa forma, torna-se possível coletar informações com o objetivo de se criar métricas e indicadores a fim de se ter visibilidade sobre todo o ambiente.

No intuito de manter a integridade e consistência nos dados, o envio destes pelas instituições deverá passar por um processo de conciliação. Quando divergente, as instituições serão notificadas e terão a possibilidade de ajustar as chamadas, o que promove um ambiente saudável de auto-regulação, prevenindo assim uma disputa.

## O que a plataforma não é

A plataforma recebe os dados de maneira póstuma, ou seja, dentro do período de fechamento, mas depois de a chamada concreta ter sido feita. Dada essa natureza, a plataforma não pode atuar como um agente que proíbe, bloqueia ou interfere nas interações entre as instituições.

Por mais que concentre informações importantes das chamadas entre as instituições, a plataforma não é uma ferramenta de BI, e o controle de acesso aos dados é feito em diferentes níveis (participante, regulador e administrador).

## Premissas Técnicas

- Tanto o envio por parte dos participantes quanto o processamento por parte da plataforma serão feitos de maneira assíncrona;

# Terminologia

Os termos abaixo estão no contexto da Plataforma de Coleta de Métricas, que por sua vez está no contexto do Open Finance Brasil.

## Client e Server

Em uma interação, a parte que solicita os dados é chamada de *client*, ao passo que a parte que devolve os dados é o *server*. Portanto, supondo que A faça uma consulta em B pelos dados de uma conta, esses dados vão ser transmitidos por quem recebeu a solicitação, e recebidos por quem a fez, nesse caso, "A" é o client e "B" é o server. Em contextos onde os termos "transmissor" e "receptor" são utilizados, eles passam a significar "server" e "client" respectivamente.

## PCM

Acrônimo para Plataforma de Coleta de Métricas.

## Reporte

No contexto da API de Coleta de Métricas, um *reporte* é o registro da chamada que será enviado tanto pelo server quanto pelo client. Esse registro será armazenado na Plataforma para posterior processo de conciliação de chamadas e extração de dados estatísticos.

## Software Statement

Um participante do Open Finance é sempre identificador pelo seu `organisationId` (com "s"). Um `organisationId` um ou mais software statements, que identifica uma instancia de software autorizada a consumir os serviços do ecossistema. 

* * *

Próximo: [Reporte, Processamento e Divergências](../../../../../OF/Open%20Finance%20Brasil/Especifica%c3%a7%c3%b5es%20de%20Integra%c3%a7%c3%a3o/Plataforma%20de%20Coleta%20de%20M%c3%a9tricas/Especifica%c3%a7%c3%a3o%20T%c3%a9cnica/Reporte,%20Processamento%20e%20Diverg%c3%aancias/index)

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/37945356)