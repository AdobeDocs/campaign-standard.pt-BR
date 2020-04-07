---
title: Configurar um processo de participação dupla
description: Siga estas etapas para configurar um processo de aceitação de duplo usando o landing page no Adobe Campaign.
page-status-flag: never-activated
uuid: 23e6c4c2-e2c7-472f-b616-36a95225ac1d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: 1a24504e-7f9d-4297-b39e-c5f085b0f388
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 3b40a9bba79d04f1635b7522cfc99f9e7566c3c0

---


# Configurar um processo de participação dupla{#setting-up-a-double-opt-in-process}

## Sobre a aceitação de duplos {#about-double-opt-in}

O mecanismo de aceitação do Duplo é uma prática recomendada para enviar emails. Ela protege a plataforma contra endereços de email errados ou inválidos, spambots e evita possíveis reclamações de spam.

O princípio é enviar um e-mail para confirmar o contrato do visitante antes de armazená-lo como &quot;perfis na sua base de dados de Campanhas: o visitante preenche uma landing page on-line, recebe um email e precisa clicar no link de confirmação para finalizar a subscrição.

![](assets/optin_mechanism.png)

Para configurar, é necessário:

1. Crie e publique uma landing page para que os visitantes possam se registrar e se inscrever. Esta landing page estará disponível em um site. Os Visitantes que preencherem e enviarem essa landing page serão armazenados no banco de dados, mas &quot;incluído na blacklist&quot;, para não receberem qualquer comunicação antes da validação final (consulte [Gerenciamento de listas negras na Campanha](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)).
1. Crie e envie automaticamente o email de aceitação, com um link de confirmação. Este email vai público alvo a população que enviou a landing page. Ele será baseado em um modelo de e-mail que permite o público alvo de perfis de não participação.
1. Redirecionar para uma landing page de confirmação. Esta landing page final irá propor um botão de confirmação: os visitantes precisam clicar nele. Você pode projetar um email de boas-vindas para ser enviado quando a confirmação for feita e, por exemplo, adicionar uma oferta especial no email para novos recipient.

Essas etapas devem ser configuradas no Adobe Campaign em uma ordem específica para que todos os parâmetros sejam ativados corretamente.

## Etapa 1: Criar a landing page de confirmação {#step-1--create-the-confirmation-landing-page}

O processo para configurar o mecanismo de aceitação do duplo start com a criação da landing page de confirmação: esta página será exibida quando os visitantes clicarem no e-mail de confirmação para se registrarem.

Para criar e configurar essa landing page, é necessário:

1. Projete uma [nova landing page](../../channels/using/getting-started-with-landing-pages.md) com base no **[!UICONTROL Profile acquisition (acquisition)]** modelo. Digite o rótulo &#39;**CONFIRMATION**&#39;.

   Se precisar usar [serviços](../../audiences/using/about-subscriptions.md), você também poderá usar o **[!UICONTROL Subscription (sub)]** modelo.

1. Edite as propriedades de landing page e, na **[!UICONTROL Access and loading]** seção, desmarque a opção **[!UICONTROL Authorize unidentified visitors]**, selecione **[!UICONTROL Preload visitor data]** (esta não é obrigatória).

   ![](assets/optin_confirmlp_param.png)

1. Na seção **[!UICONTROL Job]** > **[!UICONTROL Additional data]** , clique **[!UICONTROL Add an element]** e insira o seguinte caminho de contexto:

   /context/perfil/blackList

   Defina o valor como **false** e clique em **[!UICONTROL Add]**.

   ![](assets/optin_confirmlp_newelement.png)

   Este contexto remove o campo da lista negra, para poder enviar emails. Veremos mais tarde que a primeira landing page estava definindo esse campo como **verdadeiro** antes da confirmação, para evitar o envio de emails para perfis não confirmados. Para obter mais informações, consulte a [Etapa 3: Crie a landing page](#step-3--create-the-acquisition-landing-page)de aquisição.

1. Personalize o conteúdo da landing page: você pode exibir dados personalizados e alterar o rótulo do botão de confirmação para &quot;Clique aqui para confirmar minha subscrição&quot;, por exemplo.

   ![](assets/optin_confirmlp_design.png)

1. Adapte o conteúdo da página de confirmação para informar aos assinantes que eles estão registrados.

   ![](assets/optin_confimlp_page2.png)

1. [Teste e publique](../../channels/using/testing-publishing-landing-page.md) a landing page.

## Etapa 2: Criar o email de confirmação {#step-2--create-the-confirmation-email}

Assim que a landing page de confirmação for criada, você poderá criar o e-mail de confirmação: este email será enviado automaticamente para todos os visitantes que validarem a landing page de aquisição. Essa validação é considerada um evento e o email é um mensagen transacional, vinculado a uma regra de tipologia específica que permite público alvo de populações de opção de não participação.

As etapas para criar esses elementos estão descritas abaixo. É necessário segui-las antes de criar a landing page de aquisição propriamente dita, pois esse modelo de email será referenciado nela.

### Criar o evento {#create-the-event}

O e-mail de confirmação é um [mensagen transacional](../../channels/using/about-transactional-messaging.md) , pois reage a um evento: a validação do formulário. Primeiro, você deve criar o evento e depois criar o modelo do mensagen transacional.

1. Crie um evento, no menu **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]** , acessível a partir do logotipo do Adobe Campaign e digite o rótulo &#39;**CONFIRMAR**&#39;.
1. Selecione o **[!UICONTROL Profile]** targeting dimension e clique em **[!UICONTROL Create]**.

   ![](assets/optin_eventcreate.png)

