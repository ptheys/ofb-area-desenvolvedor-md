[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/156434452)

**Contexto**

Conforme [IN nº 306 de 19/02/2022](https://www.bcb.gov.br/estabilidadefinanceira/exibenormativo?tipo=Instru%C3%A7%C3%A3o%20Normativa%20BCB&amp;numero=306), o Item 2 do Anexo lista todas as APIs integrantes do Open Finance. Dentre elas, as APIs de Status, de Outages e Métricas são comuns a todos os participantes do Open Finance Brasil, independentemente da fase de adesão.

| Relatórios e Métricas | Situação do Ambiente | Deve dar acesso a dados sobre a disponibilidade atual das implementações, bem como dados sobre indisponibilidades programada. |
| --- | --- | --- |
|  | Métricas | Deve dar acesso a dados de performance de todas as APIs disponibilizadas. |

Sendo assim: 

1. Todas as instituições devem publicar essas APIs que monitoram a situação do ambiente;

2. API de métricas deve reportar os dados de performance de **todas as APIs** que a instituição oferece;

3. API de métricas deve ser atualizada conforme lançamento de novas APIs pela instituição ou atualização das APIs já existentes.

**Métricas**: (GET /admin/v1/metrics)

**Visão geral **

Os dados das APIs Administrativas são consumidos apenas pelo Diretório para avaliação e controle da qualidade dos serviços fornecidos pelas Instituições Financeiras. 

- Para o entendimento a respeito do cálculo do upTime e DownTime sugere o link de [<u>Disponibilidade</u>](../../../../../../../OF/Open%20Finance%20Brasil/Requisitos%20n%c3%a3o%20Funcionais/Disponibilidade);
- Para preenchimento do objeto invocativos sugere o link de [<u>Referência</u>](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17957025/Refer+ncia).

**Visão de alto nível das estruturas de dados**
![att156434469](Informa%c3%a7%c3%b5es%20Gerais%20-%20APIs%20Admins%20-%20v2.0.0-beta.1/attachments/Admin%20-%20Alto%20n%c3%advel%20das%20estruturas%20de%20dados.png)

**Dicionário de Dados **

[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/getMetrics_v2.csv)

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/156434452)