---
title: Confirmando a assinatura de um serviço
seo-title: Confirmando a assinatura de um serviço
description: Confirmando a assinatura de um serviço
seo-description: Siga estas etapas para configurar uma mensagem de confirmação para os perfis que se inscrevem em um serviço no Adobe Campaign.
page-status-flag: nunca ativado
uuid: 23e6c4c2-e2c7-472f-b616-36a95225ac1d
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: referência
topic-tags: gerenciar assinaturas
discoiquuid: 1a24504e-7f9d-4297-b39e-c5f085b0f388
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 51d80fc9c683e39b9d08ba7d36b76b71a9dd1e8c

---


# Confirmando a assinatura de um serviço{#confirming-subscription-to-a-service}

## Sobre o envio de confirmação de assinatura {#sending-subscription-confirmation}

Esta seção descreve como enviar um email de confirmação personalizado automático para os perfis que se inscrevem em um serviço específico.

Quando quiser enviar uma mensagem de confirmação de uma assinatura (ou cancelar a assinatura) para um serviço, você pode usar a mensagem padrão ou uma mensagem personalizada. As etapas para selecionar uma mensagem de confirmação são apresentadas na seção [Criação de um serviço](../../audiences/using/creating-a-service.md) .

Se você optar por usar a mensagem padrão, poderá editar seu conteúdo com as seguintes limitações:
* Você só pode personalizar o conteúdo da mensagem com campos limitados do contexto do evento.
* Essa mensagem será a mesma para todos os serviços que usam o modo padrão.

Para enviar um email de confirmação específico para um determinado serviço, é possível criar uma mensagem personalizada, na qual você também poderá aproveitar os campos de personalização de outros recursos. Para fazer isso, você deve criar e configurar uma mensagem transacional. Esta mensagem pode ser referenciada :
* Do próprio serviço. Para obter mais informações, consulte [Configurar mensagem de confirmação de um serviço](#configuring-confirmation-message-from-service).
* De uma página inicial de assinatura. Para obter mais informações, consulte [Configuração da mensagem de confirmação de uma página](#configuring-confirmation-message-from-landing-page)de aterrissagem.

## Configurar mensagem de confirmação de um serviço {#configuring-confirmation-message-from-service}

Por exemplo, você deseja enviar automaticamente uma mensagem de confirmação para os visitantes do seu site quando eles assinarem o boletim da sua marca.

Você precisa configurar um email transacional e fazer referência a essa mensagem do serviço desejado (neste caso, a assinatura do boletim da sua marca). Para enriquecer a mensagem transacional com as informações do serviço, é possível definir uma reconciliação ao criar o evento.

Ao configurá-la a partir do serviço, a mensagem de confirmação transacional será enviada somente na primeira vez que cada visitante se inscrever nesse serviço. Se um perfil já estiver inscrito, nenhuma mensagem de confirmação será enviada novamente para esse perfil.

### Etapa 1: Criar o email de confirmação {#step-1--create-the-confirmation-email-1}

Um e-mail de confirmação será enviado automaticamente para cada perfil que se inscreva no boletim informativo (por meio de uma página de aterrissagem ou qualquer outro meio). A assinatura é considerada um evento e o email é uma mensagem [](../../channels/using/about-transactional-messaging.md) transacional que direcionará cada perfil que se inscreve no serviço.

As etapas para criar o email de confirmação estão descritas abaixo. Como a mensagem transacional será referenciada no serviço, é necessário criá-la primeiro.

#### Criar o evento {#create-the-event-1}

O email de confirmação é uma mensagem transacional, pois reage a um evento: a assinatura de um serviço. Esta mensagem será enviada para confirmar a assinatura do seu boletim informativo.

1. Crie um evento no menu **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]** &gt; **[!UICONTROL Event configuration]** , acessível pelo logotipo do Adobe Campaign.
1. Insira um rótulo, selecione uma dimensão de definição de metas e clique em **[!UICONTROL Create]**.

   As etapas de configuração são apresentadas na seção [Configuração de mensagens](../../administration/using/configuring-transactional-messaging.md) transacionais.

1. Na **[!UICONTROL Fields]** seção, clique **[!UICONTROL Create element]** e adicione **[!UICONTROL publicLabel]** à estrutura de dados para ativar a reconciliação.

   ![](assets/confirmation_publicLabel-field.png)

   >[!NOTE]
   >
   >O **[!UICONTROL publicLabel]** campo é obrigatório. Se você não adicioná-lo à estrutura de dados do evento, o Adobe Campaign não poderá executar a reconciliação com o serviço. Ao assinar um serviço, esse campo será preenchido com o nome **[!UICONTROL Service label]** do serviço correspondente.

1. Na **[!UICONTROL Enrichment]** seção, clique **[!UICONTROL Create element]** e selecione o recurso de **[!UICONTROL Service]** destino.

   ![](assets/confirmation_enrichment-service.png)

1. Na **[!UICONTROL Join definition]** seção, mapeie o **[!UICONTROL publicLabel]** campo do **[!UICONTROL Service]** recurso com o **[!UICONTROL publicLabel]** campo da configuração do evento.

   ![](assets/confirmation_publicLabel-join.png)

   >[!NOTE]
   >
   >Isso permitirá que você use campos de personalização do **[!UICONTROL Service]** recurso na mensagem transacional.

1. Salve a configuração do evento e clique em **[!UICONTROL Publish]** para publicar o evento.

O evento está pronto. Agora você pode criar a mensagem de email transacional.

#### Projetar a mensagem de confirmação {#design-the-confirmation-message-1}

O email de confirmação é uma mensagem transacional com base no evento que você acabou de publicar.

1. No logotipo do Adobe Campaign, selecione **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]** e clique em **[!UICONTROL Transactional messages]**.
1. Selecione o email transacional correspondente ao evento que você acabou de publicar.