1. Na **[!UICONTROL Fields]** seção, clique em **[!UICONTROL Create element]** e adicione o **[!UICONTROL email]** na estrutura de dados para ativar a reconciliação.
1. Na **[!UICONTROL Enrichment]** seção, clique **[!UICONTROL Create element]** e selecione o recurso de **[!UICONTROL Profile]** público alvo. Você pode mapear no **[!UICONTROL email]** campo na **[!UICONTROL Join definition]** seção ou qualquer outra chave de reconciliação composta, dependendo de suas necessidades.

   ![](assets/optin_eventcreate_join.png)

   Se precisar usar serviços, adicione o recurso de **[!UICONTROL Service]** público alvo e mapeie no **[!UICONTROL serviceName]** campo. Para obter mais informações, consulte .

1. Selecione **[!UICONTROL Profile]** como o **[!UICONTROL Targeting enrichment]** na lista suspensa.
1. Clique em **[!UICONTROL Publish]** para publicar o evento.

O evento está pronto. Agora você pode criar o modelo de email. Este modelo deve incluir um link para a landing page **CONFIRMATION** criada anteriormente. Para obter mais informações, consulte [Criar a mensagem](#design-the-confirmation-message)de confirmação.

### Criar a tipologia {#create-the-typology-rule}

Você precisa criar uma [tipologia](../../sending/using/about-typology-rules.md)específica, duplicando uma predefinida. A tipologia permitirá o envio de mensagens a perfis que ainda não confirmaram seu acordo e ainda estão incluído na blacklist. Por padrão, as tipologias excluem perfis de opção de não participação (ou seja, incluído na blacklist). Para criar essa tipologia, siga estas etapas:

1. No logotipo do Adobe Campaign, selecione **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]** e clique em **[!UICONTROL Typologies]**.
1. Duplicado da tipologia predefinida **[!UICONTROL Transactional message on profile (mcTypologyProfile)]**.
1. Depois que a duplicação for confirmada, edite a nova tipologia e insira o rótulo **TYPOLOGY_PERFIL**.
1. Remova a regra de endereço **** incluído na blacklist.
1. Clique em **[!UICONTROL Save]**.

Essa tipologia agora pode ser associada ao email de confirmação.

### Projetar a mensagem de confirmação {#design-the-confirmation-message}

O e-mail de confirmação é um mensagen transacional baseado no evento criado antes. Siga as etapas abaixo para criar esta mensagem:

1. No logotipo do Adobe Campaign, selecione **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** e clique em **[!UICONTROL Transactional messages]**.
1. Edite o modelo de e-mail **CONFIRM** e personalize-o. Você pode carregar um conteúdo existente ou usar um modelo predefinido.
1. Adicione um link à landing page **CONFIRMATION** e clique **[!UICONTROL Confirm]** para salvar as modificações.

   ![](assets/optin_email_selectlp.png)

1. Edite as propriedades do modelo de email. Na seção **[!UICONTROL Advanced parameters]** > **[!UICONTROL Preparation]** , selecione a tipologia **TYPOLOGY_PERFIL** criada anteriormente.
1. Salve e publique o mensagen transacional.

## Etapa 3: Criar a landing page de aquisição {#step-3--create-the-acquisition-landing-page}

É necessário criar a landing page de aquisição inicial: este formulário de aceitação será publicado em seu site.

Para criar e configurar essa landing page, é necessário:

1. Projete uma [nova landing page](../../channels/using/getting-started-with-landing-pages.md) com base no **[!UICONTROL Profile acquisition (acquisition)]** modelo. Digite o rótulo &#39;**AQUISIÇÃO**&#39;.
1. Edite as propriedades da landing page: na seção **[!UICONTROL Job]** > **[!UICONTROL Additional data]** , clique **[!UICONTROL Add an element]** e insira o seguinte caminho de contexto:

   /context/perfil/blackList

   e defina o valor como **true**.

   Isto é obrigatório para forçar a lista negra e evitar o envio de mensagens a visitantes que não confirmaram o seu acordo. A validação da landing page CONFIRMATION definirá esse campo como **falso** após a confirmação. Para obter mais informações, consulte a [Etapa 1: Crie a landing page](#step-1--create-the-confirmation-landing-page)de confirmação.

1. Na seção **[!UICONTROL Job]** > **[!UICONTROL Specific actions]** , selecione a opção **[!UICONTROL Start sending messages]**.
1. Na lista suspensa associada, escolha o template de mensagem transacional **CONFIRMAR** que você criou.

   ![](assets/optin_acquisition_startoption.png)

1. Personalize o conteúdo da landing page, dependendo da sua marca e dos dados que você precisa adquirir. Você pode exibir dados personalizados e alterar o rótulo do botão de confirmação para **Confirmar minha subscrição** , por exemplo.

   ![](assets/optin_acquisition_page1.png)

1. Personalize a página de confirmação para informar ao novo assinante que ele precisa validar sua subscrição.

   ![](assets/optin_acquisition_page2.png)

1. [Teste e publique](../../channels/using/testing-publishing-landing-page.md) a landing page.

O mecanismo de aceitação do Duplo agora está configurado. Você pode executar e testar o procedimento de ponta a ponta, começando pelo URL público dessa **[!UICONTROL ACQUISITION]** landing page. Esse URL é exibido no painel da landing page.
