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
source-git-commit: 8800562922e68d33cca93cd838c294198b630684

---


# Configuração de mensagens transacionais{#configuring-transactional-messaging}

Para enviar uma mensagem transacional com o Adobe Campaign, primeiro é necessário descrever a estrutura dos dados do evento.

A configuração do evento deve ser executada por um **administrador** seguindo as etapas abaixo:

A configuração pode variar dependendo do tipo de mensagem transacional que você deseja enviar. Para mais informações, consulte Configurações específicas do evento [transacional](../../administration/using/configuring-transactional-messaging.md#transactional-event-specific-configurations)

Uma vez que o evento é publicado, a mensagem transacional correspondente é criada automaticamente. Para obter mais informações transacionais, consulte [esta página](../../channels/using/about-transactional-messaging.md).

## Criação de um evento {#creating-an-event}

Comece criando o evento correspondente às suas necessidades.

1. Clique no **[!UICONTROL Adobe Campaign]** logotipo, no canto superior esquerdo e selecione **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]** &gt; **[!UICONTROL Event configuration]**.
1. Clique no **[!UICONTROL Create]** botão.
1. Dê um **[!UICONTROL Label]** e um **[!UICONTROL ID]** evento. **[!UICONTROL ID]** O campo é obrigatório e deve começar com o prefixo "EVT". Se você não usar esse prefixo, ele será automaticamente adicionado depois que você **[!UICONTROL Create]** clicar em.

   ![](assets/message-center_1.png)

   >[!CAUTION]
   >
   >A ID não deve exceder 64 caracteres, incluindo o prefixo de EVT.

1. Selecione o canal que será usado para enviar suas mensagens transacionais **[!UICONTROL Email]** ou **[!UICONTROL Mobile (SMS)]****[!UICONTROL Mobile application]** (notificação por push).

   >[!NOTE]
   >
   >Apenas um canal pode ser usado para cada configuração de evento. Depois que o evento é criado, não é possível alterar o canal.

