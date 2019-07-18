---
title: Notificações por push transacionais
seo-title: Notificações por push transacionais
description: Notificações por push transacionais
seo-description: Saiba como criar e publicar uma notificação por push transacional.
page-status-flag: nunca ativado
uuid: ef 31 c 1 b 6-9 ef 8-42 e 3-b 49 d -72 f 9 eac 8 ea 32
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canais
content-type: reference
topic-tags: transacionais-messaging
discoiquuid: e 645 d 4 b 9-001 f -47 d 9-8 a 0 f-b 4696 c 75 c 5 d 3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 855db33971afdf9f02bf1b00be67c9e3f50bee06

---


# Transactional push notifications{#transactional-push-notifications}

Você pode usar o Adobe Campaign para enviar notificações por push transacionais em dispositivos móveis iOS e Android. Essas mensagens são recebidas em aplicativos móveis configurados no Adobe Campaign, aproveitando o SDK móvel da Experience Cloud.

>[!NOTE]
>
>O canal de push é opcional. Verifique seu contrato de licença. For more information on standard push notifications, see [Push notifications](../../channels/using/about-push-notifications.md).

Você pode enviar dois tipos de notificações por push transacionais:

* Notificações por push transacionais direcionadas para um evento.
* Perfis de segmentação de notificações por push transacionais do banco de dados do Adobe Campaign.

Once you have created and published an event (the cart abandonment explained in [this section](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle)), the corresponding transactional push notification is created automatically.

The configuration steps are presented in the [Configuring an event to send a transactional push notification](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) section.

Para que o evento dispare uma mensagem transacional, é necessário personalizar a mensagem e, em seguida, testar e publicá-la.

>[!NOTE]
>
>To access the transactional messages, you must have administration rights or appear in the **[!UICONTROL Message Center agents]** (mcExec) security group.

## Transactional push notifications targeting an event {#transactional-push-notifications-targeting-an-event}

Você pode enviar uma notificação por push transacional anônima para todos os usuários que aceitaram receber notificações de seu aplicativo móvel.

Nesse caso, apenas os dados contidos no próprio evento são usados para definir o destino da entrega. Nenhum dado do banco de dados de perfil integrado do Adobe Campaign é potencializado.

### Sending a transactional push notification targeting an event {#sending-a-transactional-push-notification-targeting-an-----------event}

Por exemplo, uma companhia aérea deseja convidar seus usuários do aplicativo móvel para continuar para o portfólio relevante para embarque.

A empresa enviará uma notificação por push transacional por usuário (identificada com um token de registro) usando um aplicativo móvel, por meio de um único dispositivo.

1. Vá para a mensagem transacional que foi criada para editá-la. See [Event transactional messages](../../channels/using/event-transactional-messages.md).

   ![](assets/message-center_push_message.png)

1. Click the **[!UICONTROL Content]** block to modify your message's title and body.

   Você pode inserir campos de personalização para adicionar elementos definidos quando criou seu evento.

   ![](assets/message-center_push_content.png)

   To find these fields, click the pencil next to an item, click **[!UICONTROL Insert personalization field]** and select **[!UICONTROL Transactional event]** &gt; **[!UICONTROL Event context]**.

   ![](assets/message-center_push_personalization.png)

   For more on editing a push notification content, see [Creating a push notification](../../channels/using/preparing-and-sending-a-push-notification.md).

1. Salve as alterações e publique a mensagem. See [Publishing a transactional message](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message).
1. Usando a API REST do Adobe Campaign Standard, envie um evento para um token de registro (ABCDEF 123456789), usando um aplicativo móvel (weflight), no Android (gcm), contendo os dados de embarque.

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

   For more on integrating the triggering of an event into an external system, see [Site integration](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

Se o token de registro existir, o usuário correspondente receberá uma notificação por push transacional, incluindo o seguinte conteúdo:

" Hello Jane Green, a navegação acabou! Prossiga para a Gate B 18. "

## Transactional push notifications targeting a profile {#transactional-push-notifications-targeting-a-profile}

Você pode enviar uma notificação por push transacional para os perfis do Adobe Campaign que assinaram seu aplicativo móvel. This delivery can contain [personalization](../../designing/using/inserting-a-personalization-field.md) fields, such as the recipient's first name.

Nesse caso, o evento deve conter alguns campos permitindo a reconciliação com um perfil do banco de dados do Adobe Campaign.

Ao direcionar perfis, uma notificação por push transacional é enviada por aplicativo móvel e por dispositivo. Por exemplo, se um usuário do Adobe Campaign tiver se inscrito em dois aplicativos, esse usuário receberá duas notificações. Se um usuário tiver se inscrito no mesmo aplicativo com dois dispositivos diferentes, esse usuário receberá uma notificação em cada dispositivo.

The mobile applications a profile has subscribed to are listed in the **[!UICONTROL Mobile App Subscriptions]** tab of this profile. To access this tab, select a profile and click the **[!UICONTROL Edit profile properties]** button on the right.

![](assets/push_notif_subscriptions.png)

For more information on accessing and editing profiles, see [Profiles](../../audiences/using/creating-profiles.md).

### Sending a transactional push notification targeting a profile {#sending-a-transactional-push-notification-targeting-a-----------profile}

Por exemplo, uma companhia aérea deseja enviar uma última chamada para ter acesso a todos os usuários do Adobe Campaign que assinaram seu aplicativo móvel.

1. Vá para a mensagem transacional que foi criada para editá-la. See [Event transactional messages](../../channels/using/event-transactional-messages.md).

   ![](assets/message-center_push_message_profile.png)

1. Click the **[!UICONTROL Content]** block to modify your message's title and body.

   Ao contrário das configurações baseadas em eventos em tempo real, você tem acesso direto a todas as informações de perfil para personalizar sua mensagem. See [Inserting a personalization field](../../designing/using/inserting-a-personalization-field.md).

   ![](assets/message-center_push_content_profile.png)

   Para obter mais informações sobre como editar um conteúdo de notificação por push. See [Creating a push notification](../../channels/using/preparing-and-sending-a-push-notification.md).

1. Salve as alterações e publique a mensagem. See [Publishing a transactional message](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message).
1. Usando a API REST do Adobe Campaign Standard, envie um evento para um perfil.

   ```
   {
     "ctx":
     {
       "email":"janegreen@email.com",
       "gateNumber":"D16",
     }
   }
   ```

   For more on integrating the triggering of an event into an external system, see [Site integration](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

   >[!NOTE]
   >
   >Não há campos de token de registro, aplicativos e plataforma de push. Neste exemplo, a reconciliação é realizada com o campo de email.

