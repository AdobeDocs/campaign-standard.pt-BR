---
title: Mensagens transacionais de evento
description: Saiba como criar e publicar uma mensagem transacional de evento.
page-status-flag: never-activated
uuid: d747feb5-58fb-4e12-a176-404f0eca5391
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: transactional-messaging
discoiquuid: 4f6317a1-9dfe-4714-bc1c-393629d855cd
context-tags: deliveryTransactionalTemplate,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e8f8755acdc0b778b74e2bfcd4dc898ceff82b90
workflow-type: tm+mt
source-wordcount: '2492'
ht-degree: 93%

---


# Mensagens transacionais de evento{#event-transactional-messages}

Você pode enviar mensagens transacionais de eventos direcionadas a um evento. Esse tipo de mensagem transacional não contém informações de perfil: o público-alvo do delivery é definido pelos dados contidos no próprio evento.

Depois de criar e publicar um evento (o abandono do carrinho, conforme explicado [nesta seção](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle)), a mensagem transacional correspondente é criada automaticamente.

As etapas de configuração são apresentadas na seção [Configuração de um evento para enviar uma mensagem transacional](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message).

>[!NOTE]
>
>As mensagens transacionais de evento não contêm informações sobre perfis, portanto, não são compatíveis com as regras de fadiga (mesmo no caso de um enriquecimento com perfis). Consulte [Regras de fadiga](../../sending/using/fatigue-rules.md#choosing-the-channel).

Para que o evento acione o envio de uma mensagem transacional, é necessário personalizar a mensagem, testá-la e publicá-la.

## Acessar mensagens transacionais {#accessing-transactional-messages}

Para acessar o mensagen transacional que você criou:

1. Click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner.
1. Selecione **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Transactional messages]**.

   ![](assets/message-center_4.png)

1. Clique na mensagem de sua escolha para editá-la.

>[!IMPORTANT]
>
>Para acessar mensagens transacionais, você deve fazer parte do grupo de segurança **[!UICONTROL Administrators (all units)]**.

## Personalização de uma mensagem transacional {#personalizing-a-transactional-message}

Para configurar a personalização em uma mensagem transacional, siga as etapas abaixo:

