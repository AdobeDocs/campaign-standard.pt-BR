---
title: Configuração de mensagens transacionais
seo-title: Configuração de mensagens transacionais
description: Configuração de mensagens transacionais
seo-description: Saiba como configurar as mensagens transacionais.
page-status-flag: nunca ativado
uuid: 4 caeadbe-f 4 a 7-43 ce -986 d-e 99 fa 9 ca 0 d 0 d
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuração-canais
discoiquuid: 3 f 968556-e 774-43 dc-a 0 b 8-7188 d 7665 fbc
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 20b4d5dfb297cac4cd69fe6f945b4399abd7f06a

---


# Configuring transactional messaging{#configuring-transactional-messaging}

Para enviar uma mensagem transacional com o Adobe Campaign, primeiro é necessário descrever a estrutura dos dados do evento.

Event configuration must be performed by an **administrator** by following the steps below:

A configuração pode variar dependendo do tipo de mensagem transacional que você deseja enviar. For more on this, refer to [Transactional event specific configurations](../../administration/using/configuring-transactional-messaging.md#transactional-event-specific-configurations)

Uma vez que o evento é publicado, a mensagem transacional correspondente é criada automaticamente. For more on transactional messaging, refer to [this page](../../channels/using/about-transactional-messaging.md).

## Creating an event {#creating-an-event}

Comece criando o evento correspondente às suas necessidades.

1. Click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner, then select **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]** &gt; **[!UICONTROL Event configuration]**.
1. Click the **[!UICONTROL Create]** button.
1. Give a **[!UICONTROL Label]** and an **[!UICONTROL ID]** to the event. **[!UICONTROL ID]** O campo é obrigatório e deve começar com o prefixo "EVT". If you do not use this prefix, it is automatically added once you click **[!UICONTROL Create]**.

   ![](assets/message-center_1.png)

1. Select the channel that will be used to send your transactional messages **[!UICONTROL Email]**, **[!UICONTROL Mobile (SMS)]** or **[!UICONTROL Mobile application]** (push notification).

   >[!NOTE]
   >
   >Apenas um canal pode ser usado para cada configuração de evento. Depois que o evento é criado, não é possível alterar o canal.

