---
title: Configuração de um processo duplo de aceitação
description: Siga estas etapas para configurar um processo de participação dupla usando a página de destino no Adobe Campaign.
audience: channels
content-type: reference
topic-tags: landing-pages
feature: Landing Pages
role: User
level: Intermediate
exl-id: 188b1750-e062-4328-9829-6f2848356b5c
TQID: https://experienceleague.adobe.com/uEAfmHvm5tpDoCp9nEQeveyH0oBvmP24IvkUy73QPSw
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: b631758a-142d-425f-b9aa-f756d85cb979
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 1172
ht-degree: 86%

---

# Configuração de um processo duplo de aceitação{#setting-up-a-double-opt-in-process}

## Sobre a participação dupla {#about-double-opt-in}

O mecanismo de participação dupla é uma prática recomendada para enviar emails. Ele protege a plataforma contra endereços de email incorretos ou inválidos e spambots, além de evitar possíveis reclamações de spam.

O princípio é enviar um email para confirmar o contrato do visitante antes de armazená-lo como &quot;perfis&quot; no banco de dados do Campaign: o visitante preenche uma página de destino online, recebe um email e precisa clicar no link de confirmação para finalizar a assinatura.

![](assets/optin_mechanism.png)

Para configurar, é necessário:

1. Crie e publique uma página de destino para que os visitantes possam se registrar e assinar. Essa página de destino estará disponível em um site. Os visitantes que preencherem e enviarem essa landing page serão armazenados no banco de dados, mas adicionados ao incluo na lista de bloqueios, para não receberem nenhuma comunicação antes da validação final (consulte [Gerenciamento de Inclui na lista de bloqueios no Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)).
1. Crie e envie automaticamente o email de participação, com um link de confirmação. Esse email terá como alvo a população que enviou a página de destino. Ele será baseado em um modelo de email que permite direcionar perfis de &quot;recusa de participação&quot;.
1. Redirecione para uma página de destino de confirmação. Essa página de destino final apresentará um botão de confirmação: os visitantes precisam clicar nele. Você pode compor um email de boas-vindas para ser enviado quando a confirmação for feita e, por exemplo, adicionar uma oferta especial no email para novos destinatários.

Essas etapas devem ser configuradas no Adobe Campaign em uma ordem específica para que todos os parâmetros sejam habilitados corretamente.

## Etapa 1: criar a landing page de confirmação {#step-1--create-the-confirmation-landing-page}

O processo para configurar o mecanismo de participação dupla começa com a criação da página de destino de confirmação: essa página será exibida quando os visitantes clicarem no email de confirmação para se registrarem.

Para criar e configurar essa página de destino, faça o seguinte:

1. Projete uma [nova página de destino](../../channels/using/getting-started-with-landing-pages.md) com base no modelo **[!UICONTROL Profile acquisition (acquisition)]**. Insira o rótulo &#39;**CONFIRMATION**&#39;.

   Se você precisar usar [serviços](../../audiences/using/about-subscriptions.md), também poderá usar o modelo **[!UICONTROL Subscription (sub)]**.

1. Edite as propriedades da página de destino e, na seção **[!UICONTROL Access and loading]**, desmarque a opção **[!UICONTROL Authorize unidentified visitors]** e selecione **[!UICONTROL Preload visitor data]** (esta opção não é obrigatória).

   ![](assets/optin_confirmlp_param.png)

