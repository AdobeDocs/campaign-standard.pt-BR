---
title: Mensagens transacionais de evento
seo-title: Mensagens transacionais de evento
description: Mensagens transacionais de evento
seo-description: Saiba como criar e publicar uma mensagem transacional de evento.
page-status-flag: nunca ativado
uuid: d 747 feb 5-58 fb -4 e 12-a 176-404 f 0 eca 5391
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canais
content-type: reference
topic-tags: transacionais-messaging
discoiquuid: 4 f 6317 a 1-9 dfe -4714-bc 1 c -393629 d 855 cd
context-tags: Deliverytransactionaltemplate, visão geral
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e08b7e01956a9106937cb72ab790cb2e98999fcd

---


# Event transactional messages{#event-transactional-messages}

É possível enviar mensagens transacionais de evento para um evento. Esse tipo de mensagens transacionais não contém informações de perfil: o destino de entrega é definido pelos dados contidos no próprio evento.

Once you have created and published an event (the cart abandonment as explained in [this section](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle)), the corresponding transactional message is created automatically.

The configuration steps are presented in the [Configuring an event to send an transactional message](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) section.

Para que o evento dispare uma mensagem transacional, é necessário personalizar a mensagem e, em seguida, testar e publicá-la.

>[!NOTE]
>
>To access the transactional messages, you must have administration rights or appear in the **[!UICONTROL Message Center agents]** (mcExec) security group. As mensagens transacionais de evento não contêm informações de perfil, portanto elas não são compatíveis com regras de fadiga (mesmo no caso de um enriquecimento com perfis). See [Fatigue rules](../../administration/using/fatigue-rules.md#choosing-the-channel).

## Defining a test profile in a transactional message {#defining-a-test-profile-in-a-transactional-message}

Defina um perfil de teste adaptado, que permitirá visualizar a mensagem e enviar uma prova para verificá-la.

### Creating a test profile within the transactional message {#creating-a-test-profile-within-the-transactional-----------message}

1. To access the message that you created, click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner, then select **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]** &gt; **[!UICONTROL Transactional messages]**.

   ![](assets/message-center_4.png)

1. Crie um perfil de teste que será vinculado ao seu evento.

   ![](assets/message-center_test-profile.png)

1. Specify the information to send in JSON format in the **[!UICONTROL Event data used for personalization]** section. Esse é o conteúdo que será usado ao visualizar a mensagem e quando o perfil de teste receber a prova.

   ![](assets/message-center_event-data.png)

   >[!NOTE]
   >
   >Você também pode inserir as informações relacionadas à tabela de perfil. See [Enriching the transactional message content](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content).

1. Após a criação, o perfil de teste será especificado previamente na mensagem transacional. Click the **[!UICONTROL Test profiles]** block of the message to check the target of your proof.

   ![](assets/message-center_5.png)

### Creating a test profile outside the transactional message {#creating-a-test-profile-outside-the-transactional-----------message}

You can also create a new test profile or use one that already exists in the **[!UICONTROL Test profiles]** menu.

1. Click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner, then select **[!UICONTROL Profiles & audiences]** &gt; **[!UICONTROL Test profiles]**.
1. In the **[!UICONTROL Event]** section of the page of the test profile that you have chosen, select the event that you have just created. Neste exemplo, selecione "Abandono de carrinho (evtcartabandono)".
1. Specify the information to send in JSON format in the **[!UICONTROL Event data]** text box.

   ![](assets/message-center_3.png)

1. Salve as alterações.

Agora é possível acessar a mensagem que você criou e selecionar o perfil de teste atualizado.

**Tópicos relacionados:**

* [Gerenciamento de perfis de teste](../../sending/using/managing-test-profiles-and-sending-proofs.md)
* [Definição de públicos-alvo](../../audiences/using/creating-audiences.md)

## Personalizing a transactional message {#personalizing-a-transactional-message}

Para configurar a personalização em uma mensagem transacional, siga as etapas abaixo:

1. Click the **[!UICONTROL Content]** block to modify your message's subject and content. Neste exemplo, importe um modelo HTML contendo imagens, a folha de estilos e um arquivo HTML. Importing HTML templates is presented in the [Loading an existing content](../../designing/using/selecting-an-existing-content.md) section.

   ![](assets/message-center_6.png)

