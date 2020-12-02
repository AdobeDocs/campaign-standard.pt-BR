---
solution: Campaign Standard
product: campaign
title: Mensagens transacionais de evento
description: Saiba como criar e publicar uma mensagem transacional de evento.
page-status-flag: never-activated
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
translation-type: tm+mt
source-git-commit: 9ad23468d3d1cf386d9558e6cd2344ea2316fc82
workflow-type: tm+mt
source-wordcount: '1582'
ht-degree: 69%

---


# Edição de um mensagen transacional {#editing-transactional-message}

Depois de criar e publicar um evento<!--(the cart abandonment example as explained in [this section](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle))-->, o mensagen transacional correspondente é criado automaticamente. As etapas para configurar e publicar o evento são apresentadas na seção [Configuração de um evento transacional](../../channels/using/configuring-transactional-event.md) e [Publicação de um evento transacional](../../channels/using/publishing-transactional-event.md).

As etapas para acessar, editar e personalizar esta mensagem estão descritas abaixo.

<!--Event transactional messages do not contain profile information, therefore they are not compatible with fatigue rules (even in the case of an enrichment with profiles). See [Fatigue rules](../../sending/using/fatigue-rules.md#choosing-the-channel).-->

Quando sua mensagem estiver pronta, ela poderá ser testada e publicada. Consulte [ciclo de vida do Mensagen transacional](../../channels/using/publishing-transactional-message.md).

## Acessar mensagens transacionais {#accessing-transactional-messages}

Para acessar o mensagen transacional que você criou:

1. Clique no logotipo **[!UICONTROL Adobe Campaign]**, no canto superior esquerdo.
1. Selecione **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Transactional messages]**.

   ![](assets/message-center_4.png)

1. Clique na mensagem de sua escolha para editá-la.

