---
title: Mensagens transacionais de evento
description: Saiba como criar e publicar um mensagen transacional de evento.
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
source-git-commit: efb1f14e0094e200d186423f98bfad65d25cfab2

---


# Mensagens transacionais de evento{#event-transactional-messages}

Você pode enviar mensagens transacionais de eventos direcionados a um evento. Esse tipo de mensagen transacional não contém informações de perfil: o público alvo do delivery é definido pelos dados contidos no próprio evento.

Depois de criar e publicar um evento (o abandono do carrinho como explicado em [esta seção](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle)), o mensagen transacional correspondente é criado automaticamente.

As etapas de configuração são apresentadas na seção [Configuração de um evento para enviar um mensagen transacional](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) .

Para que o evento acione o envio de um mensagen transacional, é necessário personalizar a mensagem, testá-la e publicá-la.

>[!NOTE]
>
>Para acessar mensagens transacionais, você deve fazer parte do grupo de **[!UICONTROL Administrators (all units)]** segurança.
>
>Os mensagens transacionais Eventos não contêm informações sobre perfis, portanto, não são compatíveis com as regras de fadiga (mesmo no caso de um enriquecimento com perfis). Consulte Regras de [fadiga](../../sending/using/fatigue-rules.md#choosing-the-channel).

## Definição de um perfil de teste em um mensagen transacional {#defining-a-test-profile-in-a-transactional-message}

Defina um perfil de teste adaptado, que permitirá que você pré-visualização sua mensagem e envie uma prova para verificá-la.

### Criação de um perfil de teste dentro do mensagen transacional {#creating-a-test-profile-within-the-transactional-----------message}

1. Para acessar a mensagem que você criou, clique no **[!UICONTROL Adobe Campaign]** logotipo, no canto superior esquerdo, em seguida, selecione **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Transactional messages]**.

   ![](assets/message-center_4.png)

1. Crie um perfil de teste que será vinculado ao seu evento.

   ![](assets/message-center_test-profile.png)

1. Especifique as informações para enviar no formato JSON na **[!UICONTROL Event data used for personalization]** seção. Esse é o conteúdo que será usado ao visualizar a mensagem e quando o perfil de teste receber a prova.

   ![](assets/message-center_event-data.png)

   >[!NOTE]
   >
   >Você também pode inserir as informações relacionadas à tabela do perfil. Consulte [Enriquecendo o conteúdo](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)do mensagen transacional.

1. Após a criação, o perfil de teste será pré-especificado no mensagen transacional. Clique no **[!UICONTROL Test profiles]** bloco da mensagem para verificar o público alvo de sua prova.

   ![](assets/message-center_5.png)

### Criação de um perfil de teste fora do mensagen transacional {#creating-a-test-profile-outside-the-transactional-----------message}

Você também pode criar um novo perfil de teste ou usar um que já existe no **[!UICONTROL Test profiles]** menu.

1. Clique no **[!UICONTROL Adobe Campaign]** logotipo, no canto superior esquerdo, em seguida selecione **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Test profiles]**.
1. Na **[!UICONTROL Event]** seção da página do perfil de teste que você escolheu, selecione o evento que acabou de criar. Neste exemplo, selecione &quot;Cancelamento do carrinho (EVTcartAbandonment)&quot;.
1. Especifique as informações para enviar no formato JSON na caixa de **[!UICONTROL Event data]** texto.

   ![](assets/message-center_3.png)

1. Salve as alterações.

Agora você pode acessar a mensagem que criou e selecionar o perfil de teste atualizado.

**Tópicos relacionados:**

* [Gerenciamento de perfis de teste](../../audiences/using/managing-test-profiles.md)
* [Definindo audiências](../../audiences/using/creating-audiences.md)

## Personalização de um mensagen transacional {#personalizing-a-transactional-message}

Para configurar a personalização em um mensagen transacional, siga as etapas abaixo:

