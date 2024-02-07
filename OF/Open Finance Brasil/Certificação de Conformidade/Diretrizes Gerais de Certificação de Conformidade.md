[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/280297514)

# Introdução

Esta página tem como objetivo principal dar as **diretrizes gerais** às instituições sobre como funcionam os processos de certificação de segurança e funcional. É recomendado, após a leitura desta página, um estudo mais aprofundado do [Guia de Certificação de Conformidade](../../../OF/Open%20Finance%20Brasil/Certifica%c3%a7%c3%a3o%20de%20Conformidade/Guia%20de%20Certifica%c3%a7%c3%a3o%20de%20Conformidade), contendo informações mais detalhadas e específicas para a execução dos testes e obtenção das certificações. Vale ressaltar que o Guia de Certificação está em contínuo processo de atualização, sendo passível de sofrer alterações. Qualquer dúvida em relação ao processo, fique à vontade para a submissão de tickets através do [Service Desk](https://servicedesk.openfinancebrasil.org.br/Login.jsp?gotoURL=servicePortal&amp;navLanguage=pt-BR).

# Informações Gerais

Para a entrada segura e assertiva no Ecossistema do Open Finance Brasil, a Estrutura de Governança disponibilizou um conjunto de ferramentas e infraestrutura para suportar o processo de testes e homologação dos produtos e serviços desenvolvidos pelas Instituições Participantes. Foram disponibilizados ambientes que habilitam ao participante:

- Realizar testes da camada de **segurança** de suas aplicações e posterior certificação dessas aplicações, utilizando a estrutura criada e mantida pela OpenID Foundation (OIDF) - “Motor de Conformidade de Segurança”;
- Realizar testes **funcionais** nas implementações das suas APIs dos produtos do Open Finance Brasil e posterior certificação - “Motor de Conformidade Funcional”).

As certificações são obrigatórias para todos os participantes entrarem em produção em cada fase do Open Finance Brasil, ou seja, uma implementação de versão de API só poderá ser registrada no ambiente produtivo do Diretório caso tenha sido certificada nos testes de segurança e funcionais. Vale ressaltar que as certificações de segurança e funcionais são independentes e seguem políticas de (re)certificação diferentes uma da outra.

# Calendário de Certificação

As datas relevantes e regulatórias de todos os calendários de certificações de APIs, vigentes ou antigas, podem ser encontradas no [Calendário oficial do Open Finance Brasil](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/calendars).

# Certificação de segurança

Para fins de certificação de segurança, os participantes do Open Finance são categorizados em:

- OpenID Provider (OP): transmissores de dados e detentores de conta

    - Demandam certificação FAPI e DCR e, se forem submetidas juntas, serão cobradas como uma única certificação.
- Relying Party (RP): receptores de dados e iniciadores de pagamento

    - Demandam certificação RP;
    - Certificação de segurança Relying Parties (RP) de pagamentos (escopo signed) é válida para compartilhamento de dados (escopo unsigned), mas o contrário não é válido.

        - §  O escopo a ser utilizado é definido no momento da chamada da API. Não existe diferença na parametrização do teste, porém, no momento da execução de cada teste, a ferramenta irá disponibilizar endpoints de accounts e payments e cabe ao receptor/iniciador chamar o endpoint correto conforme o perfil de certificação desejado.

A certificação em cada uma das modalidades citadas acima é obrigatória e possui custos que podem ser consultados no site da OpenID Foundation ou nos Informas do ecossistema.

O processamento dos pedidos de certificação é realizado por ordem de submissão. Portanto, recomendamos que o pedido de certificação seja submetido com, pelo menos, 2 meses de antecedência, devido às limitações de capacidade de processamento da OpenID Foundation.

# Certificação Funcional

A certificação de Conformidade Funcional é um mecanismo necessário para garantia de desenvolvimento adequado das APIs por parte dos participantes. Com a obrigação de sucesso completo nos testes do motor de conformidade, essa ferramenta acaba sendo vital para garantia da interoperabilidade e saúde do ecossistema.

O período entre o lançamento da beta1 das especificações de um produto do Open Finance e a entrada em produção (go live) é dividido entre o período de maturidade e o período de certificação. Durante o período de maturidade, é esperado que as instituições desenvolvam suas APIs e executem os testes disponíveis com objetivo de garantir a maturidade das especificações, dos testes e das implementações das instituições, visando a interoperabilidade em produção. Sendo assim, para cada lançamento são estabelecidos “marcos de sucesso” que as instituições precisam cumprir em cada data, que vinculam uma quantidade de testes que a instituição precisa obter sucesso como evidência de seu desenvolvimento. Caso a instituição tenha dúvidas, comentários, sugestões ou encontre algum bug, um ticket deve ser aberto para a estrutura no Gitlab ou no Service Desk.

