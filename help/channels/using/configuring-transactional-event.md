---
solution: Campaign Standard
product: campaign
title: Configuração de um evento transacional
description: Saiba como configurar eventos transacionais no Adobe Campaign.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '1677'
ht-degree: 7%

---


# Configuração de um evento transacional {#configuring-transactional-event}

Para enviar uma mensagem transacional com o Adobe Campaign, primeiro é necessário descrever a estrutura dos dados do evento criando e configurando um evento.

>[!IMPORTANT]
>
>Somente [Os administradores funcionais](../../administration/using/users-management.md#functional-administrators) <!--being part of the **[!UICONTROL All]** [organizational unit](../../administration/using/organizational-units.md) -->têm os direitos apropriados para criar e editar configurações de evento.

A configuração varia dependendo do [tipo de mensagem transacional](../../channels/using/getting-started-with-transactional-msg.md#transactional-message-types) que você deseja enviar e do canal que será usado. Para obter mais informações, consulte [Configurações específicas](#transactional-event-specific-configurations).

Quando a configuração for concluída, o evento deverá ser publicado. Consulte [Publicação de um evento transacional](../../channels/using/publishing-transactional-event.md).

## Criação de um evento {#creating-an-event}

Para começar, crie o evento correspondente às suas necessidades.

1. Clique no logotipo **[!UICONTROL Adobe Campaign]**, no canto superior esquerdo, em seguida selecione **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**.
1. Clique no botão **[!UICONTROL Create]**.
1. Insira um **[!UICONTROL Label]** e um **[!UICONTROL ID]** para o evento. O campo **[!UICONTROL ID]** é obrigatório e deve começar com o prefixo &quot;EVT&quot;. Se você não usar esse prefixo, ele será adicionado automaticamente quando você clicar em **[!UICONTROL Create]**.

   ![](assets/message-center_1.png)

   >[!IMPORTANT]
   >
   >A ID não deve exceder 64 caracteres, incluindo o prefixo EVT.

1. Selecione o canal que será usado para enviar suas mensagens transacionais **[!UICONTROL Email]**, **[!UICONTROL Mobile (SMS)]** ou **[!UICONTROL Push notification]**. Somente um canal pode ser usado para cada evento e não pode ser alterado posteriormente.

1. Selecione o targeting dimension correspondente à configuração de evento desejada e clique em **[!UICONTROL Create]**.

   As mensagens transacionais baseadas em eventos direcionam os dados contidos no próprio evento, enquanto as mensagens transacionais baseadas em perfil segmentam os dados contidos no banco de dados do Adobe Campaign. Para obter mais informações, consulte [Configurações específicas](#transactional-event-specific-configurations).

>[!NOTE]
>
>O número de eventos transacionais pode afetar sua plataforma. Para garantir o melhor desempenho, exclua os eventos não utilizados. Consulte [Excluindo um evento](../../channels/using/publishing-transactional-event.md#deleting-an-event).

## Definição dos atributos de evento {#defining-the-event-attributes}

Na seção **[!UICONTROL Fields]** , defina os atributos que serão integrados ao conteúdo do evento e poderão ser usados para personalizar a mensagem transacional.

As etapas para adicionar e modificar campos são as mesmas de [recursos personalizados](../../developing/using/configuring-the-resource-s-data-structure.md#adding-fields-to-a-resource).

![](assets/message-center_2.png)

>[!NOTE]
>
>Se quiser criar uma mensagem transacional multilíngue, defina um atributo de evento adicional com a ID **[!UICONTROL AC_language]**. Isso se aplica somente às mensagens transacionais de evento. Depois que o evento é publicado, as etapas para editar o conteúdo de uma mensagem transacional multilíngue são as mesmas de um email padrão multilíngue. Consulte [Criação de um email multilíngue](../../channels/using/creating-a-multilingual-email.md).

## Definição de coleções de dados {#defining-data-collections}

Você pode adicionar ao conteúdo do evento uma coleção de elementos, cada elemento incluindo vários atributos.

Essa coleção pode ser usada em um email transacional para adicionar [listas de produtos](../../designing/using/using-product-listings.md) ao conteúdo da mensagem, por exemplo, uma lista de produtos - com o preço, o número de referência, a quantidade etc. para cada produto da lista.

1. Na seção **[!UICONTROL Collections]**, clique no botão **[!UICONTROL Create element]**.

   ![](assets/message-center_collection_create.png)

1. Adicione um rótulo e uma ID para sua coleção.
1. Adicione todos os campos que deseja exibir na mensagem transacional para cada produto da lista.

   Neste exemplo, adicionamos os seguintes campos:

   ![](assets/message-center_collection_fields.png)

1. A guia **[!UICONTROL Enrichment]** permite enriquecer cada item da coleção. Isso permitirá personalizar os elementos da lista de produtos correspondente com informações do banco de dados do Adobe Campaign ou de outros recursos que você criou.

>[!NOTE]
>
>As etapas para enriquecer os elementos de uma coleção são as mesmas descritas na seção [Enriquecimento do evento](#enriching-the-transactional-message-content) . Observe que enriquecer o evento não permitirá enriquecer uma coleção: é necessário adicionar um enriquecimento à própria coleção na seção **[!UICONTROL Collections]**.

Depois que o evento e a mensagem forem publicados, você poderá usar essa coleção na mensagem transacional.

Aqui está a pré-visualização da API para este exemplo:

![](assets/message-center_collection_api-preview.png)

**Tópicos relacionados:**

* [Pré-visualização e publicação do evento](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)
* [Uso de listas de produtos em uma mensagem transacional](../../designing/using/using-product-listings.md)
* [Publicação de mensagem transacional](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)

## Enriquecimento do evento {#enriching-the-transactional-message-content}

Você pode enriquecer o conteúdo da mensagem transacional com informações do banco de dados do Adobe Campaign para personalizar suas mensagens. A partir do sobrenome ou da ID do CRM de cada um dos recipients, por exemplo, é possível recuperar dados, como seu endereço ou data de nascimento ou qualquer outro campo personalizado adicionado na tabela Perfil, para personalizar as informações enviadas a eles.

É possível enriquecer o conteúdo da mensagem transacional com informações de **[!UICONTROL Profile and services Ext API]** estendidas. Para obter mais informações, consulte [Extensão da API: Publicar a extensão](../../developing/using/step-2--publish-the-extension.md)

Essas informações também podem ser armazenadas em novos recursos. Nesse caso, o recurso deve ser vinculado aos recursos **[!UICONTROL Profile]** ou **[!UICONTROL Service]** diretamente ou por outra tabela. Por exemplo, na configuração abaixo, é possível enriquecer o conteúdo da mensagem transacional com informações do recurso **[!UICONTROL Product]**, como a categoria do produto ou a ID, se o recurso **[!UICONTROL Product]** estiver vinculado ao recurso **[!UICONTROL Profile]**.

![](assets/message-center_usecaseschema.png)

Para obter mais informações sobre criação e publicação de recursos, consulte [esta seção](../../developing/using/key-steps-to-add-a-resource.md).

1. Na seção **[!UICONTROL Enrichment]**, clique no botão **[!UICONTROL Create element]**.

   ![](assets/message-center_addenrichment.png)

1. Selecione o recurso com o qual deseja vincular a mensagem. Nesse caso, escolha o recurso **[!UICONTROL Profile]**.

   ![](assets/message-center_new-enrichment.png)

1. Use o botão **[!UICONTROL Create element]** para vincular um campo do recurso selecionado a um dos campos que você adicionou anteriormente ao evento (consulte [Definição dos atributos de evento](#defining-the-event-attributes)).

   ![](assets/message-center_enrichment-join.png)

1. Neste exemplo, reconciliamos os campos **[!UICONTROL Last name]** e **[!UICONTROL First name]** com os campos correspondentes no recurso **[!UICONTROL Profile]**.

   ![](assets/message-center_enrichment-join-fields.png)

   Você também pode enriquecer o conteúdo da mensagem transacional usando o recurso **[!UICONTROL Service]** . Para obter mais informações sobre serviços, consulte [esta seção](../../audiences/using/creating-a-service.md).

1. Se estiver criando ou editando um [evento baseado em perfil](#profile-based-transactional-messages), na seção **[!UICONTROL Targeting enrichment]**, selecione o enriquecimento que será usado como o público alvo da mensagem durante a execução do delivery.

   ![](assets/message-center_marketing_targeting_enrichment.png)

   >[!NOTE]
   >
   >Criar um enriquecimento e selecionar um enriquecimento de direcionamento com base no recurso **[!UICONTROL Profile]** são obrigatórios para eventos com base em perfil.

Depois que o evento e a mensagem forem publicados, esse link permitirá enriquecer o conteúdo da mensagem transacional.

**Tópicos relacionados:**

* [Pré-visualização e publicação do evento](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)
* [Personalização de uma mensagem transacional](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message)
* [Publicação de mensagem transacional](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)

## Pesquisar eventos transacionais {#searching-transactional-events}

Para acessar e pesquisar os eventos transacionais já criados, siga as etapas abaixo.

1. Clique no logotipo **[!UICONTROL Adobe Campaign]**, no canto superior esquerdo, em seguida selecione **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**.
1. Clique no botão **[!UICONTROL Show search]**.

   ![](assets/message-center_search-events.png)

1. Você pode filtrar no **[!UICONTROL Publication status]**. Isso permite exibir somente os eventos publicados, por exemplo.
1. Você também pode filtrar os eventos usando o **[!UICONTROL Last event received]**. Por exemplo, se inserir 10, somente as configurações de evento com o último evento recebido há 10 dias ou mais serão exibidas. Isso permite exibir quais eventos ficaram inativos por um determinado período.

   ![](assets/message-center_last-event-received.png)

   >[!NOTE]
   >
   >O valor padrão é 0. Todos os eventos são exibidos.

## Configurações específicas {#transactional-event-specific-configurations}

A configuração de evento transacional pode variar dependendo do [tipo de mensagem transacional](../../channels/using/getting-started-with-transactional-msg.md#transactional-message-types) que você deseja enviar (evento ou perfil) e no canal que será usado.

As seções a seguir detalham qual configuração específica deve ser definida de acordo com a mensagem transacional desejada. Para obter mais informações sobre as etapas gerais para configurar um evento, consulte [Criação de um evento](#creating-an-event).

### Mensagens transacionais baseadas em evento {#event-based-transactional-messages}

Você pode enviar mensagens transacionais de eventos direcionadas a um evento. Esse tipo de mensagem transacional não contém informações de perfil: o público-alvo do delivery é definido pelos dados contidos no próprio evento.

Para enviar uma mensagem transacional baseada em eventos, primeiro é necessário criar e configurar um evento direcionado aos **dados contidos no próprio evento**.

1. Ao criar a configuração do evento, selecione o targeting dimension **[!UICONTROL Real-time event]** (consulte [Criação de um evento](#creating-an-event)).
1. Adicione campos ao evento, para personalizar a mensagem transacional (consulte [Definição dos atributos do evento](#defining-the-event-attributes)).
1. As mensagens transacionais baseadas em evento só devem usar os dados contidos no evento enviado para definir o recipient e a personalização do conteúdo da mensagem.

   No entanto, se desejar usar informações adicionais do banco de dados do Adobe Campaign, você poderá enriquecer o conteúdo da mensagem transacional (consulte [Enriquecimento do conteúdo da mensagem transacional](#enriching-the-transactional-message-content)).

1. Visualize e publique o evento (consulte [Pré-visualizar e publicar o evento](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)).

   Ao visualizar o evento, a REST API contém um atributo especificando o endereço de email, celular ou atributos específicos da notificação por push, de acordo com o canal selecionado.

   Depois que o evento for publicado, uma mensagem transacional vinculada ao novo evento será criada automaticamente. Para que o evento acione o envio de uma mensagem transacional, é necessário [modificar](../../channels/using/editing-transactional-message.md) e [publicar](../../channels/using/publishing-transactional-message.md) a mensagem que acabou de ser criada.

1. Integre o evento em seu site (consulte [Integrar o evento que aciona](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)).

### Mensagens transacionais baseadas em perfil {#profile-based-transactional-messages}

Você pode enviar mensagens transacionais com base nos perfis do cliente, o que permite aplicar regras de tipologia de marketing, incluir o link de cancelamento de inscrição, adicionar a mensagem ao relatório de delivery global e aproveitá-la na jornada do cliente.

Para enviar uma mensagem transacional baseada em perfil, primeiro é necessário criar e configurar um direcionamento de evento **dados do banco de dados do Adobe Campaign**.

1. Ao criar a configuração do evento, selecione o targeting dimension **[!UICONTROL Profile event]** (consulte [Criação de um evento](#creating-an-event)).
1. Adicione campos ao evento, para personalizar a mensagem transacional (consulte [Definição dos atributos do evento](#defining-the-event-attributes)). Você deve adicionar pelo menos um campo para criar um enriquecimento. Você não precisa criar outros campos, como **First name** e **Last name**, pois poderá usar campos de personalização do banco de dados do Adobe Campaign.
1. Crie um enriquecimento para vincular o evento ao recurso **[!UICONTROL Profile]** (consulte [Enriquecendo o evento](#enriching-the-transactional-message-content)) e selecione esse enriquecimento como o **[!UICONTROL Targeting enrichment]**.

   >[!IMPORTANT]
   >
   >Esta etapa é obrigatória para eventos baseados em perfil.

1. Visualize e publique o evento (consulte [Pré-visualizar e publicar o evento](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)).

   Ao visualizar o evento, a REST API não contém um atributo especificando o endereço de email, celular ou atributos específicos da notificação por push, pois será recuperada do recurso **[!UICONTROL Profile]**.

   Depois que o evento for publicado, uma mensagem transacional vinculada ao novo evento será criada automaticamente. Para que o evento acione o envio de uma mensagem transacional, é necessário [modificar](../../channels/using/editing-transactional-message.md) e [publicar](../../channels/using/publishing-transactional-message.md) a mensagem que acabou de ser criada.

1. Integre o evento em seu site (consulte [Integrar o evento que aciona](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)).

<!--### Transactional SMS messages {#transactional-sms}

The steps to configure an  event to send an SMS transactional message are the same as for the email channel. The only differences are as follows:

* When creating the corresponding event, you need to select the **[!UICONTROL Mobile (SMS)]** channel.

* When previewing the event corresponding to an event-based transactional SMS, the REST API contains an attribute specifying the mobile phone instead of the email address.

* The specificities to edit the content of an SMS transactional message are the same as for a [standard SMS](../../channels/using/about-sms-and-push-content-design.md).-->

### Notificações por push transacionais {#transactional-push-notifications}

Você pode enviar dois tipos de notificações transacionais por push:
* Uma notificação por push transacional anônima para todos os usuários que optaram por receber notificações do aplicativo móvel. Consulte [Configuração de notificações transacionais por push baseadas em eventos](../../channels/using/transactional-push-notifications.md#event-based-transactional-push-notifications).
* Uma notificação por push transacional para os perfis do Adobe Campaign que assinaram seu aplicativo móvel. Consulte [Configuração de notificações transacionais por push baseadas em perfil](../../channels/using/transactional-push-notifications.md#profile-based-transactional-push-notifications).

>[!IMPORTANT]
>
>Para enviar notificações transacionais por push, é necessário configurar o Adobe Campaign adequadamente. Consulte [Configuração de um aplicativo móvel](../../administration/using/configuring-a-mobile-application.md).

### Mensagens de acompanhamento {#follow-up-messages}

Você pode enviar uma mensagem de acompanhamento aos clientes que receberam uma mensagem transacional específica.

As etapas para configurar um evento que permita enviar uma mensagem de acompanhamento são detalhadas em [this section](../../channels/using/follow-up-messages.md#configuring-an-event-to-send-a-follow-up-message).
