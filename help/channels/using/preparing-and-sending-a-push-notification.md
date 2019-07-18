---
title: Como preparar e enviar uma notificação por push
seo-title: Como preparar e enviar uma notificação por push
description: Como preparar e enviar uma notificação por push
seo-description: Siga estas etapas para criar uma notificação por push de envio único no Adobe Campaign.
page-status-flag: nunca ativado
uuid: 01997725-ca 0 a -420 c -9 e 81-5 ea 801652 f 87
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canais
content-type: reference
topic-tags: notificações por push
discoiquuid: ec 930 cd 4-6365-4 e 54-babe -9 dc 2 eed 041 fc
context-tags: entrega, mobileappcontent, back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6df0e764750a31f29d6fe3ec4d92e19b3f07f728

---


# Preparing and sending a push notification{#preparing-and-sending-a-push-notification}

## Preparing the notification {#preparing-the-notification}

As etapas para criar uma notificação por push com o Adobe Campaign são:

1. From the **[!UICONTROL Marketing activities]** window, [create a new marketing activity](../../start/using/marketing-activities.md#creating-a-marketing-activity).

   Note that a single push notification can also be created from a [campaign](../../start/using/marketing-activities.md#creating-a-marketing-activity) or from the Adobe Campaign [home page](../../start/using/interface-description.md#home-page).

   Também é possível usar uma atividade de entrega de notificação por push em um fluxo de trabalho. This activity is presented in the [Push notification delivery](../../automating/using/push-notification-delivery.md) section.

1. Select **[!UICONTROL Push notification]**.
1. Selecione um modelo.

   ![](assets/push_notif_type.png)

   Por padrão, você pode selecionar um dos dois modelos a seguir:

   * **[!UICONTROL Send push to Campaign profiles]**: use este modelo para direcionar os perfis do Adobe Campaign CRM que assinaram seu aplicativo móvel e aceitaram receber notificações por push. You can insert [personalization](../../designing/using/inserting-a-personalization-field.md) fields into your push notification, such as the recipient's first name.
   * **[!UICONTROL Send push to app subscribers]**: use este modelo para enviar uma notificação por push para todos os usuários de aplicativos móveis conhecidos e anônimos que aceitaram receber notificações de seu aplicativo. É possível personalizar essas mensagens com dados coletados do aplicativo móvel.
   Você também pode selecionar modelos multilíngues. For more information, refer to [Creating a multilingual push notification](../../channels/using/creating-a-multilingual-push-notification.md).

   For more on templates, refer to the [Managing templates](../../start/using/about-templates.md) section.

1. Enter your push notification properties and select your mobile app in the **[!UICONTROL Associate a Mobile App to a delivery]** field.

   Observe que a lista suspensa exibirá os aplicativos SDK V 4 e Experience Platform SDK.

   ![](assets/push_notif_properties.png)

   Você pode vincular a notificação por push a uma campanha. Para fazer isso, selecione-o nas campanhas que já foram criadas.

1. Na tela a seguir, você pode especificar um público-alvo, por exemplo, todos os clientes VIP que assinaram um aplicativo móvel específico. For more on this, see [Creating audiences](../../audiences/using/creating-audiences.md).

   Seu público será filtrado automaticamente com base no aplicativo móvel selecionado na etapa anterior.

   ![](assets/push_notif_audience.png)

1. Agora você pode personalizar a notificação por push. First, choose the message style: **[!UICONTROL Alert/Message/Badge]** or **[!UICONTROL Silent push]**. The push notification types are described in the [About push notifications](../../channels/using/about-push-notifications.md) section.

   Edite o conteúdo da notificação por push e defina as opções avançadas. See [Customizing a push notification](../../channels/using/customizing-a-push-notification.md).

   ![](assets/push_notif_content.png)

   O conteúdo e as opções de notificação por push configurados aqui são passados para seu aplicativo móvel na forma de uma carga. The detailed structure of the payload is described in the [Understanding ACS push notifications payload structure](https://helpx.adobe.com/campaign/kb/understanding-campaign-standard-push-notifications-payload-struc.html) technote.

1. Click **[!UICONTROL Create]**.

   ![](assets/push_notif_content_2.png)

1. Antes de enviar a notificação, você pode testá-la com perfis de teste e ver exatamente o que os destinatários verão antes de enviar a entrega. Select **[!UICONTROL Audiences]** from your delivery summary and click the **[!UICONTROL Test profiles]** tab.

   For more on sending tests, refer to [Test profiles](../../sending/using/managing-test-profiles-and-sending-proofs.md).

1. Select your test profiles and click **[!UICONTROL Preview]** to display the notification: content is personalized with the test profile data.
1. Verifique o layout de notificação por push em diferentes dispositivos: selecione iphone, telefone Android, ipad ou tablet Android para visualizar renderização.

   ![](assets/push_notif_preview.png)

1. The **[!UICONTROL Estimated Payload Size]** is an estimate based on test profile data. O tamanho da carga real pode variar. O limite da mensagem é 4 KB.

   >[!CAUTION]
   >
   >Se o tamanho da carga exceder o limite de 4 KB, a mensagem não será entregue. Os dados de personalização afetam o tamanho da mensagem.

## Sending the notification {#sending-the-notification}

As notificações por push podem ser enviadas para um público-alvo selecionado no Adobe Campaign definindo os critérios do público-alvo. Para o exemplo abaixo, nosso público selecionado consiste em 4 assinantes do aplicativo móvel direcionado.

1. Click **[!UICONTROL Prepare]** to compute the target and generate the notifications.

   ![](assets/push_send_1.png)

1. Once the preparation has finished successfully, the **[!UICONTROL Deployment]** window presents the following KPIs: **[!UICONTROL Target]** and **[!UICONTROL To deliver]**. Observe que a contagem **[!UICONTROL To deliver]** é menor do que **[!UICONTROL Targeted]**, devido a exclusões que podem ser visualizadas ao clicar no ![](assets/lp_link_properties.png) botão na parte inferior da janela **[!UICONTROL Deployment]**.

   ![](assets/push_send_2.png)

1. In the **[!UICONTROL Exclusion logs]** tab, you can find the list of all the messages excluded from the target sent and the reason behind this exclusion.

   Aqui, podemos observar que um dos assinantes do aplicativo móvel foi excluído porque o endereço foi bloqueado e os outros assinantes, pois o perfil foi duplicado.

   ![](assets/push_send_5.png)

1. Click the **[!UICONTROL Exclusion causes]** tab to display the volume of excluded messages.

   ![](assets/push_send_7.png)

1. You can now click **[!UICONTROL Confirm]** to start sending push notifications.
1. Verifique o status da entrega através do painel de mensagens e logs. For more on this, see [Sending messages](../../sending/using/confirming-the-send.md) and [Delivery logs](../../sending/using/monitoring-a-delivery.md#delivery-logs).

   Neste exemplo, o painel de mensagens exibe que o Adobe Campaign tentou enviar duas notificações por push: uma foi entregue com sucesso ao dispositivo e outra falha. To know why the delivery has errors, click the ![](assets/lp_link_properties.png) button at the bottom of the **[!UICONTROL Deployment]** window.

   ![](assets/push_send_4.png)

1. From the **[!UICONTROL Deployment]** window, click the **[!UICONTROL Sending logs]** tab to access the list of sent push notifications and their statuses. Para essa entrega, uma notificação por push foi enviada com êxito, enquanto a outra falhou devido a um token de dispositivo incorreto. Esse assinante será então bloqueado por entregas adicionais.

   >[!NOTE]
   >
   >Os motivos podem ser qualquer falha em downstream para o Adobe Campaign. No caso de falhas de provedores como aplicativos e fcm, o motivo também refletirá isso. For more information on provider failures, you can refer to the [Apple](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CommunicatingwithAPNs.html) and [Android](https://firebase.google.com/docs/cloud-messaging/http-server-ref) documentation.

   ![](assets/push_send_6.png)

Agora você pode medir o impacto da entrega de notificações por push com relatórios dinâmicos.

**Tópicos relacionados:**

* [Relatório de notificação por push](../../reporting/using/push-notification-report.md)
* [Envio de uma notificação por push em um fluxo de trabalho](../../automating/using/push-notification-delivery.md)

