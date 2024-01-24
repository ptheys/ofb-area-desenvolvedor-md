[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/86835231)

## **Etapas do ciclo de vida da API**

- ***Design*****: **etapa em que um dos GTs de Especificações de Dados Abertos, Dados do Cliente e/ou Serviços estão construindo uma nova versão da API. Nesta etapa a parte das especificações já desenvolvidas e aprovadas pelo GT serão disponibilizadas no ambiente de *Draft *na Área do Desenvolvedor no Portal do Open Finance.

    - O início das discussões sobre a evolução da API pelos GTs de Especificações marca o início desta etapa.
- ***Implementing*****: **etapa em que a nova versão da API (***unstable***) estará disponível para implementação. 

    - O evento de publicação da nova versão da API na Área do Desenvolvedor marcará o início desta etapa;
    - Poderá ser usada para reportar possíveis *bugs *nas especificações;
    - As detentoras/transmissoras devem iniciar as implementações a partir da publicação da nova versão da API.
- ***Certifying*****: **etapa em que a versão ***unstable** *da API estará disponível para implementação e certificação. 

    - O evento de liberação do uso dos motores de certificação marcará o início desta etapa;
    - Poderá ser usada para reportar possíveis *bugs* nas especificações ou nos motores de teste.
- ***Current*****: **etapa que indica a versão oficial da API que deve estar em produção. Quando uma nova versão da API (x+1) entrar em produção a versão antiga (versão x) sairá da etapa *current *para *deprecated *durante o período de convivência e a nova versão (versão x+1) sairá da etapa *certifying *para *current*.

    - O evento de entrada em produção marcará o início desta etapa.
- ***Deprecated*****:** etapa em que a versão atual (versão x) da API está sendo substituída pela próxima versão (x+1) em ambiente produtivo pelos participantes dando início ao período de convivência destas versões. 

    - O evento de entrada em produção da próxima versão da API marcará o início desta etapa.
- ***Retired*****:** etapa em que a versão da API se torna indisponível em ambiente produtivo.

    - O evento de remoção desta versão da API do ambiente produtivo marcará o início desta etapa.

## **Período de convivência**

- Quando temos a versão x em *deprecated*, significa que a versão x+1 está em *current*;
- Este período é utilizado para que tenhamos uma transição mais suave entre a versão que está sendo aposentada (*retired*) e a versão que está se tornando oficial (*current*);
- Neste período, teremos obrigatoriamente os participantes detentores de conta e transmissores de dados com as duas versões em produção, desde o primeiro dia do período de convivência, enquanto que os iniciadores de pagamento e os receptores de dados estarão lançando em produção suas implementações da versão x+1, sendo obrigatório o lançamento completo até o final do período de convivência;
- O período de convivência terá no máximo duas versões da mesma API convivendo.

![att86835248](Ciclo%20de%20Vida/attachments/PB14.png)

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/86835231)