---
title: Extensão das assinaturas para um recurso de aplicativo
description: null
page-status-flag: nunca ativado
uuid: 8879b427-b31b-4311-bf54-258a91b1fb78
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: desenvolvimento
content-type: referência
topic-tags: casos de uso — extensão de recursos
discoiquuid: 59faa74e-86fc-42d3-90da-f48580b5ec13
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Extensão das assinaturas para um recurso de aplicativo{#extending-the-subscriptions-to-an-application-resource}

In Adobe Campaign, mobile profile attributes data sent from mobile device are stored in **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** resource which allows you to define the data that you want to collect from your applications' subscribers. For more information on custom resources, refer to this [page](../../developing/using/key-steps-to-add-a-resource.md).

Esse recurso pode ser estendido para coletar dados que você pretende enviar do dispositivo móvel para o Adobe Campaign.

1. No menu avançado, por meio do logotipo do Adobe Campaign, selecione **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** e, em seguida, **[!UICONTROL Custom resources]**.
1. Clique **[!UICONTROL Create]** e escolha a **[!UICONTROL Extend an existing resource]** opção.
1. Selecione o **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** recurso e clique em **[!UICONTROL Create]**.

   ![](assets/in_app_personal_data_4.png)

1. Na **[!UICONTROL Fields]** categoria da guia **[!UICONTROL Data structure]** , defina os dados do cliente que você deseja recuperar do aplicativo móvel clicando no **[!UICONTROL Add field]** botão.

   >[!NOTE]
   >
   >Se você estiver gerenciando vários aplicativos móveis, todos os campos usados por todos os seus aplicativos devem estar listados. A chamada de coleta de PII do iOS ou Android define quais campos são capturados por cada aplicativo.

   ![](assets/in_app_personal_data.png)

1. Adicione um **[!UICONTROL Label]** e um **[!UICONTROL ID]** ao seu novo campo. Selecione o campo **[!UICONTROL Type]**.

   ![](assets/schema_extension_uc9.png)

1. Na **[!UICONTROL Link to profiles]** categoria, configure a chave de reconciliação usada para vincular os perfis do banco de dados do Adobe Campaign aos assinantes de seus aplicativos, como o email.

   Observe que para suas mensagens no aplicativo você pode definir apenas uma chave de reconciliação para todos os seus aplicativos móveis.

   ![](assets/in_app_personal_data_3.png)

1. **[!UICONTROL Save]** e publique seu recurso personalizado. Para obter mais informações sobre a publicação de recursos personalizados, consulte esta [página](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).

