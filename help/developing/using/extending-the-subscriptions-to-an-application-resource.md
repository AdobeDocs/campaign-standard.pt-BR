---
title: Extensão das subscrições para um recurso de aplicativo
description: Saiba como estender a assinatura para um recurso de aplicativo
audience: developing
content-type: reference
topic-tags: use-cases--extending-resources
feature: Data Model
role: Developer
level: Experienced
exl-id: ac9c556d-c0f6-4b33-8855-1f5f669c148f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 10%

---

# Extensão das subscrições para um recurso de aplicativo{#extending-the-subscriptions-to-an-application-resource}

No Adobe Campaign, os dados de atributos do perfil móvel enviados de dispositivo móvel são armazenados no **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** recurso que permite definir os dados que deseja coletar dos assinantes de aplicativos. Para obter mais informações sobre recursos personalizados, consulte [esta página](../../developing/using/key-steps-to-add-a-resource.md).

Esse recurso pode ser estendido para coletar dados que você pretende enviar do dispositivo móvel para o Adobe Campaign.

1. No menu avançado, selecione **[!UICONTROL Administration]** > **[!UICONTROL Development]** e **[!UICONTROL Custom resources]** pelo logotipo do Adobe Campaign.
1. Clique em **[!UICONTROL Create]** e escolha o **[!UICONTROL Extend an existing resource]** opção.
1. Selecione o **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** e clique em **[!UICONTROL Create]**.

   ![](assets/in_app_personal_data_4.png)

1. No **[!UICONTROL Fields]** categoria do **[!UICONTROL Data structure]** defina os dados do cliente que deseja recuperar do aplicativo móvel clicando no link **[!UICONTROL Add field]** botão.

   >[!NOTE]
   >
   >Se você estiver gerenciando vários aplicativos móveis, todos os campos usados por todos os aplicativos devem ser listados. A chamada PII de coleta do iOS ou Android define quais campos são capturados por cada aplicativo.

   ![](assets/in_app_personal_data.png)

1. Adicionar um **[!UICONTROL Label]** e uma **[!UICONTROL ID]** ao novo campo. Selecione o do campo **[!UICONTROL Type]**.

   ![](assets/schema_extension_uc9.png)

1. No **[!UICONTROL Link to profiles]** , configure a chave de reconciliação usada para vincular os perfis do banco de dados do Adobe Campaign aos assinantes de seus aplicativos, como o email.

   Observe que, para suas mensagens no aplicativo, você só pode definir uma chave de reconciliação para todos os aplicativos móveis.

   ![](assets/in_app_personal_data_3.png)

1. **[!UICONTROL Save]** e publique seu recurso personalizado. Para obter mais informações sobre publicação de recursos personalizados, consulte esta [página](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).
