---
title: Criar e enviar uma notificação por push
description: Siga estas etapas para criar uma notificação por push de envio único no Adobe Campaign.
page-status-flag: never-activated
uuid: 01997725-ca0a-420c-9e81-5ea801652f87
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: push-notifications
discoiquuid: ec930cd4-6365-4e54-babe-9dc2eed041fc
context-tags: delivery,mobileAppContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 9c812b0b622b82ba7aa382f04edb7a2a3f717cd4
workflow-type: tm+mt
source-wordcount: '856'
ht-degree: 4%

---


# Preparação e envio de uma notificação por push{#preparing-and-sending-a-push-notification}

## Preparação da notificação {#preparing-the-notification}

As etapas para criar uma notificação por push com o Adobe Campaign são:

1. Na **[!UICONTROL Marketing activities]** janela, [crie uma nova atividade](../../start/using/marketing-activities.md#creating-a-marketing-activity)de marketing.

   Observe que uma única notificação por push também pode ser criada a partir de uma [campanha](../../start/using/marketing-activities.md#creating-a-marketing-activity) ou do [home page](../../start/using/interface-description.md#home-page)Adobe Campaign.

   Você também pode usar uma atividade de delivery de notificação por push em um fluxo de trabalho. Essa atividade é apresentada na seção delivery [de notificação por](../../automating/using/push-notification-delivery.md) push.

1. Selecione **[!UICONTROL Push notification]**.
1. Selecione um modelo.

   ![](assets/push_notif_type.png)

   Por padrão, você pode selecionar um dos dois modelos a seguir:

   * **[!UICONTROL Send push to Campaign profiles]**: use este modelo para público alvo dos perfis do Adobe Campaign CRM que se inscreveram em seu aplicativo móvel e opt in receber notificações por push. Você pode inserir campos de [personalização](../../designing/using/personalization.md#inserting-a-personalization-field) na notificação por push, como o nome do recipient.
   * **[!UICONTROL Send push to app subscribers]**: use este modelo para enviar uma notificação por push a todos os usuários conhecidos e anônimos do aplicativo móvel que opt in receber notificações do aplicativo. Você pode personalizar essas mensagens com dados coletados do seu aplicativo móvel.

   Você também pode selecionar modelos multilíngues. Para obter mais informações, consulte [Criação de uma notificação](../../channels/using/creating-a-multilingual-push-notification.md)por push multilíngue.

   For more on templates, refer to the [Managing templates](../../start/using/marketing-activity-templates.md) section.

1. Enter your push notification properties and select your mobile app in the **[!UICONTROL Associate a Mobile App to a delivery]** field.

   Observe que o menu suspenso exibirá os aplicativos SDK V4 e Experience Platform SDK.

   ![](assets/push_notif_properties.png)

   Você pode vincular a notificação por push a uma campanha. Para fazer isso, selecione-o nas campanhas que já foram criadas.

1. Na tela a seguir, você pode especificar uma audiência, por exemplo, todos os clientes VIP que se inscreveram em um aplicativo móvel específico. Para obter mais informações, consulte [Criação de audiências](../../audiences/using/creating-audiences.md).

   Sua audiência será filtrada automaticamente com base no aplicativo móvel selecionado na etapa anterior.

   ![](assets/push_notif_audience.png)

1. Agora você pode personalizar sua notificação por push. Primeiro, escolha o estilo da mensagem: **[!UICONTROL Alert/Message/Badge]** ou **[!UICONTROL Silent push]**. Os tipos de notificação por push são descritos na seção [Sobre notificações](../../channels/using/about-push-notifications.md) por push.

   Edite o conteúdo de sua notificação por push e defina as opções avançadas. See [Customizing a push notification](../../channels/using/customizing-a-push-notification.md).

   ![](assets/push_notif_content.png)

   O conteúdo e as opções de notificação por push configurados aqui são passados para seu aplicativo móvel na forma de uma carga. A estrutura detalhada da carga é descrita na nota técnica [Entendendo notificações por push ACS da estrutura](https://helpx.adobe.com/br/campaign/kb/understanding-campaign-standard-push-notifications-payload-struc.html) da carga.

1. Clique em **[!UICONTROL Create]**.

   ![](assets/push_notif_content_2.png)

1. Antes de enviar a notificação, você pode testá-la com perfis de teste e depois ver exatamente o que seus recipient verão antes de enviar o delivery. Selecione **[!UICONTROL Audiences]** no resumo do delivery e clique na **[!UICONTROL Test profiles]** guia.

   Para obter mais informações sobre como enviar testes, consulte [Testar perfis](../../sending/using/sending-proofs.md).

1. Selecione os perfis de teste e clique em **[!UICONTROL Preview]** para exibir a notificação: o conteúdo é personalizado com os dados do perfil de teste.
1. Verifique o layout da notificação por push em diferentes dispositivos: selecione iPhone, telefone Android, iPad ou tablet Android para pré-visualização da renderização.

   ![](assets/push_notif_preview.png)

1. A estimativa **[!UICONTROL Estimated Payload Size]** é baseada nos dados do perfil de teste. O tamanho real da carga pode variar. O limite da mensagem é de 4 KB.

   >[!CAUTION]
   >
   >Se o tamanho da carga exceder o limite de 4 KB, a mensagem não será entregue.

Observe que os dados de personalização afetam o tamanho da mensagem.

## Envio da notificação {#sending-the-notification}

As notificações por push podem ser enviadas para uma audiência selecionada no Adobe Campaign definindo os critérios de audiência. Por exemplo abaixo, nossa audiência selecionada consiste em 4 assinantes de aplicativos móveis direcionados.

1. Click **[!UICONTROL Prepare]** to compute the target and generate the notifications.

   ![](assets/push_send_1.png)

1. Once the preparation has finished successfully, the **[!UICONTROL Deployment]** window presents the following KPIs: **[!UICONTROL Target]** and **[!UICONTROL To deliver]**. Note that the **[!UICONTROL To deliver]** count is lower than the **[!UICONTROL Targeted]** one due to exclusions which can be viewed by clicking ![](assets/lp_link_properties.png) button at the bottom of the **[!UICONTROL Deployment]** window.

   ![](assets/push_send_2.png)

1. Na **[!UICONTROL Exclusion logs]** guia, você pode encontrar a lista de todas as mensagens excluídas do público alvo enviado e o motivo por trás dessa exclusão.

   Aqui, podemos ver que um de nossos assinantes de aplicativos móveis foi excluído porque o endereço estava na lista de bloqueios e os outros assinantes porque o perfil era um duplicado.

   ![](assets/push_send_5.png)

1. Clique na **[!UICONTROL Exclusion causes]** guia para exibir o volume de mensagens excluídas.

   ![](assets/push_send_7.png)

1. Agora, você pode clicar em **[!UICONTROL Confirm]** start para enviar notificações por push.
1. Verifique o status do delivery no painel de mensagens e logs. Para obter mais informações, consulte [Enviar mensagens](../../sending/using/confirming-the-send.md) e [Logs do delivery](../../sending/using/monitoring-a-delivery.md#delivery-logs).

   Neste exemplo, o painel de mensagem exibe que a Adobe Campaign tentou enviar duas notificações por push: um foi entregue com êxito ao dispositivo e outro falhou. Para saber por que o delivery apresenta erros, clique no ![](assets/lp_link_properties.png) botão na parte inferior da **[!UICONTROL Deployment]** janela.

   ![](assets/push_send_4.png)

1. Na **[!UICONTROL Deployment]** janela, clique na **[!UICONTROL Sending logs]** guia para acessar a lista de notificações por push enviadas e seus status. Para este delivery, uma notificação por push foi enviada com êxito, enquanto a outra falhou devido a um token de dispositivo inválido. Esse assinante será então adicionado à lista de bloqueios a partir de outros delivery.

   >[!NOTE]
   >
   >Os motivos podem ser qualquer falha no Adobe Campaign. No caso de falhas de provedores como apns e fcm, a razão também refletirá isso. Para obter mais informações sobre falhas no provedor, consulte a documentação da [Apple](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CommunicatingwithAPNs.html) e do [Android](https://firebase.google.com/docs/cloud-messaging/http-server-ref) .

   ![](assets/push_send_6.png)

Agora você pode medir o impacto do delivery de notificação por push com relatórios dinâmicos.

**Tópicos relacionados:**

* [Relatório de notificação por push](../../reporting/using/push-notification-report.md)
* [Enviar uma notificação por push em um workflow](../../automating/using/push-notification-delivery.md)