1. Na seção **[!UICONTROL Job]** > **[!UICONTROL Additional data]**, clique em **[!UICONTROL Add an element]** e insira o seguinte caminho de contexto:

   /context/profile/blackList

   Defina o valor como **false** e clique em **[!UICONTROL Add]**.

   ![](assets/optin_confirmlp_newelement.png)

   Esse contexto remove o campo &quot;Na inclui na lista de bloqueios&quot; para poder enviar emails. Veremos mais tarde que a primeira página de destino estava definindo esse campo como **true** antes da confirmação, para evitar o envio de emails a perfis não confirmados. Para obter mais informações, consulte [Etapa 3: criar a página de destino de aquisição](#step-3--create-the-acquisition-landing-page).

1. Personalizar o conteúdo da página de destino: você pode exibir dados personalizados e alterar o rótulo do botão de confirmação para &quot;Clique aqui para confirmar minha assinatura&quot;, por exemplo.

   ![](assets/optin_confirmlp_design.png)

1. Adapte o conteúdo da página de confirmação para informar aos assinantes que eles estão agora registrados.

   ![](assets/optin_confimlp_page2.png)

1. [Teste e publique](../../channels/using/testing-publishing-landing-page.md) a página de destino.

## Etapa 2: criar o email de confirmação {#step-2--create-the-confirmation-email}

Assim que a página de destino de confirmação for criada, você poderá criar o email de confirmação: esse email será enviado automaticamente a todos os visitantes que validarem a página de destino de aquisição. Essa validação é considerada um evento, e o email é uma mensagem transacional vinculada a uma regra de tipologia específica que permite o direcionamento a populações que se recusaram a participar.

As etapas para criar esses elementos estão descritas abaixo. É necessário segui-las antes de criar a página de destino de aquisição propriamente dita, pois esse modelo de email será referenciado nela.

### Criar o evento {#create-the-event}

O email de confirmação é uma [mensagem transacional](../../channels/using/getting-started-with-transactional-msg.md), pois reage a um evento: a validação do formulário. Primeiro, você deve criar o evento e depois criar o modelo da mensagem transacional.

1. Crie um evento, no menu **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**, acessível no logotipo do Adobe Campaign, e insira o rótulo &#39;**CONFIRM**&#39;.
1. Selecione a **[!UICONTROL Profile]** dimensão de direcionamento e clique em **[!UICONTROL Create]**.

   ![](assets/optin_eventcreate.png)

1. Na seção **[!UICONTROL Fields]**, clique em **[!UICONTROL Create element]** e adicione o **[!UICONTROL email]** na estrutura de dados para habilitar a reconciliação.
1. Na seção **[!UICONTROL Enrichment]**, clique em **[!UICONTROL Create element]** e selecione o recurso do público-alvo **[!UICONTROL Profile]**. Em seguida, será possível mapear no campo **[!UICONTROL email]** da seção **[!UICONTROL Join definition]** ou em qualquer outra chave de reconciliação composta, dependendo das suas necessidades.

   ![](assets/optin_eventcreate_join.png)

   Se você precisar usar serviços, adicione o recurso de público-alvo **[!UICONTROL Service]** e mapeie no campo **[!UICONTROL serviceName]**. Para obter mais informações, consulte .

1. Selecione **[!UICONTROL Profile]** como o **[!UICONTROL Targeting enrichment]** na lista suspensa.
1. Clique em **[!UICONTROL Publish]** para publicar o evento.

O evento está pronto. Agora, você pode criar o modelo de email. Esse modelo deve incluir um link para a página de destino **CONFIRMATION** criada anteriormente. Para obter mais informações, consulte [Compor a mensagem de confirmação](#design-the-confirmation-message).

### Criar a tipologia {#create-the-typology-rule}

Você precisa criar uma [tipologia](../../sending/using/about-typology-rules.md) específica, duplicando uma tipologia predefinida. A tipologia permitirá o envio de mensagens a perfis que ainda não confirmaram a aceitação e ainda estão em inclui na lista de bloqueios. Por padrão, as tipologias excluem perfis de recusa de participação (ou seja, na inclui na lista de bloqueios). Para criar essa tipologia, siga estas etapas:

1. No logotipo do Adobe Campaign, selecione **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]** e clique em **[!UICONTROL Typologies]**.
1. Duplique a tipologia predefinida **[!UICONTROL Transactional message on profile (mcTypologyProfile)]**.
1. Depois que a duplicação for confirmada, edite a nova tipologia e insira o rótulo **TYPOLOGY_PROFILE**.
1. Remova a regra **Endereço na inclui na lista de bloqueios**.
1. Clique em **[!UICONTROL Save]**.

Essa tipologia agora pode ser associada ao email de confirmação.

### Criar a mensagem de confirmação {#design-the-confirmation-message}

O email de confirmação é uma mensagem transacional baseada no evento criado antes. Siga as etapas abaixo para criar essa mensagem:

1. No logotipo do Adobe Campaign, selecione **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** e clique em **[!UICONTROL Transactional messages]**.
1. Edite o modelo de email **CONFIRM** e personalize-o. Você pode fazer upload de um conteúdo existente ou usar um modelo predefinido.
1. Adicione um link à página de destino **CONFIRMATION** e clique em **[!UICONTROL Confirm]** para salvar as modificações.

   ![](assets/optin_email_selectlp.png)

1. Edite as propriedades do modelo de email. Na seção **[!UICONTROL Advanced parameters]** > **[!UICONTROL Preparation]**, selecione a tipologia **TYPOLOGY_PROFILE** criada anteriormente.
1. Salve e publique a mensagem transacional.

## Etapa 3: criar a landing page de aquisição {#step-3--create-the-acquisition-landing-page}

É necessário criar a página de destino de aquisição inicial: esse formulário de participação será publicado no seu site.

Para criar e configurar essa página de destino, faça o seguinte:

1. Projete uma [nova página de destino](../../channels/using/getting-started-with-landing-pages.md) com base no modelo **[!UICONTROL Profile acquisition (acquisition)]**. Insira o rótulo &#39;**ACQUISITION**&#39;.
1. Edite as propriedades da página de destino: na seção **[!UICONTROL Job]** > **[!UICONTROL Additional data]**, clique em **[!UICONTROL Add an element]** e insira o seguinte caminho de contexto:

   /context/profile/blackList

   e defina o valor como **true**.

   Isso é obrigatório para forçar a adição de conteúdo ao incluo na lista de bloqueios e evitar o envio de mensagens a visitantes que não confirmaram a aceitação. A validação da página de destino CONFIRMATION definirá esse campo como **false** após a confirmação. Para obter mais informações, consulte [Etapa 1: criar a página de destino de confirmação](#step-1--create-the-confirmation-landing-page).

1. Na seção **[!UICONTROL Job]** > **[!UICONTROL Specific actions]**, selecione a opção **[!UICONTROL Start sending messages]**.
1. Na lista suspensa associada, escolha o modelo de mensagem transacional **CONFIRM** que você criou.

   ![](assets/optin_acquisition_startoption.png)

1. Personalize o conteúdo da página de destino, dependendo da sua marca e dos dados que você precisa adquirir. Você pode exibir dados personalizados e alterar o rótulo do botão de confirmação para **Confirmar minha assinatura**, por exemplo.

   ![](assets/optin_acquisition_page1.png)

1. Personalize a página de confirmação para informar aos novos assinantes que eles precisam validar suas assinaturas.

   ![](assets/optin_acquisition_page2.png)

1. [Teste e publique](../../channels/using/testing-publishing-landing-page.md) a página de destino.

O mecanismo de participação dupla agora está configurado. Você pode executar e testar o procedimento de ponta a ponta, começando pelo URL público desta **[!UICONTROL ACQUISITION]** página de destino. Esse URL é exibido no painel da página de destino.
