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
source-wordcount: '852'
ht-degree: 4%

---

# Preparação e envio de uma notificação por push{#preparing-and-sending-a-push-notification}

## Preparação da notificação {#preparing-the-notification}

As etapas para criar uma notificação por push com o Adobe Campaign são:

1. No **[!UICONTROL Marketing activities]** janela, [criar uma nova atividade de marketing](../../start/using/marketing-activities.md#creating-a-marketing-activity).

   Observe que uma única notificação por push também pode ser criada a partir de um [campanha](../../start/using/marketing-activities.md#creating-a-marketing-activity) ou da Adobe Campaign [página inicial](../../start/using/interface-description.md#home-page).

   Você também pode usar uma atividade de delivery de notificação por push em um workflow. Essa atividade é apresentada na [Entrega por notificação por push](../../automating/using/push-notification-delivery.md) seção.

1. Selecione **[!UICONTROL Push notification]**.
1. Selecione um modelo.

   ![](assets/push_notif_type.png)

   Por padrão, você pode selecionar um dos dois templates a seguir:

   * **[!UICONTROL Send push to Campaign profiles]**: use esse modelo para direcionar os perfis do Adobe Campaign CRM que assinaram seu aplicativo móvel e aceitaram receber notificações por push. É possível inserir [personalização](../../designing/using/personalization.md#inserting-a-personalization-field) campos na notificação por push, como o nome do recipient.
   * **[!UICONTROL Send push to app subscribers]**: use este modelo para enviar uma notificação por push para todos os usuários conhecidos e anônimos de aplicativos móveis que optaram por receber notificações de seu aplicativo. É possível personalizar essas mensagens com dados coletados do aplicativo móvel.

   Também é possível selecionar modelos multilíngues. Para obter mais informações, consulte [Criação de uma notificação por push multilíngue](../../channels/using/creating-a-multilingual-push-notification.md).

   Para obter mais informações sobre templates, consulte [Gerenciamento de modelos](../../start/using/marketing-activity-templates.md) seção.

1. Insira suas propriedades de notificação por push e selecione seu aplicativo móvel no **[!UICONTROL Associate a Mobile App to a delivery]** campo.

   Observe que a lista suspensa exibirá os aplicativos SDK V4 e Experience Platform.

   ![](assets/push_notif_properties.png)

   Você pode vincular a notificação por push a uma campanha. Para fazer isso, selecione-a nas campanhas que já foram criadas.

1. Na tela a seguir, é possível especificar um público-alvo, por exemplo, todos os clientes do VIP que assinaram um aplicativo móvel específico. Para obter mais informações, consulte [Criação de públicos-alvo](../../audiences/using/creating-audiences.md).

   O público-alvo será automaticamente filtrado com base no aplicativo móvel selecionado na etapa anterior.

   ![](assets/push_notif_audience.png)

1. Agora é possível personalizar a notificação por push. Primeiro, escolha o estilo da mensagem: **[!UICONTROL Alert/Message/Badge]** ou **[!UICONTROL Silent push]**. Os tipos de notificação por push são descritos na seção [Sobre as notificações por push](../../channels/using/about-push-notifications.md) seção.

   Edite o conteúdo da notificação por push e defina as opções avançadas. Consulte [Personalização de uma notificação por push](../../channels/using/customizing-a-push-notification.md).

   ![](assets/push_notif_content.png)

   O conteúdo da notificação por push e as opções configuradas aqui são passadas para seu aplicativo móvel no formato de um payload. A estrutura detalhada da carga é descrita na seção [Como entender a estrutura de payload das notificações por push do Campaign Standard](../../administration/using/push-payload.md) nota técnica.

1. Clique em **[!UICONTROL Create]**.

   ![](assets/push_notif_content_2.png)

1. Antes de enviar a notificação, você pode testá-la com perfis de teste e depois ver exatamente o que seus recipients verão antes de enviar o delivery. Selecionar **[!UICONTROL Audiences]** do resumo do delivery e clique no link **[!UICONTROL Test profiles]** guia .

   Para obter mais informações sobre o envio de testes, consulte [Testar perfis](../../sending/using/sending-proofs.md).

1. Selecione os perfis de teste e clique em **[!UICONTROL Preview]** para exibir a notificação: o conteúdo é personalizado com os dados do perfil de teste.
1. Verifique o layout de notificação por push em diferentes dispositivos: selecione iPhone, Android phone, iPad ou Android tablet para visualizar a renderização.

   ![](assets/push_notif_preview.png)

1. O **[!UICONTROL Estimated Payload Size]** é uma estimativa baseada em dados de perfil de teste. O tamanho real da carga pode variar. O limite da mensagem é de 4 KB.

   >[!CAUTION]
   >
   >Se o tamanho da carga exceder o limite de 4 KB, a mensagem não será entregue.

Observe que os dados de personalização afetam o tamanho da mensagem.

## Envio da notificação {#sending-the-notification}

As notificações por push podem ser enviadas para um público-alvo selecionado no Adobe Campaign, definindo os critérios de público-alvo. Para o exemplo abaixo, nosso público-alvo selecionado consiste em 4 assinantes de aplicativos móveis direcionados.

1. Clique em **[!UICONTROL Prepare]** para calcular o target e gerar as notificações.

   ![](assets/push_send_1.png)

1. Depois que a preparação for concluída com sucesso, a variável **[!UICONTROL Deployment]** apresenta os seguintes KPIs: **[!UICONTROL Target]** e **[!UICONTROL To deliver]**. Observe que a variável **[!UICONTROL To deliver]** a contagem é menor que a **[!UICONTROL Targeted]** um por causa das exclusões que podem ser visualizadas ao clicar em ![](assets/lp_link_properties.png) na parte inferior da **[!UICONTROL Deployment]** janela.

   ![](assets/push_send_2.png)

1. No **[!UICONTROL Exclusion logs]** , é possível encontrar a lista de todas as mensagens excluídas do público-alvo enviado e o motivo por trás dessa exclusão.

   Aqui, podemos ver que um de nossos assinantes de aplicativos móveis foi excluído porque o endereço estava na lista de bloqueios e os outros assinantes porque o perfil era duplicado.

   ![](assets/push_send_5.png)

1. Clique no botão **[!UICONTROL Exclusion causes]** para exibir o volume de mensagens excluídas.

   ![](assets/push_send_7.png)

1. Agora você pode clicar em **[!UICONTROL Confirm]** para começar a enviar notificações por push.
1. Verifique o status do delivery no painel de mensagens e logs. Para obter mais informações, consulte [Envio de mensagens](../../sending/using/confirming-the-send.md) e [Logs do delivery](../../sending/using/monitoring-a-delivery.md#delivery-logs).

   Neste exemplo, o painel de mensagens exibe que o Adobe Campaign tentou enviar duas notificações por push: um foi entregue com êxito ao dispositivo e outro falhou. Para saber por que o delivery tem erros, clique no link ![](assets/lp_link_properties.png) na parte inferior da **[!UICONTROL Deployment]** janela.

   ![](assets/push_send_4.png)

1. No **[!UICONTROL Deployment]** clique no botão **[!UICONTROL Sending logs]** para acessar a lista de notificações por push enviadas e seus status. Para esse delivery, uma notificação por push foi enviada com êxito, enquanto a outra falhou devido a um token de dispositivo incorreto. Esse assinante será adicionado à  de lista de bloqueios a partir de outros deliveries.

   >[!NOTE]
   >
   >Os motivos podem ser qualquer falha downstream de Adobe Campaign. No caso de falhas de provedores como apns e fcm, o motivo também refletirá isso. Para obter mais informações sobre falhas do provedor, consulte [Apple](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CommunicatingwithAPNs.html) e [Android](https://firebase.google.com/docs/cloud-messaging/http-server-ref) documentação.

   ![](assets/push_send_6.png)

Agora é possível medir o impacto do delivery de notificação por push com relatórios dinâmicos.

**Tópicos relacionados:**

* [Relatório de notificação por push](../../reporting/using/push-notification-report.md)
* [Enviar uma notificação por push em um workflow](../../automating/using/push-notification-delivery.md)
