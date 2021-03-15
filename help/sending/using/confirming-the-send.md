---
solution: Campaign Standard
product: campaign
title: Confirmação do envio
description: Saiba como finalizar a preparação da mensagem.
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
context-tags: delivery,deployment,back
feature: Monitoramento de desempenho
role: Profissional
level: Intermediário
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '947'
ht-degree: 65%

---


# Confirmação do envio{#confirming-the-send}

Quando terminar de preparar as mensagens e as etapas de aprovação forem executadas, você poderá enviá-las. Para saber mais sobre a preparação de mensagens, consulte [Preparação do envio](../../sending/using/preparing-the-send.md).

Somente usuários com a função **[!UICONTROL Start deliveries]** podem confirmar o envio. Para saber mais, consulte a seção [Lista de funções](../../administration/using/list-of-roles.md).

<!--Users without this role will see the following message: 

![](assets/confirm_delivery_2.png)-->

## Envio da mensagem {#sending-message}

Quando a preparação estiver concluída, siga as etapas abaixo para enviar sua mensagem.

1. Clique no botão **[!UICONTROL Confirm send]** localizado na barra de ação da mensagem.

   ![](assets/confirm_delivery.png)

1. Finalize o envio clicando no botão **[!UICONTROL OK]**.

   ![](assets/confirm_delivery1.png)

1. Aguarde enquanto a mensagem está sendo enviada. O bloco **[!UICONTROL Deployment]** mostra o progresso do envio.

>[!NOTE]
>
>Se a mensagem estiver programada, ela será enviada quando o horário de envio for atingido. Para saber mais sobre como programar mensagens, consulte [esta seção](../../sending/using/about-scheduling-messages.md).

Se estiver usando um delivery recorrente sem nenhum período de agregação, você poderá solicitar uma confirmação antes de o delivery ser enviado. Ao configurar sua mensagem, abra o bloco **[!UICONTROL Schedule]** do painel de delivery e ative a opção dedicada.

![](assets/confirmation_recurring_deliveries.png)

## Noções básicas sobre indicadores de mensagem {#message-indicators}

Depois que a mensagem é enviada aos contatos, a zona **[!UICONTROL Deployment]** mostra seus KPIs (indicadores principais de desempenho), inclusive:

* Número de mensagens para delivery
* Número de mensagens enviadas
* A porcentagem de mensagens entregues
* A porcentagem de rejeições e erros
* A porcentagem de mensagens abertas
* A porcentagem de cliques nas mensagens (para emails)

   >[!NOTE]
   >
   >A **[!UICONTROL Open rate]** e a **[!UICONTROL Click-through rate]** são atualizadas a cada hora.

![](assets/sending_delivery.png)

Se os KPIs demorarem para atualizar ou não refletirem os resultados dos logs de envio, clique no botão **[!UICONTROL Compute stats]** na janela **[!UICONTROL Deployment]**.

![](assets/sending_delivery7.png)

A mensagem pode ser exibida no histórico de um dos perfis direcionados. Consulte [Perfil de cliente integrado](../../audiences/using/integrated-customer-profile.md).

Depois que uma mensagem é enviada, você pode rastrear o comportamento de seus recipients e monitorá-la para medir seu impacto. Para saber mais, consulte estas seções:

* [Rastreamento de mensagens](../../sending/using/tracking-messages.md)
* [Monitorar um delivery](../../sending/using/monitoring-a-delivery.md)

### Relatórios de sucesso do delivery {#delivered-status-report}

>[!NOTE]
>
>Esta seção se aplica somente ao canal de email.

