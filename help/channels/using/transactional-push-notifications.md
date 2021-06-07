---
solution: Campaign Standard
product: campaign
title: Notificações por push transacionais
description: Saiba como enviar notificações transacionais por push com o Adobe Campaign Standard.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Mensagens transacionais
role: Business Practitioner
level: Intermediate
exl-id: 61988c1d-d538-47b1-94c1-f3fbdf314b65
source-git-commit: 33d3dc43a64b9670666844a3266e2aa2458a1c40
workflow-type: tm+mt
source-wordcount: '1453'
ht-degree: 4%

---

# Notificações por push transacionais{#transactional-push-notifications}

Você pode usar o Adobe Campaign para enviar notificações transacionais por push em dispositivos móveis iOS e Android. Essas mensagens são recebidas em aplicativos móveis que você configurou no Adobe Campaign por meio do SDK do Experience Cloud Mobile.

>[!NOTE]
>
>O canal de push é opcional. Verifique o contrato de licença. Para obter mais informações sobre notificações por push padrão, consulte [Sobre notificações por push](../../channels/using/about-push-notifications.md).

Para enviar notificações transacionais por push, é necessário configurar o Adobe Campaign adequadamente. Consulte [Configuração de um aplicativo móvel](../../administration/using/configuring-a-mobile-application.md).

Você pode enviar dois tipos de notificações transacionais por push:

