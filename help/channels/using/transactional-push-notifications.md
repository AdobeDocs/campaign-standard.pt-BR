---
title: Notificações por push transacionais
seo-title: Notificações por push transacionais
description: Notificações por push transacionais
seo-description: Saiba como criar e publicar uma notificação por push transacional.
page-status-flag: nunca ativado
uuid: ef31c1b6-9ef8-42e3-b49d-72f9eac8ea32
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: canais
content-type: referência
topic-tags: mensagens transacionais
discoiquuid: e645d4b9-001f-47d9-8a0f-b4696c75c5d3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d9357481a567cb0d11eea43211abf08a6dcb07d6

---


# Notificações por push transacionais{#transactional-push-notifications}

Você pode usar o Adobe Campaign para enviar notificações por push transacionais em dispositivos móveis iOS e Android. Essas mensagens são recebidas em aplicativos móveis que você configura no Adobe Campaign, aproveitando o SDK móvel da Experience Cloud.

>[!NOTE]
>
>O canal de push é opcional. Verifique o contrato de licença. Para obter mais informações sobre notificações por push padrão, consulte Notificações por [push](../../channels/using/about-push-notifications.md).

Você pode enviar dois tipos de notificações por push transacionais:

* Notificações por push transacionais direcionadas a um evento.
* Notificações por push transacionais direcionando perfis do banco de dados do Adobe Campaign.

Depois de criar e publicar um evento (o abandono do carrinho explicado nesta seção [](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle)), a notificação por push transacional correspondente é criada automaticamente.

As etapas de configuração são apresentadas na seção [Configuração de um evento para enviar uma notificação](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) por push transacional.

Para que o evento dispare o envio de uma mensagem transacional, é necessário personalizar a mensagem, testá-la e publicá-la.

>[!NOTE]
>
>Para acessar as mensagens transacionais, é necessário ter direitos administrativos ou aparecer no grupo de segurança **[!UICONTROL Message Center agents]** (mcExec).

## Notificações por push transacionais direcionadas a um evento {#transactional-push-notifications-targeting-an-event}

Você pode enviar uma notificação por push transacional anônima para todos os usuários que aceitaram receber notificações do seu aplicativo móvel.

Nesse caso, somente os dados contidos no próprio evento são usados para definir o destino de entrega. Nenhum dado do banco de dados de perfil integrado do Adobe Campaign é aproveitado.

### Envio de uma notificação por push transacional direcionada a um evento {#sending-a-transactional-push-notification-targeting-an-----------event}

Por exemplo, uma companhia aérea deseja convidar seus usuários de aplicativos móveis a seguir para a porta de embarque relevante.

A empresa enviará uma notificação por push transacional por usuário (identificada com um token de registro), usando um aplicativo móvel, por meio de um único dispositivo.

1. Vá para a mensagem transacional criada para editá-la. Consulte Mensagens [transacionais de](../../channels/using/event-transactional-messages.md)eventos.

   ![](assets/message-center_push_message.png)

1. Clique no **[!UICONTROL Content]** bloco para modificar o título e o corpo da mensagem.

   É possível inserir campos de personalização para adicionar elementos definidos ao criar o evento.

   ![](assets/message-center_push_content.png)

   Para localizar esses campos, clique no lápis ao lado de um item, clique em **[!UICONTROL Insert personalization field]** e selecione **[!UICONTROL Context]** &gt; **[!UICONTROL Real-time event]** &gt; **[!UICONTROL Event context]**.

   ![](assets/message-center_push_personalization.png)

   Para obter mais informações sobre como editar um conteúdo de notificação por push, consulte [Criar uma notificação](../../channels/using/preparing-and-sending-a-push-notification.md)por push.

1. Salve as alterações e publique a mensagem. Consulte [Publicar uma mensagem](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message)transacional.
1. Usando a API REST do Adobe Campaign Standard, envie um evento para um token de registro (ABCDEF123456789), usando um aplicativo móvel (WeFlight), no Android (gcm), que contém os dados de embarque.

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

   Para obter mais informações sobre a integração do acionamento de um evento em um sistema externo, consulte Integração [](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)do site.

Se o token de registro existir, o usuário correspondente receberá uma notificação por push transacional incluindo o seguinte conteúdo:

"Olá Jane Green, o embarque acabou de começar! Prossiga para o portão B18."

## Notificações por push transacionais direcionadas a um perfil {#transactional-push-notifications-targeting-a-profile}

Você pode enviar uma notificação por push transacional para os perfis do Adobe Campaign que se inscreveram no seu aplicativo móvel. Essa entrega pode conter campos de [personalização](../../designing/using/personalization.md#inserting-a-personalization-field) , como o nome do destinatário.

Nesse caso, o evento deve conter alguns campos que permitem a reconciliação com um perfil do banco de dados do Adobe Campaign.

Ao direcionar perfis, uma notificação por push transacional é enviada por aplicativo móvel e por dispositivo. Por exemplo, se um usuário do Adobe Campaign se inscreveu em dois aplicativos, esse usuário receberá duas notificações. Se um usuário se inscreveu no mesmo aplicativo com dois dispositivos diferentes, esse usuário receberá uma notificação em cada dispositivo.

Os aplicativos móveis aos quais um perfil se inscreveu são listados na **[!UICONTROL Mobile App Subscriptions]** guia desse perfil. Para acessar essa guia, selecione um perfil e clique no **[!UICONTROL Edit profile properties]** botão à direita.

![](assets/push_notif_subscriptions.png)

Para obter mais informações sobre como acessar e editar perfis, consulte [Perfis](../../audiences/using/creating-profiles.md).

### Envio de uma notificação por push transacional direcionada a um perfil {#sending-a-transactional-push-notification-targeting-a-----------profile}

Por exemplo, uma companhia aérea deseja enviar uma última chamada para o embarque a todos os usuários do Adobe Campaign que se inscreveram em seu aplicativo móvel.

1. Vá para a mensagem transacional criada para editá-la. Consulte Mensagens [transacionais de](../../channels/using/event-transactional-messages.md)eventos.

   <!--![](assets/message-center_push_message_profile.png)-->

1. Clique no **[!UICONTROL Content]** bloco para modificar o título e o corpo da mensagem.

   Ao contrário das configurações baseadas em eventos em tempo real, você tem acesso direto a todas as informações de perfil para personalizar sua mensagem. See [Inserting a personalization field](../../designing/using/personalization.md#inserting-a-personalization-field).

   <!--![](assets/message-center_push_content_profile.png)-->

   Para obter mais informações sobre como editar um conteúdo de notificação por push. Consulte [Criação de uma notificação](../../channels/using/preparing-and-sending-a-push-notification.md)por push.

1. Salve as alterações e publique a mensagem. Consulte [Publicar uma mensagem](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message)transacional.
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

   Para obter mais informações sobre a integração do acionamento de um evento em um sistema externo, consulte Integração [](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)do site.

   >[!NOTE]
   >
   >Não há campos de token de registro, aplicativo e plataforma de push. Neste exemplo, a reconciliação é executada com o campo de email.