Na visualização **[!UICONTROL Summary]** de cada email, a porcentagem **[!UICONTROL Delivered]** começa em 100% e depois diminui progressivamente durante todo o [período de validade](../../administration/using/configuring-email-channel.md#validity-period-parameters) do delivery, à medida que as devoluções temporárias e permanentes são relatadas<!--from the Enhanced MTA to Campaign-->.

Na verdade, todas as mensagens são exibidas como **[!UICONTROL Sent]** no [logs de envio](../../sending/using/monitoring-a-delivery.md#sending-logs) assim que são retransmitidas com êxito do Campaign para o MTA aprimorado (Agente de transferência de mensagens). Eles permanecem com esse status, a menos que uma [rejeição](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons) para essa mensagem seja comunicada do MTA aprimorado para o Campaign.

Quando mensagens de rejeição permanente são relatadas do MTA aprimorado, seu status muda de **[!UICONTROL Sent]** para **[!UICONTROL Failed]** e a porcentagem de **[!UICONTROL Delivered]** é diminuída de maneira apropriada.

Quando mensagens de rejeição temporária são relatadas do MTA aprimorado, elas ainda são exibidas como **[!UICONTROL Sent]** e a porcentagem de **[!UICONTROL Delivered]** ainda não é atualizada. As mensagens de rejeição temporária são então [tentadas](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure) durante todo o período de validade do delivery:

* Se uma tentativa for bem-sucedida antes do fim do período de validade, o status da mensagem permanecerá como **[!UICONTROL Sent]** e a porcentagem de **[!UICONTROL Delivered]** permanecerá inalterada.

* Caso contrário, o status mudará para **[!UICONTROL Failed]** e a porcentagem de **[!UICONTROL Delivered]** será diminuída de maneira apropriada.

Portanto, você deve aguardar até o fim do período de validade para ver a porcentagem final **[!UICONTROL Delivered]** e o número final das mensagens **[!UICONTROL Sent]** e **[!UICONTROL Failed]**.

### Serviço de feedback por email (beta) {#email-feedback-service}

Com o recurso Serviço de feedback por email (EFS), o status de cada email é relatado com precisão, pois o feedback é capturado diretamente do MTA aprimorado (Agente de transferência de mensagem).

>[!IMPORTANT]
>
>O Serviço de feedback por email está disponível no momento como um recurso beta.

Depois que o delivery é iniciado, não há alteração na porcentagem de **[!UICONTROL Delivered]** quando a mensagem é transmitida com êxito do Campaign para o MTA aprimorado.

![](assets/efs-sending.png)

Os logs do delivery mostram o status **[!UICONTROL Pending]** para cada endereço direcionado.

![](assets/efs-pending.png)

Quando o delivery de mensagem para os perfis segmentados é relatado em tempo real a partir do MTA aprimorado, os logs do delivery mostram o status **[!UICONTROL Sent]** para cada endereço que recebeu a mensagem com êxito. A porcentagem de **[!UICONTROL Delivered]** aumenta de acordo com cada delivery bem-sucedido.

Quando mensagens de rejeição permanente são relatadas pelo MTA aprimorado, o status do log muda de **[!UICONTROL Pending]** para **[!UICONTROL Failed]** e a porcentagem **[!UICONTROL Bounces + errors]** é aumentada adequadamente.

Quando as mensagens de rejeição temporária são relatadas de volta do MTA aprimorado, o status do log também muda de **[!UICONTROL Pending]** para **[!UICONTROL Failed]** e a porcentagem **[!UICONTROL Bounces + errors]** é aumentada adequadamente. A porcentagem de **[!UICONTROL Delivered]** permanece inalterada. As mensagens com rejeição temporária são então repetidas durante todo o [período de validade do delivery](../../administration/using/configuring-email-channel.md#validity-period-parameters)

* Se uma nova tentativa for bem-sucedida antes do fim do período de validade, o status da mensagem mudará para **[!UICONTROL Sent]** e a porcentagem **[!UICONTROL Delivered]** será aumentada de maneira apropriada.

* Caso contrário, o status permanecerá como **[!UICONTROL Failed]**. As porcentagens **[!UICONTROL Delivered]** e **[!UICONTROL Bounces + errors]** permanecem inalteradas.

>[!NOTE]
>
>Para obter mais informações sobre rejeições permanentes e temporárias, consulte [esta seção](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons).
>
>Para obter mais informações sobre tentativas após uma falha temporária de delivery, consulte [esta seção](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

<!--Soft-bouncing messages increment an error counter. When the error counter reaches the limit threshold or when the validity period is over, the address goes into quarantine and the status remains as **[!UICONTROL Failed]**. For more on conditions for sending an address to quarantine, see [this section](../../help/sending/using/understanding-quarantine-management.md#conditions-for-sending-an-address-to-quarantine).-->

### Alterações introduzidas pelo EFS {#changes-introduced-by-efs}

As tabelas abaixo mostram as alterações nos KPIs e no envio de status de logs introduzidos pelo recurso EFS.

**Com o serviço de feedback por email**

| Etapa do processo de envio | Resumo do KPI | Envio de status de logs |
|--- |--- |--- |
| A mensagem foi transmitida com êxito do Campaign para o MTA aprimorado | <ul><li>**[!UICONTROL Delivered]** porcentagem começa em 0%</li><li>**[!UICONTROL Bounces + errors]** porcentagem começa em 0%</li></ul> | Pending |
| Mensagens com rejeição permanente são relatadas de volta do MTA aprimorado | <ul><li>Nenhuma alteração na porcentagem de **[!UICONTROL Delivered]**</li><li>A porcentagem de **[!UICONTROL Bounces + errors]** é aumentada de maneira apropriada</li></ul> | Com falha |
| Mensagens com rejeição temporária são relatadas de volta do MTA aprimorado | <ul><li>Nenhuma alteração na porcentagem de **[!UICONTROL Delivered]**</li><li>A porcentagem de **[!UICONTROL Bounces + errors]** é aumentada de maneira apropriada</li></ul> | Com falha |
| Tentativas de mensagens com rejeição temporária são bem-sucedidas | <ul><li>A porcentagem de **[!UICONTROL Delivered]** é aumentada de maneira apropriada</li><li>A porcentagem de **[!UICONTROL Bounces + errors]** é reduzida de maneira apropriada</li></ul> | Enviada |
| Falha nas tentativas de mensagens com rejeição temporária | <ul><li> Nenhuma alteração na porcentagem de **[!UICONTROL Delivered]** </li><li> Nenhuma alteração na porcentagem de **[!UICONTROL Bounces + errors]** </li></ul> | Com falha |

**Sem Serviço de feedback por email**

| Etapa do processo de envio | Resumo do KPI | Envio de status de logs |
|--- |--- |--- |
| A mensagem foi transmitida com êxito do Campaign para o MTA aprimorado | <ul><li>A porcentagem de **[!UICONTROL Delivered]** começa em 100%</li><li>A porcentagem de **[!UICONTROL Bounces + errors]** começa em 0%</li></ul> | Enviada |
| Mensagens com rejeição permanente são relatadas de volta do MTA aprimorado | <ul><li>A porcentagem de **[!UICONTROL Delivered]** é reduzida de maneira apropriada</li><li>A porcentagem de **[!UICONTROL Bounces + errors]** é aumentada de maneira apropriada</li></ul> | Com falha |
| Mensagens com rejeição temporária são relatadas de volta do MTA aprimorado | <ul><li>Nenhuma alteração na porcentagem de **[!UICONTROL Delivered]**</li><li>Nenhuma alteração na porcentagem de **[!UICONTROL Bounces + errors]**</li></ul> | Enviada |
| Tentativas de mensagens com rejeição temporária são bem-sucedidas | <ul><li>Nenhuma alteração na porcentagem de **[!UICONTROL Delivered]**</li><li>Nenhuma alteração na porcentagem de **[!UICONTROL Bounces + errors]**</li></ul> | Enviada |
| Falha nas tentativas de mensagens com rejeição temporária | <ul><li>A porcentagem de **[!UICONTROL Delivered]** é reduzida de maneira apropriada</li><li>A porcentagem de **[!UICONTROL Bounces + errors]** é aumentada de maneira apropriada</li></ul> | Com falha |
