---
title: Configurar um processo de aceitação dupla
seo-title: Configurar um processo de aceitação dupla
description: Configurar um processo de aceitação dupla
seo-description: Siga estas etapas para configurar um processo de aceitação dupla usando páginas de aterrissagem no Adobe Campaign.
page-status-flag: nunca ativado
uuid: 23 e 6 c 4 c 2-e 2 c 7-472 f-b 616-36 a 95225 ac 1 d
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canais
content-type: reference
topic-tags: páginas de aterrissagem
discoiquuid: 1 a 24504 e -7 f 9 d -4297-b 39 e-c 5 f 085 b 0 f 388
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 855db33971afdf9f02bf1b00be67c9e3f50bee06

---


# Setting up a double opt-in process{#setting-up-a-double-opt-in-process}

## About double opt-in {#about-double-opt-in}

O mecanismo de opção dupla é uma prática recomendada ao enviar emails. Ele protege a plataforma de endereços de email incorretos ou inválidos, spâmbios e evita possíveis reclamações de spam.

O princípio é enviar um email para confirmar o contrato do visitante antes de armazená-lo como "perfis" no banco de dados da Campanha: o visitante preenche uma página de aterrissagem online, depois recebe um e-mail e precisa clicar no link de confirmação para finalizar sua assinatura.

![](assets/optin_mechanism.png)

Para configurar isso, é necessário:

1. Crie e publique uma página de aterrissagem para que os visitantes possam se registrar e assinar. Essa página inicial estará disponível em um site. Visitors who fill in and submit this landing page will be stored in the database but ‘blacklisted', in order not to receive any communication before the final validation (see [Managing blacklisting in Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)).
1. Crie e envie automaticamente o email de aceitação, com um link de confirmação. Esse email direcionará a população que enviou a página de aterrissagem. Isso se baseará em um modelo de e-mail que permite a definição de perfis de «não participação».
1. Redirecione para uma página de aterrissagem de confirmação. Esta página inicial final proporá um botão de confirmação: os visitantes precisam clicar neles. Você pode criar um email de boas-vindas para ser enviado como confirmação e, por exemplo, adicionar uma oferta especial no email para novos destinatários.

Essas etapas precisam ser configuradas no Adobe Campaign em uma ordem específica para ter todos os parâmetros habilitados corretamente.

## Step 1: Create the confirmation landing page {#step-1--create-the-confirmation-landing-page}

O processo para configurar o mecanismo de aceitação dupla começa com a criação da página inicial de confirmação: essa página será exibida quando os visitantes clicarem no e-mail de confirmação para se registrar.

Para criar e configurar essa página de aterrissagem, é necessário:

1. Design a [new landing page](../../channels/using/about-landing-pages.md) based on the **[!UICONTROL Profile acquisition (acquisition)]** template. Enter the label '**CONFIRMATION**'.

   If you need to use [services](../../audiences/using/about-subscriptions.md), you can also use the **[!UICONTROL Subscription (sub)]** template.

1. Edit the landing page properties and under the **[!UICONTROL Access and loading]** section, unselect the option **[!UICONTROL Authorize unidentified visitors]**, select **[!UICONTROL Preload visitor data]** (this one is not mandatory).

   ![](assets/optin_confirmlp_param.png)

1. In the **[!UICONTROL Job]** &gt; **[!UICONTROL Additional data]** section, click **[!UICONTROL Add an element]** and enter the following context path:

   /context/profile/blackList

   Set the value to **false** and click **[!UICONTROL Add]**.

   ![](assets/optin_confirmlp_newelement.png)

   Esse contexto remove o campo da lista de negação para poder enviar emails. We will see later that the first landing page was setting this field to **true** before confirmation, to prevent from sending emails to non-confirmed profiles. For more on this, see [Step 3: Create the acquisition landing page](../../channels/using/setting-up-a-double-opt-in-process.md#step-3--create-the-acquisition-landing-page).

1. Personalize o conteúdo da página de aterrissagem: você pode exibir dados personalizados e alterar o rótulo do botão de confirmação para "Clique aqui para confirmar minha assinatura" por exemplo.

   ![](assets/optin_confirmlp_design.png)

1. Adapte o conteúdo da página de confirmação para informar aos assinantes que eles foram registrados.

   ![](assets/optin_confimlp_page2.png)

1. [Teste e publique](../../channels/using/sharing-a-landing-page.md) a página de aterrissagem.

## Step 2: Create the confirmation email {#step-2--create-the-confirmation-email}

Depois que a página de aterrissagem de confirmação é criada, você pode criar o e-mail de confirmação: esse email será enviado automaticamente para cada visitante que valida a página de aterrissagem de aquisição. Essa validação é considerada como um evento e o e-mail é uma mensagem transacional, vinculada a uma regra de tipologia específica, que permite direcionar as populações de não participação.

As etapas para criar esses elementos estão descritas abaixo. É necessário acompanhá-los antes de criar a própria página de aterrissagem de aquisição, pois esse modelo de e-mail será mencionado nele.

### Create the event {#create-the-event}

The confirmation email is a [transactional message](../../channels/using/about-transactional-messaging.md) as it reacts to an event: the validation of the form. Primeiro, você deve criar o evento e criar o modelo da mensagem transacional.

1. Create an event, from the **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]** &gt; **[!UICONTROL Event configuration]** menu, accessible from the Adobe Campaign logo, and enter the label '**CONFIRM**'.
1. Select the **[!UICONTROL Profile]** targeting dimension and click **[!UICONTROL Create]**.

   ![](assets/optin_eventcreate.png)

