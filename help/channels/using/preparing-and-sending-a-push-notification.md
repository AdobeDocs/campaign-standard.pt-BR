---
title: Preparação e envio de uma notificação por push
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
source-git-commit: c26f98c8edd832beeedfedafb8ad27730cc30d25

---


# Preparação e envio de uma notificação por push{#preparing-and-sending-a-push-notification}

## Preparação da notificação {#preparing-the-notification}

As etapas para criar uma notificação por push com o Adobe Campaign são:

1. Na **[!UICONTROL Marketing activities]** janela, [crie uma nova atividade](../../start/using/marketing-activities.md#creating-a-marketing-activity)de marketing.

   Observe que uma única notificação por push também pode ser criada a partir de uma [campanha](../../start/using/marketing-activities.md#creating-a-marketing-activity) ou da [página](../../start/using/interface-description.md#home-page)inicial do Adobe Campaign.

   Você também pode usar uma atividade de entrega de notificação por push em um fluxo de trabalho. Essa atividade é apresentada na seção de entrega [da notificação por](../../automating/using/push-notification-delivery.md) push.

1. Select **[!UICONTROL Push notification]**.
1. Selecione um modelo.

   ![](assets/push_notif_type.png)

   Por padrão, você pode selecionar um dos dois modelos a seguir:

   * **[!UICONTROL Send push to Campaign profiles]**: use este modelo para direcionar os perfis do Adobe Campaign CRM que se inscreveram no aplicativo móvel e aceitaram receber notificações por push. Você pode inserir campos de [personalização](../../designing/using/personalization.md#inserting-a-personalization-field) na notificação por push, como o nome do destinatário.
   * **[!UICONTROL Send push to app subscribers]**: use este modelo para enviar uma notificação por push a todos os usuários conhecidos e anônimos do aplicativo móvel que aceitaram receber notificações do aplicativo. Você pode personalizar essas mensagens com dados coletados do seu aplicativo móvel.
   Você também pode selecionar modelos multilíngues. Para obter mais informações, consulte [Criação de uma notificação](../../channels/using/creating-a-multilingual-push-notification.md)por push multilíngue.

   Para obter mais informações sobre modelos, consulte a seção [Gerenciar modelos](../../start/using/marketing-activity-templates.md) .

1. Digite as propriedades de notificação por push e selecione o aplicativo móvel no **[!UICONTROL Associate a Mobile App to a delivery]** campo.

   Observe que a lista suspensa exibirá os aplicativos SDK V4 e Experience Platform.

   ![](assets/push_notif_properties.png)

   Você pode vincular a notificação por push a uma campanha. Para fazer isso, selecione-o nas campanhas que já foram criadas.

1. Na tela a seguir, você pode especificar um público-alvo, por exemplo, todos os seus clientes VIP que se inscreveram em um aplicativo móvel específico. Para obter mais informações, consulte [Criação de públicos-alvo](../../audiences/using/creating-audiences.md).

   Seu público-alvo será filtrado automaticamente com base no aplicativo móvel selecionado na etapa anterior.

   ![](assets/push_notif_audience.png)

1. Agora você pode personalizar sua notificação por push. Primeiro, escolha o estilo da mensagem: **[!UICONTROL Alert/Message/Badge]** ou **[!UICONTROL Silent push]**. Os tipos de notificação por push são descritos na seção [Sobre notificações](../../channels/using/about-push-notifications.md) por push.

   Edite o conteúdo de sua notificação por push e defina as opções avançadas. See [Customizing a push notification](../../channels/using/customizing-a-push-notification.md).

   ![](assets/push_notif_content.png)

   O conteúdo e as opções de notificação por push configurados aqui são passados para seu aplicativo móvel na forma de uma carga. A estrutura detalhada da carga é descrita na nota técnica [Entendendo notificações por push ACS da estrutura](https://helpx.adobe.com/campaign/kb/understanding-campaign-standard-push-notifications-payload-struc.html) da carga.

1. Clique em **[!UICONTROL Create]**.

   ![](assets/push_notif_content_2.png)

1. Antes de enviar a notificação, você pode testá-la com perfis de teste e ver exatamente o que seus destinatários verão antes de enviar a entrega. Selecione **[!UICONTROL Audiences]** o resumo de entrega e clique na **[!UICONTROL Test profiles]** guia.

   Para obter mais informações sobre como enviar testes, consulte Perfis [de](../../sending/using/managing-test-profiles-and-sending-proofs.md)teste.

1. Selecione os perfis de teste e clique em **[!UICONTROL Preview]** para exibir a notificação: o conteúdo é personalizado com os dados do perfil de teste.
1. Verifique o layout da notificação por push em diferentes dispositivos: selecione iPhone, telefone Android, iPad ou tablet Android para visualizar a renderização.

   ![](assets/push_notif_preview.png)

1. A estimativa **[!UICONTROL Estimated Payload Size]** é baseada nos dados do perfil de teste. O tamanho real da carga pode variar. O limite da mensagem é de 4 KB.

   >[!CAUTION]
   >
   >Se o tamanho da carga exceder o limite de 4 KB, a mensagem não será entregue. Os dados de personalização afetam o tamanho da mensagem.

## Envio da notificação {#sending-the-notification}

As notificações por push podem ser enviadas para um público selecionado no Adobe Campaign definindo os critérios do público-alvo. Para o exemplo abaixo, nosso público-alvo selecionado consiste em 4 assinantes de aplicativos móveis direcionados.

1. Clique em **[!UICONTROL Prepare]** para calcular a meta e gerar as notificações.

   ![](assets/push_send_1.png)

1. Once the preparation has finished successfully, the **[!UICONTROL Deployment]** window presents the following KPIs:**[!UICONTROL Target]** and **[!UICONTROL To deliver]**. Note that the **[!UICONTROL To deliver]** count is lower than the **[!UICONTROL Targeted]** one due to exclusions which can be viewed by clicking![](assets/lp_link_properties.png)button at the bottom of the **[!UICONTROL Deployment]** window.

   ![](assets/push_send_2.png)

1. Na **[!UICONTROL Exclusion logs]** guia, você pode encontrar a lista de todas as mensagens excluídas do destino enviado e o motivo por trás dessa exclusão.

   Aqui, podemos ver que um de nossos assinantes de aplicativos móveis foi excluído porque o endereço estava na lista negra e os outros assinantes porque o perfil era uma duplicata.

   ![](assets/push_send_5.png)

1. Clique na **[!UICONTROL Exclusion causes]** guia para exibir o volume de mensagens excluídas.

   ![](assets/push_send_7.png)

1. Agora você pode clicar em **[!UICONTROL Confirm]** para começar a enviar notificações por push.
1. Verifique o status de sua entrega através do painel de mensagens e logs. Para obter mais informações, consulte [Enviar mensagens](../../sending/using/confirming-the-send.md) e registros [](../../sending/using/monitoring-a-delivery.md#delivery-logs)de entrega.

   Neste exemplo, o painel de mensagens exibe que o Adobe Campaign tentou enviar duas notificações por push: um foi entregue com êxito ao dispositivo e outro falhou. Para saber por que a entrega tem erros, clique no ![](assets/lp_link_properties.png) botão na parte inferior da **[!UICONTROL Deployment]** janela.

   ![](assets/push_send_4.png)

1. Na **[!UICONTROL Deployment]** janela, clique na **[!UICONTROL Sending logs]** guia para acessar a lista de notificações por push enviadas e seus status. Para esta entrega, uma notificação por push foi enviada com êxito, enquanto a outra falhou devido a um token de dispositivo inválido. Esse assinante será então incluído na lista negra de entregas posteriores.

   >[!NOTE]
   >
   >Os motivos podem ser qualquer falha no downstream do Adobe Campaign. No caso de falhas de provedores como apns e fcm, a razão também refletirá isso. Para obter mais informações sobre falhas no provedor, consulte a documentação da [Apple](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CommunicatingwithAPNs.html) e do [Android](https://firebase.google.com/docs/cloud-messaging/http-server-ref) .

   ![](assets/push_send_6.png)

Agora você pode medir o impacto da entrega da notificação por push com relatórios dinâmicos.

**Tópicos relacionados:**

* [Relatório de notificação por push](../../reporting/using/push-notification-report.md)
* [Envio de uma notificação por push em um fluxo de trabalho](../../automating/using/push-notification-delivery.md)

