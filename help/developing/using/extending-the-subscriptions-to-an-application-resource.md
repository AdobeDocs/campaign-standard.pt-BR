---
title: Extensão das assinaturas para um recurso de aplicativo
description: null
page-status-flag: never-activated
uuid: 8879b427-b31b-4311-bf54-258a91b1fb78
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: use-cases--extending-resources
discoiquuid: 59faa74e-86fc-42d3-90da-f48580b5ec13
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 25%

---


# Extensão das assinaturas para um recurso de aplicativo{#extending-the-subscriptions-to-an-application-resource}

No Adobe Campaign, os dados de atributos do perfil móvel enviados de dispositivo móvel são armazenados no recurso **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]**, que permite definir os dados que você deseja coletar dos assinantes de aplicativos. For more information on custom resources, refer to [this page](../../developing/using/key-steps-to-add-a-resource.md).

Este recurso pode ser estendido para coletar dados que você pretende enviar do dispositivo móvel para a Adobe Campaign.

1. No menu avançado, selecione **[!UICONTROL Administration]** > **[!UICONTROL Development]** e **[!UICONTROL Custom resources]** pelo logotipo do Adobe Campaign.
1. Clique **[!UICONTROL Create]** e escolha a **[!UICONTROL Extend an existing resource]** opção.
1. Select the **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** resource and click **[!UICONTROL Create]**.

   ![](assets/in_app_personal_data_4.png)

1. Na **[!UICONTROL Fields]** categoria da **[!UICONTROL Data structure]** guia, defina os dados do cliente que você deseja recuperar do seu aplicativo móvel clicando no **[!UICONTROL Add field]** botão.

   >[!NOTE]
   >
   >Se você estiver gerenciando vários aplicativos móveis, todos os campos usados por todos os seus aplicativos devem estar listados. A chamada de coleta de PII do iOS ou Android define quais campos são capturados por cada aplicativo.

   ![](assets/in_app_personal_data.png)

1. Adicione um **[!UICONTROL Label]** e um **[!UICONTROL ID]** ao seu novo campo. Selecione o campo **[!UICONTROL Type]**.

   ![](assets/schema_extension_uc9.png)

1. Na **[!UICONTROL Link to profiles]** categoria, configure a chave de reconciliação usada para vincular os perfis do banco de dados da Adobe Campaign aos assinantes de seus aplicativos, como o email.

   Observe que para suas mensagens no aplicativo você só pode definir uma chave de reconciliação para todos os seus aplicativos móveis.

   ![](assets/in_app_personal_data_3.png)

1. **[!UICONTROL Save]** e publique seu recurso personalizado. Para obter mais informações sobre a publicação de recursos personalizados, consulte esta [página](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).