1. Clique na **[!UICONTROL Content]** seção e selecione um modelo de email. Para obter mais informações sobre como editar um conteúdo de mensagem transacional, consulte Mensagens [transacionais de](../../channels/using/event-transactional-messages.md)evento.
1. Como você tem acesso direto a todos os campos do **[!UICONTROL Service]** recurso, é possível selecionar qualquer campo do nó **[!UICONTROL Context]** &gt; **[!UICONTROL Real-time event (rtEvent)]** &gt; **[!UICONTROL Event context (ctx)]** &gt;**[!UICONTROL Service]** para personalizar o conteúdo.

   ![](assets/confirmation_personalization-service.png)

   Para obter mais informações sobre como personalizar uma mensagem transacional, consulte [esta seção](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message).

1. Visualize sua mensagem usando um perfil de teste. Para obter mais informações, consulte [Definição de um perfil de teste em uma mensagem](../../channels/using/event-transactional-messages.md#defining-a-test-profile-in-a-transactional-message)transacional.

1. Clique em **[!UICONTROL Save & close]** para salvar seu conteúdo.
1. Publique a mensagem transacional. Consulte [Publicar uma mensagem](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message)transacional.

### Etapa 2: Criar e configurar o serviço {#step-2--create-and-configure-the-service-1}

1. No menu avançado, **Perfis e públicos** &gt; **Serviços** por meio do logotipo do Adobe Campaign, crie um serviço.
1. Vá para a **[!UICONTROL Service properties]** seção, acessada pelo ![](assets/edit_darkgrey-24px.png) botão no painel de serviço.
1. Fill in the **[!UICONTROL Service label]** field.

   ![](assets/confirmation_service-label.png)

   >[!NOTE]
   >
   >É necessário preencher esse campo para permitir a reconciliação com a mensagem transacional.

1. Na **[!UICONTROL Confirmation messages]** seção, selecione **[!UICONTROL Custom message]**: este modo permite que você faça referência a uma mensagem de confirmação específica para perfis que se inscrevem no seu serviço.
1. Selecione o **[!UICONTROL Custom subscription event configuration]** associado à mensagem transacional que você criou.

   ![](assets/confirmation_service-confirmation-message.png)

1. Click **[!UICONTROL Confirm]** and save the service.

Agora, cada vez que um perfil se inscreve nesse serviço, ele recebe a mensagem transacional que você definiu, com campos personalizados mapeados para o serviço selecionado.

>[!NOTE]
>
>Uma mensagem será enviada somente na primeira vez que o usuário se inscrever.

## Configurar mensagem de confirmação de uma página de aterrissagem {#configuring-confirmation-message-from-landing-page}

Você também pode consultar a mensagem de confirmação de uma página inicial de assinatura usando a **[!UICONTROL Start sending messages]** opção da **[!UICONTROL Job]** seção da página inicial.

Ao referenciar a mensagem de confirmação da página de aterrissagem, uma mensagem será enviada toda vez que a página de aterrissagem for enviada (mesmo se o perfil já estiver inscrito).

### Etapa 1: Criar o email de confirmação {#step-1--create-the-confirmation-email-2}

Um e-mail de confirmação será enviado automaticamente para cada perfil que se inscreva no boletim informativo por meio de uma página de aterrissagem. A assinatura é considerada um evento e o email é uma mensagem [](../../channels/using/about-transactional-messaging.md) transacional que direcionará cada perfil que se inscreve no serviço.

As etapas para criar esses elementos estão descritas abaixo. Como a mensagem transacional será referenciada na página inicial, é necessário criá-la primeiro.

#### Criar o evento {#create-the-event-2}

O email de confirmação é uma mensagem [](../../channels/using/about-transactional-messaging.md) transacional, pois reage a um evento: a assinatura de um serviço. Esta mensagem será enviada para confirmar a assinatura do seu boletim informativo.

1. Crie um evento no menu **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]** &gt; **[!UICONTROL Event configuration]** , acessível pelo logotipo do Adobe Campaign.
1. Insira um rótulo, selecione uma dimensão de definição de metas e clique em **[!UICONTROL Create]**.

   As etapas de configuração são apresentadas na seção [Configuração de mensagens](../../administration/using/configuring-transactional-messaging.md) transacionais.

