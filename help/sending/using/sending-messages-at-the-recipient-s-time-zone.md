---
title: Enviar mensagens no fuso horário do destinatário
seo-title: Enviar mensagens no fuso horário do destinatário
description: Enviar mensagens no fuso horário do destinatário
seo-description: Saiba como enviar mensagens no fuso horário do destinatário.
page-status-flag: nunca ativado
uuid: 70228 c 07-451 f -4 ddb -8 d 26-92 a 5 a 4814 e 3 a
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: enviando
content-type: reference
topic-tags: sheduling-messages
discoiquuid: daa 980 ba -8 c 7 c -4673-a 68 f -379 d 63 e 4 b 8 bd
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 806dc4736ffb395a0eea102090c688102478aaca

---


# Sending messages at the recipient's time zone{#sending-messages-at-the-recipient-s-time-zone}

Ao gerenciar uma campanha em que a data e a hora são importantes, você pode programar uma entrega que leva em conta o horário local de cada destinatário: receberão e-mail, SMS ou noftficações de push no momento agendado, em seu próprio fuso horário.

>[!NOTE]
>
>To use this functionality, make sure that all profiles targeted by your delivery have a time zone specified in the **[!UICONTROL Address]** section of their properties. For more information on accessing profile properties, refer to this [section](../../audiences/using/editing-profiles.md).

To send a delivery at the recipient's time zone, you can also use the **[!UICONTROL Scheduler]** activity in a workflow. For more on this, refer to this [page](../../automating/using/scheduler.md).

No exemplo a seguir, queremos enviar um código promocional que é válido somente no Dia de Valentine para todos os clientes em todo o mundo. Para fornecer tempo suficiente para usá-lo durante o dia, todos os clientes devem receber sua mensagem em 14 de fevereiro às 8:00, dependendo dos fusos horários.

1. In the **[!UICONTROL Marketing activities]** tab, start creating your delivery, in our case an email. To learn more on delivery creation, refer to this [section](../../channels/using/creating-an-email.md).
1. After designing your Valentine's Day email, click **[!UICONTROL Create]** to access the delivery dashboard. For more on email designing, refer to this [page](../../designing/using/example--email-personalization.md).

   ![](assets/send-time_opt_valentine_1.png)

1. From the delivery dashboard, select the **[!UICONTROL Schedule]** block.

   ![](assets/send-time_opt_valentine_2.png)

1. Select the **[!UICONTROL Messages to be sent automatically on the date]** option specified below. Then in the **[!UICONTROL Start sending from]** field, set the contact date, in our case February 14th at 8:00 AM so that every recipient receives it on Valentine's Day.

   ![](assets/send-time_opt_valentine.png)

1. In the **[!UICONTROL Time zone of the contact date]** field, select at which time zone your delivery should be sent by default.

   If a profile's **[!UICONTROL Time zone]** is left as **[!UICONTROL Default]**, the recipients will receive the delivery depending on the chosen time zone here.

1. From the **[!UICONTROL Optimize the sending time per recipient]** drop-down menu, choose **[!UICONTROL Send at the recipient's time zone]**. Isso permite que os destinatários recebam o email de dia de Valentine em 14 de fevereiro, dependendo do fuso horário.

   ![](assets/send-time_opt_valentine_3.png)

1. After confirming your schedule for your delivery, click the **[!UICONTROL Prepare]** button then **[!UICONTROL Confirm]** your delivery.

   Certifique-se de confirmar o envio pelo menos 24 horas com antecedência. Caso contrário, dependendo dos locais, alguns destinatários poderão receber a entrega antes do evento dia real do Namentine.

   ![](assets/send-time_opt_valentine_4.png)

Não importa onde eles estão localizados, todos os destinatários receberão a mensagem em 14 de fevereiro às 8:h. AM horário local.
