---
title: Criar e enviar uma notificação por push
description: Siga estas etapas para criar uma notificação por push de envio único no Adobe Campaign.
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: delivery,mobileAppContent,back
feature: Push
role: User
level: Intermediate
exl-id: 41b83014-aea9-4ec2-b20e-c0a05bcad503
source-git-commit: affd4f9716235a283df20de5539e43c4832762f7
workflow-type: tm+mt
source-wordcount: '841'
ht-degree: 3%

---

# Preparação e envio de uma notificação por push{#preparing-and-sending-a-push-notification}

## Preparação da notificação {#preparing-the-notification}

As etapas para criar uma notificação por push com o Adobe Campaign são:

1. Na janela **[!UICONTROL Marketing activities]**, [crie uma nova atividade de marketing](../../start/using/marketing-activities.md#creating-a-marketing-activity).

   Observe que uma única notificação por push também pode ser criada a partir de uma [campanha](../../start/using/marketing-activities.md#creating-a-marketing-activity) ou da [home page](../../start/using/interface-description.md#home-page) do Adobe Campaign.

   Você também pode usar uma atividade de delivery de notificação por push em um workflow. Esta atividade é apresentada na seção [Entrega por notificação por push](../../automating/using/push-notification-delivery.md).

1. Selecione **[!UICONTROL Push notification]**.
1. Selecione um modelo.

   ![](assets/push_notif_type.png)

   Por padrão, você pode selecionar um dos dois modelos a seguir:

   * **[!UICONTROL Send push to Campaign profiles]**: use este modelo para direcionar os perfis do Adobe Campaign CRM que assinaram seu aplicativo para dispositivos móveis e optaram por receber notificações por push. Você pode inserir campos de [personalização](../../designing/using/personalization.md#inserting-a-personalization-field) na sua notificação por push, como o nome do destinatário.
   * **[!UICONTROL Send push to app subscribers]**: use este modelo para enviar uma notificação por push a todos os usuários de aplicativos móveis conhecidos e anônimos que optaram por receber notificações do seu aplicativo. Você pode personalizar essas mensagens com dados coletados do seu aplicativo móvel.

   Também é possível selecionar templates multilíngues. Para obter mais informações, consulte [Criação de uma notificação por push multilíngue](../../channels/using/creating-a-multilingual-push-notification.md).

   Para obter mais informações sobre modelos, consulte a seção [Gerenciamento de modelos](../../start/using/marketing-activity-templates.md).

1. Insira suas propriedades de notificação por push e selecione seu aplicativo móvel no campo **[!UICONTROL Associate a Mobile App to a delivery]**.

   Observe que o menu suspenso exibirá os aplicativos SDK V4 e Experience Platform SDK.

   ![](assets/push_notif_properties.png)

   Você pode vincular a notificação por push a uma campanha. Para fazer isso, selecione-o nas campanhas já criadas.

1. Na tela a seguir, você pode especificar um público-alvo, por exemplo, todos os clientes do VIP que se inscreveram em um aplicativo para dispositivos móveis específico. Para obter mais informações, consulte [Criação de públicos-alvo](../../audiences/using/creating-audiences.md).

   Seu público-alvo será filtrado automaticamente com base no aplicativo para dispositivos móveis selecionado na etapa anterior.

   ![](assets/push_notif_audience.png)

1. Agora você pode personalizar sua notificação por push. Primeiro, escolha o estilo da mensagem: **[!UICONTROL Alert/Message/Badge]** ou **[!UICONTROL Silent push]**. Os tipos de notificação por push estão descritos na seção [Sobre notificações por push](../../channels/using/about-push-notifications.md).

   Edite o conteúdo da sua notificação por push e defina as opções avançadas. Consulte [Personalizando uma notificação por push](../../channels/using/customizing-a-push-notification.md).

   ![](assets/push_notif_content.png)

   O conteúdo e as opções de notificação por push configuradas aqui são passados para o aplicativo móvel na forma de uma carga. A estrutura detalhada da carga é descrita na nota técnica [Como entender a estrutura de carga das notificações por push do Campaign Standard](../../administration/using/push-payload.md).

1. Clique em **[!UICONTROL Create]**.

   ![](assets/push_notif_content_2.png)

1. Antes de enviar a notificação, você pode testá-la com perfis de teste e ver exatamente o que os recipients verão antes de enviar o delivery. Selecione **[!UICONTROL Audiences]** no resumo da entrega e clique na guia **[!UICONTROL Test profiles]**.

   Para obter mais informações sobre como enviar testes, consulte [Perfis de teste](../../sending/using/sending-proofs.md).

1. Selecione seus perfis de teste e clique em **[!UICONTROL Preview]** para exibir a notificação: o conteúdo é personalizado com os dados do perfil de teste.
1. Verifique o layout de notificação por push em diferentes dispositivos: selecione iPhone, Android phone, iPad ou Android tablet para visualizar a renderização.

   ![](assets/push_notif_preview.png)

1. **[!UICONTROL Estimated Payload Size]** é uma estimativa baseada em dados de perfil de teste. O tamanho real do conteúdo pode variar. O limite da mensagem é 4 KB.

   >[!CAUTION]
   >
   >Se o tamanho da carga exceder o limite de 4 KB, a mensagem não será entregue.

Observe que os dados de personalização afetam o tamanho da mensagem.

## Envio da notificação {#sending-the-notification}

As notificações por push podem ser enviadas para um público selecionado no Adobe Campaign definindo os critérios de público. Para o exemplo abaixo, nosso público-alvo selecionado consiste em 4 assinantes de aplicativos para dispositivos móveis direcionados.

1. Clique em **[!UICONTROL Prepare]** para calcular o destino e gerar as notificações.

   ![](assets/push_send_1.png)

1. Ao concluir com êxito a preparação, a janela **[!UICONTROL Deployment]** apresenta os seguintes KPIs: **[!UICONTROL Target]** e **[!UICONTROL To deliver]**. Observe que a contagem **[!UICONTROL To deliver]** é menor do que **[!UICONTROL Targeted]**, devido a exclusões que podem ser visualizadas ao clicar no botão ![](assets/lp_link_properties.png), na parte inferior da janela **[!UICONTROL Deployment]**.

   ![](assets/push_send_2.png)

1. Na guia **[!UICONTROL Exclusion logs]**, é possível encontrar a lista de todas as mensagens excluídas do público-alvo enviado e o motivo por trás dessa exclusão.

   Aqui, podemos ver que um de nossos assinantes de aplicativos móveis foi excluído porque o endereço estava na inclui na lista de bloqueios de assinantes e os outros assinantes porque o perfil era uma duplicata.

   ![](assets/push_send_5.png)

1. Clique na guia **[!UICONTROL Exclusion causes]** para exibir o volume de mensagens excluídas.

   ![](assets/push_send_7.png)

1. Agora você pode clicar em **[!UICONTROL Confirm]** para começar a enviar notificações por push.
1. Verifique o status da entrega no painel de mensagens e logs. Para obter mais informações, consulte [Envio de mensagens](../../sending/using/confirming-the-send.md) e [Logs de entrega](../../sending/using/monitoring-a-delivery.md#delivery-logs).

   Neste exemplo, o painel de mensagens exibe que o Adobe Campaign tentou enviar duas notificações por push: uma foi entregue com êxito ao dispositivo e a outra falhou. Para saber por que a entrega tem erros, clique no botão ![](assets/lp_link_properties.png) na parte inferior da janela **[!UICONTROL Deployment]**.

   ![](assets/push_send_4.png)

1. Na janela **[!UICONTROL Deployment]**, clique na guia **[!UICONTROL Sending logs]** para acessar a lista de notificações por push enviadas e seus status. Para esse delivery, uma notificação por push foi enviada com êxito, enquanto a outra falhou devido a um token de dispositivo inválido. Esse assinante será adicionado ao incluo na lista de bloqueios de delivery adicional.

   >[!NOTE]
   >
   >Os motivos podem ser qualquer falha downstream para o Adobe Campaign. No caso de falhas de provedores como apns e fcm, a razão também refletirá isso. Para obter mais informações sobre falhas de provedor, consulte a documentação do [Apple](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CommunicatingwithAPNs.html) e do [Android](https://firebase.google.com/docs/cloud-messaging/http-server-ref).

   ![](assets/push_send_6.png)

Agora você pode medir o impacto da entrega de notificações por push com relatórios dinâmicos.

**Tópicos relacionados:**

* [Relatório de notificação por push](../../reporting/using/push-notification-report.md)
* [Envio de uma notificação por push em um workflow](../../automating/using/push-notification-delivery.md)