1. Selecione a dimensão de definição de metas correspondente à configuração do evento desejado e clique **[!UICONTROL Create]** em.

   As mensagens transacionais baseadas em eventos são dados de destino contidos no próprio evento, enquanto mensagens transacionais baseadas em perfil são dados de destino contidos no banco de dados do Adobe Campaign. Para saber mais sobre isso, consulte Configurações específicas do evento [transacional](../../administration/using/configuring-transactional-messaging.md#transactional-event-specific-configurations).

## Definição dos atributos do evento {#defining-the-event-attributes}

Na **[!UICONTROL Fields]** seção, defina os atributos que serão integrados ao conteúdo do evento e poderão ser usados para personalizar a mensagem transacional.

As etapas para adicionar e modificar campos são as mesmas para os recursos [personalizados](../../developing/using/configuring-the-resource-s-data-structure.md#adding-fields-to-a-resource).

![](assets/message-center_2.png)

>[!NOTE]
>
>Se você quiser criar uma mensagem transacional multilíngue, defina um atributo de evento adicional com a **[!UICONTROL AC_language]** ID. Isso se aplica somente às mensagens transacionais de eventos. Depois que o evento é publicado, as etapas para editar o conteúdo de uma mensagem transacional multilíngue são as mesmas para um email padrão multilíngue. Consulte [Criar um email multilíngue](../../channels/using/creating-a-multilingual-email.md).

## Definição de coleções de dados {#defining-data-collections}

Você pode adicionar ao conteúdo do evento uma coleção de elementos, cada elemento incluindo vários atributos.

Essa coleção pode ser usada em um email transacional para adicionar listagens de produto ao conteúdo da mensagem, por exemplo, uma lista de produtos - com o preço, número de referência, quantidade etc. para cada produto da lista.

1. Na **[!UICONTROL Collections]** seção, clique no **[!UICONTROL Create element]** botão.

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

## Enriquecimento do conteúdo transacional da mensagem {#enriching-the-transactional-message-content}

Enriquecer o conteúdo da mensagem transacional com informações do banco de dados do Adobe Campaign permite que você personalize suas mensagens. Por exemplo, a partir do sobrenome ou ID de CRM de cada um dos seus destinatários, você pode recuperar dados como o endereço ou a data de nascimento ou qualquer outro campo personalizado adicionado na tabela Perfil para personalizar as informações enviadas para eles.

É possível aprimorar o conteúdo da mensagem transacional com informações de recursos estendidos **[!UICONTROL Profile]** ou **[!UICONTROL Service]** recursos.

Essas informações também podem ser armazenadas em novos recursos. Nesse caso, o recurso deve estar vinculado aos recursos **[!UICONTROL Profile]** ou **[!UICONTROL Service]** aos recursos diretamente, ou por outra tabela. Por exemplo, na configuração abaixo, é possível aprimorar o conteúdo da mensagem transacional com informações do **[!UICONTROL Product]** recurso como a categoria ou ID do produto, se **[!UICONTROL Product]** o recurso estiver vinculado ao **[!UICONTROL Profile]** recurso.

![](assets/message-center_usecaseschema.png)

Para obter mais informações sobre criação e publicação de recursos, consulte [esta página](../../developing/using/key-steps-to-add-a-resource.md).

1. Na **[!UICONTROL Enrichment]** seção, clique no **[!UICONTROL Create element]** botão.

   ![](assets/message-center_addenrichment.png)

1. Selecione o recurso com o qual você deseja vincular sua mensagem. Nesse caso, escolha o **[!UICONTROL Profile]** recurso.

   ![](assets/message-center_new-enrichment.png)

1. Use o **[!UICONTROL Create element]** botão para vincular um campo do recurso selecionado a um dos campos adicionados anteriormente ao evento (consulte [Definição dos atributos do evento](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)).

   ![](assets/message-center_enrichment-join.png)

1. Neste exemplo, nós reconciliamos os **[!UICONTROL Last name]****[!UICONTROL First name]** campos com os campos correspondentes no **[!UICONTROL Profile]** recurso.

   ![](assets/message-center_enrichment-join-fields.png)

1. Na **[!UICONTROL Targeting enrichment]** seção, selecione o enriquecimento que será usado como meta de mensagem durante a execução da entrega. Neste exemplo, selecione **[!UICONTROL Profile]**. A seleção de um enriquecimento de definição de metas é obrigatória para eventos baseados em perfil.

   ![](assets/message-center_marketing_targeting_enrichment.png)

Depois que o evento e a mensagem forem publicados, o link com **[!UICONTROL Profile]** o recurso permitirá aprimorar o conteúdo da mensagem transacional.

**Tópicos relacionados:**

* [Visualizar e publicar o evento](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event).
* [Personalização de uma mensagem transacional](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message).

## Visualizar e publicar o evento {#previewing-and-publishing-the-event}

Antes de poder usar o evento, você deve visualizar e publicá-lo.

1. Clique no **[!UICONTROL API preview]** botão para ver uma simulação da REST API que será usada pelo desenvolvedor de seu site antes de ser publicada. Depois que o evento é publicado, esse botão também permite visualizar uma visualização da API na produção. Consulte [Integração do acionamento do evento em um site](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

   ![](assets/message-center_api_preview.png)

   >[!NOTE]
   >
   >A REST API varia de acordo com o canal selecionado e a dimensão de definição de metas selecionada. Para obter mais detalhes sobre as várias configurações, consulte Configurações específicas do evento [transacional](../../administration/using/configuring-transactional-messaging.md#transactional-event-specific-configurations).

1. Clique **[!UICONTROL Publish]** em para iniciar a publicação.

   ![](assets/message-center_pub.png)

1. Você pode exibir os logs de publicação selecionando a guia correspondente.

   ![](assets/message-center_logs.png)

   Você também pode consultar as publicações anteriores selecionando a guia.

>[!NOTE]
>
>Sempre que você modificar o evento, clique **[!UICONTROL Publish]** em novamente para gerar a REST API atualizada que será usada pelo desenvolvedor do site.

Uma vez que o evento foi publicado, uma mensagem transacional vinculada ao novo evento é criada automaticamente. Para que esse evento dispare uma mensagem transacional, você deve modificar e publicar a mensagem que acabou de ser criada. Consulte [Mensagens transacionais de evento](../../channels/using/event-transactional-messages.md).

É possível acessar a mensagem transacional que foi criada diretamente do link na área do lado esquerdo.

![](assets/message-center_messagegeneration.png)

Também é necessário integrar esse evento de acionamento ao seu site. Consulte [Integração do acionamento do evento em um site](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

### Cancelar publicação de um evento {#unpublishing-an-event}

O **[!UICONTROL Unpublish]** botão permite cancelar a publicação do evento, que exclui da REST API o recurso correspondente ao evento criado anteriormente. Agora, mesmo que o evento seja acionado por meio do seu site, as mensagens correspondentes não são mais enviadas e não são armazenadas no banco de dados.

![](assets/message-center_unpublish.png)

>[!NOTE]
>
>Se você já tiver publicado a mensagem transacional correspondente, a publicação de mensagem transacional também será cancelada. Consulte [Desfazer publicação de uma mensagem transacional](../../channels/using/event-transactional-messages.md#unpublishing-a-transactional-message).

Clique no **[!UICONTROL Publish]** botão para gerar uma nova REST API.

## Integração do acionamento do evento em um site {#integrating-the-triggering-of-the-event-in-a-website}

Após criar um evento, será necessário integrar o acionamento desse evento ao seu site.

No exemplo descrito na seção [do princípio](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle) de operação de mensagem transacional, você deseja que um evento "Abandono do carrinho" seja acionado sempre que um de seus clientes sair do site antes de comprar os produtos no carrinho. Para fazer isso, o desenvolvedor da Web do site deve usar a API REST do Adobe Campaign Standard.

Consulte a Documentação [REST da API](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#transactional-messages-api) .

## Configurações específicas do evento transacional {#transactional-event-specific-configurations}

A configuração de evento transacional pode variar dependendo do tipo de mensagem transacional que você deseja enviar (evento ou perfil) e do canal que será usado.

As seções a seguir detalham qual configuração específica deve ser definida de acordo com a mensagem transacional desejada. Para obter mais informações sobre as etapas gerais para configurar um evento, consulte [Criar um evento](../../administration/using/configuring-transactional-messaging.md#creating-an-event).

### Mensagens transacionais baseadas em eventos {#event-based-transactional-messages}

Para enviar uma mensagem transacional baseada em eventos, primeiro você deve criar e configurar um evento direcionado aos dados contidos no próprio evento.
Para obter mais informações, consulte [Participação com mensagens transacionais](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Managedatatofuelengagingexperiences).

1. Ao criar a configuração do evento, selecione a dimensão **[!UICONTROL Real-time event]** de definição de metas (consulte [Criar um evento](../../administration/using/configuring-transactional-messaging.md#creating-an-event)).
1. Adicione campos ao evento para poder personalizar a mensagem transacional (consulte [Definição dos atributos do evento](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)).
1. Enriqueça o conteúdo de mensagem transacional se desejar usar informações adicionais do banco de dados do Adobe Campaign (consulte [Enriquecer o conteúdo da mensagem transacional](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)).

   >[!NOTE]
   >
   >As mensagens transacionais baseadas em eventos devem usar apenas os dados que estão no evento enviado para definir o destinatário e a personalização do conteúdo da mensagem. No entanto, você pode aprimorar o conteúdo da sua mensagem transacional usando informações do banco de dados do Adobe Campaign.

1. Visualize e publique o evento (consulte [Visualizar e publicar o evento](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)).

   Ao visualizar o evento, a REST API contém um atributo que especifica o endereço de email ou o telefone celular de acordo com o canal selecionado.

   Uma vez que o evento foi publicado, uma mensagem transacional vinculada ao novo evento é criada automaticamente. Para que o evento dispare uma mensagem transacional, você deve modificar e publicar a mensagem recém-criada, consulte [Mensagens transacionais de evento](../../channels/using/event-transactional-messages.md).

1. Integre o evento ao seu site (consulte [Integração do acionamento do evento em um site](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)).

### Mensagens transacionais baseadas em perfil {#profile-based-transactional-messages}

Para enviar uma mensagem transacional baseada em perfil, é necessário primeiro criar e configurar os dados de definição de metas de eventos contidos no banco de dados do Adobe Campaign.

1. Ao criar a configuração do evento, selecione a dimensão **[!UICONTROL Profile event]** de definição de metas (consulte [Criar um evento](../../administration/using/configuring-transactional-messaging.md#creating-an-event)).
1. Adicione campos ao evento para poder personalizar a mensagem transacional (consulte [Definição dos atributos do evento](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)). Você deve adicionar pelo menos um campo para criar um enriquecimento. Não é necessário criar outros campos como **nome** e **sobrenome** , pois você poderá usar campos de personalização do banco de dados do Adobe Campaign.
1. Crie um enriquecimento para vincular o evento ao **[!UICONTROL Profile]** recurso (consulte [Enriquecer o conteúdo da mensagem transacional](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)). A criação de um enriquecimento é obrigatória ao usar uma dimensão **[!UICONTROL Profile]** de definição de metas.
1. Visualize e publique o evento (consulte [Visualizar e publicar o evento](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)).

   Ao visualizar o evento, a REST API não contém um atributo que especifique o endereço de email ou o telefone celular conforme ele será recuperado do **[!UICONTROL Profile]** recurso.

   Uma vez que o evento foi publicado, uma mensagem transacional vinculada ao novo evento é criada automaticamente. Para que o evento dispare uma mensagem transacional, você deve modificar e publicar a mensagem recém-criada, consulte [Enviar uma mensagem transacional de perfil](../../channels/using/profile-transactional-messages.md#sending-a-profile-transactional-message).

1. Integre o evento ao seu site (consulte [Integração do acionamento do evento em um site](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)).

### Notificações por push transacionais baseadas em eventos {#event-based-transactional-push-notifications}

Para enviar notificações por push transacionais, você precisa configurar o Adobe Campaign de acordo. Consulte [Configuração de push](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html).

Para enviar uma notificação por push transacional anônima para todos os usuários que aceitaram receber notificações do aplicativo móvel, primeiro é necessário criar e configurar um evento direcionado aos dados contidos no próprio evento. As etapas correspondentes são apresentadas abaixo.

O evento deve conter os três elementos a seguir:

* Um **token de registro**, que é a ID de usuário de um aplicativo móvel e um dispositivo. Pode não corresponder a nenhum perfil do banco de dados do Adobe Campaign.
* Um **nome de aplicativo móvel** (um para todos os dispositivos - Android e iOS). Essa é a ID do aplicativo móvel configurada no Adobe Campaign que será usada para receber notificações por push nos dispositivos dos usuários. Para saber mais sobre isso, consulte [esta página](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)
* Uma **plataforma de push** («gcm» para Android ou «aplicativos» para iOS).

1. Ao criar a configuração do evento, selecione o **[!UICONTROL Mobile application]** canal e a dimensão **[!UICONTROL Real-time event]** de definição de metas (consulte [Criar um evento](../../administration/using/configuring-transactional-messaging.md#creating-an-event)).
1. Adicione campos ao evento para poder personalizar a mensagem transacional (consulte [Definição dos atributos do evento](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)).
1. Enriqueça o conteúdo de mensagem transacional se desejar usar informações adicionais do banco de dados do Adobe Campaign (consulte [Enriquecer o conteúdo da mensagem transacional](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)).

   >[!NOTE]
   >
   >As mensagens transacionais baseadas em eventos devem usar apenas os dados que estão no evento enviado para definir o destinatário e a personalização do conteúdo da mensagem. No entanto, você pode aprimorar o conteúdo da sua mensagem transacional usando informações do banco de dados do Adobe Campaign.

1. Visualize e publique o evento (consulte [Visualizar e publicar o evento](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)).

   Ao visualizar o evento, a REST API contém os atributos "registrationtoken", "application" e "pushplatform" que serão usados para direcionar a entrega.

   ![](assets/message-center_push_api.png)

   Uma vez que o evento foi publicado, uma notificação por push transacional vinculada ao novo evento é criada automaticamente. Para modificar e publicar a mensagem recém-criada, consulte [Envio de uma notificação por push transacional e de evento](../../channels/using/transactional-push-notifications.md#transactional-push-notifications-targeting-an-event).

1. Integre o evento ao seu site (consulte [Integração do acionamento do evento em um site](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)).

### Notificações por push transacionais baseadas em perfil {#profile-based-transactional-push-notifications}

Para enviar uma notificação por push transacional para os perfis do Adobe Campaign que assinaram seu aplicativo móvel, primeiro você deve criar e configurar um evento direcionado ao banco de dados do Adobe Campaign.

1. Ao criar a configuração do evento, selecione o **[!UICONTROL Mobile application]** canal e a dimensão **[!UICONTROL Profile]** de definição de metas (consulte [Criar um evento](../../administration/using/configuring-transactional-messaging.md#creating-an-event)).

   Por padrão, a notificação por push transacional será enviada para todos os aplicativos móveis aos quais os destinatários assinaram. Para enviar a notificação por push para um aplicativo móvel específico, selecione-a na lista. Os outros aplicativos móveis serão direcionados pela mensagem, mas serão excluídos do envio.

   ![](assets/message-center_push_appfilter.png)

1. Adicione campos ao evento, se quiser personalizar a mensagem transacional (consulte [Definição dos atributos do evento](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)).

   >[!NOTE]
   >
   >Você deve adicionar pelo menos um campo para criar um enriquecimento. Não é necessário criar outros campos como **nome** e **sobrenome** , pois você poderá usar campos de personalização do banco de dados do Adobe Campaign.

1. Crie um enriquecimento para vincular o evento ao **[!UICONTROL Profile]** recurso (consulte [Enriquecer o conteúdo da mensagem transacional](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)). A criação de um enriquecimento é obrigatória ao usar uma dimensão **[!UICONTROL Profile]** de definição de metas.
1. Visualize e publique o evento (consulte [Visualizar e publicar o evento](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)).

   Ao visualizar o evento, a REST API não contém um atributo que especifique o token de registro, o nome do aplicativo e a plataforma de push que serão recuperados do **[!UICONTROL Profile]** recurso.

   Uma vez que o evento foi publicado, uma notificação por push transacional vinculada ao novo evento é criada automaticamente. Para modificar e publicar a mensagem recém-criada, consulte [Enviar uma notificação por push transacional para um perfil](../../channels/using/transactional-push-notifications.md#transactional-push-notifications-targeting-a-profile).

1. Integre o evento ao seu site (consulte [Integração do acionamento do evento em um site](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)).

### Configurar um evento para enviar uma mensagem de acompanhamento {#configuring-an-event-to-send-a-follow-up-message}

Uma mensagem de acompanhamento é um modelo de entrega de marketing predefinido que pode ser usado em um fluxo de trabalho para enviar mensagens aos destinatários de uma mensagem transacional específica. Para saber mais sobre isso, consulte [Mensagens de acompanhamento](../../channels/using/follow-up-messages.md).

1. Use a mesma configuração de evento criada para enviar uma mensagem transacional de evento. Consulte [Mensagens transacionais baseadas em eventos](../../administration/using/configuring-transactional-messaging.md#event-based-transactional-messages).
1. Ao configurar seu evento, marque a **[!UICONTROL Create follow-up delivery template for this event]** caixa antes de publicar o evento.

   ![](assets/message-center_follow-up-checkbox.png)

1. Visualize e publique o evento (consulte [Visualizar e publicar o evento](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)).

   Uma vez que o evento foi publicado, uma mensagem transacional e um modelo de entrega subsequente vinculados ao novo evento são criados automaticamente. Para obter mais informações sobre como usar mensagens de acompanhamento, consulte [Enviar uma mensagem de acompanhamento](../../channels/using/follow-up-messages.md#sending-a-follow-up-message).

## Caso de uso: configurar um evento para enviar uma mensagem transacional {#use-case--configuring-an-event-to-send-a-transactional-message}

Neste exemplo, queremos configurar um evento para enviar mensagens de confirmação após cada compra em nosso site com os seguintes pré-requisitos:

Como queremos identificar o cliente por meio da ID do CRM, primeiro certifique-se de que **[!UICONTROL Profile]** o recurso foi estendido com este novo campo.

Da mesma forma, um recurso personalizado correspondente às compras deve ter sido criado e publicado, e deve estar vinculado ao **[!UICONTROL Profile]** recurso. Dessa forma, você poderá recuperar informações desse recurso para aprimorar o conteúdo da mensagem.

Para obter mais informações sobre criação e publicação de recursos, consulte [esta página](../../developing/using/key-steps-to-add-a-resource.md).

1. Crie um novo evento usando **[!UICONTROL Email]** o canal e a dimensão **[!UICONTROL Profile]** de definição de metas (consulte [Criar um evento](../../administration/using/configuring-transactional-messaging.md#creating-an-event)).
1. Defina os atributos que estarão disponíveis para personalizar a mensagem transacional. Em nosso caso, adicione a "ID do CRM" e os campos "Identificador de produto" (consulte [Definição dos atributos do evento](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)).

   ![](assets/message-center_usecase1.png)

1. Para aprimorar o conteúdo da mensagem com informações relacionadas às compras anteriores do cliente, crie um enriquecimento para o **[!UICONTROL Purchase]** recurso (consulte [Enriquecer o conteúdo da mensagem transacional](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)).

   ![](assets/message-center_usecase2.png)

1. Criar uma condição de junção entre o campo "Identificador de produto" adicionado anteriormente à mensagem e o campo correspondente do **[!UICONTROL Purchase]** recurso

   ![](assets/message-center_usecase3.png)

1. Visualize e publique o evento (consulte [Visualizar e publicar o evento](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)).
1. Integre o evento em seu site (consulte [Integração do acionamento do evento em um site](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)).

