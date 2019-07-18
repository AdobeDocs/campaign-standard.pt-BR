---
title: Estender as assinaturas para um recurso de aplicativo
seo-title: Estender as assinaturas para um recurso de aplicativo
description: Estender as assinaturas para um recurso de aplicativo
seo-description: null
page-status-flag: nunca ativado
uuid: 8879 b 427-b 31 b -4311-bf 54-258 a 91 b 1 fb 78
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: casos de uso—extensão-recursos
discoiquuid: 59 faa 74 e -86 fc -42 d 3-90 da-f 48580 b 5 ec 13
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 866567d63dd2798eb56d42d4e163e5484c9b4d68

---


# Extending the subscriptions to an application resource{#extending-the-subscriptions-to-an-application-resource}

In Adobe Campaign, mobile profile attributes data sent from mobile device are stored in **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** resource which allows you to define the data that you want to collect from your applications' subscribers. For more information on custom resources, refer to this [page](../../developing/using/key-steps-of-adding-a-resource.md).

Esse recurso pode ser estendido para coletar dados que pretende enviar do dispositivo móvel para o Adobe Campaign.

1. From the advanced menu, via the Adobe Campaign logo, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]**, then **[!UICONTROL Custom resources]**.
1. Click **[!UICONTROL Create]** and choose the **[!UICONTROL Extend an existing resource]** option.
1. Select the **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** resource and click **[!UICONTROL Create]**.

   ![](assets/in_app_personal_data_4.png)

1. In the **[!UICONTROL Fields]** category of the **[!UICONTROL Data structure]** tab, define the customer data that you want to retrieve from your mobile application by clicking the **[!UICONTROL Add field]** button.

   >[!NOTE]
   >
   >Se você estiver gerenciando vários aplicativos móveis, todos os campos usados por todos os seus aplicativos devem ser listados. A chamada de coleta de PII para iOS ou Android define quais campos são capturados por cada aplicativo.

   ![](assets/in_app_personal_data.png)

1. Add a **[!UICONTROL Label]** and an **[!UICONTROL ID]** to your new field. Select your field's **[!UICONTROL Type]**.

   ![](assets/schema_extension_uc9.png)

1. In the **[!UICONTROL Link to profiles]** category, configure the reconciliation key used to link the profiles from the Adobe Campaign database to your applications' subscribers, such as the email.

   Observe que para suas mensagens no aplicativo você só pode definir uma chave de reconciliação para todos os aplicativos móveis.

   ![](assets/in_app_personal_data_3.png)

1. **[!UICONTROL Save]** e publicar seu recurso personalizado. For more information on custom resource publication, refer to this [page](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).