1. Select the targeting dimension corresponding to the desired event configuration and click **[!UICONTROL Create]**.

   As mensagens transacionais baseadas em eventos são dados de destino contidos no próprio evento, enquanto mensagens transacionais baseadas em perfil são dados de destino contidos no banco de dados do Adobe Campaign. For more on this, refer to [Transactional event specific configurations](../../administration/using/configuring-transactional-messaging.md#transactional-event-specific-configurations).

## Defining the event attributes {#defining-the-event-attributes}

In the **[!UICONTROL Fields]** section, define the attributes that will be integrated into the event content and will then be able to be used to personalize the transactional message.

The steps for adding and modifying fields are the same as for [custom resources](../../developing/using/configuring-the-resource-s-data-structure.md#adding-fields-to-a-resource).

![](assets/message-center_2.png)

>[!NOTE]
>
>If you want to create a multilingual transactional message, define an additional event attribute with the **[!UICONTROL AC_language]** ID. Isso se aplica somente às mensagens transacionais de eventos. Depois que o evento é publicado, as etapas para editar o conteúdo de uma mensagem transacional multilíngue são as mesmas para um email padrão multilíngue. See [Creating a multilingual email](../../channels/using/creating-a-multilingual-email.md).

## Defining data collections {#defining-data-collections}

Você pode adicionar ao conteúdo do evento uma coleção de elementos, cada elemento incluindo vários atributos.

Essa coleção pode ser usada em um email transacional para adicionar listagens de produto ao conteúdo da mensagem, por exemplo, uma lista de produtos - com o preço, número de referência, quantidade etc. para cada produto da lista.

1. In the **[!UICONTROL Collections]** section, click the **[!UICONTROL Create element]** button.

   ![](assets/message-center_collection_create.png)

1. Adicione um rótulo e uma ID para a sua coleção.
1. Adicione todos os campos que deseja exibir na mensagem transacional para cada produto da lista.

   Neste exemplo, adicionamos os seguintes campos:

   ![](assets/message-center_collection_fields.png)

Depois que o evento e a mensagem forem publicados, você poderá usar essa coleção na sua mensagem transacional.

Esta é a visualização da API para este exemplo:

![](assets/message-center_collection_api-preview.png)

**Tópicos relacionados:**

* [Visualizar e publicar o evento](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)
* [Uso de listagens de produto em uma mensagem transacional](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message)

## Enriching the transactional message content {#enriching-the-transactional-message-content}

Enriquecer o conteúdo da mensagem transacional com informações do banco de dados do Adobe Campaign permite que você personalize suas mensagens. Por exemplo, a partir do sobrenome ou ID de CRM de cada um dos seus destinatários, você pode recuperar dados como o endereço ou a data de nascimento ou qualquer outro campo personalizado adicionado na tabela Perfil para personalizar as informações enviadas para eles.

It is possible to enrich the transactional message content with information from extended **[!UICONTROL Profile]** or **[!UICONTROL Service]** resources.

Essas informações também podem ser armazenadas em novos recursos. In that case, the resource must be linked to the **[!UICONTROL Profile]** or **[!UICONTROL Service]** resources either directly, or via another table. For example, in the configuration below, it is possible to enrich the transactional message content with information from the **[!UICONTROL Product]** resource like the product category or ID, if the **[!UICONTROL Product]** resource is linked to the **[!UICONTROL Profile]** resource.

![](assets/message-center_usecaseschema.png)

For more on resource creation and publishing, refer to [this page](../../developing/using/key-steps-to-add-a-resource.md).

1. In the **[!UICONTROL Enrichment]** section, click the **[!UICONTROL Create element]** button.

   ![](assets/message-center_addenrichment.png)

1. Selecione o recurso com o qual você deseja vincular sua mensagem. In this case, choose the **[!UICONTROL Profile]** resource.

   ![](assets/message-center_new-enrichment.png)

1. Use the **[!UICONTROL Create element]** button to link a field from the selected resource to one of the fields you previously added to the event (see [Defining the event attributes](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)).

   ![](assets/message-center_enrichment-join.png)

1. In this example, we reconcile the **[!UICONTROL Last name]** and the **[!UICONTROL First name]** fields with the corresponding fields in the **[!UICONTROL Profile]** resource.

   ![](assets/message-center_enrichment-join-fields.png)

1. In the **[!UICONTROL Targeting enrichment]** section, select the enrichment that will be used as the message target during the delivery execution. In this example, select **[!UICONTROL Profile]**. A seleção de um enriquecimento de definição de metas é obrigatória para eventos baseados em perfil.

   ![](assets/message-center_marketing_targeting_enrichment.png)

Once the event and the message are published, the link with the **[!UICONTROL Profile]** resource will allow you to enrich the content of the transactional message.

**Tópicos relacionados:**

* [Visualizar e publicar o evento](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event).
* [Personalização de uma mensagem transacional](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message).

## Previewing and publishing the event {#previewing-and-publishing-the-event}

Antes de poder usar o evento, você deve visualizar e publicá-lo.

1. Click the **[!UICONTROL API preview]** button to see a simulation of the REST API that will be used by your website developer before it is published. Depois que o evento é publicado, esse botão também permite visualizar uma visualização da API na produção. See [Integrating the triggering of the event in a website](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

   ![](assets/message-center_api_preview.png)

   >[!NOTE]
   >
   >A REST API varia de acordo com o canal selecionado e a dimensão de definição de metas selecionada. For more details on the various configurations, refer to [Transactional event specific configurations](../../administration/using/configuring-transactional-messaging.md#transactional-event-specific-configurations).

1. Click **[!UICONTROL Publish]** to start publication.

   ![](assets/message-center_pub.png)

1. Você pode exibir os logs de publicação selecionando a guia correspondente.

   ![](assets/message-center_logs.png)

   Você também pode consultar as publicações anteriores selecionando a guia.

>[!NOTE]
>
>Each time you modify the event, you must click **[!UICONTROL Publish]** again to generate the updated REST API that will be used by your website developer.

Uma vez que o evento foi publicado, uma mensagem transacional vinculada ao novo evento é criada automaticamente. Para que esse evento dispare uma mensagem transacional, você deve modificar e publicar a mensagem que acabou de ser criada. See [Event transactional messages](../../channels/using/event-transactional-messages.md).

É possível acessar a mensagem transacional que foi criada diretamente do link na área do lado esquerdo.

![](assets/message-center_messagegeneration.png)

Também é necessário integrar esse evento de acionamento ao seu site. See [Integrating the triggering of the event in a website](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

### Unpublishing an event {#unpublishing-an-event}

The **[!UICONTROL Unpublish]** button lets you cancel the publication of the event, which deletes from the REST API the resource corresponding to the event that you previously created. Agora, mesmo que o evento seja acionado por meio do seu site, as mensagens correspondentes não são mais enviadas e não são armazenadas no banco de dados.

![](assets/message-center_unpublish.png)

>[!NOTE]
>
>Se você já tiver publicado a mensagem transacional correspondente, a publicação de mensagem transacional também será cancelada. See [Unpublishing a transactional message](../../channels/using/event-transactional-messages.md#unpublishing-a-transactional-message).

Click the **[!UICONTROL Publish]** button to generate a new REST API.

## Integrating the triggering of the event in a website {#integrating-the-triggering-of-the-event-in-a-website}

Após criar um evento, será necessário integrar o acionamento desse evento ao seu site.

In the example described in the [Transactional messaging operating principle](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle) section, you want a "Cart abandonment" event to be triggered whenever one of your clients leaves your website before purchasing the products in their cart. Para fazer isso, o desenvolvedor da Web do site deve usar a API REST do Adobe Campaign Standard.

See the [REST API Documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#transactional-messages-api) .

## Transactional event specific configurations {#transactional-event-specific-configurations}

A configuração de evento transacional pode variar dependendo do tipo de mensagem transacional que você deseja enviar (evento ou perfil) e do canal que será usado.

As seções a seguir detalham qual configuração específica deve ser definida de acordo com a mensagem transacional desejada. For more on the general steps to configure an event, refer to [Creating an event](../../administration/using/configuring-transactional-messaging.md#creating-an-event).

### Event-based transactional messages {#event-based-transactional-messages}

Para enviar uma mensagem transacional baseada em eventos, primeiro você deve criar e configurar um evento direcionado aos dados contidos no próprio evento.

1. When creating the event configuration, select the **[!UICONTROL Real-time event]** targeting dimension (see [Creating an event](../../administration/using/configuring-transactional-messaging.md#creating-an-event)).
1. Add fields to the event, in order to be able to personalize the transactional message (see [Defining the event attributes](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)).
1. Enrich the transactional message content if you want to use additional information from the Adobe Campaign database (see [Enriching the transactional message content](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)).

   >[!NOTE]
   >
   >As mensagens transacionais baseadas em eventos devem usar apenas os dados que estão no evento enviado para definir o destinatário e a personalização do conteúdo da mensagem. No entanto, você pode aprimorar o conteúdo da sua mensagem transacional usando informações do banco de dados do Adobe Campaign.

1. Preview and publish the event (see [Previewing and publishing the event](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)).

   Ao visualizar o evento, a REST API contém um atributo que especifica o endereço de email ou o telefone celular de acordo com o canal selecionado.

   Uma vez que o evento foi publicado, uma mensagem transacional vinculada ao novo evento é criada automaticamente. In order for the event to trigger sending a transactional message, you must modify and publish the message that was just created, see [Event transactional messages](../../channels/using/event-transactional-messages.md).

1. Integrate the event into your website (see [Integrating the triggering of the event in a website](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)).

### Profile-based transactional messages {#profile-based-transactional-messages}

Para enviar uma mensagem transacional baseada em perfil, é necessário primeiro criar e configurar os dados de definição de metas de eventos contidos no banco de dados do Adobe Campaign.

1. When creating the event configuration, select the **[!UICONTROL Profile event]** targeting dimension (see [Creating an event](../../administration/using/configuring-transactional-messaging.md#creating-an-event)).
1. Add fields to the event, in order to be able to personalize the transactional message (see [Defining the event attributes](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)). Você deve adicionar pelo menos um campo para criar um enriquecimento. You do not need to create other fields such as **First name** and **Last name** as you will be able to use personalization fields from the Adobe Campaign database.
1. Create an enrichment in order to link the event to the **[!UICONTROL Profile]** resource (see [Enriching the transactional message content](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)). Creating an enrichment is mandatory when using a **[!UICONTROL Profile]** targeting dimension.
1. Preview and publish the event (see [Previewing and publishing the event](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)).

   When previewing the event, the REST API does not contain an attribute specifying the email address or the mobile phone as it will be retrieved from the **[!UICONTROL Profile]** resource.

   Uma vez que o evento foi publicado, uma mensagem transacional vinculada ao novo evento é criada automaticamente. In order for the event to trigger sending a transactional message, you must modify and publish the message that was just created, see [Sending a profile transactional message](../../channels/using/profile-transactional-messages.md#sending-a-profile-transactional-message).

1. Integrate the event into your website (see [Integrating the triggering of the event in a website](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)).

### Event-based transactional push notifications {#event-based-transactional-push-notifications}

Para enviar notificações por push transacionais, você precisa configurar o Adobe Campaign de acordo. See [Push configuration](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html).

Para enviar uma notificação por push transacional anônima para todos os usuários que aceitaram receber notificações do aplicativo móvel, primeiro é necessário criar e configurar um evento direcionado aos dados contidos no próprio evento. As etapas correspondentes são apresentadas abaixo.

O evento deve conter os três elementos a seguir:

* A **registration token**, which is the user ID for one mobile application and one device. Pode não corresponder a nenhum perfil do banco de dados do Adobe Campaign.
* A **mobile application name** (one for all devices - Android and iOS). Essa é a ID do aplicativo móvel configurada no Adobe Campaign que será usada para receber notificações por push nos dispositivos dos usuários. For more on this, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)
* A **push platform** ("gcm" for Android or "apns" for iOS).

1. When creating the event configuration, select the **[!UICONTROL Mobile application]** channel and the **[!UICONTROL Real-time event]** targeting dimension (see [Creating an event](../../administration/using/configuring-transactional-messaging.md#creating-an-event)).
1. Add fields to the event, in order to be able to personalize the transactional message (see [Defining the event attributes](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)).
1. Enrich the transactional message content if you want to use additional information from Adobe Campaign database (see [Enriching the transactional message content](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)).

   >[!NOTE]
   >
   >As mensagens transacionais baseadas em eventos devem usar apenas os dados que estão no evento enviado para definir o destinatário e a personalização do conteúdo da mensagem. No entanto, você pode aprimorar o conteúdo da sua mensagem transacional usando informações do banco de dados do Adobe Campaign.

1. Preview and publish the event (see [Previewing and publishing the event](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)).

   Ao visualizar o evento, a REST API contém os atributos "registrationtoken", "application" e "pushplatform" que serão usados para direcionar a entrega.

   ![](assets/message-center_push_api.png)

   Uma vez que o evento foi publicado, uma notificação por push transacional vinculada ao novo evento é criada automaticamente. To modify and publish the message that was just created, see [Sending a transactional push notification targeting an event](/channels/using/transactional-push-notifications.html#sending-a-transactional-push-notification-targeting-an
----------event#sending-a-transactional-push-notification-targeting-an
----------event#sending-a-transactional-push-notification-targeting-an
----------event#sending-a-transactional-push-notification-targeting-an
----------event).

1. Integrate the event into your website (see [Integrating the triggering of the event in a website](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)).

### Profile-based transactional push notifications {#profile-based-transactional-push-notifications}

Para enviar uma notificação por push transacional para os perfis do Adobe Campaign que assinaram seu aplicativo móvel, primeiro você deve criar e configurar um evento direcionado ao banco de dados do Adobe Campaign.

1. When creating the event configuration, select the **[!UICONTROL Mobile application]** channel and the **[!UICONTROL Profile]** targeting dimension (see [Creating an event](../../administration/using/configuring-transactional-messaging.md#creating-an-event)).

   Por padrão, a notificação por push transacional será enviada para todos os aplicativos móveis aos quais os destinatários assinaram. Para enviar a notificação por push para um aplicativo móvel específico, selecione-a na lista. Os outros aplicativos móveis serão direcionados pela mensagem, mas serão excluídos do envio.

   ![](assets/message-center_push_appfilter.png)

1. Add fields to the event, if you want to personalize the transactional message (see [Defining the event attributes](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)).

   >[!NOTE]
   >
   >Você deve adicionar pelo menos um campo para criar um enriquecimento. You do not need to create other fields such as **First name** and **Last name** as you will be able to use personalization fields from the Adobe Campaign database.

1. Create an enrichment in order to link the event to the **[!UICONTROL Profile]** resource (see [Enriching the transactional message content](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)). Creating an enrichment is mandatory when using a **[!UICONTROL Profile]** targeting dimension.
1. Preview and publish the event (see [Previewing and publishing the event](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)).

   When previewing the event, the REST API does not contain an attribute specifying the registration token, the application name and the push platform as they will be retrieved from the **[!UICONTROL Profile]** resource.

   Uma vez que o evento foi publicado, uma notificação por push transacional vinculada ao novo evento é criada automaticamente. To modify and publish the message that was just created, see [Sending a transactional push notification targeting a profile](/channels/using/transactional-push-notifications.html#sending-a-transactional-push-notification-targeting-a
----------profile#sending-a-transactional-push-notification-targeting-a
----------profile#sending-a-transactional-push-notification-targeting-a
----------profile#sending-a-transactional-push-notification-targeting-a
----------profile).

1. Integrate the event into your website (see [Integrating the triggering of the event in a website](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)).

### Configuring an event to send a follow-up message {#configuring-an-event-to-send-a-follow-up-message}

Uma mensagem de acompanhamento é um modelo de entrega de marketing predefinido que pode ser usado em um fluxo de trabalho para enviar mensagens aos destinatários de uma mensagem transacional específica. For more on this, see [Follow-up messages](../../channels/using/follow-up-messages.md).

1. Use a mesma configuração de evento criada para enviar uma mensagem transacional de evento. See [Event-based transactional messages](../../administration/using/configuring-transactional-messaging.md#event-based-transactional-messages).
1. When configuring your event, check the **[!UICONTROL Create follow-up delivery template for this event]** box before publishing the event.

   ![](assets/message-center_follow-up-checkbox.png)

1. Preview and publish the event (see [Previewing and publishing the event](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)).

   Uma vez que o evento foi publicado, uma mensagem transacional e um modelo de entrega subsequente vinculados ao novo evento são criados automaticamente. For more on using follow-up messages, see [Sending a follow-up message](../../channels/using/follow-up-messages.md#sending-a-follow-up-message).

## Use case: configuring an event to send a transactional message {#use-case--configuring-an-event-to-send-a-transactional-message}

Neste exemplo, queremos configurar um evento para enviar mensagens de confirmação após cada compra em nosso site com os seguintes pré-requisitos:

As we want to identify our client via his CRM ID, first make sure that the **[!UICONTROL Profile]** resource has been extended with this new field.

In the same way, a custom resource corresponding to purchases must have been created and published, and must be linked to the **[!UICONTROL Profile]** resource. Dessa forma, você poderá recuperar informações desse recurso para aprimorar o conteúdo da mensagem.

For more on resource creation and publishing, refer to [this page](../../developing/using/key-steps-to-add-a-resource.md).

1. Create a new event using the **[!UICONTROL Email]** channel and the **[!UICONTROL Profile]** targeting dimension (see [Creating an event](../../administration/using/configuring-transactional-messaging.md#creating-an-event)).
1. Defina os atributos que estarão disponíveis para personalizar a mensagem transacional. In our case, add the "CRM ID" and the "Product identifier" fields (see [Defining the event attributes](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)).

   ![](assets/message-center_usecase1.png)

1. To enrich the message content with information regarding the client's previous purchases, create an enrichment targeting the **[!UICONTROL Purchase]** resource (see [Enriching the transactional message content](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)).

   ![](assets/message-center_usecase2.png)

1. Create a join condition between the "Product identifier" field that was previously added to the message, and the corresponding field from the **[!UICONTROL Purchase]** resource

   ![](assets/message-center_usecase3.png)

1. Preview and publish the event (see [Previewing and publishing the event](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)).
1. Integrate the event in your website (see [Integrating the triggering of the event in a website](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)).