* [Notificações por push transacionais direcionadas a um evento](#transactional-push-notifications-targeting-an-event)
* [Notificações por push transacionais direcionadas a ](#transactional-push-notifications-targeting-a-profile) perfis do banco de dados do Adobe Campaign

## Notificações por push transacionais direcionadas a um evento {#transactional-push-notifications-targeting-an-event}

Você pode usar o Adobe Campaign para enviar **notificações transacionais por push anônimas a todos os usuários** que optaram por receber notificações do aplicativo móvel.

Nesse caso, somente **os dados contidos no próprio evento são usados para definir o target do delivery**. Nenhum dado do banco de dados de perfis integrados do Adobe Campaign é aproveitado.

### Configurar uma notificação por push transacional baseada em eventos {#configuring-event-based-transactional-push-notification}

Para enviar uma notificação por push transacional para todos os usuários que optaram por receber notificações do aplicativo móvel, primeiro é necessário criar e configurar um evento direcionado aos dados contidos no próprio evento.

>[!NOTE]
>
>Você ainda pode personalizar o conteúdo de uma notificação por push transacional baseada em eventos usando [atributos de evento](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes) (dados do evento) e [enriquecimento de evento](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content) (dados do banco de dados do Campaign). Consulte [o exemplo abaixo](#sending-event-based-transactional-push-notification).

O evento deve conter os três elementos a seguir:

* Um **token de registro**, que é o ID do usuário para um aplicativo móvel e um dispositivo. Pode não corresponder a nenhum perfil do banco de dados do Adobe Campaign.
* Um **nome do aplicativo móvel** (um para todos os dispositivos - Android e iOS). Essa é a ID do aplicativo móvel configurado no Adobe Campaign que será usada para receber notificações por push nos dispositivos dos usuários. Para obter mais informações, consulte [Configuração de um aplicativo móvel](../../administration/using/configuring-a-mobile-application.md).
* Uma **plataforma de push** (&quot;gcm&quot; para Android ou &quot;apns&quot; para iOS).

Para configurar o evento, siga as etapas abaixo:

1. Ao criar a configuração do evento, selecione o canal **[!UICONTROL Push notification]** e o targeting dimension **[!UICONTROL Real-time event]** (consulte [Criação de um evento](../../channels/using/configuring-transactional-event.md#creating-an-event)).
1. Adicione campos ao evento. Isso permitirá personalizar a mensagem transacional (consulte [Definição dos atributos de evento](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes)). Neste exemplo, defina os campos &quot;gateNumber&quot;, &quot;lastname&quot; e &quot;firstname&quot;.
1. Você também pode enriquecer o conteúdo de sua mensagem. Para fazer isso, adicione campos da tabela que você vinculou à configuração do evento (consulte [Enriquecendo o evento](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)).

   <!--Event-based transactional messaging is supposed to use only the data that are in the sent event to define the recipient and the message content personalization. However, you can enrich the content of your transactional message using information from the Adobe Campaign database.-->

1. [Visualize e publique o evento](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event).

   Ao visualizar o evento, a API REST contém os atributos &quot;registrationToken&quot;, &quot;application&quot; e &quot;pushPlatform&quot; que serão usados para direcionar o delivery.

   ![](assets/message-center_push_api.png)

   Depois que o evento for publicado, uma notificação por push transacional vinculada ao novo evento será criada automaticamente. Agora você pode modificar e publicar a mensagem que acabou de ser criada (consulte [esta seção](#sending-event-based-transactional-push-notification)).

1. Integre o evento em seu site (consulte [Integrar o evento que aciona](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)).

### Envio de uma notificação por push transacional baseada em eventos {#sending-event-based-transactional-push-notification}

Por exemplo, uma companhia aérea deseja convidar seus usuários de aplicativos móveis para prosseguir para a porta de embarque relevante.

A empresa enviará uma notificação por push transacional por usuário (identificada com um token de registro), usando um aplicativo móvel, por meio de um único dispositivo.

1. Acesse a mensagem transacional criada para editá-la. Consulte [Acesso a mensagens transacionais](../../channels/using/editing-transactional-message.md#accessing-transactional-messages).

   ![](assets/message-center_push_message.png)

1. Clique no bloco **[!UICONTROL Content]** para modificar o título e o corpo da mensagem.

1. Você pode inserir campos de personalização para adicionar elementos definidos ao criar o evento (consulte [Definição dos atributos do evento](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes)).

   ![](assets/message-center_push_content.png)

   Para localizar esses campos, clique no lápis ao lado de um item, clique em **[!UICONTROL Insert personalization field]** e selecione **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**.

   ![](assets/message-center_push_personalization.png)

   Para obter mais informações sobre como editar o conteúdo de uma notificação por push, consulte [Preparação e envio de uma notificação por push](../../channels/using/preparing-and-sending-a-push-notification.md).

1. Você também pode enriquecer o conteúdo da mensagem transacional se desejar usar informações adicionais do banco de dados do Adobe Campaign (consulte [Enriquecendo o evento](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)).

1. Salve as alterações e publique a mensagem. Consulte [Publicação de uma mensagem transacional](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message).

1. Usando a API REST do Adobe Campaign Standard, envie um evento para um token de registro (ABCDEF123456789), usando um aplicativo móvel (WeFlight), no Android (gcm), com os dados de embarque:

   ```
   {
     "registrationToken":"ABCDEF123456789",
     "application":"WeFlight",
     "pushPlatform":"gcm",
     "ctx":
     {
       "gateNumber":"Gate B18",
       "lastname":"Green",
       "firstname":"Jane"
     }
   }
   ```

   Para obter mais informações sobre como integrar o acionamento de um evento em um sistema externo, consulte [Integrar o evento que aciona](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger).

Se o token de registro existir, o usuário correspondente receberá uma notificação por push transacional, incluindo o seguinte conteúdo:

*&quot;Olá Jane Green, o embarque acabou de começar! Prossiga para o Portão B18.&quot;*

## Notificações por push transacionais direcionadas a um perfil {#transactional-push-notifications-targeting-a-profile}

Você pode enviar uma notificação por push transacional **para os perfis do Adobe Campaign que assinaram seu aplicativo móvel**. Esse delivery pode conter [campos de personalização](../../designing/using/personalization.md#inserting-a-personalization-field), como o nome do recipient, recuperados diretamente do banco de dados do Adobe Campaign.

Nesse caso, o evento deve conter alguns campos **permitindo a reconciliação com um perfil do banco de dados do Adobe Campaign**.

Ao direcionar perfis, uma notificação por push transacional é enviada por aplicativo móvel e por dispositivo. Por exemplo, se um usuário do Adobe Campaign se inscreveu em dois aplicativos, esse usuário receberá duas notificações. Se um usuário se inscreveu no mesmo aplicativo com dois dispositivos diferentes, esse usuário receberá uma notificação em cada dispositivo.

Os aplicativos móveis que um perfil assinou são listados na guia **[!UICONTROL Mobile App Subscriptions]** desse perfil. Para acessar essa guia, selecione um perfil e clique no botão **[!UICONTROL Edit profile properties]** à direita.

![](assets/push_notif_subscriptions.png)

Para obter mais informações sobre acesso e edição de perfis, consulte [Sobre perfis](../../audiences/using/about-profiles.md).

### Configurar uma notificação por push transacional baseada em perfil {#configuring-profile-based-transactional-push-notification}

Para enviar uma notificação por push transacional para os perfis do Adobe Campaign que assinaram seu aplicativo móvel, primeiro é necessário criar e configurar um evento direcionado ao banco de dados do Adobe Campaign.

1. Ao criar a configuração do evento, selecione o canal **[!UICONTROL Push notification]** e o targeting dimension **[!UICONTROL Profile]** (consulte [Criação de um evento](../../channels/using/configuring-transactional-event.md#creating-an-event)).

   Por padrão, a notificação por push transacional será enviada para todos os aplicativos móveis aos quais os recipients assinaram. Para enviar a notificação por push para um aplicativo móvel específico, selecione-a na lista. Os outros aplicativos móveis serão direcionados pela mensagem, mas serão excluídos do envio.

   ![](assets/message-center_push_appfilter.png)

1. Adicione campos ao evento, se desejar personalizar a mensagem transacional (consulte [Definição dos atributos do evento](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes)).

   >[!NOTE]
   >
   >Você deve adicionar pelo menos um campo para criar um enriquecimento. Você não precisa criar outros campos, como **First name** e **Last name**, pois poderá usar campos de personalização do banco de dados do Adobe Campaign.

1. Crie um enriquecimento para vincular o evento ao recurso **[!UICONTROL Profile]** (consulte [Enriquecendo o evento](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)) e selecione esse enriquecimento como o **[!UICONTROL Targeting enrichment]**.

   >[!IMPORTANT]
   >
   >Esta etapa é obrigatória para eventos baseados em perfil.

1. [Visualize e publique o evento](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event).

   Ao visualizar o evento, a API REST não contém um atributo especificando o token de registro, o nome do aplicativo e a plataforma de push, conforme serão recuperados do recurso **[!UICONTROL Profile]**.

   Depois que o evento for publicado, uma notificação por push transacional vinculada ao novo evento será criada automaticamente. Agora você pode modificar e publicar a mensagem que acabou de ser criada (consulte [esta seção](#sending-profile-based-transactional-push-notification)).

1. Integre o evento em seu site (consulte [Integrar o evento que aciona](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)).

### Envio de uma notificação por push transacional baseada em perfil {#sending-profile-based-transactional-push-notification}

Por exemplo, uma companhia aérea deseja enviar uma última chamada de internação para todos os usuários da Adobe Campaign que assinaram seu aplicativo móvel.

1. Acesse a mensagem transacional criada para editá-la. Consulte [Acesso a mensagens transacionais](../../channels/using/editing-transactional-message.md#accessing-transactional-messages).

1. Clique no bloco **[!UICONTROL Content]** para modificar o título e o corpo da mensagem.

   Ao contrário das configurações baseadas em eventos em tempo real, você tem acesso direto a todas as informações de perfil para personalizar sua mensagem. Consulte [Inserção de um campo de personalização](../../designing/using/personalization.md#inserting-a-personalization-field).

   Para obter mais informações sobre como editar o conteúdo de uma notificação por push, consulte [Preparação e envio de uma notificação por push](../../channels/using/preparing-and-sending-a-push-notification.md).

1. Salve as alterações e publique a mensagem. Consulte [Publicação de uma mensagem transacional](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message).
1. Com a API REST do Adobe Campaign Standard, envie um evento para um perfil:

   ```
   {
     "ctx":
     {
       "email":"janegreen@email.com",
       "gateNumber":"D16",
     }
   }
   ```

Para obter mais informações sobre como integrar o acionamento de um evento em um sistema externo, consulte [Integrar o evento que aciona](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger).

O usuário correspondente recebe uma notificação por push transacional incluindo todos os elementos de personalização recuperados do banco de dados do Adobe Campaign.

>[!NOTE]
>
>Não há campos de token de registro, aplicativo e plataforma de push. Neste exemplo, a reconciliação é executada com o campo de email .

## Alteração do target mapping em uma notificação por push transacional {#change-target-mapping}

As notificações por push transacionais usam um [target mapping](../../administration/using/target-mappings-in-campaign.md) específico que contém as configurações técnicas necessárias para enviar esse tipo de delivery.

Para alterar esse target mapping, siga as etapas abaixo:

1. Na lista de mensagens transacionais, selecione uma notificação por push.

1. No painel da mensagem, clique no botão **[!UICONTROL Edit properties]**.

   ![](assets/message-center_push_edit.png)

1. Expanda a seção **[!UICONTROL Advanced parameters]**.

1. Clique em **[!UICONTROL Select a 'Target mapping' element]**.

   ![](assets/message-center_push_target-mapping.png)

1. Selecione um target mapping na lista.

   >[!NOTE]
   >
   >Para obter o tempo e o desempenho ideais de preparação de delivery ao enviar **notificações por push transacionais baseadas em perfil**, use o target mapping **[!UICONTROL Profile - Real-time event for Push (mapRtEventAppSubRcp)]**.

   ![](assets/message-center_push_target-mapping_change.png)

1. Confirme sua alteração e publique a mensagem. Consulte [Publicação de uma mensagem transacional](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message).

   >[!IMPORTANT]
   >
   >Você deve publicar a mensagem novamente para que a alteração seja efetiva, caso contrário, o target mapping anterior ainda será usado.


