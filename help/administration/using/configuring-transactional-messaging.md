---
title: Configuração de mensagens transacionais
description: Saiba como configurar mensagens transacionais.
page-status-flag: never-activated
uuid: 4caeadbe-f4a7-43ce-986d-e99fa9ca0d0d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 3f968556-e774-43dc-a0b8-7188d7665fbc
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e62fdfba531bcfe18c147e7035c79e1ac6bca979

---


# Configuração de mensagens transacionais{#configuring-transactional-messaging}

Para enviar uma mensagem transacional com o Adobe Campaign, primeiro é necessário descrever a estrutura dos dados do evento.

A configuração do evento deve ser executada por um **administrador** , seguindo as etapas abaixo:

A configuração pode variar dependendo do tipo de mensagem transacional que você deseja enviar. Para obter mais informações, consulte Configurações específicas de evento [transacional](#transactional-event-specific-configurations)

Depois que o evento é publicado, a mensagem transacional correspondente é criada automaticamente. For more on transactional messaging, refer to [this page](../../channels/using/about-transactional-messaging.md).

## Criação de um evento {#creating-an-event}

Comece criando o evento que corresponde às suas necessidades.

1. Clique no **[!UICONTROL Adobe Campaign]** logotipo, no canto superior esquerdo, em seguida selecione **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**.
1. Clique no botão **[!UICONTROL Create]**.
1. Dê um **[!UICONTROL Label]** e-mail **[!UICONTROL ID]** ao evento. O **[!UICONTROL ID]** campo é obrigatório e deve começar com o prefixo &quot;EVT&quot;. Se você não usar esse prefixo, ele será adicionado automaticamente quando você clicar **[!UICONTROL Create]**.

   ![](assets/message-center_1.png)

   >[!IMPORTANT]
   >
   >A ID não deve exceder 64 caracteres, incluindo o prefixo EVT.

1. Selecione o canal que será usado para enviar suas mensagens transacionais **[!UICONTROL Email]** ou **[!UICONTROL Mobile (SMS)]** **[!UICONTROL Mobile application]** (notificação por push).

   >[!NOTE]
   >
   >Somente um canal pode ser usado para cada configuração de evento. Depois que o evento é criado, não é possível alterar o canal.

1. Selecione a dimensão de definição de metas correspondente à configuração de evento desejada e clique em **[!UICONTROL Create]**.

   Mensagens transacionais baseadas em eventos direcionam dados contidos no próprio evento, enquanto mensagens transacionais baseadas em perfil direcionam dados contidos no banco de dados do Adobe Campaign. Para obter mais informações, consulte Configurações [específicas de evento](#transactional-event-specific-configurations)transacional.

## Definição dos atributos do evento {#defining-the-event-attributes}

Na **[!UICONTROL Fields]** seção, defina os atributos que serão integrados ao conteúdo do evento e poderão ser usados para personalizar a mensagem transacional.

As etapas para adicionar e modificar campos são as mesmas para recursos [](../../developing/using/configuring-the-resource-s-data-structure.md#adding-fields-to-a-resource)personalizados.

![](assets/message-center_2.png)

>[!NOTE]
>
>Se quiser criar uma mensagem transacional multilíngue, defina um atributo de evento adicional com a **[!UICONTROL AC_language]** ID. Isso se aplica somente às mensagens transacionais de eventos. Depois que o evento é publicado, as etapas para editar o conteúdo de uma mensagem transacional multilíngue são as mesmas de um email multilíngue padrão. See [Creating a multilingual email](../../channels/using/creating-a-multilingual-email.md).

## Definição de coleções de dados {#defining-data-collections}

Você pode adicionar ao conteúdo do evento uma coleção de elementos, cada elemento incluindo vários atributos.

Essa coleção pode ser usada em um email transacional para adicionar listas de produtos ao conteúdo da mensagem, por exemplo, uma lista de produtos - com o preço, o número de referência, a quantidade etc. para cada produto da lista.

1. Na **[!UICONTROL Collections]** seção, clique no **[!UICONTROL Create element]** botão.

   ![](assets/message-center_collection_create.png)

1. Adicione um rótulo e uma ID para sua coleção.
1. Adicione todos os campos que deseja exibir na mensagem transacional para cada produto da lista.

   Neste exemplo, adicionamos os seguintes campos:

   ![](assets/message-center_collection_fields.png)

Depois que o evento e a mensagem forem publicados, você poderá usar essa coleção na mensagem transacional.

Este é o exemplo da visualização da API:

![](assets/message-center_collection_api-preview.png)

**Tópicos relacionados:**

* [Visualização e publicação do evento](#previewing-and-publishing-the-event)
* [Uso das listas de produtos em uma mensagem transacional](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message)

## Enriquecer o conteúdo transacional de mensagens {#enriching-the-transactional-message-content}

O enriquecimento do conteúdo transacional de mensagens com informações do banco de dados do Adobe Campaign permite que você personalize suas mensagens. Por exemplo, a partir do sobrenome ou da ID do CRM de cada um dos destinatários, é possível recuperar dados como o endereço ou a data de nascimento ou qualquer outro campo personalizado adicionado na tabela Perfil para personalizar as informações enviadas a eles.

É possível enriquecer o conteúdo de mensagens transacionais com informações de recursos **[!UICONTROL Profile]** **[!UICONTROL Service]** ou recursos estendidos.

Essas informações também podem ser armazenadas em novos recursos. Nesse caso, o recurso deve estar vinculado ao **[!UICONTROL Profile]** ou aos recursos **[!UICONTROL Service]** diretamente ou por meio de outra tabela. Por exemplo, na configuração abaixo, é possível aprimorar o conteúdo da mensagem transacional com informações do **[!UICONTROL Product]** recurso, como a categoria do produto ou a ID, se o **[!UICONTROL Product]** recurso estiver vinculado ao **[!UICONTROL Profile]** recurso.

![](assets/message-center_usecaseschema.png)

Para obter mais informações sobre criação e publicação de recursos, consulte [esta página](../../developing/using/key-steps-to-add-a-resource.md).

1. Na **[!UICONTROL Enrichment]** seção, clique no **[!UICONTROL Create element]** botão.

   ![](assets/message-center_addenrichment.png)

1. Selecione o recurso com o qual deseja vincular sua mensagem. In this case, choose the **[!UICONTROL Profile]** resource.

   ![](assets/message-center_new-enrichment.png)

1. Use o **[!UICONTROL Create element]** botão para vincular um campo do recurso selecionado a um dos campos que você adicionou anteriormente ao evento (consulte [Definição dos atributos](#defining-the-event-attributes)do evento).

   ![](assets/message-center_enrichment-join.png)

1. Neste exemplo, reconciliamos os campos **[!UICONTROL Last name]** e **[!UICONTROL First name]** com os campos correspondentes no **[!UICONTROL Profile]** recurso.

   ![](assets/message-center_enrichment-join-fields.png)

   Você também pode enriquecer o conteúdo de mensagens transacionais usando o **[!UICONTROL Service]** recurso. Para obter mais informações sobre serviços, consulte esta [seção](../../audiences/using/creating-a-service.md).

1. Se você estiver criando ou editando um evento baseado em perfil, na **[!UICONTROL Targeting enrichment]** seção, selecione o enriquecimento que será usado como o destino da mensagem durante a execução da entrega.

   ![](assets/message-center_marketing_targeting_enrichment.png)

   >[!NOTE]
   >
   >A seleção de um enriquecimento de direcionamento com base no **[!UICONTROL Profile]** recurso é obrigatória para eventos baseados em perfil.

Assim que o evento e a mensagem forem publicados, esse link permitirá que você enriqueça o conteúdo da mensagem transacional.

**Tópicos relacionados:**

* [Visualizar e publicar o evento](#previewing-and-publishing-the-event).
* [Personalizando uma mensagem](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message)transacional.

## Visualização e publicação do evento {#previewing-and-publishing-the-event}

Antes de poder usar o evento, você deve visualizá-lo e publicá-lo.

1. Clique no **[!UICONTROL API preview]** botão para ver uma simulação da REST API que será usada pelo desenvolvedor do seu site antes de ser publicada. Depois que o evento é publicado, esse botão também permite que você visualize a API na produção. Consulte [Integrar o acionamento do evento em um site](#integrating-the-triggering-of-the-event-in-a-website).

   ![](assets/message-center_api_preview.png)

   >[!NOTE]
   >
   >A API REST varia de acordo com o canal selecionado e a dimensão de definição de metas selecionada. Para obter mais detalhes sobre as várias configurações, consulte Configurações [específicas de evento](#transactional-event-specific-configurations)transacional.

1. Clique em **[!UICONTROL Publish]** para iniciar a publicação.

   ![](assets/message-center_pub.png)

1. É possível exibir os logs de publicação na guia correspondente.

   ![](assets/message-center_logs.png)


>[!NOTE]
>
>Sempre que modificar o evento, você deve clicar **[!UICONTROL Publish]** novamente para gerar a REST API atualizada que será usada pelo desenvolvedor do site.

Depois que o evento é publicado, uma mensagem transacional vinculada ao novo evento é criada automaticamente. Para que esse evento dispare o envio de uma mensagem transacional, você deve modificar e publicar a mensagem que acabou de ser criada. See [Event transactional messages](../../channels/using/event-transactional-messages.md).

Você pode acessar a mensagem transacional criada diretamente do link na área do lado esquerdo.

![](assets/message-center_messagegeneration.png)

Você também precisa integrar esse evento de disparo ao seu site. Consulte [Integrar o acionamento do evento em um site](#integrating-the-triggering-of-the-event-in-a-website).

<!-->>[!NOTE]
>Para consultar as publicações anteriores, se houver, clique no **[!UICONTROL Latest transactional events]** link na **[!UICONTROL History]** seção da área à esquerda.-->

### Cancelamento de publicação de um evento {#unpublishing-an-event}

O **[!UICONTROL Unpublish]** botão permite cancelar a publicação do evento, que exclui da REST API o recurso correspondente ao evento criado anteriormente. Agora, mesmo se o evento for acionado por meio do site, as mensagens correspondentes não serão mais enviadas e não serão armazenadas no banco de dados.

![](assets/message-center_unpublish.png)

>[!NOTE]
Se você já tiver publicado a mensagem transacional correspondente, a publicação de mensagem transacional também será cancelada. Consulte [Cancelar publicação de uma mensagem](../../channels/using/event-transactional-messages.md#unpublishing-a-transactional-message)transacional.

Clique no **[!UICONTROL Publish]** botão para gerar uma nova REST API.

### Excluindo um evento {#deleting-an-event}

Depois que um evento for despublicado ou se um evento ainda não tiver sido publicado, você poderá excluí-lo da lista de configuração do evento. Para fazer isso:

1. Clique no **[!UICONTROL Adobe Campaign]** logotipo, no canto superior esquerdo, em seguida selecione **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**.
1. Passe o mouse sobre a configuração de evento de sua escolha e selecione o **[!UICONTROL Delete element]** botão.

   ![](assets/message-center_delete-button.png)

   >[!NOTE]
   Certifique-se de que a configuração do evento tenha o **[!UICONTROL Draft]** status; caso contrário, você não poderá excluí-la. O **[!UICONTROL Draft]** status se aplica a um evento que ainda não foi publicado ou que não foi [publicado](#unpublishing-an-event).

1. Clique no botão **[!UICONTROL Confirm]**.

   ![](assets/message-center_delete-confirm.png)

>[!IMPORTANT]
A exclusão de uma configuração de evento que tenha sido publicada e já usada também excluirá as mensagens transacionais correspondentes e seus registros de envio e rastreamento.

## Integração do acionamento do evento em um site {#integrating-the-triggering-of-the-event-in-a-website}

Depois de criar um evento, é necessário integrar o acionamento desse evento ao seu site.

No exemplo descrito na seção [Transactional Messaging Operating Princípio](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle) Operacional, você deseja que um evento de &quot;abandono do carrinho&quot; seja acionado sempre que um de seus clientes sair do site antes de comprar os produtos no carrinho. Para fazer isso, o desenvolvedor da Web do site deve usar a API REST do Adobe Campaign Standard.

Consulte a Documentação [da API](../../api/using/managing-transactional-messages.md) REST.

## Configurações específicas de evento transacional {#transactional-event-specific-configurations}

A configuração de evento transacional pode variar dependendo do tipo de mensagem transacional que você deseja enviar (evento ou perfil) e do canal que será usado.

As seções a seguir detalham qual configuração específica deve ser definida de acordo com a mensagem transacional desejada. Para obter mais informações sobre as etapas gerais para configurar um evento, consulte [Criação de um evento](#creating-an-event).

### Mensagens transacionais baseadas em eventos {#event-based-transactional-messages}

Para enviar uma mensagem transacional baseada em eventos, primeiro é necessário criar e configurar um evento direcionando os dados contidos no próprio evento.
Para obter mais informações, consulte [Participação em mensagens transacionais](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Managedatatofuelengagingexperiences).

1. Ao criar a configuração do evento, selecione a dimensão de **[!UICONTROL Real-time event]** definição de metas (consulte [Criação de um evento](#creating-an-event)).
1. Adicione campos ao evento para personalizar a mensagem transacional (consulte [Definição dos atributos](#defining-the-event-attributes)do evento).
1. Enriqueça o conteúdo da mensagem transacional se quiser usar informações adicionais do banco de dados do Adobe Campaign (consulte [Enriquecendo o conteúdo](#enriching-the-transactional-message-content)da mensagem transacional).

   >[!NOTE]
   As mensagens transacionais baseadas em eventos devem usar somente os dados que estão no evento enviado para definir o destinatário e a personalização do conteúdo da mensagem. No entanto, você pode enriquecer o conteúdo de sua mensagem transacional usando informações do banco de dados do Adobe Campaign.

1. Visualize e publique o evento (consulte [Visualizar e publicar o evento](#previewing-and-publishing-the-event)).

   Ao visualizar o evento, a REST API contém um atributo que especifica o endereço de email ou o telefone celular de acordo com o canal selecionado.

   Depois que o evento é publicado, uma mensagem transacional vinculada ao novo evento é criada automaticamente. Para que o evento dispare o envio de uma mensagem transacional, você deve modificar e publicar a mensagem que acabou de ser criada, consulte Mensagens [transacionais do](../../channels/using/event-transactional-messages.md)evento.

1. Integre o evento ao seu site (consulte [Integrar o acionamento do evento em um site](#integrating-the-triggering-of-the-event-in-a-website)).

### Mensagens transacionais baseadas em perfil {#profile-based-transactional-messages}

Para enviar uma mensagem transacional com base em perfil, primeiro é necessário criar e configurar os dados de direcionamento de evento contidos no banco de dados do Adobe Campaign.

1. Ao criar a configuração do evento, selecione a dimensão de **[!UICONTROL Profile event]** definição de metas (consulte [Criação de um evento](#creating-an-event)).
1. Adicione campos ao evento para personalizar a mensagem transacional (consulte [Definição dos atributos](#defining-the-event-attributes)do evento). É necessário adicionar pelo menos um campo para criar um enriquecimento. Não é necessário criar outros campos, como **Nome** e **Sobrenome** , pois você poderá usar os campos de personalização do banco de dados do Adobe Campaign.
1. Crie um enriquecimento para vincular o evento ao **[!UICONTROL Profile]** recurso (consulte [Enriquecendo o conteúdo](#enriching-the-transactional-message-content)da mensagem transacional). A criação de um enriquecimento é obrigatória ao usar uma dimensão de **[!UICONTROL Profile]** definição de metas.
1. Visualize e publique o evento (consulte [Visualizar e publicar o evento](#previewing-and-publishing-the-event)).

   Ao visualizar o evento, a API REST não contém um atributo que especifique o endereço de email ou o telefone móvel como ele será recuperado do **[!UICONTROL Profile]** recurso.

   Depois que o evento é publicado, uma mensagem transacional vinculada ao novo evento é criada automaticamente. Para que o evento dispare o envio de uma mensagem transacional, você deve modificar e publicar a mensagem que acabou de ser criada, consulte [Envio de uma mensagem](../../channels/using/profile-transactional-messages.md#sending-a-profile-transactional-message)transacional de perfil.

1. Integre o evento ao seu site (consulte [Integrar o acionamento do evento em um site](#integrating-the-triggering-of-the-event-in-a-website)).

### Notificações por push transacionais baseadas em eventos {#event-based-transactional-push-notifications}

Para poder enviar notificações por push transacionais, é necessário configurar o Adobe Campaign de acordo. Consulte Configuração [de push](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html).

Para enviar uma notificação por push transacional anônima a todos os usuários que aceitaram receber notificações do seu aplicativo móvel, primeiro é necessário criar e configurar um evento direcionando os dados contidos no próprio evento. As etapas correspondentes são apresentadas abaixo.

O evento deve conter os três elementos a seguir:

* Um token **de** registro, que é a ID do usuário para um aplicativo móvel e um dispositivo. Pode não corresponder a nenhum perfil do banco de dados do Adobe Campaign.
* Um nome **de aplicativo** móvel (um para todos os dispositivos - Android e iOS). Essa é a ID do aplicativo móvel configurado no Adobe Campaign que será usada para receber notificações por push nos dispositivos dos usuários. Para obter mais informações, consulte esta [página](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)
* Uma plataforma **de** push (&quot;gcm&quot; para Android ou &quot;apns&quot; para iOS).

1. Ao criar a configuração do evento, selecione o **[!UICONTROL Mobile application]** canal e a dimensão de **[!UICONTROL Real-time event]** definição de metas (consulte [Criação de um evento](#creating-an-event)).
1. Adicione campos ao evento para personalizar a mensagem transacional (consulte [Definição dos atributos](#defining-the-event-attributes)do evento).
1. Enriqueça o conteúdo da mensagem transacional se quiser usar informações adicionais do banco de dados do Adobe Campaign (consulte [Enriquecendo o conteúdo](#enriching-the-transactional-message-content)da mensagem transacional).

   >[!NOTE]
   As mensagens transacionais baseadas em eventos devem usar somente os dados que estão no evento enviado para definir o destinatário e a personalização do conteúdo da mensagem. No entanto, você pode enriquecer o conteúdo de sua mensagem transacional usando informações do banco de dados do Adobe Campaign.

1. Visualize e publique o evento (consulte [Visualizar e publicar o evento](#previewing-and-publishing-the-event)).

   Ao visualizar o evento, a API REST contém os atributos &quot;registrationToken&quot;, &quot;application&quot; e &quot;pushPlatform&quot; que serão usados para direcionar a entrega.

   ![](assets/message-center_push_api.png)

   Depois que o evento é publicado, uma notificação por push transacional vinculada ao novo evento é criada automaticamente. Para modificar e publicar a mensagem que acabou de ser criada, consulte [Envio de uma notificação por push transacional direcionada a um evento](../../channels/using/transactional-push-notifications.md#transactional-push-notifications-targeting-an-event).

1. Integre o evento ao seu site (consulte [Integrar o acionamento do evento em um site](#integrating-the-triggering-of-the-event-in-a-website)).

### Notificações por push transacionais baseadas em perfil {#profile-based-transactional-push-notifications}

Para enviar uma notificação por push transacional para os perfis do Adobe Campaign que se inscreveram no seu aplicativo móvel, primeiro é necessário criar e configurar um evento direcionado ao banco de dados do Adobe Campaign.

1. Ao criar a configuração do evento, selecione o **[!UICONTROL Mobile application]** canal e a dimensão de **[!UICONTROL Profile]** definição de metas (consulte [Criação de um evento](#creating-an-event)).

   Por padrão, a notificação por push transacional será enviada para todos os aplicativos móveis nos quais os destinatários se inscreveram. Para enviar a notificação por push para um aplicativo móvel específico, selecione-o na lista. Os outros aplicativos móveis serão direcionados pela mensagem, mas serão excluídos do envio.

   ![](assets/message-center_push_appfilter.png)

1. Adicione campos ao evento, se desejar personalizar a mensagem transacional (consulte [Definição dos atributos](#defining-the-event-attributes)do evento).

   >[!NOTE]
   É necessário adicionar pelo menos um campo para criar um enriquecimento. Não é necessário criar outros campos, como **Nome** e **Sobrenome** , pois você poderá usar os campos de personalização do banco de dados do Adobe Campaign.

1. Crie um enriquecimento para vincular o evento ao **[!UICONTROL Profile]** recurso (consulte [Enriquecendo o conteúdo](#enriching-the-transactional-message-content)da mensagem transacional). A criação de um enriquecimento é obrigatória ao usar uma dimensão de **[!UICONTROL Profile]** definição de metas.
1. Visualize e publique o evento (consulte [Visualizar e publicar o evento](#previewing-and-publishing-the-event)).

   Ao visualizar o evento, a API REST não contém um atributo que especifique o token de registro, o nome do aplicativo e a plataforma de push, conforme serão recuperados do **[!UICONTROL Profile]** recurso.

   Depois que o evento é publicado, uma notificação por push transacional vinculada ao novo evento é criada automaticamente. Para modificar e publicar a mensagem que acabou de ser criada, consulte [Envio de uma notificação por push transacional direcionada a um perfil](../../channels/using/transactional-push-notifications.md#transactional-push-notifications-targeting-a-profile).

1. Integre o evento ao seu site (consulte [Integrar o acionamento do evento em um site](#integrating-the-triggering-of-the-event-in-a-website)).

### Configurar um evento para enviar uma mensagem de acompanhamento {#configuring-an-event-to-send-a-follow-up-message}

Uma mensagem de acompanhamento é um modelo de entrega de marketing predefinido que pode ser usado em um fluxo de trabalho para enviar mensagens aos destinatários de uma mensagem transacional específica. Para obter mais informações, consulte Mensagens [de](../../channels/using/follow-up-messages.md)acompanhamento.

1. Use a mesma configuração de evento criada para enviar uma mensagem transacional de evento. Consulte Mensagens [transacionais baseadas em](#event-based-transactional-messages)eventos.
1. Ao configurar seu evento, marque a **[!UICONTROL Create follow-up delivery template for this event]** caixa antes de publicar o evento.

   ![](assets/message-center_follow-up-checkbox.png)

1. Visualize e publique o evento (consulte [Visualizar e publicar o evento](#previewing-and-publishing-the-event)).

   Depois que o evento é publicado, uma mensagem transacional e um modelo de entrega de acompanhamento vinculado ao novo evento são criados automaticamente. Para obter mais informações sobre como usar mensagens de acompanhamento, consulte [Enviar uma mensagem](../../channels/using/follow-up-messages.md#sending-a-follow-up-message)de acompanhamento.

## Caso de uso: configurar um evento para enviar uma mensagem transacional {#use-case--configuring-an-event-to-send-a-transactional-message}

Neste exemplo, queremos configurar um evento para enviar mensagens de confirmação após cada compra em nosso site com os seguintes pré-requisitos:

Como queremos identificar nosso cliente por meio de sua ID do CRM, primeiro verifique se o **[!UICONTROL Profile]** recurso foi estendido com esse novo campo.

Do mesmo modo, um recurso personalizado correspondente às compras deve ter sido criado e publicado e deve estar vinculado ao **[!UICONTROL Profile]** recurso. Dessa forma, você poderá recuperar informações desse recurso para enriquecer o conteúdo da mensagem.

Para obter mais informações sobre criação e publicação de recursos, consulte [esta página](../../developing/using/key-steps-to-add-a-resource.md).

1. Crie um novo evento usando o **[!UICONTROL Email]** canal e a dimensão de **[!UICONTROL Profile]** definição de metas (consulte [Criação de um evento](#creating-an-event)).
1. Defina os atributos que estarão disponíveis para personalizar a mensagem transacional. Em nosso caso, adicione os campos &quot;ID do CRM&quot; e &quot;Identificador do produto&quot; (consulte [Definição dos atributos](#defining-the-event-attributes)do evento).

   ![](assets/message-center_usecase1.png)

1. Para enriquecer o conteúdo da mensagem com informações relacionadas às compras anteriores do cliente, crie um enriquecimento direcionado ao **[!UICONTROL Purchase]** recurso (consulte [Enriquecendo o conteúdo](#enriching-the-transactional-message-content)da mensagem transacional).

   ![](assets/message-center_usecase2.png)

1. Crie uma condição de junção entre o campo &quot;Identificador do produto&quot; que foi adicionado anteriormente à mensagem e o campo correspondente do **[!UICONTROL Purchase]** recurso

   ![](assets/message-center_usecase3.png)

1. Visualize e publique o evento (consulte [Visualizar e publicar o evento](#previewing-and-publishing-the-event)).
1. Integre o evento em seu site (consulte [Integrar o acionamento do evento em um site](#integrating-the-triggering-of-the-event-in-a-website)).

