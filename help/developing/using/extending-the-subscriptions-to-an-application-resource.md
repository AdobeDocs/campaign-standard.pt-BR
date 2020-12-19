---
solution: Campaign Standard
product: campaign
title: Extensão das assinaturas para um recurso de aplicativo
description: null
audience: developing
content-type: reference
topic-tags: use-cases--extending-resources
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 25%

---


# Extensão das assinaturas para um recurso de aplicativo{#extending-the-subscriptions-to-an-application-resource}

No Adobe Campaign, os dados de atributos do perfil móvel enviados de dispositivo móvel são armazenados no recurso **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]**, que permite definir os dados que você deseja coletar dos assinantes de aplicativos. Para obter mais informações sobre recursos personalizados, consulte [esta página](../../developing/using/key-steps-to-add-a-resource.md).

Este recurso pode ser estendido para coletar dados que você pretende enviar do dispositivo móvel para a Adobe Campaign.

1. No menu avançado, selecione **[!UICONTROL Administration]** > **[!UICONTROL Development]** e **[!UICONTROL Custom resources]** pelo logotipo do Adobe Campaign.
1. Clique em **[!UICONTROL Create]** e escolha a opção **[!UICONTROL Extend an existing resource]**.
1. Selecione o recurso **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** e clique em **[!UICONTROL Create]**.

   ![](assets/in_app_personal_data_4.png)

1. Na categoria **[!UICONTROL Fields]** da guia **[!UICONTROL Data structure]**, defina os dados do cliente que você deseja recuperar do aplicativo móvel clicando no botão **[!UICONTROL Add field]**.

   >[!NOTE]
   >
   >Se você estiver gerenciando vários aplicativos móveis, todos os campos usados por todos os seus aplicativos devem estar listados. A chamada de coleta de PII do iOS ou Android define quais campos são capturados por cada aplicativo.

   ![](assets/in_app_personal_data.png)

1. Adicione um **[!UICONTROL Label]** e um **[!UICONTROL ID]** ao seu novo campo. Selecione **[!UICONTROL Type]** do seu campo.

   ![](assets/schema_extension_uc9.png)

1. Na categoria **[!UICONTROL Link to profiles]**, configure a chave de reconciliação usada para vincular os perfis do banco de dados Adobe Campaign aos assinantes de seus aplicativos, como o email.

   Observe que para suas mensagens no aplicativo você só pode definir uma chave de reconciliação para todos os seus aplicativos móveis.

   ![](assets/in_app_personal_data_3.png)

1. **[!UICONTROL Save]** e publique seu recurso personalizado. Para obter mais informações sobre a publicação de recursos personalizados, consulte esta [página](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).