>[!IMPORTANT]
>
>Para acessar mensagens transacionais, você deve fazer parte do grupo de segurança **[!UICONTROL Administrators (all units)]**. Para obter mais informações, consulte [Gerenciamento de usuários](../../administration/using/users-management.md#functional-administrators).

## Personalização de uma mensagem transacional {#personalizing-a-transactional-message}

Para configurar a personalização em uma mensagem transacional, siga as etapas abaixo.

>[!NOTE]
>
>Esta seção descreve como personalizar um mensagen transacional **baseado em eventos**.  As etapas de configuração para criar um mensagen transacional baseado em eventos são apresentadas em [esta seção](../../channels/using/configuring-transactional-event.md#event-based-transactional-messages).
>
>As especificidades do mensagen transacional **baseado em perfis** estão detalhadas [abaixo](#profile-transactional-message-specificities).

Por exemplo, você deseja enviar uma notificação para os usuários do seu site que adicionaram produtos ao carrinho e saíram do site sem ter que fazer compras. Este exemplo é apresentado na seção [Princípio operacional de mensagens transacionais](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle).

1. Clique no bloco **[!UICONTROL Content]** para modificar o assunto e o conteúdo da mensagem. Neste exemplo, selecione qualquer modelo que contenha imagens e texto. Para obter mais informações sobre modelos de conteúdo de email, consulte [Criar emails usando modelos](../../designing/using/using-reusable-content.md#designing-templates).

   ![](assets/message-center_6.png)

1. Adicione um assunto e edite o conteúdo da mensagem de acordo com suas necessidades.

   >[!NOTE]
   >
   >O link para o carrinho abandonado é um link para um URL externo que redirecionará a pessoa para o carrinho. Esse parâmetro não é gerenciado no Adobe Campaign.

1. Neste exemplo, você deseja adicionar três campos definidos ao [criar o evento](../../channels/using/configuring-transactional-event.md): nome, último produto consultado, quantidade total do carrinho. Para fazer isso, [insira um campo de personalização ](../../designing/using/personalization.md#inserting-a-personalization-field) no conteúdo da mensagem.

1. Navegue até esses campos passando por **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**.

   ![](assets/message-center_7.png)

1. Para enriquecer o conteúdo da mensagem, adicione campos selecionando-os da tabela com a qual você vinculou seu evento. Neste exemplo, selecione o campo **[!UICONTROL Title (salutation)]** na tabela **[!UICONTROL Profile]** até **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**.

   ![](assets/message-center_7-enrichment.png)

1. Insira todos os campos necessários.

   ![](assets/message-center_8.png)

1. Pré-visualize a mensagem selecionando o perfil definido para esse evento.

   As etapas para visualizar uma mensagem são detalhadas na seção [Pré-visualização de mensagens](../../sending/using/previewing-messages.md).

   ![](assets/message-center_9.png)

   Você pode verificar se os campos de personalização correspondem às informações inseridas no perfil de teste. Para obter mais informações, consulte [Definição de um perfil de teste específico](../../channels/using/publishing-transactional-message.md#defining-specific-test-profile).

## Uso de listas de produtos em uma mensagem transacional {#using-product-listings-in-a-transactional-message}

É possível criar listas de produtos que façam referência a uma ou mais coleções de dados no conteúdo de um email transacional. Por exemplo, em um email de abandono de carrinho, você pode incluir uma lista de todos os produtos que estavam nos carrinhos dos usuários quando eles saíram do site, com uma imagem, o preço e um link para cada produto.

>[!IMPORTANT]
>
>As listas de produtos só estão disponíveis ao editar mensagens de email transacionais por meio da interface do [Designer de email](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-interface).

Para adicionar uma lista de produtos abandonados em uma mensagem transacional, siga as etapas abaixo.

Você também pode assistir [a este conjunto de vídeos](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/designing-content/product-listings-in-transactional-email.html?lang=en#configure-product-listings-in-transactional-emails) explicando as etapas necessárias para configurar as listas de produtos em um email transacional.

>[!NOTE]
>
>O Adobe Campaign não é compatível com listas de produtos aninhados, o que significa que não é possível incluir uma lista de produtos dentro de outra.

### Definição de uma lista de produtos {#defining-a-product-listing}

Antes de usar uma lista de produtos em uma mensagem transacional, é necessário definir no nível do evento a lista de produtos e os campos para cada produto da lista que você deseja exibir. Para obter mais informações, consulte [Definição de coleções de dados](../../channels/using/configuring-transactional-event.md#defining-data-collections).

1. Na mensagem transacional, clique no bloco **[!UICONTROL Content]** para modificar o conteúdo do email.
1. Arraste e solte um componente de estrutura no espaço de trabalho. Para obter mais informações, consulte [Definição da estrutura de e-mail](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

   Por exemplo, selecione um componente de estrutura de uma coluna e adicione um componente de texto, um componente de imagem e um componente de botão. Para obter mais informações, consulte [Uso de componentes de conteúdo](../../designing/using/designing-from-scratch.md#about-content-components).

1. Selecione o componente de estrutura que você acabou de criar e clique no ícone **[!UICONTROL Enable product listing]**, na barra de ferramentas contextual.

   ![](assets/message-center_loop_create.png)

   O componente de estrutura está realçado com um quadro laranja e as configurações da **[!UICONTROL Product listing]** são exibidas na paleta esquerda.

   ![](assets/message-center_loop_palette.png)

1. Selecione como os elementos da coleção serão exibidos:

   * **[!UICONTROL Row]**: horizontalmente, o que significa cada elemento em uma linha abaixo da outra.
   * **[!UICONTROL Column]**: verticalmente, o que significa cada elemento ao lado do outro na mesma linha.

   >[!NOTE]
   >
   >A opção **[!UICONTROL Column]** só está disponível ao usar um componente de estrutura de várias colunas ( **[!UICONTROL 2:2 column]**, **[!UICONTROL 3:3 column]** e **[!UICONTROL 4:4 column]** ). Ao editar a lista de produtos, preencha apenas a primeira coluna: as outras colunas não serão consideradas. Para obter mais informações sobre como selecionar componentes de estrutura, consulte [Definição da estrutura de email](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

1. Selecione a coleção de dados criada ao configurar o evento relacionado à mensagem transacional. Você pode encontrá-la no nó **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**.

   ![](assets/message-center_loop_selection.png)

   Para obter mais informações sobre como configurar o evento, consulte [Definição de coleções de dados](../../channels/using/configuring-transactional-event.md#defining-data-collections).

1. Use a lista suspensa **[!UICONTROL First item]** para selecionar qual elemento iniciará a lista exibida no email.

   Por exemplo, se você selecionar 2, o primeiro item da coleção não será exibido no email. A lista de produtos iniciará no segundo item.

1. Selecione o número máximo de itens que serão exibidos na lista.

   >[!NOTE]
   >
   >Se quiser que os elementos da lista sejam exibidos verticalmente ( **[!UICONTROL Column]** ), o número máximo de itens é limitado de acordo com o componente de estrutura selecionado (2, 3 ou 4 colunas). Para obter mais informações sobre como selecionar componentes de estrutura, consulte [Edição da estrutura do email](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

### Preenchimento da lista de produtos {#populating-the-product-listing}

Para exibir uma lista de produtos provenientes do evento vinculado ao email transacional, siga as etapas abaixo.

Para obter mais informações sobre como criar uma coleção e campos relacionados ao configurar o evento, consulte [Definição de coleções de dados](../../channels/using/configuring-transactional-event.md#defining-data-collections).

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

1. No painel Configurações, edite os estilos para a lista de produtos. Para obter mais informações, consulte [Gerenciar estilos de e-mail](../../designing/using/styles.md).
1. Pré-visualize o email usando um perfil de teste vinculado ao evento transacional relevante e para o qual você definiu os dados da coleta. Por exemplo, adicione as seguintes informações na seção **[!UICONTROL Event data]** para o perfil de teste que você deseja usar:

   ![](assets/message-center_loop_test-profile_payload.png)

   Para obter mais informações sobre como definir um perfil de teste em uma mensagem transacional, consulte [esta seção](../../channels/using/publishing-transactional-message.md#defining-specific-test-profile).

## Especificidades de mensagen transacional baseadas em perfis {#profile-transactional-message-specificities}

Você pode enviar mensagens transacionais com base em perfis de marketing do cliente, o que permite aproveitar todas as informações do perfil para personalizar o conteúdo da mensagem, usar o link de unsubscription e aplicar regras de tipologia de marketing, como [regras de fadiga](../../sending/using/fatigue-rules.md).

* Para obter mais informações sobre as diferenças entre mensagens transacionais baseados em eventos e perfis, consulte [esta seção](../../channels/using/getting-started-with-transactional-msg.md#transactional-message-types).

* As etapas de configuração para criar um mensagen transacional baseado em perfis estão detalhadas em [nesta seção](../../channels/using/configuring-transactional-event.md#profile-based-transactional-messages).

### Edição de um mensagen transacional de perfil {#editing-profile-transactional-message}

As etapas para criar, personalizar e publicar um mensagen transacional de perfil são, em geral, as mesmas que para um mensagen transacional de evento.

As diferenças são listadas abaixo.

1. [Acesse a mensagem transacional criada para editá-la.](#accessing-transactional-messages)
1. Na mensagem transacional, clique na seção **[!UICONTROL Content]**. Além dos modelos de e-mail transacionais, você também pode escolher qualquer modelo de e-mail direcionado ao recurso **[!UICONTROL Profile]**.

   ![](assets/message-center_marketing_templates.png)

1. Selecione o template de email padrão. Semelhante a todos os emails de marketing, ele inclui um **link de unsubscription**.

   ![](assets/message-center_marketing_perso_unsubscription.png)

   Para obter mais informações sobre modelos, consulte [esta seção](../../designing/using/using-reusable-content.md#content-templates).

1. Além disso, ao contrário das configurações baseadas em eventos em tempo real, você tem **acesso direto a todas as informações do perfil** para personalizar sua mensagem. Você pode adicionar [campos de personalização](../../designing/using/personalization.md#inserting-a-personalization-field) como faria com qualquer outro email de marketing padrão.

1. Salve as alterações antes de publicar a mensagem. Para obter mais informações, consulte [Publicação de mensagem transacional](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message).

### Monitoramento de um delivery de mensagem transacional de perfil {#monitoring-a-profile-transactional-message-delivery}

Quando a mensagem for publicada e a integração do site estiver concluída, você poderá monitorar o delivery.

1. Para exibir o log de delivery da mensagem, clique no ícone na parte inferior direita do bloco **[!UICONTROL Deployment]**.

   Para obter mais informações sobre como acessar os registros, consulte [Monitorando um delivery](../../sending/using/monitoring-a-delivery.md).

1. Selecione a guia **[!UICONTROL Sending logs]**. Na coluna **[!UICONTROL Status]**, **[!UICONTROL Sent]** indica que um perfil foi aceito.

   ![](assets/message-center_marketing_sending_logs.png)

1. Selecione a guia **[!UICONTROL Exclusions logs]** para visualização de recipient que foram excluídos do público alvo de mensagens, como endereços em lista de bloqueios.

   ![](assets/message-center_marketing_exclusion_logs.png)

Para os perfis recusados, a regra de tipologia **[!UICONTROL Address on denylist]** exclui o recipient correspondente.

Essa regra faz parte de uma tipologia específica aplicável a todas as mensagens transacionais baseadas na tabela **[!UICONTROL Profile]**.

![](assets/message-center_marketing_typology.png)

**Tópicos relacionados**:

* Integrar acionamento de evento(../../channels/using/getting-started-with-transactional-msg.md#integration-evento-trigger)
* [Sobre tipologias e regras de tipologia](../../sending/using/about-typology-rules.md)