1. Na **[!UICONTROL Fields]** seção, clique **[!UICONTROL Create element]** e adicione **[!UICONTROL serviceName]** à estrutura de dados para ativar a reconciliação.

   ![](assets/confirmation_serviceName-field.png)

   >[!NOTE]
   >
   >O **[!UICONTROL serviceName]** campo é obrigatório. Se você não adicioná-la à estrutura de dados do evento, o Adobe Campaign não poderá executar a reconciliação com o serviço inscrito.

1. Na **[!UICONTROL Enrichment]** seção, clique **[!UICONTROL Create element]** e selecione o recurso de **[!UICONTROL Service]** destino.
1. Na **[!UICONTROL Join definition]** seção, mapeie o **[!UICONTROL serviceName]** campo do **[!UICONTROL Service]** recurso com o **[!UICONTROL name]** campo da configuração do evento.

   ![](assets/confirmation_serviceName-join.png)

   >[!NOTE]
   >
   >Isso permitirá que você use campos de personalização do [!UICONTROL Service] recurso na mensagem transacional.

#### Projetar a mensagem de confirmação {#design-the-confirmation-message-2}

As etapas para projetar a mensagem transacional são apresentadas nesta [seção](#design-the-confirmation-message-1).

### Etapa 2: Criar e configurar o serviço {#step-2--create-and-configure-the-service-2}

1. No menu avançado **[!UICONTROL Profiles & audiences]** &gt; **[!UICONTROL Services]** pelo logotipo do Adobe Campaign, crie um serviço.
1. Vá para a **[!UICONTROL Service properties]** seção, acessada pelo ![](assets/edit_darkgrey-24px.png) botão no painel de serviço.
1. Fill in the **[!UICONTROL Service label]** field. Esse rótulo será exibido na mensagem de confirmação e na página inicial da assinatura.
1. Click **[!UICONTROL Confirm]** and save the service.

### Etapa 3:Criar e configurar a página de aterrissagem {#step-3--create-and-configure-the-landing-page}

Crie uma página inicial de assinatura que será publicada no seu site.

Para criar e configurar esta página inicial, siga as etapas abaixo:

1. Projete uma [nova página](../../channels/using/about-landing-pages.md) inicial com base no **[!UICONTROL Subscription]** modelo.
1. Edite as propriedades da página inicial. Na seção **[!UICONTROL Job]** &gt; **[!UICONTROL Specific actions]** , selecione a **[!UICONTROL Specific service]** opção e escolha o serviço que você acabou de criar na lista suspensa.

   ![](assets/confirmation_lp-specific-service.png)

1. Selecione a **[!UICONTROL Start sending message]** opção e escolha a mensagem transacional que você acabou de criar na lista suspensa.

   ![](assets/confirmation_lp-start-sending-message.png)

1. Personalize o conteúdo da página de aterrissagem.

1. [Teste e publique](../../channels/using/sharing-a-landing-page.md) a página de aterrissagem.

Agora, cada vez que um perfil se inscreve no seu boletim informativo enviando a página de aterrissagem, ele recebe a mensagem de confirmação que você definiu com campos personalizados mapeados para o serviço.

>[!NOTE]
>
>Uma mensagem será enviada sempre que a página de aterrissagem for enviada, mesmo se o perfil já estiver inscrito.
