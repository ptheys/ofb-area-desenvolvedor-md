[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/157450475)

## **Vinculação de Conta**
![att157450486](M%c3%a1quina%20de%20estados%20-%20v1.0.0-rc.1%20-%20API%20Pagamentos%20sem%20Redirecionamento/attachments/maquina%20de%20estados%20sem%20redirecionamento.png)
#### **AWAITING\_AUTHORISATION**

O Vínculo da conta começa no status **AWAITING\_AUTHORISATION, **a transição de status para **AWAITING\_ACCOUNT\_HOLDER\_VALIDATION** é feita no tempo de até 5 minutos, caso contrário é alterado para **REJECTED **ou** **na situação de cancelamento do usuário

#### **AWAITING\_ACCOUNT\_HOLDER\_VALIDATION**

Estado transitório para o redirecionamento, onde são recebidos os sinais de riscos e validações das credências do vínculo da conta no tempo de até 15 minutos, onde o seu estado é alterando para **AWAITING\_ENROLLMENT**, caso não haja o recebimento dos sinais, validações e redirecionamento o status e alterado para **REJECTED**

#### **AWAITING\_ENROLLMENT**

Possui uma janela de 5 minutos para a expiração, caso o usuário não conclua o *enrollment *do seu dispositivo, o estado deve ser alterado para **REJECTED.**

#### **AUTHORISED**

O usuário possui uma janela de 5 minutos para expiração após a vinculação da conta para concluir a autorização enviando suas credenciais a detentora, caso usuário não conclua a autorização, o estado deve ser alterado para **REVOKED**. Com isso, o dispositivo do usuário estará apto a realizar transações sem redirecionamento entre ITP e detentora.

#### **REJECTED**

Se o usuário não respeitar a janela máxima de tempo para conclusão de alguma etapa anteriormente citada, o *enrollment *deve ser enviado para o estado **REJECTED. **Também pode ocorrer caso seja detectado algum tipo de fraude na tentativa de *enrollment*.

#### **REVOKED**

O usuário, após ter concluído todo o processo de *enrollment*, decide cancelar o vínculo. Pode ocorrer tanto através da ITP quanto no ambiente da Detentora de Conta, uma vez que com a perda/roubo do dispositivo o usuário deve ter como cancelar seu vínculo nos canais da Detentora de Conta e do ITP

## Iniciação de Pagamentos

Será utilizada a máquina de estados vigente da API de Pagamentos conforme especificado na página [Máquina de Estados - v3.0.0-beta.2 - Pagamentos](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/142671991/M+quina+de+Estados+-+v3.0.0-beta.2+-+Pagamentos).

[Link para página original no Confluence](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/157450475)