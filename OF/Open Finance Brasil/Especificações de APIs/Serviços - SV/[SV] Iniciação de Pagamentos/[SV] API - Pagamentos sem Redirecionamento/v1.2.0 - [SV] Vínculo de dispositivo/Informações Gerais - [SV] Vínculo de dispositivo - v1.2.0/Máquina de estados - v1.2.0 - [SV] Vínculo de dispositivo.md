[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/212009017)

## **Vinculação de Conta**
![att212009051](M%c3%a1quina%20de%20estados%20-%20v1.2.0%20-%20[SV]%20V%c3%adnculo%20de%20dispositivo/attachments/Timeouts%20e%20mudan%c3%a7a%20de%20status.drawio.png)

#### **AWAITING\_RISK\_SIGNALS**

O Vínculo da conta começa no status **AWAITING\_RISK\_SIGNALS**, a transição de status para **AWAITING\_ACCOUNT\_HOLDER\_VALIDATION** acontece com o recebimento dos sinais de risco e deve ocorrer em até 5 minutos, caso contrário é alterado para **REJECTED**. Também será alterado para **REJECTED** caso cancelado pelo usuário.

#### **AWAITING\_ACCOUNT\_HOLDER\_VALIDATION**

Estado transitório para o redirecionamento, onde o seu estado é alterando para **AWAITING\_ENROLLMENT**, caso não haja o recebimento dos sinais, validações e redirecionamento em até** 15 minutos** o status e alterado para **REJECTED.**

#### **AWAITING\_ENROLLMENT**

Estado que representa a espera do usuário concluir o processo de autenticação FAPI tradicional para liberar o registro do dispositivo, no qual possui uma janela de 5 minutos para a expiração, caso o usuário não conclua o enrollment do seu dispositivo, o estado deve ser alterado para **REJECTED**.

#### **AUTHORISED**

O usuário possui uma janela de 5 minutos para expiração após a vinculação da conta para concluir a autorização enviando suas credenciais a detentora, caso usuário não conclua a autorização, o estado deve ser alterado para **REVOKED**. Com isso, o dispositivo do usuário estará apto a realizar transações sem redirecionamento entre ITP e detentora.

#### **REJECTED**

Se o usuário não respeitar a janela máxima de tempo para conclusão de alguma etapa anteriormente citada, o *enrollment *deve ser enviado para o estado **REJECTED. **Também pode ocorrer caso seja detectado algum tipo de fraude na tentativa de *enrollment*.

#### **REVOKED**

A revogação do vínculo de conta pode ocorrer a qualquer momento, tanto no âmbito do usuário, ITP e Detentora de contas.

O usuário, após ter concluído todo o processo de *enrollment*, decide cancelar o vínculo. Pode ocorrer tanto através da ITP quanto no ambiente da Detentora de Conta, uma vez que com a perda/roubo do dispositivo o usuário deve ter como cancelar seu vínculo nos canais da Detentora de Conta e do ITP.

ITP e/ou Detentora de contas, a princípio, também podem realizar a revogação do vínculo de conta unilateralmente caso identifiquem a necessidade em algum processo interno ou caso alguma regra não tenha sido respeitada.

## Iniciação de Pagamentos

Será utilizada a máquina de estados vigente da API de Pagamentos conforme especificado na página [Máquina de Estados - v3.0.0-rc.1 - Pagamentos](../../../../../../../../OF/Open%20Finance%20Brasil/Especifica%c3%a7%c3%b5es%20de%20APIs/Servi%c3%a7os%20-%20SV/[SV]%20Inicia%c3%a7%c3%a3o%20de%20Pagamentos/[SV]%20API%20-%20Pagamentos/Hist%c3%b3rico%20de%20Especifica%c3%a7%c3%b5es%20-%20Pagamentos/v3.0.0-rc.1%20-%20Pagamentos/Informa%c3%a7%c3%b5es%20Gerais%20-%20Pagamentos%20-%20v3.0.0-rc.1/M%c3%a1quina%20de%20Estados%20-%20v3.0.0-rc.1%20-%20Pagamentos).

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/212009017)