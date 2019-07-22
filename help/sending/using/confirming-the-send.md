---
title: Confirmação do envio
seo-title: Confirmação do envio
description: Confirmação do envio
seo-description: Saiba como finalizar a preparação de mensagens.
page-status-flag: nunca ativado
uuid: 1 eabce 32-ffd 2-45 d 0-a 8 b 4-f 97 bee 59 a 1 bd
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: enviando
content-type: reference
topic-tags: enviar e rastrear mensagens
discoiquuid: 8 bb 160 b 1-7 de 9-4 c 1 f-bb 89-b 2 e 5 fdafed 41
context-tags: entrega, implantação, voltar
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e9dd7c374903d0c57ac4881ed125c3215bd7fe11

---


# Confirming the send{#confirming-the-send}

Depois que terminar de preparar suas mensagens e as etapas de aprovação tiverem sido executadas, você poderá enviá-las. For more on messages preparation, refer to [Preparing the send](../../sending/using/preparing-the-send.md).

Only users with the **[!UICONTROL Start deliveries]** role can confirm send. For more on this, refer to the [List of roles](../../administration/using/list-of-roles.md) section.

Os usuários sem essa função verão a seguinte mensagem:

![](assets/confirm_delivery_2.png)

To send your delivery, click the **[!UICONTROL Confirm send]** button found in the message's action bar.

![](assets/confirm_delivery.png)

You will be asked to finalize the send definitively by clicking the **[!UICONTROL OK]** button.

![](assets/confirm_delivery1.png)

A mensagem está sendo enviada.

>[!NOTE]
>
>Se a mensagem estiver programada, ela será enviada quando o tempo de envio for atingido. For more on scheduling messages, refer to [this section](../../sending/using/about-scheduling-messages.md).

Se você estiver usando uma entrega recorrente sem período de agregação, poderá solicitar confirmação antes da entrega ser enviada. To do this, open the **[!UICONTROL Schedule]** block of the delivery dashboard, then activate the dedicated option.

![](assets/confirmation_recurring_deliveries.png)

The **[!UICONTROL Deployment]** block shows the progress of the send.

Once the message is sent to the contacts, the **[!UICONTROL Deployment]** zone shows your KPIs (Key Performance Indicator) data , including:

* O número de mensagens a serem entregues
* O número de mensagens enviadas
* A porcentagem de mensagens entregues
* A porcentagem de rejeições e erros
* A porcentagem de mensagens abertas
* A porcentagem de cliques nas mensagens (para emails)

   >[!NOTE]
   >
   >The **[!UICONTROL Open rate]** and **[!UICONTROL Click-through rate]** are updated every hour.

![](assets/sending_delivery.png)

If the KPIs take too long to update or don't take into account the results from the sending logs, click the **[!UICONTROL Compute stats]** button in the **[!UICONTROL Deployment]** window.

![](assets/sending_delivery7.png)

A mensagem pode ser visualizada no histórico de um dos perfis cliente que faz parte do público-alvo. See [Integrated customer profile](../../audiences/using/integrated-customer-profile.md).

Depois que uma mensagem é enviada, você pode rastrear o comportamento de seus destinatários e monitorá-lo para medir seu impacto. Para saber mais sobre isso, consulte estas seções:

* [Mensagens de rastreamento](../../sending/using/tracking-messages.md)
* [Monitoramento de uma entrega](../../sending/using/monitoring-a-delivery.md)