1. Insira o conteúdo da mensagem. Neste exemplo, adicionamos três campos de personalização: sobrenome, último produto consultado, valor total do carrinho. O link para o carrinho abandonado é um link para um URL externo que redirecionará a pessoa para o carrinho. Esse parâmetro não é gerenciado no Adobe Campaign.

   To add fields that you defined when you created your event (see [Configuring an event](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message)), insert a personalization field in the message content. You can find the fields by selecting **[!UICONTROL Transactional event]** &gt; **[!UICONTROL Event context]**.

   ![](assets/message-center_7.png)

1. Para aprimorar o conteúdo de sua mensagem, adicione campos selecionando-os a partir da tabela com a qual você vinculou seu evento. In our example, select the **[!UICONTROL Title (salutation)]** field in the **[!UICONTROL Profile]** table.

   ![](assets/message-center_7-enrichment.png)

   The steps for inserting a personalization field are detailed in the [Inserting a personalization field](../../designing/using/inserting-a-personalization-field.md) section.

   ![](assets/message-center_8.png)

1. Visualize a mensagem selecionando o perfil definido para esse evento.

   The steps for previewing a message are detailed in the [Previewing messages](../../sending/using/preparing-the-send.md) section.

   ![](assets/message-center_9.png)

   Você pode verificar se os campos de personalização correspondem às informações inseridas no perfil de teste. For more on this, see [Defining a test profile in a transactional message](../../channels/using/event-transactional-messages.md#defining-a-test-profile-in-a-transactional-message).

## Using product listings in a transactional message {#using-product-listings-in-a-transactional-message}

Você pode criar listagens de produto fazendo referência a uma ou mais coleções de dados no conteúdo de um email transacional. Por exemplo, em um email de abandono de carrinho, você pode incluir uma lista de todos os produtos que estavam nos carrinhos dos usuários quando saíram do site, com uma imagem, o preço e um link para cada produto.

>[!CAUTION]
>
>Product listings are only available when editing transactional email messages through the [Email Designer](../../designing/using/about-email-content-design.md#about-the-email-designer) interface.

Para adicionar uma lista de produtos abandonados em uma mensagem transacional, siga as etapas abaixo.

Você também pode assistir a um conjunto de vídeos explicando as etapas necessárias para configurar as listagens de produtos em um email transacional. For more on this, see [this page](https://helpx.adobe.com/campaign/kt/acs/using/acs-product-listings-in-transactional-emails-feature-video-setup.html).

>[!NOTE]
>
>O Adobe Campaign não oferece suporte a listagens de produto aninhadas, o que significa que você não pode incluir uma listagem de produto dentro de outra.

### Defining a product listing {#defining-a-product-listing}

Antes de poder usar uma listagem de produto em uma mensagem transacional, é necessário definir no nível do evento a lista de produtos e os campos para cada produto da lista que você deseja exibir. For more on this, see [Defining data collections](../../administration/using/configuring-transactional-messaging.md#defining-data-collections).

1. In the transactional message, click the **[!UICONTROL Content]** block to modify the email content.
1. Arraste e solte um componente de estrutura na área de trabalho. For more on this, see [Editing the email structure](../../designing/using/defining-the-email-structure.md#editing-the-email-structure).

   Por exemplo, selecione um componente de estrutura de uma coluna e adicione um componente de texto, um componente de imagem e um componente de botão. For more on this, see [Adding fragments and components](../../designing/using/defining-the-email-structure.md#adding-fragments-and-content-components).

1. Select the structure component you just created and click the **[!UICONTROL Enable product listing]** icon from the contextual toolbar.

   ![](assets/message-center_loop_create.png)

   The structure component is highlighted with an orange frame and the **[!UICONTROL Product listing]** settings are displayed in the left palette.

   ![](assets/message-center_loop_palette.png)

1. Selecione como os elementos da coleção serão exibidos:

   * **[!UICONTROL Row]**: horizontalmente, ou seja, cada elemento em uma linha na outra.
   * **[!UICONTROL Column]**: verticalmente, ou seja, cada elemento ao lado do outro na mesma linha.
   >[!NOTE]
   >
   >The **[!UICONTROL Column]** option is only available when using a multicolumn structure component ( **[!UICONTROL 2:2 column]**, **[!UICONTROL 3:3 column]** and **[!UICONTROL 4:4 column]** ). Ao editar a lista de produtos, preencha apenas a primeira coluna: as outras colunas não serão consideradas. For more on selecting structure components, see [Editing the email structure](../../designing/using/defining-the-email-structure.md#editing-the-email-structure).

1. Selecione a coleção de dados criada ao configurar o evento relacionado à mensagem transacional. You can find it under the **[!UICONTROL Context]** &gt; **[!UICONTROL Real-time event]** &gt; **[!UICONTROL Event context]** node.

   ![](assets/message-center_loop_selection.png)

   For more on configuring the event, see [Defining data collections](../../administration/using/configuring-transactional-messaging.md#defining-data-collections).

1. Use the **[!UICONTROL First item]** drop-down list to select which element will start the list displayed in the email.

   Por exemplo, se você selecionar 2, o primeiro item da coleção não será exibido no email. A listagem de produtos começará no segundo item.

1. Selecione o número máximo de itens a serem exibidos na lista.

   >[!NOTE]
   >
   >If you want the elements of your list to be displayed vertically ( **[!UICONTROL Column]** ), the maximum number of items is limited according to the selected structure component (2, 3 or 4 columns). For more on selecting structure components, see [Editing the email structure](../../designing/using/defining-the-email-structure.md#editing-the-email-structure).

### Populating the product listing {#populating-the-product-listing}

Para exibir uma lista de produtos que vêm do evento vinculado ao email transacional, siga as etapas abaixo.

For more on creating a collection and related fields when configuring the event, see [Defining data collections](../../administration/using/configuring-transactional-messaging.md#defining-data-collections).

1. Select the image component you inserted, select **[!UICONTROL Enable personalization]** and click the pencil in the Settings pane.

   ![](assets/message-center_loop_image.png)

1. Select **[!UICONTROL Add personalization field]** in the **[!UICONTROL Image source URL]** window that opens.

   From the **[!UICONTROL Context]** &gt; **[!UICONTROL Real-time event]** &gt; **[!UICONTROL Event context]** node, open the node corresponding to the collection that you created (here **[!UICONTROL Product list]** ) and select the image field that you defined (here **[!UICONTROL Product image]** ). Click **[!UICONTROL Save]**.

   ![](assets/message-center_loop_product-image.png)

   O campo de personalização selecionado agora é exibido no painel Configurações.

1. At the desired position, select **[!UICONTROL Insert personalization field]** from the contextual toolbar.

   ![](assets/message-center_loop_product.png)

1. From the **[!UICONTROL Context]** &gt; **[!UICONTROL Real-time event]** &gt; **[!UICONTROL Event context]** node, open the node corresponding to the collection that you created (here **[!UICONTROL Product list]** ) and select the field that you created (here **[!UICONTROL Product name]** ). Click **[!UICONTROL Confirm]**.

   ![](assets/message-center_loop_product_node.png)

   O campo de personalização selecionado agora é exibido na posição desejada no conteúdo de email.

1. Prossiga de forma semelhante para inserir o preço.
1. Select some text and select **[!UICONTROL Insert link]** from the contextual toolbar.

   ![](assets/message-center_loop_link_insert.png)

1. Select **[!UICONTROL Add personalization field]** in the **[!UICONTROL Insert link]** window that opens.

   From the **[!UICONTROL Context]** &gt; **[!UICONTROL Real-time event]** &gt; **[!UICONTROL Event context]** node, open the node corresponding to the collection that you created (here **[!UICONTROL Product list]** ) and select the URL field that you created (here **[!UICONTROL Product URL]** ). Click **[!UICONTROL Save]**.

   >[!CAUTION]
   >
   >Por motivos de segurança, certifique-se de inserir o campo de personalização dentro de um link começando com um nome de domínio estático apropriado.

   ![](assets/message-center_loop_link_select.png)

   O campo de personalização selecionado agora é exibido no painel Configurações.

1. Select the structure component on which the product listing is applied and select **[!UICONTROL Show fallback]** to define a default content.

   ![](assets/message-center_loop_fallback_show.png)

1. Arraste um ou mais componentes de conteúdo e edite-os conforme necessário.

   ![](assets/message-center_loop_fallback.png)

   O conteúdo de fallback será exibido se a coleção estiver vazia quando o evento for acionado, por exemplo, se um cliente não tiver nada no carrinho.

1. No painel Configurações, edite os estilos da lista de produtos. For more on this, see [Editing email styles](../../designing/using/editing-email-styles.md).
1. Visualize o e-mail usando um perfil de teste vinculado ao evento transacional relevante e para o qual os dados de coleção foram definidos. For example, add the following information in the **[!UICONTROL Event data]** section for the test profile you want to use:

   ![](assets/message-center_loop_test-profile_payload.png)

   For more on defining a test profile in a transactional message, see [this section](../../channels/using/event-transactional-messages.md#defining-a-test-profile-in-a-transactional-message).

## Testing a transactional message {#testing-a-transactional-message}

Após salvar sua mensagem transacional, agora você pode enviar uma prova para testá-la.

![](assets/message-center_10.png)

The steps for sending a proof are detailed in the [Sending a proof](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs) section.

## Publishing a transactional message {#publishing-a-transactional-message}

Após marcar sua mensagem transacional, você pode publicá-la.

![](assets/message-center_12.png)

Agora, assim que o evento "Abandono do carrinho" for acionado, ele solicitará automaticamente uma mensagem contendo o título e o sobrenome do destinatário, o URL do carrinho, o último produto consultado ou uma lista de produtos, se você definir uma lista de produtos, e o valor total do carrinho será enviado.

To access reports concerning your transactional message, use the **[!UICONTROL Reports]** button. See [Reports](../../reporting/using/about-dynamic-reports.md).

![](assets/message-center_13.png)

## Suspending a transactional message publication {#suspending-a-transactional-message-publication}

You can suspend publishing your transactional message by using the **[!UICONTROL Pause]** button, for example, to modify the data contained in the message. Os eventos não são mais processados, mas sim mantidos em fila no banco de dados do Adobe Campaign.

The queued events are kept during a period of time that is defined in the REST API (see [REST API documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html)) or in the trigger event if you are using the Triggers core service (see [Working with Campaign and Experience Cloud Triggers](../../integrating/using/about-adobe-experience-cloud-triggers.md)).

![](assets/message-center_pause.png)

When clicking **[!UICONTROL Resume]**, all of the queued events (provided that they are not expired) are processed. Agora, todas as modificações foram realizadas enquanto a publicação do modelo foi suspensa.

## Unpublishing a transactional message {#unpublishing-a-transactional-message}

Clicking **[!UICONTROL Unpublish]** allows you to cancel the transactional message publication, but also the publication of the corresponding event, which deletes from the REST API the resource corresponding to the event that you previously created. Agora, mesmo que o evento seja acionado por meio do seu site, as mensagens correspondentes não são mais enviadas e não são armazenadas no banco de dados.

![](assets/message-center_unpublish-template.png)

>[!NOTE]
>
>Para publicar a mensagem novamente, volte à configuração de evento correspondente, publique-a e depois publique a mensagem. For more on this, see [Publishing a transactional message](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message).

Se você cancelar a publicação de uma mensagem transacional pausada, talvez precise aguardar até 24 horas para poder publicá-la novamente. This is to let the **[!UICONTROL Database cleanup]** workflow clean all the events that were sent to the queue. The steps for pausing a message are detailed in the [Suspending a transactional message publication](../../channels/using/event-transactional-messages.md#suspending-a-transactional-message-publication) section.

The **[!UICONTROL Database cleanup]** workflow, which runs every day at 4am, is accessible through **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Workflows]**.

## Deleting a transactional message {#deleting-a-transactional-message}

![](assets/message-center_delete-template.png)

By selecting a transactional message, you can delete it with the **[!UICONTROL Delete element]** button even if it has already been published. No entanto, excluir uma mensagem transacional só pode ser feita em determinadas condições:

* **Mensagens transacionais**: Para excluir uma mensagem transacional, a mensagem não deve ser publicada e não pausada.

   Se a mensagem transacional não for publicada, a configuração do evento também precisará ser cancelada para excluir com êxito sua mensagem transacional, a menos que outra mensagem transacional esteja vinculada ao evento correspondente. For more information on how to unpublish a transactional message, refer to this [section](../../channels/using/event-transactional-messages.md#unpublishing-a-transactional-message).

   >[!CAUTION]
   >
   >Excluir uma mensagem transacional que já tenha enviado notificações também excluirá seus logs de envio e rastreamento.

* **Mensagens transacionais de um modelo de evento predefinido (mensagens transacionais internas)**: Para excluir uma mensagem transacional interna, a mensagem não deve ser publicada e não pausada.

   Ela também não deve ser a única mensagem transacional no evento, outras precisam estar vinculadas ao evento correspondente.

## Transactional message retry process {#transactional-message-retry-process}

Uma mensagem transacional não entregue temporariamente está sujeita a tentativas automáticas que são realizadas até que a entrega expire. For more on the delivery duration, see [Validity period parameters](../../administration/using/configuring-email-channel.md#validity-period-parameters).

Quando uma mensagem transacional falha ao ser enviada, há dois sistemas de tentativa:

* No nível transacional de mensagem, uma mensagem transacional pode falhar antes que o evento seja atribuído a uma entrega de execução, o que significa que entre a recepção do evento e a preparação de entrega. See [Event processing retry process](../../channels/using/event-transactional-messages.md#event-processing-retry-process).
* No nível do processo de envio, uma vez que o evento foi atribuído a uma entrega de execução, a mensagem transacional pode falhar devido a um erro temporário. See [Message sending retry process](../../channels/using/event-transactional-messages.md#message-sending-retry-process).

### Event processing retry process {#event-processing-retry-process}

Se o evento não puder ser atribuído a uma entrega de execução, o processamento do evento será adiado. As tentativas são feitas até que sejam atribuídas a uma nova entrega de execução.

>[!NOTE]
>
>Um evento adiado não aparece na mensagem transacional que envia logs porque ainda não está atribuída a uma entrega de execução.

Por exemplo, o evento não pode ser atribuído a uma entrega de execução porque seu conteúdo não estava correto, ocorreu um problema com direitos de acesso ou marca, foi detectado um erro na aplicação de regras de tipologia etc. Nesse caso, você pode pausar a mensagem, editá-la para corrigir o problema e publicá-la novamente. O sistema de tentativas irá atribuí-lo a uma nova entrega de execução.

### Message sending retry process {#message-sending-retry-process}

Uma vez que o evento foi atribuído a uma entrega de execução, a mensagem transacional pode falhar devido a um erro temporário, se a caixa de correio do destinatário estiver cheia por exemplo. For more on this, see [Retries after a delivery temporary failure](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

>[!NOTE]
>
>Quando um evento é atribuído a uma entrega de execução, ele aparece nos registros de envio dessa disponibilização de execução e apenas no momento. The failed deliveries are displayed in the **[!UICONTROL Execution list]** tab of the transactional message.

### Limitations {#limitations}

**Atualização de registros de logs**

No processo de nova tentativa, o envio de logs da nova entrega de execução não é atualizado imediatamente (a atualização é realizada por meio de um fluxo de trabalho programado). It means that the message could be in **[!UICONTROL Pending]** status even if the transactional event has been processed by the new execution delivery.

**Falha na entrega da execução**

Não é possível interromper uma entrega de execução. No entanto, se a entrega atual de execução falhar, uma nova será criada assim que um novo evento for recebido, e todos os novos eventos serão processados por essa nova entrega de execução. Nenhum evento novo é processado pela entrega de execução falha.

Se alguns eventos já atribuídos a uma entrega de execução tiverem sido adiados e houver falha na entrega da execução, o sistema de tentativas não atribuirá os eventos adiados para a nova entrega de execução, o que significa que esses eventos são perdidos.
