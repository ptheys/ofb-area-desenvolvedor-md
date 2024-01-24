[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/212008982)

## Informações Iniciais

O serviço de iniciação de pagamentos sem redirecionamento (ou Jornada Sem Redirecionamento) é aquele em que o cliente inicia e conclui a solicitação de transação sem sair do ambiente da ITP – ou seja, sem ser redirecionado ao ambiente da detentora de conta.

O desenvolvimento da Jornada Sem Redirecionamento foi sugerido pelo Banco Central do Brasil com o objetivo de melhorar a experiência do usuário, preservando a segurança de pagamento e ser uma alternativa à jornada de iniciação de pagamento com redirecionamento.

Para habilitar a Jornada Sem Redirecionamento, o BCB delineou as seguintes Diretrizes:

- O processo deve ser constituído de duas etapas: (i) Vínculo de Conta e (ii) Pagamento;

    - <u>Vínculo de conta:</u> Processo em que o cliente vincula sua conta a ITP, com autenticação usual no detentor de contas;
    - <u>Pagamento:</u> Processo em que o cliente solicita a iniciação de pagamento, onde é autenticado no próprio ITP e não é redirecionado ao ambiente da detentora de conta.
- Instituição detentora de conta permanece responsável pela autenticação do cliente;
- Processo de autenticação do cliente delegado pela detentora de conta a ITP;

    - Relação da detentora com ITP deve ser regida pela regulação de segurança cibernética e contratação de serviços de processamento e armazenamento de dados.  
Contrato é necessário em função da terceirização parcial da autenticação;
    - BCB poderá disciplinar os requisitos mínimos do respectivo contrato *baseline *com objetivo de preservar os objetivos do Open Finance;
- O modelo deve ser padronizado e aberto, e a Estrutura de Governança deve definir as especificações e o protocolo de segurança a ser adotado como padrão pelos participantes.

Por último, a Estrutura de Governança responsável pelo desenvolvimento da Jornada Sem Redirecionamento elegeu o FIDO2 como padrão de segurança que irá habilitar o serviço de acordo com as Diretrizes do Banco Central do Brasil.

## Introdução sobre FIDO