1. In the **[!UICONTROL Fields]** section, click **[!UICONTROL Create element]** and add the **[!UICONTROL email]** in the data structure to enable reconciliation.
1. In the **[!UICONTROL Enrichment]** section, click **[!UICONTROL Create element]** and select the target resource **[!UICONTROL Profile]**. You can then map on the **[!UICONTROL email]** in the **[!UICONTROL Join definition]** section, or any other composite reconciliation key, depending on your needs.

   ![](assets/optin_eventcreate_join.png)

   If you need to use services, you can also add the **[!UICONTROL serviceName]**.

1. Select **[!UICONTROL Profile]** as the **[!UICONTROL Targeting enrichment]** in the dropdown list.
1. Click **[!UICONTROL Publish]** to publish the event.

O evento está pronto. Agora é possível projetar o modelo de e-mail. This template must include a link to the **CONFIRMATION** landing page created before. For more on this, see [Design the confirmation message](../../channels/using/setting-up-a-double-opt-in-process.md#design-the-confirmation-message).

### Create the typology rule {#create-the-typology-rule}

You need to create a specific [typology rule](../../administration/using/about-typology-rules.md), by duplicating an out-of-box one. Esta regra permitirá enviar mensagens para perfis que ainda não confirmaram seu contrato e ainda estão proibidas. Por padrão, as regras de tipologia excluem os perfis de recusa (ou seja, lista negra). Para criar essa regra de tipologia, siga estas etapas:

1. From the Adobe Campaign logo, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Typologies]** and click **[!UICONTROL Typologies]**.
1. Duplicate the out-of-box typology **[!UICONTROL Transactional message on profile (mcTypologyProfile)]**.
1. Once duplication confirmed, edit the new typology and enter the label **TYPOLOGY_PROFILE**.
1. Click **[!UICONTROL Save]**.

Agora, essa tipologia pode ser associada ao e-mail de confirmação.

### Design the confirmation message {#design-the-confirmation-message}

O e-mail de confirmação é uma mensagem transacional com base no evento criado anteriormente. Siga as etapas abaixo para criar esta mensagem:

1. From the Adobe Campaign logo, select **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]** and click **[!UICONTROL Transactional messages]**.
1. Edit the **CONFIRM** email template and personalize it. Você pode carregar um conteúdo existente ou usar um modelo out-of-box.
1. Add a link to the **CONFIRMATION** landing page, and click **[!UICONTROL Confirm]** to save modifications.

   ![](assets/optin_email_selectlp.png)

1. Edite as propriedades do modelo de e-mail. In the **[!UICONTROL Advanced parameters]** &gt; **[!UICONTROL Preparation]** section, select the **TYPOLOGY_PROFILE** typology created before.
1. Salve e publique a mensagem transacional.

## Step 3: Create the acquisition landing page {#step-3--create-the-acquisition-landing-page}

É necessário criar a página inicial de aquisição inicial: este formulário de op-in será publicado em seu site.

Para criar e configurar essa página de aterrissagem, é necessário:

1. Design a [new landing page](../../channels/using/about-landing-pages.md) based on the **[!UICONTROL Profile acquisition (acquisition)]** template. Enter the label '**ACQUISITION**'.
1. Edit the landing page properties: in the **[!UICONTROL Job]** &gt; **[!UICONTROL Additional data]** section, click **[!UICONTROL Add an element]** and enter the following context path:

   /context/profile/blackList

   and set the value to **true**.

   Isso é obrigatório para forçar a lista de negação e evitar enviar mensagens a visitantes que não confirmaram seu contrato. The validation of the CONFIRMATION landing page will set this field to **false** after confirmation. For more on this, see [Step 1: Create the confirmation landing page](../../channels/using/setting-up-a-double-opt-in-process.md#step-1--create-the-confirmation-landing-page).

1. In the **[!UICONTROL Job]** &gt; **[!UICONTROL Specific actions]** section, select the option **[!UICONTROL Start sending messages]**.
1. In the associated drop-down list, choose the **CONFIRM** transactional message template you created.

   ![](assets/optin_acquisition_startoption.png)

1. Personalize o conteúdo da página de aterrissagem, dependendo da sua marca e dos dados que você precisa adquirir. You can display personalized data and change the label of the confirmation button to **Confirm my subscription** for example.

   ![](assets/optin_acquisition_page1.png)

1. Personalize a página de confirmação para informar o novo assinante que precisa validar sua assinatura.

   ![](assets/optin_acquisition_page2.png)

1. [Teste e publique](../../channels/using/sharing-a-landing-page.md) a página de aterrissagem.

O mecanismo de aceitação dupla agora está configurado. You can run and test the procedure from end to end, starting from the public URL of this **[!UICONTROL ACQUISITION]** landing page. Esse URL é exibido no painel de página de aterrissagem.
