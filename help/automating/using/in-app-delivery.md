---
title: Entrega no aplicativo
seo-title: Entrega no aplicativo
description: Entrega no aplicativo
seo-description: A atividade de entrega dentro do aplicativo permite configurar o envio de uma mensagem no aplicativo dentro de um fluxo de trabalho.
page-status-flag: nunca ativado
uuid: 528 d 9472-e 447-47 af-a 6 b 2-3181 aa 5 fb 5 anúncio
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizando
content-type: reference
topic-tags: channel-activities
discoiquuid: 19796 aca -6 e 9 e -4 d 3 a -8917-ba 660 ec 7993 c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 36727e82d3aa73add6116fa2916752ff0e407d9d

---


# In-App delivery{#in-app-delivery}

## Description {#description}

![](assets/wkf_in_app_1.png)

The **In-App delivery** activity allows you to configure sending an In-App message within a workflow. As mensagens no aplicativo permitem exibir uma mensagem quando o usuário está ativo no aplicativo. For more information concerning the In-App delivery, refer to this [section](../../channels/using/about-in-app-messaging.md).

## Context of use {#context-of-use}

The **[!UICONTROL In-App delivery]** activity is generally used to automate sending an In-App message to a target audience calculated in the same workflow.

Os destinatários são definidos como upstream da atividade no mesmo fluxo de trabalho, por atividades de definição de metas como consultas, interseções etc.

A preparação de mensagens é acionada de acordo com os parâmetros de execução do fluxo de trabalho. No painel de mensagens, você pode selecionar se deseja ou não solicitar ou não uma confirmação manual para enviar a mensagem (obrigatório por padrão). Você pode iniciar o fluxo de trabalho manualmente ou colocar uma atividade de agendamento no fluxo de trabalho para automatizar a execução.

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Query]** activity to your workflow. Please note that the **[!UICONTROL Query]** activity targeting dimension in the **[!UICONTROL Properties]** tab needs to be updated according to the template chosen in Step 4:

   * Targeting dimension should be set to **[!UICONTROL mobileApp (mobileAppV5)]** for the **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]** template.
   * Targeting dimension should be set to **[!UICONTROL profile (profile)]** for the **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]** template.
   * Targeting dimension should be set to **[!UICONTROL subscriptions to an application (nms:appSubscriptionRcp:appSubscriptionRcpDetail)]** for the **[!UICONTROL Target users based on their Mobile profile (inApp)]** template.

1. Drag and drop a **[!UICONTROL In-App delivery]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.

   >[!NOTE]
   >
   >You can access the general properties and advanced options of the activity (and not of the delivery itself) via the ![](assets/dlv_activity_params-24px.png) button from the activity's quick actions.

   ![](assets/wkf_in_app_3.png)

1. Selecione o tipo de mensagem no aplicativo. This will depend on the data targeted in your **[!UICONTROL Query]** activity.

   * **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**: Este tipo de mensagem permite direcionar os perfis do Adobe Campaign que assinaram seu aplicativo móvel e personalizar mensagens no aplicativo com atributos de perfil disponíveis no Campaign.
   * **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**: Esse tipo de mensagem permite que você envie uma mensagem a todos os usuários do aplicativo móvel mesmo que eles não tenham um perfil existente no Campaign.
   * **[!UICONTROL Target users based on their Mobile profile (inApp)]**: Este tipo de mensagem permite que você direcione todos os usuários de um aplicativo móvel que tenha um perfil móvel no Campaign seja conhecido ou desconhecido e para personalizar mensagens no aplicativo com quaisquer atributos de perfil obtidos de dispositivo móvel.
   ![](assets/wkf_in_app_4.png)

1. Enter your In-App message properties and select your mobile app in the **[!UICONTROL Associate a Mobile App to a delivery]** field.
1. In the **[!UICONTROL Triggers]** tab, drag and drop the event that will trigger your message. Três categorias de eventos estão disponíveis:
1. Defina o conteúdo no aplicativo. Refer to the section concerning [In-App customization](../../channels/using/customizing-an-in-app-message.md).
1. By default, the **[!UICONTROL In-App delivery]** activity does not include any outbound transitions. If you would like to add an outbound transition to your **[!UICONTROL In-App delivery]** activity, go to the **[!UICONTROL General]** tab of the advanced activity options ( ![](assets/dlv_activity_params-24px.png) button in the activity's quick actions) then check one of the following options:

   * **[!UICONTROL Add outbound transition without the population]**: isso permite gerar uma transição de saída que contenha exatamente a mesma população que a transição de entrada.
   * **[!UICONTROL Add outbound transition with the population]**: isso permite gerar uma transição de saída contendo a população para a qual a mensagem foi enviada. Os membros da meta excluída durante a preparação de entrega são excluídos desta transição.
   ![](assets/wkf_in_app_5.png)

1. Confirme a configuração da atividade e salve seu fluxo de trabalho.

Ao reabrir a atividade, você será direcionado diretamente para o painel no aplicativo. Somente seu conteúdo pode ser editado.

Por padrão, iniciar um fluxo de trabalho de entrega apenas aciona a preparação de mensagens. O envio de mensagens criadas a partir de um fluxo de trabalho ainda precisa ser confirmado após a inicialização do fluxo de trabalho. But from the message dashboard, and only if the message was created from a workflow, you can disable the **[!UICONTROL Request confirmation before sending messages]** option. Ao desmarcar essa opção, as mensagens são enviadas sem aviso prévio após a conclusão da preparação.

## Remarks {#remarks}

As entregas criadas em um fluxo de trabalho podem ser acessadas na lista de atividades de marketing do aplicativo. Você pode visualizar o status de execução do fluxo de trabalho usando o painel. Os links no painel de resumo de notificações por push permitem acessar diretamente os elementos vinculados (fluxo de trabalho, campanha etc.).

In the parent deliveries, which can be accessed from the marketing activity list, you can view the total number of sends that have been processed (according to the aggregation period specified when the **[!UICONTROL In-App delivery]** activity was configured). To do this, open the detail view of the parent delivery's **[!UICONTROL Deployment]** block by selecting ![](assets/wkf_dlv_detail_button.png).