FIDO (*Fast Identity Online*) é uma tecnologia desenvolvida pela FIDO Alliance ([http://fidoalliance.org](http://fidoalliance.org)) com o objetivo de facilitar, agilizar e tornar mais seguro o processo de autenticação de usuários em plataformas digitais. FIDO permite que os usuários façam login com chaves de acesso (i.e.: chave biométrica ou chave de segurança) em seus dispositivos.

Ao longo dos últimos anos, a FIDO Alliance lançou especificações abertas como UAF, U2F, FIDO2 e CTAP2. Para fins de Jornada Sem Redirecionamento, a Estrutura de Governança elegeu o FIDO2 como protocolo aderente aos seus propósitos.

FIDO2 foi um projeto entre a FIDO Alliance e a World Wide Web Consortium (W3C) que teve como principal objetivo estabelecer um padrão de forte autenticação para o ambiente web.

De acordo com a FIDO Alliance, os benefícios do FIDO2 são:

- <u>Segurança:</u> as credenciais de login criptográficas FIDO2 são exclusivas em cada site, nunca saem do dispositivo do usuário e nunca são armazenadas em um servidor. Este modelo de segurança elimina os riscos de *phishing*, todas as formas de roubo de senhas e ataques de repetição;
- <u>Conveniência:</u> os usuários desbloqueiam credenciais de login criptográficas com métodos integrados simples, como leitores de impressão digital ou câmeras em seus dispositivos, ou aproveitando chaves de segurança FIDO fáceis de usar. Os consumidores podem selecionar o dispositivo que melhor atende às suas necessidades;
- <u>Privacidade:</u> Como as chaves criptográficas FIDO são exclusivas para cada site da Internet, elas não podem ser usadas para rastrear usuários entre sites. Além disso, os dados biométricos, quando usados, nunca saem do dispositivo do usuário;
- <u>Escalabilidade:</u> Os sites podem ativar o FIDO2 por meio de uma simples chamada de API JavaScript que é compatível com os principais navegadores e plataformas em bilhões de dispositivos que os consumidores usam todos os dias.

## Visão Geral

A Estrutura de Governança responsável pelo desenvolvimento da Jornada Sem Redirecionamento definiu que essa deverá utilizar:

- *Endpoints *para a etapa de vinculação de conta para a Jornada sem Redirecionamento;
- Utilizar os *endpoints *da versão vigente da API de Iniciação de Pagamentos, sem alterações na etapa de iniciação de pagamento para a jornada sem redirecionamento.

Deste modo, todas as informações abaixo, também definidas para o serviço de iniciação de pagamentos com redirecionamento, se aplicam à jornada sem redirecionamento:

- [Idempotência - v3.0.0 - Pagamentos](../../../../../../../../OF/Open%20Finance%20Brasil/Especifica%c3%a7%c3%b5es%20de%20APIs/Servi%c3%a7os%20-%20SV/[SV]%20Inicia%c3%a7%c3%a3o%20de%20Pagamentos/[SV]%20API%20-%20Pagamentos/v3.0.0%20-%20[SV]%20Pagamentos/Informa%c3%a7%c3%b5es%20Gerais%20-%20[SV]%20Pagamentos%20-%20v3.0.0/Idempot%c3%aancia%20-%20v3.0.0%20-%20[SV]%20Pagamentos)
- [Recomendação Uso de Polling e Controle de Acesso -  v3.0.0 - Pagamentos](../../../../../../../../OF/Open%20Finance%20Brasil/Especifica%c3%a7%c3%b5es%20de%20APIs/Servi%c3%a7os%20-%20SV/[SV]%20Inicia%c3%a7%c3%a3o%20de%20Pagamentos/[SV]%20API%20-%20Pagamentos/v3.0.0%20-%20[SV]%20Pagamentos/Informa%c3%a7%c3%b5es%20Gerais%20-%20[SV]%20Pagamentos%20-%20v3.0.0/Recomenda%c3%a7%c3%a3o%20Uso%20de%20Polling%20e%20Controle%20de%20Acesso%20-%20%20v3.0.0%20-%20[SV]%20Pagamentos)
- [Como Assinar o Payload - v3.0.0 - Pagamentos](../../../../../../../../OF/Open%20Finance%20Brasil/Especifica%c3%a7%c3%b5es%20de%20APIs/Servi%c3%a7os%20-%20SV/[SV]%20Inicia%c3%a7%c3%a3o%20de%20Pagamentos/[SV]%20API%20-%20Pagamentos/v3.0.0%20-%20[SV]%20Pagamentos/Informa%c3%a7%c3%b5es%20Gerais%20-%20[SV]%20Pagamentos%20-%20v3.0.0/Como%20Assinar%20o%20Payload%20-%20v3.0.0%20-%20[SV]%20Pagamentos)
- [Assinatura de Mensagem vs Idempotência - v3.0.0 - Pagamentos](../../../../../../../../OF/Open%20Finance%20Brasil/Especifica%c3%a7%c3%b5es%20de%20APIs/Servi%c3%a7os%20-%20SV/[SV]%20Inicia%c3%a7%c3%a3o%20de%20Pagamentos/[SV]%20API%20-%20Pagamentos/v3.0.0%20-%20[SV]%20Pagamentos/Informa%c3%a7%c3%b5es%20Gerais%20-%20[SV]%20Pagamentos%20-%20v3.0.0/Assinatura%20de%20Mensagem%20vs%20Idempot%c3%aancia%20-%20v3.0.0%20-%20[SV]%20Pagamentos)
- [Validação de informações no DICT - v3.0.0 - Pagamentos](../../../../../../../../OF/Open%20Finance%20Brasil/Especifica%c3%a7%c3%b5es%20de%20APIs/Servi%c3%a7os%20-%20SV/[SV]%20Inicia%c3%a7%c3%a3o%20de%20Pagamentos/[SV]%20API%20-%20Pagamentos/v3.0.0%20-%20[SV]%20Pagamentos/Informa%c3%a7%c3%b5es%20Gerais%20-%20[SV]%20Pagamentos%20-%20v3.0.0/Valida%c3%a7%c3%a3o%20de%20informa%c3%a7%c3%b5es%20no%20DICT%20-%20v3.0.0%20-%20[SV]%20Pagamentos)
- [Convenções de formatação e fuso horário de campos de data e hora - v3.0.0 - Pagamentos](../../../../../../../../OF/Open%20Finance%20Brasil/Especifica%c3%a7%c3%b5es%20de%20APIs/Servi%c3%a7os%20-%20SV/[SV]%20Inicia%c3%a7%c3%a3o%20de%20Pagamentos/[SV]%20API%20-%20Pagamentos/v3.0.0%20-%20[SV]%20Pagamentos/Informa%c3%a7%c3%b5es%20Gerais%20-%20[SV]%20Pagamentos%20-%20v3.0.0/Conven%c3%a7%c3%b5es%20de%20formata%c3%a7%c3%a3o%20e%20fuso%20hor%c3%a1rio%20de%20campos%20de%20data%20e%20hora%20-%20v3.0.0%20-%20[SV]%20Pagamentos)

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/212008982)