1. Clique no **[!UICONTROL Content]** bloco para modificar o assunto e o conteúdo de sua mensagem. Neste exemplo, selecione qualquer modelo que contenha imagens e texto. Para obter mais informações sobre modelos de conteúdo de email, consulte [Design usando modelos](../../designing/using/using-reusable-content.md#designing-templates).

   ![](assets/message-center_6.png)

1. Adicione um assunto e edite o conteúdo da sua mensagem de acordo com suas necessidades.

   >[OBSERVAÇÃO]
   >
   >O link para o carrinho abandonado é um link para um URL externo que redirecionará a pessoa para o carrinho. Esse parâmetro não é gerenciado no Adobe Campaign.

1. Neste exemplo, você deseja adicionar três campos definidos ao [criar o evento](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message): nome, último produto consultado, quantidade total do carrinho. Para fazer isso, [insira um campo](../../designing/using/personalization.md#inserting-a-personalization-field) de personalização no conteúdo da mensagem.

1. Navegue até esses campos em **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**.

   ![](assets/message-center_7.png)

1. Para enriquecer o conteúdo de sua mensagem, adicione campos selecionando-os na tabela com a qual você vinculou seu evento. Em nosso exemplo, selecione o **[!UICONTROL Title (salutation)]** campo na **[!UICONTROL Profile]** tabela em **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**.

   ![](assets/message-center_7-enrichment.png)

1. Insira todos os campos necessários.

   ![](assets/message-center_8.png)

1. Pré-visualização sua mensagem selecionando o perfil definido para esse evento.

   As etapas para visualizar uma mensagem são detalhadas na seção [Visualizar mensagens](../../sending/using/previewing-messages.md) .

   ![](assets/message-center_9.png)

   Você pode verificar se os campos de personalização correspondem às informações inseridas no perfil de teste. Para obter mais informações, consulte [Definição de um perfil de teste em um mensagen transacional](#defining-a-test-profile-in-a-transactional-message).

## Utilização das listas de produtos num mensagen transacional {#using-product-listings-in-a-transactional-message}

É possível criar listas de produtos que façam referência a uma ou mais coleções de dados no conteúdo de um email transacional. Por exemplo, em um email de abandono de carrinho, você pode incluir uma lista de todos os produtos que estavam nos carrinhos dos usuários quando eles saíram do site, com uma imagem, o preço e um link para cada produto.

>[!IMPORTANT]
>
>As listas de produtos só estão disponíveis ao editar mensagens de email transacionais por meio da interface do [Email Designer](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-interface) .

Para adicionar uma lista de produtos abandonados em um mensagen transacional, siga as etapas abaixo.

Você também pode assistir a um conjunto de vídeos explicando as etapas necessárias para configurar as listas de produtos em um email transacional. For more on this, see [this page](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/product-listings-in-transactional-email.html).

>[!NOTE]
>
>O Adobe Campaign não suporta listagens de produtos aninhados, o que significa que não é possível incluir uma listagem de produtos dentro de outra.

### Definição de uma lista de produtos {#defining-a-product-listing}

Antes de poder usar uma listagem de produtos em um mensagen transacional, é necessário definir no nível do evento a lista de produtos e os campos para cada produto da lista que você deseja exibir. Para obter mais informações, consulte [Definição de coleções](../../administration/using/configuring-transactional-messaging.md#defining-data-collections)de dados.

1. No mensagen transacional, clique no **[!UICONTROL Content]** bloco para modificar o conteúdo do email.
1. Arraste e solte um componente de estrutura no espaço de trabalho. Para obter mais informações, consulte [Edição da estrutura](../../designing/using/designing-from-scratch.md#defining-the-email-structure)de email.

   Por exemplo, selecione um componente de estrutura de uma coluna e adicione um componente de texto, um componente de imagem e um componente de botão. Para obter mais informações, consulte [Adicionar fragmentos e componentes](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

1. Selecione o componente de estrutura que você acabou de criar e clique no **[!UICONTROL Enable product listing]** ícone na barra de ferramentas contextual.

   ![](assets/message-center_loop_create.png)

   O componente de estrutura é realçado com um quadro laranja e as **[!UICONTROL Product listing]** configurações são exibidas na paleta esquerda.

   ![](assets/message-center_loop_palette.png)

1. Selecione como os elementos da coleção serão exibidos:

   * **[!UICONTROL Row]**: horizontalmente, o que significa cada elemento em uma linha abaixo da outra.
   * **[!UICONTROL Column]**: verticalmente, o que significa cada elemento próximo ao outro na mesma linha.
   >[!NOTE]
   >
   >A **[!UICONTROL Column]** opção só está disponível ao usar um componente de estrutura de várias colunas ( **[!UICONTROL 2:2 column]**, **[!UICONTROL 3:3 column]** e **[!UICONTROL 4:4 column]** ). Ao editar a lista de produtos, preencha apenas a primeira coluna: as outras colunas não serão tomadas em consideração. Para obter mais informações sobre como selecionar componentes de estrutura, consulte [Editar a estrutura](../../designing/using/designing-from-scratch.md#defining-the-email-structure)de email.

1. Selecione a coleção de dados criada ao configurar o evento relacionado ao mensagen transacional. Você pode encontrá-lo no nó **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]** .

   ![](assets/message-center_loop_selection.png)

   Para obter mais informações sobre como configurar o evento, consulte [Definição de coleções](../../administration/using/configuring-transactional-messaging.md#defining-data-collections)de dados.

1. Use a lista **[!UICONTROL First item]** suspensa para selecionar qual elemento irá start a lista exibida no email.

   Por exemplo, se você selecionar 2, o primeiro item da coleção não será exibido no email. A lista de produtos será start no segundo item.

1. Selecione o número máximo de itens a serem exibidos na lista.

   >[!NOTE]
   >
   >Se quiser que os elementos da sua lista sejam exibidos verticalmente ( **[!UICONTROL Column]** ), o número máximo de itens é limitado de acordo com o componente de estrutura selecionado (2, 3 ou 4 colunas). Para obter mais informações sobre como selecionar componentes de estrutura, consulte [Editar a estrutura](../../designing/using/designing-from-scratch.md#defining-the-email-structure)de email.

### Preenchimento da lista de produtos {#populating-the-product-listing}

Para exibir uma lista de produtos provenientes do evento vinculado ao email transacional, siga as etapas abaixo.

Para obter mais informações sobre como criar uma coleção e campos relacionados ao configurar o evento, consulte [Definição de coleções](../../administration/using/configuring-transactional-messaging.md#defining-data-collections)de dados.

1. Selecione o componente de imagem inserido, selecione **[!UICONTROL Enable personalization]** e clique no lápis no painel Configurações.

   ![](assets/message-center_loop_image.png)

1. Selecione **[!UICONTROL Add personalization field]** na **[!UICONTROL Image source URL]** janela que será aberta.

   No nó **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]** , abra o nó correspondente à coleção que você criou (aqui **[!UICONTROL Product list]** ) e selecione o campo de imagem definido (aqui **[!UICONTROL Product image]** ). Clique em **[!UICONTROL Save]**.

   ![](assets/message-center_loop_product-image.png)

   O campo de personalização selecionado agora é exibido no painel Configurações.

1. Na posição desejada, selecione **[!UICONTROL Insert personalization field]** na barra de ferramentas contextual.

   ![](assets/message-center_loop_product.png)

1. No nó **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]** , abra o nó correspondente à coleção que você criou (aqui **[!UICONTROL Product list]** ) e selecione o campo que você criou (aqui **[!UICONTROL Product name]** ). Clique em **[!UICONTROL Confirm]**.

   ![](assets/message-center_loop_product_node.png)

   O campo de personalização selecionado agora é exibido na posição desejada no conteúdo de email.

1. Procede da mesma forma para inserir o preço.
1. Selecione algum texto e selecione **[!UICONTROL Insert link]** na barra de ferramentas contextual.

   ![](assets/message-center_loop_link_insert.png)

1. Selecione **[!UICONTROL Add personalization field]** na **[!UICONTROL Insert link]** janela que será aberta.

   No nó **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]** , abra o nó correspondente à coleção que você criou (aqui **[!UICONTROL Product list]** ) e selecione o campo URL que você criou (aqui **[!UICONTROL Product URL]** ). Clique em **[!UICONTROL Save]**.

   >[!IMPORTANT]
   >
   >Por motivos de segurança, insira o campo de personalização dentro de um link que comece com um nome de domínio estático apropriado.

   ![](assets/message-center_loop_link_select.png)

   O campo de personalização selecionado agora é exibido no painel Configurações.

1. Selecione o componente de estrutura no qual a lista de produtos é aplicada e selecione **[!UICONTROL Show fallback]** para definir um conteúdo padrão.

   ![](assets/message-center_loop_fallback_show.png)

1. Arraste um ou mais componentes de conteúdo e edite-os conforme necessário.

   ![](assets/message-center_loop_fallback.png)

   O conteúdo de fallback será exibido se a coleção estiver vazia quando o evento for acionado, por exemplo, se um cliente não tiver nada em seu carrinho.

1. No painel Configurações, edite os estilos para a lista de produtos. Para obter mais informações, consulte [Edição de estilos](../../designing/using/styles.md)de email.
1. Pré-visualização o email usando um perfil de teste vinculado ao evento transacional relevante e para o qual você definiu os dados da coleta. Por exemplo, adicione as seguintes informações na **[!UICONTROL Event data]** seção do perfil de teste que você deseja usar:

   ![](assets/message-center_loop_test-profile_payload.png)

   Para obter mais informações sobre como definir um perfil de teste em um mensagen transacional, consulte [esta seção](#defining-a-test-profile-in-a-transactional-message).

## Teste de um mensagen transacional {#testing-a-transactional-message}

Depois de salvar seu mensagen transacional, você pode enviar uma prova para testá-lo.

![](assets/message-center_10.png)

As etapas para enviar uma prova são detalhadas na seção [Envio de uma prova](../../sending/using/sending-proofs.md) .

## Publicar um mensagen transacional {#publishing-a-transactional-message}

Depois de verificar seu mensagen transacional, você pode publicá-lo.

![](assets/message-center_12.png)

Agora, assim que o evento de &quot;abandono do carrinho&quot; for acionado, ele automaticamente solicitará uma mensagem contendo o título e sobrenome do recipient, o URL do carrinho, o último produto consultado ou uma lista de produtos, se você tiver definido uma lista de produtos, e o valor total do carrinho a ser enviado.

Para acessar os relatórios referentes ao seu mensagen transacional, use o **[!UICONTROL Reports]** botão. Consulte [Relatórios](../../reporting/using/about-dynamic-reports.md).

![](assets/message-center_13.png)

## Suspensão de uma publicação de mensagen transacional {#suspending-a-transactional-message-publication}

Você pode suspender a publicação de seu mensagen transacional usando o **[!UICONTROL Pause]** botão, por exemplo, para modificar os dados contidos na mensagem. Portanto, os eventos não são mais processados, mas mantidos em fila no banco de dados do Adobe Campaign.

Os eventos em fila são mantidos durante um período definido na REST API (consulte a documentação [REST API) ou no evento trigger se você estiver usando o serviço principal Triggers (consulte](../../api/using/about-campaign-standard-apis.md)Trabalhar com Campanhas e Experience Cloud Triggers [](../../integrating/using/about-adobe-experience-cloud-triggers.md)).

![](assets/message-center_pause.png)

Ao clicar **[!UICONTROL Resume]**, todos os eventos em fila (desde que não tenham expirado) são processados. Contêm agora todas as modificações efetuadas durante a suspensão da publicação do modelo.

## Cancelamento de publicação de um mensagen transacional {#unpublishing-a-transactional-message}

Clicar **[!UICONTROL Unpublish]** permite cancelar a publicação do mensagen transacional, mas também a publicação do evento correspondente, que exclui da REST API o recurso correspondente ao evento criado anteriormente.

![](assets/message-center_unpublish-template.png)

Agora, mesmo se o evento for acionado pelo seu site, as mensagens correspondentes não serão mais enviadas e não serão armazenadas no banco de dados.

>[!NOTE]
>
>Para publicar a mensagem novamente, você precisa voltar para a configuração de evento correspondente, publicá-la e, em seguida, publicar a mensagem. Para obter mais informações, consulte [Publicação de um mensagen transacional](#publishing-a-transactional-message).

Se você cancelar a publicação de um mensagen transacional pausado, talvez precise aguardar até 24 horas para poder publicá-lo novamente. Isso permite que o **[!UICONTROL Database cleanup]** fluxo de trabalho limpe todos os eventos enviados para a fila.

As etapas para pausar uma mensagem são detalhadas na seção [Suspender uma publicação](#suspending-a-transactional-message-publication) de mensagen transacional.

O **[!UICONTROL Database cleanup]** fluxo de trabalho, que é executado todos os dias às 4h da manhã, pode ser acessado por meio de **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Workflows]**.

## Excluindo um mensagen transacional {#deleting-a-transactional-message}

Uma vez que um mensagen transacional não tenha sido publicado, ou se um mensagen transacional ainda não tiver sido publicado, você poderá excluí-lo da lista do mensagen transacional. Para fazer isso:

1. Clique no **[!UICONTROL Adobe Campaign]** logotipo, no canto superior esquerdo, em seguida selecione **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Transactional messages]**.
1. Passe o mouse sobre a mensagem de sua escolha.
1. Clique no botão **[!UICONTROL Delete element]**.

![](assets/message-center_delete-template.png)

No entanto, a exclusão de um mensagen transacional só pode ser feita sob certas condições:

* Certifique-se de que o mensagen transacional tenha o **[!UICONTROL Draft]** status; caso contrário, você não poderá excluí-lo. O **[!UICONTROL Draft]** status se aplica a uma mensagem que ainda não foi publicada ou que foi [não publicada](#unpublishing-a-transactional-message) (e não [pausada](#suspending-a-transactional-message-publication)).

* **Mensagens transacionais**: A menos que outro mensagen transacional esteja vinculado ao evento correspondente, se o mensagen transacional não for publicado, a configuração do evento também precisará ser despublicada para excluir com êxito seu mensagen transacional. Para obter mais informações, consulte [Desfazer publicação de um evento](../../administration/using/configuring-transactional-messaging.md#unpublishing-an-event).

   >[!IMPORTANT]
   >
   >A exclusão de um mensagen transacional que já enviou notificações também excluirá seus logs de rastreamento e envios.

* **Mensagens transacionais de um modelo de evento predefinido (mensagens transacionais internos)**: Se um mensagen transacional interno for o único associado ao evento interno correspondente, ele não poderá ser excluído. Primeiro, você deve criar outro mensagen transacional duplicando-o ou pelo menu **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Transactional message templates]** .

## Processo de nova tentativa de Mensagen transacional {#transactional-message-retry-process}

Um mensagen transacional temporariamente não entregue está sujeito a tentativas automáticas que são executadas até que o delivery expire. Para obter mais informações sobre a duração do delivery, consulte Parâmetros [do período de](../../administration/using/configuring-email-channel.md#validity-period-parameters)validade.

Quando um mensagen transacional não é enviado, há dois sistemas de repetição:

* No nível de mensagens transacionais, um mensagen transacional pode falhar antes de ser atribuído a um delivery de execução, o que significa entre a recepção do evento e a preparação do delivery. Consulte Processo [de nova tentativa de processamento de](#event-processing-retry-process)Eventos.
* No nível do processo de envio, depois que o evento é atribuído a um delivery de execução, o mensagen transacional pode falhar devido a um erro temporário. Consulte Processo [de nova tentativa de envio de](#message-sending-retry-process)mensagens.

### processo de nova tentativa de processamento de Eventos {#event-processing-retry-process}

Se o evento não puder ser atribuído a um delivery de execução, o processamento do evento será adiado. As Tentativas são executadas até que sejam atribuídas a um novo delivery de execução.

>[!NOTE]
>
>Um evento adiado não é exibido nos registros de envio do mensagen transacional, pois ele ainda não foi atribuído a um delivery de execução.

Por exemplo, o evento não pôde ser atribuído a um delivery de execução porque seu conteúdo não estava correto, havia um problema com direitos de acesso ou marca, um erro foi detectado ao aplicar o regra de tipologia etc. Nesse caso, você pode pausar a mensagem, editá-la para corrigir o problema e publicá-la novamente. O sistema de nova tentativa o atribuirá a um novo delivery de execução.

### Processo de nova tentativa de envio de mensagem {#message-sending-retry-process}

Depois que o evento tiver sido atribuído a um delivery de execução, ele poderá falhar devido a um erro temporário, se a caixa de correio do recipient estiver cheia, por exemplo. For more on this, see [Retries after a delivery temporary failure](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

>[!NOTE]
>
>Quando um evento é atribuído a um delivery de execução, ele é exibido nos registros de envio desse delivery de execução e apenas no momento. Os delivery com falha são exibidos na guia **[!UICONTROL Execution list]** do mensagen transacional.

### Limitações {#limitations}

**Enviando atualização de logs**

No processo de repetição, os logs de envio do novo delivery de execução não são atualizados imediatamente (a atualização é executada por meio de um fluxo de trabalho programado). Isso significa que a mensagem pode estar em **[!UICONTROL Pending]** status mesmo se o evento transacional tiver sido processado pelo novo delivery de execução.

**delivery de execução com falha**

Não é possível parar um delivery de execução. No entanto, se o delivery de execução atual falhar, um novo será criado assim que um novo evento for recebido e todos os novos eventos serão processados por esse novo delivery de execução. Nenhum novo evento é processado pelo delivery de execução com falha.

Se alguns eventos já atribuídos a um delivery de execução tiverem sido adiados e esse delivery falhar, o sistema de nova tentativa não atribuirá os eventos adiados ao novo delivery de execução, o que significa que esses eventos serão perdidos.