Seguem alguns links úteis relacionados ao motor de conformidade:

- [**Acesso ao Motor de Conformidade Funcional,**](https://web.conformance.directory.openbankingbrasil.org.br/) que é a ferramenta para execução dos testes de conformidade funcional
- [**Release notes**](https://gitlab.com/raidiam-conformance/open-finance/certification/-/wikis/home) do motor de conformidade funcional é uma página de nosso fornecedor contendo as principais informações relativas ao motor, separada para cada uma das APIs. Na página de *release notes*¸ após seleção da API específica para detalhamento no menu lateral, podem ser encontradas informações atualizadas relativas à:

    - ***Release Dates*****: **Especificação das datas de lançamentos do motor de testes funcional, disponibilização dos novos módulos e versão da especificação utilizada de base para a criação dos testes;
    - ***Breaking Changes***: São mudanças relevantes no motor de conformidade, tornando um ou mais módulos mais restritivos do que a sua versão anterior, ocorrendo devido a bugs encontrados no motor de conformidade. Assim sendo, módulos de teste impactados por *Breaking Changes* devem obter sucesso apenas a partir da data da alteração relevante no motor. Portanto, torna-se necessária a divulgação e a documentação de módulos impactados, bem como a data da alteração relevante no motor de conformidade;
    - **Lista completa de testes**: Disponível na seção “Test Plan List”, a lista contempla todos os testes disponíveis no motor, junto com o seu detalhamento do que será testado nele.
- [**Issues do motor**](https://gitlab.com/raidiam-conformance/open-finance/certification/-/issues/?label_name%5B%5D=PHASE%203%20%3A%3A%20V4) de conformidade funcional é uma página destinada à interação dos participantes com o fornecedor, com o objetivo de tirar dúvidas, comunicar e dar visibilidade aos problemas encontrados no motor. Incentivamos os participantes a utilizarem essa plataforma, seja abrindo tickets para eventuais dúvidas, problemas ou divergências encontradas no motor de conformidade funcional. Essa plataforma permite o acompanhamento e interação com dúvidas de outras instituições e dá visibilidade para itens que já estão em correção ou que já foram esclarecidos.
- [**Dashboard de Acompanhamento**](https://app.powerbi.com/groups/me/reports/cedb6c5e-199c-48ba-8c25-018468c2ab8b/ReportSection095753bc49cb2b709399?ctid=7531e8b3-c928-494b-9b89-7ee3d353272d&amp;experience=power-bi&amp;bookmarkGuid=8aefcd43-cb71-40ad-af0c-3ff03eccde95) para acompanhar o status de execução dos testes e habilitar a visualização de maturidade do motor de conformidade e evitar eventuais transtornos próximos à data de *Go-live*, pois o respeito aos marcos de certificação é fundamental e obrigatório.

Para melhor acompanhamento da evolução da sua instituição com relação aos marcos de conformidade, é possível solicitar acesso ao Dashboard de Acompanhamento de Conformidade, com detalhamento do processo de pedido de acesso descrito no [Informe #431](https://mailchi.mp/ca867f20a701/open-banking-informa-9389280?e=2eb7798bd9). No dashboard de acompanhamento, é possível analisar dados como, por exemplo, testes já com sucesso da sua instituição e módulos executados.

Vale ressaltar que, para validar o atendimento dos marcos, alguns filtros podem ser aplicados como a data da última *breaking change*.

# Outros Links Úteis

- [Guia de Certificação de Conformidade](../../../OF/Open%20Finance%20Brasil/Certifica%c3%a7%c3%a3o%20de%20Conformidade/Guia%20de%20Certifica%c3%a7%c3%a3o%20de%20Conformidade): Página contendo informações mais detalhadas e específicas para a execução dos testes e obtenção das certificações;
- [Service Desk](https://servicedesk.openfinancebrasil.org.br/): Canal para envio de dúvidas das instituições e envio de notificações pela Estrutura;
- [Repositório de Informes](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17367115/Reposit+rio+de+Informes): Consolidado dos comunicados enviados ao ecossistema;
- [Canal do Youtube do Open Finance Brasil](https://www.youtube.com/@openfinancebrasil): Link para o canal do Youtube com workshops de lançamentos das APIs, contendo detalhamentos e explicações sob diferentes pontos de vista, como de produto, técnico, experiência do usuário (UX) e conformidade (testes e certificação).

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/280297514)