1. Clique no bloco **[!UICONTROL Content]** para modificar o assunto e o conteúdo da mensagem. Neste exemplo, selecione qualquer modelo que contenha imagens e texto. Para obter mais informações sobre modelos de conteúdo de email, consulte [Design usando modelos](../../designing/using/using-reusable-content.md#designing-templates).

   ![](assets/message-center_6.png)

1. Adicione um assunto e edite o conteúdo da mensagem de acordo com suas necessidades.

   >[!NOTE]
   >
   >O link para o carrinho abandonado é um link para um URL externo que redirecionará a pessoa para o carrinho. Esse parâmetro não é gerenciado no Adobe Campaign.

1. Neste exemplo, você deseja adicionar três campos definidos ao [criar o evento](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message): nome, último produto consultado, quantidade total do carrinho. Para fazer isso, [insira um campo de personalização ](../../designing/using/personalization.md#inserting-a-personalization-field) no conteúdo da mensagem.

1. Navegue até esses campos passando por **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**.

   ![](assets/message-center_7.png)

1. Para enriquecer o conteúdo da mensagem, adicione campos selecionando-os da tabela com a qual você vinculou seu evento. Em nosso exemplo, selecione o campo **[!UICONTROL Title (salutation)]** na tabela **[!UICONTROL Profile]** passando por **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**.

   ![](assets/message-center_7-enrichment.png)

1. Insira todos os campos necessários.

   ![](assets/message-center_8.png)

1. Pré-visualize a mensagem selecionando o perfil definido para esse evento.

   As etapas para visualizar uma mensagem são detalhadas na seção [Pré-visualização de mensagens](../../sending/using/previewing-messages.md).

   ![](assets/message-center_9.png)

   Você pode verificar se os campos de personalização correspondem às informações inseridas no perfil de teste. Para saber mais, consulte [Definição de um perfil de teste em uma mensagem transacional](#defining-a-test-profile-in-a-transactional-message).

## Uso de listas de produtos em uma mensagem transacional {#using-product-listings-in-a-transactional-message}

É possível criar listas de produtos que façam referência a uma ou mais coleções de dados no conteúdo de um email transacional. Por exemplo, em um email de abandono de carrinho, você pode incluir uma lista de todos os produtos que estavam nos carrinhos dos usuários quando eles saíram do site, com uma imagem, o preço e um link para cada produto.

>[!IMPORTANT]
>
>As listas de produtos só estão disponíveis ao editar mensagens de email transacionais por meio da interface do [Designer de email](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-interface).

Para adicionar uma lista de produtos abandonados em uma mensagem transacional, siga as etapas abaixo.

Você também pode assistir a um conjunto de vídeos explicando as etapas necessárias para configurar as listas de produtos em um email transacional. Para obter mais informações, consulte [esta seção](https://docs.adobe.com/content/help/pt-BR/campaign-standard-learn/tutorials/designing-content/product-listings-in-transactional-email.translate.html).

>[!NOTE]
>
>O Adobe Campaign não é compatível com listas de produtos aninhados, o que significa que não é possível incluir uma lista de produtos dentro de outra.

### Definição de uma lista de produtos {#defining-a-product-listing}

Antes de usar uma lista de produtos em uma mensagem transacional, é necessário definir no nível do evento a lista de produtos e os campos para cada produto da lista que você deseja exibir. Para obter mais informações, consulte [Definição de coleções de dados](../../administration/using/configuring-transactional-messaging.md#defining-data-collections).

1. Na mensagem transacional, clique no bloco **[!UICONTROL Content]** para modificar o conteúdo do email.
1. Arraste e solte um componente de estrutura no espaço de trabalho. Para obter mais informações, consulte [Edição da estrutura do email](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

   Por exemplo, selecione um componente de estrutura de uma coluna e adicione um componente de texto, um componente de imagem e um componente de botão. Para obter mais informações, consulte [Inclusão de fragmentos e componentes](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

1. Selecione o componente de estrutura que você acabou de criar e clique no ícone **[!UICONTROL Enable product listing]**, na barra de ferramentas contextual.

   ![](assets/message-center_loop_create.png)

   O componente de estrutura está realçado com um quadro laranja e as configurações da **[!UICONTROL Product listing]** são exibidas na paleta esquerda.

   ![](assets/message-center_loop_palette.png)

1. Selecione como os elementos da coleção serão exibidos:

   * **[!UICONTROL Row]**: horizontalmente, o que significa cada elemento em uma linha abaixo da outra.
   * **[!UICONTROL Column]**: verticalmente, o que significa cada elemento ao lado do outro na mesma linha.

   >[!NOTE]
   >
   >A opção **[!UICONTROL Column]** só está disponível ao usar um componente de estrutura de várias colunas ( **[!UICONTROL 2:2 column]**, **[!UICONTROL 3:3 column]** e **[!UICONTROL 4:4 column]** ). Ao editar a lista de produtos, preencha apenas a primeira coluna: as outras colunas não serão consideradas. Para obter mais informações sobre como selecionar componentes de estrutura, consulte [Edição da estrutura do email](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

1. Selecione a coleção de dados criada ao configurar o evento relacionado à mensagem transacional. Você pode encontrá-la no nó **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**.

   ![](assets/message-center_loop_selection.png)

   Para obter mais informações sobre como configurar o evento, consulte [Definição de coleções de dados](../../administration/using/configuring-transactional-messaging.md#defining-data-collections).

1. Use a lista suspensa **[!UICONTROL First item]** para selecionar qual elemento iniciará a lista exibida no email.

   Por exemplo, se você selecionar 2, o primeiro item da coleção não será exibido no email. A lista de produtos iniciará no segundo item.

1. Selecione o número máximo de itens que serão exibidos na lista.

   >[!NOTE]
   >
   >Se quiser que os elementos da lista sejam exibidos verticalmente ( **[!UICONTROL Column]** ), o número máximo de itens é limitado de acordo com o componente de estrutura selecionado (2, 3 ou 4 colunas). Para obter mais informações sobre como selecionar componentes de estrutura, consulte [Edição da estrutura do email](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

### Preenchimento da lista de produtos {#populating-the-product-listing}

Para exibir uma lista de produtos provenientes do evento vinculado ao email transacional, siga as etapas abaixo.

Para obter mais informações sobre como criar uma coleção e campos relacionados ao configurar o evento, consulte [Definição de coleções de dados](../../administration/using/configuring-transactional-messaging.md#defining-data-collections).

1. Selecione o componente de imagem inserido, selecione **[!UICONTROL Enable personalization]** e clique no lápis, no painel Configurações.

   ![](assets/message-center_loop_image.png)

1. Selecione **[!UICONTROL Add personalization field]** na janela **[!UICONTROL Image source URL]** que será aberta.

   No nó **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**, abra o nó correspondente à coleção que você criou (aqui **[!UICONTROL Product list]** ) e selecione o campo de imagem definido (aqui **[!UICONTROL Product image]** ). Clique em **[!UICONTROL Save]**.

   ![](assets/message-center_loop_product-image.png)

   O campo de personalização selecionado agora é exibido no painel Settings.

1. Na posição desejada, selecione **[!UICONTROL Insert personalization field]** na barra de ferramentas contextual.

   ![](assets/message-center_loop_product.png)

1. No nó **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**, abra o nó correspondente à coleção que você criou (aqui **[!UICONTROL Product list]** ) e selecione o campo que você criou (aqui **[!UICONTROL Product name]** ). Clique em **[!UICONTROL Confirm]**.

   ![](assets/message-center_loop_product_node.png)

   O campo de personalização selecionado agora é exibido na posição desejada no conteúdo de email.

1. Proceda da mesma forma para inserir o preço.
1. Selecione algum texto e selecione **[!UICONTROL Insert link]** na barra de ferramentas contextual.

   ![](assets/message-center_loop_link_insert.png)

1. Selecione **[!UICONTROL Add personalization field]** na janela **[!UICONTROL Insert link]** que será aberta.

   No nó **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**, abra o nó correspondente à coleção que você criou (aqui **[!UICONTROL Product list]** ) e selecione o campo URL que você criou (aqui **[!UICONTROL Product URL]** ). Clique em **[!UICONTROL Save]**.

   >[!IMPORTANT]
   >
   >Por motivos de segurança, insira o campo de personalização dentro de um link que comece com um nome de domínio estático apropriado.

   ![](assets/message-center_loop_link_select.png)

   O campo de personalização selecionado agora é exibido no painel Settings.

1. Selecione o componente de estrutura no qual a lista de produtos é aplicada e selecione **[!UICONTROL Show fallback]** para definir um conteúdo padrão.

   ![](assets/message-center_loop_fallback_show.png)

1. Arraste um ou mais componentes de conteúdo e edite-os conforme necessário.

   ![](assets/message-center_loop_fallback.png)

   O conteúdo de fallback será exibido se a coleção estiver vazia quando o evento for acionado. Por exemplo, se um cliente não tiver nada em seu carrinho.

1. No painel Configurações, edite os estilos para a lista de produtos. Para obter mais informações, consulte [Edição de estilos de email](../../designing/using/styles.md).
1. Pré-visualize o email usando um perfil de teste vinculado ao evento transacional relevante e para o qual você definiu os dados da coleta. Por exemplo, adicione as seguintes informações na seção **[!UICONTROL Event data]** para o perfil de teste que você deseja usar:

   ![](assets/message-center_loop_test-profile_payload.png)

   Para obter mais informações sobre como definir um perfil de teste em uma mensagem transacional, consulte [esta seção](#defining-a-test-profile-in-a-transactional-message).

## Teste de mensagem transacional {#testing-a-transactional-message}

Primeiro, é necessário criar um perfil de teste específico que permita verificar o mensagen transacional corretamente.

### Definição de um perfil de teste específico {#defining-specific-test-profile}

Defina um perfil de teste que será vinculado ao seu evento, o que permitirá que você pré-visualização sua mensagem e envie uma prova relevante.

1. From the transactional message dashboard, click the **[!UICONTROL Create test profile]** button.

   ![](assets/message-center_test-profile.png)

1. Especifique as informações para enviar no formato JSON, na seção **[!UICONTROL Event data used for personalization]**. Esse é o conteúdo que será usado ao visualizar a mensagem e quando o perfil de teste receber a prova.

   ![](assets/message-center_event-data.png)

   >[!NOTE]
   >
   >Você também pode inserir as informações relacionadas à tabela do perfil. Consulte [Enriquecimento de conteúdo de mensagens transacionais](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content).

1. Depois de criado, o perfil de teste será pré-especificado no mensagen transacional. Clique no bloco **[!UICONTROL Test profiles]** da mensagem para verificar o público-alvo da prova.

   ![](assets/message-center_5.png)

Você também pode criar um novo perfil de teste ou usar um que já existe no menu **[!UICONTROL Test profiles]**. Para fazer isso:

1. Clique no logotipo **[!UICONTROL Adobe Campaign]**, no canto superior esquerdo, em seguida, selecione **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Test profiles]**.
1. Na **[!UICONTROL Event]** seção, selecione o evento que você acabou de criar. Neste exemplo, selecione &quot;Abandono de carrinho (EVTcartAbandonment)&quot;.
1. Especifique as informações para enviar no formato JSON na caixa de texto **[!UICONTROL Event data]**.

   ![](assets/message-center_3.png)

1. Salve as alterações.
1. Acesse a mensagem que você criou e selecione o perfil de teste atualizado.

**Tópicos relacionados:**

* [Gerenciamento de perfis de teste](../../audiences/using/managing-test-profiles.md)
* [Definição de públicos-alvo](../../audiences/using/creating-audiences.md)

### Envio de uma prova {#sending-proof}

Depois de criar um ou mais perfis de teste específicos e salvar seu mensagen transacional, você pode enviar uma prova para testá-lo.

![](assets/message-center_10.png)

As etapas para enviar uma prova estão detalhadas na seção [Envio de prova](../../sending/using/sending-proofs.md).

## Publicação de mensagem transacional {#publishing-a-transactional-message}

Depois de verificar a mensagem transacional, você pode publicá-la.

![](assets/message-center_12.png)

Agora, assim que o evento &quot;Abandono do carrinho&quot; for acionado, ele automaticamente solicitará uma mensagem contendo o título e sobrenome do recipient, o URL do carrinho, o último produto consultado ou uma lista de produtos, se você tiver definido uma lista de produtos, e o valor total do carrinho a ser enviado.

Para acessar os relatórios referentes à sua mensagem transacional, use o botão **[!UICONTROL Reports]**. Consulte [Relatórios](../../reporting/using/about-dynamic-reports.md).

![](assets/message-center_13.png)

### Suspensão de publicação de mensagem transacional {#suspending-a-transactional-message-publication}

Você pode suspender a publicação da mensagem transacional usando o botão **[!UICONTROL Pause]**, por exemplo, para modificar os dados contidos na mensagem. Portanto, os eventos não são mais processados, mas mantidos em fila no banco de dados do Adobe Campaign.

Os eventos em fila são mantidos durante um período definido na API REST (consulte a [documentação da API REST](../../api/using/get-started-apis.md)) ou no evento Acionadores, se você estiver usando o serviço principal Acionadores (consulte [Trabalho com Acionadores do Campaign e da Experience Cloud](../../integrating/using/about-adobe-experience-cloud-triggers.md)).

![](assets/message-center_pause.png)

Ao clicar em **[!UICONTROL Resume]**, todos os eventos em fila (desde que não tenham expirado) são processados. Eles agora contêm todas as modificações efetuadas durante a suspensão da publicação do modelo.

### Cancelamento de publicação de uma mensagem transacional {#unpublishing-a-transactional-message}

Clicar em **[!UICONTROL Unpublish]** permite cancelar a publicação da mensagem transacional, mas também a publicação do evento correspondente, que exclui da API REST o recurso correspondente ao evento criado anteriormente.

![](assets/message-center_unpublish-template.png)

Agora, mesmo que o evento seja acionado pelo seu site, as mensagens correspondentes não serão mais enviadas e não serão armazenadas no banco de dados.

>[!NOTE]
>
>Para publicar a mensagem novamente, você precisa voltar para a configuração do evento correspondente, publicá-la e, em seguida, publicar a mensagem. Para obter mais informações, consulte [Publicação de mensagem transacional](#publishing-a-transactional-message).

Se você cancelar a publicação de uma mensagem transacional pausada, talvez precise aguardar até 24 horas para poder publicá-la novamente. Isso permite que o fluxo de trabalho da **[!UICONTROL Database cleanup]** limpe todos os eventos enviados para a fila.

As etapas para pausar uma mensagem estão detalhadas na seção [Suspensão de publicação de mensagem transacional](#suspending-a-transactional-message-publication).

O fluxo de trabalho da **[!UICONTROL Database cleanup]**, que é executado todos os dias às 4h da manhã, pode ser acessado por meio de **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Workflows]**.

### Exclusão de uma mensagem transacional {#deleting-a-transactional-message}

Depois de cancelada a publicação de uma mensagem transacional, ou se uma mensagem transacional ainda não tiver sido publicada, você poderá excluí-la da lista de mensagens transacionais. Para fazer isso:

1. Clique no logotipo **[!UICONTROL Adobe Campaign]**, no canto superior esquerdo, em seguida selecione **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Transactional messages]**.
1. Passe o mouse sobre a mensagem de sua escolha.
1. Clique no botão **[!UICONTROL Delete element]**.

![](assets/message-center_delete-template.png)

No entanto, a exclusão de uma mensagem transacional só pode ser feita sob certas condições:

* Verifique se a mensagem transacional tem o status **[!UICONTROL Draft]**; caso contrário, você não poderá excluí-la. O status **[!UICONTROL Draft]** se aplica a uma mensagem que ainda não foi publicada ou cuja [publicação foi cancelada](#unpublishing-a-transactional-message) (e não [pausada](#suspending-a-transactional-message-publication)).

* **Mensagens transacionais**: a menos que outra mensagem transacional esteja vinculada ao evento correspondente, se a publicação da mensagem transacional for cancelada, a publicação da configuração do evento também precisará ser cancelada para excluir com êxito a mensagem transacional. Para obter mais informações, consulte [Cancelamento de publicação de evento](../../administration/using/configuring-transactional-messaging.md#unpublishing-an-event).

   >[!IMPORTANT]
   >
   >A exclusão de uma mensagem transacional que já enviou notificações também excluirá seus logs de rastreamento e envios.

* **Mensagens transacionais de um modelo de evento pronto para uso (mensagens transacionais internas)**: se uma mensagem transacional interna for a única associada ao evento interno correspondente, ela não poderá ser excluída. Primeiro, você precisa criar outra mensagem transacional duplicando-a, ou pelo menu **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Transactional message templates]**.

## Processo de nova tentativa de Mensagem transacional {#transactional-message-retry-process}

Uma mensagem transacional temporariamente não entregue está sujeita a tentativas automáticas que são executadas até que o delivery expire. Para mais informações sobre a duração do delivery, consulte [Parâmetros do período de validade](../../administration/using/configuring-email-channel.md#validity-period-parameters).

Quando uma mensagem transacional não é enviada, há dois sistemas de repetição:

* No nível de mensagens transacionais, uma mensagem transacional pode falhar antes de ser atribuída a um delivery de execução, ou seja, entre a recepção do evento e a preparação do delivery. Consulte [Processo de nova tentativa de processamento de eventos](#event-processing-retry-process).
* No nível do processo de envio, depois que o evento é atribuído a um delivery de execução, a mensagem transacional pode falhar devido a um erro temporário. Consulte [Processo de nova tentativa de envio de mensagens](#message-sending-retry-process).

### Processo de nova tentativa de processamento de eventos {#event-processing-retry-process}

Se o evento não puder ser atribuído a um delivery de execução, o processamento do evento será adiado. As tentativas são executadas até que sejam atribuídas a um novo delivery de execução.

>[!NOTE]
>
>Um evento adiado não é exibido nos logs de envio da mensagem transacional, pois ela ainda não foi atribuída a um delivery de execução.

Por exemplo, o evento não pôde ser atribuído a um delivery de execução porque seu conteúdo não estava correto. Houve um problema com direitos de acesso ou marca, um erro foi detectado ao aplicar regras de tipologia etc. Nesse caso, você pode pausar a mensagem, editá-la para corrigir o problema e publicá-la novamente. O sistema de nova tentativa a atribuirá a um novo delivery de execução.

### Processo de nova tentativa de envio de mensagem {#message-sending-retry-process}

Depois que o evento tiver sido atribuído a um delivery de execução, a mensagem transacional poderá falhar devido a um erro temporário, se a caixa de correio do recipient estiver cheia, por exemplo. Para obter mais informações, consulte [Tentativas após uma falha temporária de delivery](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

>[!NOTE]
>
>Quando um evento é atribuído a um delivery de execução, ele é exibido nos logs de envio desse delivery de execução e apenas no momento. The failed deliveries are displayed in the **[!UICONTROL Execution list]** tab of the transactional message sending logs.

### Repetir limitações do processo {#limitations}

**Envio de atualização de logs**

No processo de repetição, os logs de envio do novo delivery de execução não são atualizados imediatamente (a atualização é executada por meio de um fluxo de trabalho programado). Isso significa que a mensagem pode estar em status **[!UICONTROL Pending]** mesmo se o evento transacional tiver sido processado pelo novo delivery de execução.

**Delivery de execução com falha**

Não é possível interromper um delivery de execução. No entanto, se o delivery de execução atual falhar, um novo será criado assim que um novo evento for recebido, e todos os novos eventos serão processados por esse novo delivery de execução. Nenhum novo evento é processado pelo delivery de execução com falha.

Se alguns eventos já atribuídos a um delivery de execução tiverem sido adiados e esse delivery falhar, o sistema de nova tentativa não atribuirá os eventos adiados ao novo delivery de execução, ou seja, esses eventos serão perdidos.
