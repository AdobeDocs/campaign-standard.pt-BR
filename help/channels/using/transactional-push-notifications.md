---
solution: Campaign Standard
product: campaign
title: Notificações por push transacionais
description: Saiba como criar e publicar um push transacional         notificação.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
translation-type: tm+mt
source-git-commit: 9ad23468d3d1cf386d9558e6cd2344ea2316fc82
workflow-type: tm+mt
source-wordcount: '1397'
ht-degree: 8%

---


# Notificações por push transacionais{#transactional-push-notifications}

Você pode usar o Adobe Campaign para enviar notificações por push transacionais em dispositivos móveis iOS e Android. Essas mensagens são recebidas em aplicativos móveis configurados no Adobe Campaign por meio do SDK do Experience Cloud Mobile.

>[!NOTE]
>
>O canal push é opcional. Verifique o contrato de licença. Para obter mais informações sobre notificações por push padrão, consulte [Sobre notificações por push](../../channels/using/about-push-notifications.md).

Para poder enviar notificações por push transacionais, é necessário configurar o Adobe Campaign de acordo. Consulte [Configurar um aplicativo móvel](../../administration/using/configuring-a-mobile-application.md).

Você pode enviar dois tipos de notificações por push transacionais:

* [Notificações por push transacionais direcionadas a um evento](#transactional-push-notifications-targeting-an-event)
* [Notificações por push transacionais direcionando ](#transactional-push-notifications-targeting-a-profile) perfis do banco de dados Adobe Campaign

>[!NOTE]
>
>Para acessar mensagens transacionais, você deve fazer parte do grupo de segurança **[!UICONTROL Administrators (all units)]**. Para obter mais informações, consulte [Gerenciamento de usuários](../../administration/using/users-management.md#functional-administrators).

## Notificações por push transacionais direcionadas a um evento {#transactional-push-notifications-targeting-an-event}

Você pode usar o Adobe Campaign para enviar **notificações por push transacionais anônimas a todos os usuários** que opt in receber notificações do seu aplicativo móvel.

Nesse caso, somente **os dados contidos no próprio evento são usados para definir o público alvo do delivery**. Nenhum dado do banco de dados do perfil integrado da Adobe Campaign é aproveitado.

### Configurar uma notificação por push transacional baseada em eventos {#configuring-event-based-transactional-push-notification}

Para enviar uma notificação por push transacional para todos os usuários que opt in receber notificações do aplicativo móvel, primeiro é necessário criar e configurar um evento direcionando os dados contidos no próprio evento.

>[!NOTE]
>
>Você ainda pode personalizar o conteúdo de uma notificação por push transacional baseada em eventos usando [atributos do evento](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes) (dados do evento) e [enriquecimento](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content) (dados do banco de dados da Campanha). Consulte [o exemplo abaixo](#sending-event-based-transactional-push-notification).

O evento deve conter os três elementos seguintes:

* Um **token de registro**, que é a ID de usuário para um aplicativo móvel e um dispositivo. Pode não corresponder a nenhum perfil do banco de dados Adobe Campaign.
* Um **nome do aplicativo móvel** (um para todos os dispositivos - Android e iOS). Esta é a ID do aplicativo móvel configurado no Adobe Campaign que será usada para receber notificações por push nos dispositivos dos usuários. Para obter mais informações, consulte [Configurar um aplicativo móvel](../../administration/using/configuring-a-mobile-application.md).
* Uma **plataforma push** (&quot;gcm&quot; para Android ou &quot;apns&quot; para iOS).

Para configurar o evento, siga as etapas abaixo:

1. Ao criar a configuração do evento, selecione o canal **[!UICONTROL Mobile application]** e o targeting dimension **[!UICONTROL Real-time event]** (consulte [Criação de um evento](../../channels/using/configuring-transactional-event.md#creating-an-event)).
1. Adicione campos ao evento. Isso permitirá que você personalize o mensagen transacional (consulte [Definição dos atributos do evento](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes)). Neste exemplo, defina os campos &quot;gateNumber&quot;, &quot;lastname&quot; e &quot;firstname&quot;.
1. Enriqueça o conteúdo do mensagen transacional se quiser usar informações adicionais do banco de dados Adobe Campaign (consulte [Enriquecendo o evento](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)).

   >[!NOTE]
   >
   >As mensagens transacionais baseadas em evento só devem usar os dados contidos no evento enviado para definir o recipient e a personalização do conteúdo da mensagem. No entanto, você pode enriquecer o conteúdo da mensagem transacional usando informações do banco de dados do Adobe Campaign.

1. [Pré-visualização e publique o evento](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event).

   Ao visualizar o evento, a REST API contém os atributos &quot;registrationToken&quot;, &quot;application&quot; e &quot;pushPlatform&quot; que serão usados para público alvo do delivery.

   ![](assets/message-center_push_api.png)

   Depois que o evento é publicado, uma notificação por push transacional vinculada ao novo evento é criada automaticamente. Agora você pode modificar e publicar a mensagem que acabou de ser criada (consulte [esta seção](#sending-event-based-transactional-push-notification)).

1. Integre o evento ao seu site (consulte Integrar o acionamento do evento (../../channels/using/getting-started-with-transactional-msg.md#integration-evento-trigger)).

### Envio de uma notificação por push transacional baseada em eventos {#sending-event-based-transactional-push-notification}

Por exemplo, uma empresa de companhia aérea deseja convidar seus usuários de aplicativos móveis a seguir para a porta de embarque relevante.

A empresa enviará uma notificação por push transacional por usuário (identificada com um token de registro), usando um aplicativo móvel, por meio de um único dispositivo.

1. Acesse a mensagem transacional criada para editá-la. Consulte [Acesso a mensagens transacionais](../../channels/using/editing-transactional-message.md#accessing-transactional-messages).

   ![](assets/message-center_push_message.png)

1. Clique no bloco **[!UICONTROL Content]** para modificar o título e o corpo da mensagem.

1. Você pode inserir campos de personalização para adicionar elementos definidos ao criar o evento (consulte [Definição dos atributos do evento](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes)).

   ![](assets/message-center_push_content.png)

   Para localizar esses campos, clique no lápis ao lado de um item, clique em **[!UICONTROL Insert personalization field]** e selecione **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**.

   ![](assets/message-center_push_personalization.png)

   Para obter mais informações sobre como editar um conteúdo de notificação por push, consulte [Preparação e envio de uma notificação por push](../../channels/using/preparing-and-sending-a-push-notification.md).

1. Você também pode enriquecer o conteúdo do mensagen transacional se quiser usar informações adicionais do banco de dados Adobe Campaign (consulte [Enriquecendo o evento](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)).

1. Salve as alterações e publique a mensagem. Consulte [Publicação de uma mensagem transacional](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message).

1. Usando a API REST da Adobe Campaign Standard, envie um evento para um token de registro (ABCDEF123456789), usando um aplicativo móvel (WeFlight), no Android (gcm), que contém os dados de embarque:

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

   Para obter mais informações sobre a integração do acionamento de um evento em um sistema externo, consulte Integrar o acionamento do evento (../../channels/using/getting-started-with-transactional-msg.md#integration-evento-trigger).

Se o token de registro existir, o usuário correspondente receberá uma notificação por push transacional incluindo o seguinte conteúdo:

*&quot;Olá Jane Green, o embarque acabou de começar! Prossiga para o Portão B18.&quot;*

## Notificações por push transacionais direcionadas a um perfil {#transactional-push-notifications-targeting-a-profile}

Você pode enviar uma notificação por push transacional **para os perfis Adobe Campaign que se inscreveram no seu aplicativo móvel**. Este delivery pode conter [campos de personalização](../../designing/using/personalization.md#inserting-a-personalization-field), como o nome do recipient, diretamente recuperado do banco de dados da Adobe Campaign.

Nesse caso, o evento deve conter alguns campos **permitindo a reconciliação com um perfil do banco de dados Adobe Campaign**.

Ao direcionar perfis, uma notificação por push transacional é enviada por aplicativo móvel e por dispositivo. Por exemplo, se um usuário do Adobe Campaign se inscreveu em dois aplicativos, esse usuário receberá duas notificações. Se um usuário se inscreveu no mesmo aplicativo com dois dispositivos diferentes, esse usuário receberá uma notificação em cada dispositivo.

Os aplicativos móveis nos quais um perfil se inscreveu estão listados na guia **[!UICONTROL Mobile App Subscriptions]** desse perfil. Para acessar essa guia, selecione um perfil e clique no botão **[!UICONTROL Edit profile properties]** à direita.

![](assets/push_notif_subscriptions.png)

Para obter mais informações sobre como acessar e editar perfis, consulte [Sobre perfis](../../audiences/using/about-profiles.md).

### Configurar uma notificação por push transacional baseada em perfis {#configuring-profile-based-transactional-push-notification}

Para enviar uma notificação por push transacional para os perfis Adobe Campaign que se inscreveram em seu aplicativo móvel, primeiro é necessário criar e configurar um evento direcionado ao banco de dados Adobe Campaign.

1. Ao criar a configuração do evento, selecione o canal **[!UICONTROL Mobile application]** e o targeting dimension **[!UICONTROL Profile]** (consulte [Criação de um evento](../../channels/using/configuring-transactional-event.md#creating-an-event)).

   Por padrão, a notificação por push transacional será enviada para todos os aplicativos móveis nos quais os recipient se inscreveram. Para enviar a notificação por push para um aplicativo móvel específico, selecione-o na lista. Os outros aplicativos móveis serão direcionados pela mensagem, mas serão excluídos do envio.

   ![](assets/message-center_push_appfilter.png)

1. Adicione campos ao evento, se quiser personalizar o mensagen transacional (consulte [Definição dos atributos do evento](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes)).

   >[!NOTE]
   >
   >É necessário adicionar pelo menos um campo para criar um enriquecimento. Não é necessário criar outros campos, como **Nome** e **Sobrenome**, pois você poderá usar campos de personalização do banco de dados Adobe Campaign.

1. Crie um enriquecimento para vincular o evento ao recurso **[!UICONTROL Profile]** (consulte [Enriquecendo o evento](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)). A criação de um enriquecimento é obrigatória ao usar um targeting dimension **[!UICONTROL Profile]**.
1. [Pré-visualização e publique o evento](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event).

   Ao visualizar o evento, a API REST não contém um atributo que especifique o token de registro, o nome do aplicativo e a plataforma de push, conforme serão recuperados do recurso **[!UICONTROL Profile]**.

   Depois que o evento é publicado, uma notificação por push transacional vinculada ao novo evento é criada automaticamente. Agora você pode modificar e publicar a mensagem que acabou de ser criada (consulte [esta seção](#sending-profile-based-transactional-push-notification)).

1. Integre o evento ao seu site (consulte Integrar o acionamento do evento (../../channels/using/getting-started-with-transactional-msg.md#integration-evento-trigger)).

### Envio de uma notificação por push transacional baseada em perfis {#sending-profile-based-transactional-push-notification}

Por exemplo, uma empresa aérea deseja enviar uma última chamada de embarque para todos os usuários do Adobe Campaign que se inscreveram em seu aplicativo móvel.

1. Acesse a mensagem transacional criada para editá-la. Consulte [Acesso a mensagens transacionais](../../channels/using/editing-transactional-message.md#accessing-transactional-messages).

1. Clique no bloco **[!UICONTROL Content]** para modificar o título e o corpo da mensagem.

   Ao contrário das configurações baseadas em eventos em tempo real, você tem acesso direto a todas as informações do perfil para personalizar sua mensagem. Consulte [Inserção de um campo de personalização](../../designing/using/personalization.md#inserting-a-personalization-field).

   Para obter mais informações sobre como editar um conteúdo de notificação por push, consulte [Preparação e envio de uma notificação por push](../../channels/using/preparing-and-sending-a-push-notification.md).

1. Salve as alterações e publique a mensagem. Consulte [Publicação de uma mensagem transacional](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message).
1. Usando a API REST da Adobe Campaign Standard, envie um evento para um perfil:

   ```
   {
     "ctx":
     {
       "email":"janegreen@email.com",
       "gateNumber":"D16",
     }
   }
   ```

Para obter mais informações sobre a integração do acionamento de um evento em um sistema externo, consulte Integrar o acionamento do evento (../../channels/using/getting-started-with-transactional-msg.md#integration-evento-trigger).

O usuário correspondente recebe uma notificação por push transacional incluindo todos os elementos de personalização recuperados do banco de dados Adobe Campaign.

>[!NOTE]
>
>Não há campos de token de registro, aplicativo e plataforma de push. Neste exemplo, a reconciliação é executada com o campo de email.
