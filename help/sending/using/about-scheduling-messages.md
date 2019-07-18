---
title: Sobre mensagens de agendamento
seo-title: Sobre mensagens de agendamento
description: Sobre mensagens de agendamento
seo-description: Saiba como agendar suas mensagens.
page-status-flag: nunca ativado
uuid: 286 fceee -65 a 9-4 cb 9-b 205-9 ce 5 d 024675 c
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: enviando
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 9 c 7 fd 670-bba 9-4 f 3 c -8 cb 1-87397 a 1 acd 27
context-tags: entrega, programação, voltar
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: cb6396228e42f99f7e184a82e6c894b09a164cd9

---


# About scheduling messages{#about-scheduling-messages}

>[!CAUTION]
>
>Whenever making changes to a delivery’s schedule, you must re-prepare the delivery by clicking on the **Prepare** button before clicking **Confirm**.

In the message dashboard, the **[!UICONTROL Schedule]** block allows you to define when messages (email, SMS or Push notifications) will be sent.

![](assets/delivery_dashboard.png)

The **[!UICONTROL Schedule]** properties let you set sending options for your emails, SMS or push notifications:

* **[!UICONTROL Messages to be sent once confirmed]**: são enviadas assim que o envio é confirmado. See [Confirming the send](../../sending/using/confirming-the-send.md).

   ![](assets/delivery_planning_1.png)

* **[!UICONTROL Messages to be sent automatically on the date specified below]**: serão enviadas em uma data e hora posterior. Specify the **contact date** in the **Start sending from** field.

   Você pode preparar e confirmar o envio, mas as mensagens só serão enviadas iniciando a data e a hora selecionadas. Preparing and confirming the send are presented in the [Preparing the send](../../sending/using/preparing-the-send.md) and [Confirming the send](../../sending/using/confirming-the-send.md) sections.

   The **[!UICONTROL Time zone of the contact date]** drop-down list allows you to modify the time zone that will be taken into account for the sending time. For example, if you enter 9:00 AM in the **[!UICONTROL Start sending from]** field and if you select Brussels, Copenhagen, Madrid, Paris (GMT+1) in the **[!UICONTROL Time zone of the contact date]** drop-down list, all recipients will receive the message at 9:00 AM Paris time. Portanto, um destinatário localizado em Moscou (GMT +3) receberá a mensagem às 11h time 0 de Moscou.

   If you would like to manually confirm the send, check the **[!UICONTROL Request confirmation before sending messages]** option. Essa opção está habilitada por padrão.

   ![](assets/delivery_planning.png)

>[!CAUTION]
>
>Ao duplicar uma entrega, todas as configurações de programação são excluídas. A menos que você programe uma nova data de contato, a entrega duplicada será enviada assim que o envio for confirmado.

**Tópicos relacionados**:

* [Otimizar o tempo de envio](../../sending/using/optimizing-the-sending-time.md)
* [Enviar mensagens no fuso horário do destinatário](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)
* [Cálculo da data de envio](../../sending/using/computing-the-sending-date.md)

