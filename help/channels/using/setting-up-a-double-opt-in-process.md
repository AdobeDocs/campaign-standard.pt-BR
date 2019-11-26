---
title: Configurar um processo de participação dupla
description: Siga estas etapas para configurar um processo de aceitação dupla usando páginas iniciais no Adobe Campaign.
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
source-git-commit: 95e01eb33097fc76caac3f4dd5f5591461b887cf

---


# Configurar um processo de participação dupla{#setting-up-a-double-opt-in-process}

## Sobre aceitação dupla {#about-double-opt-in}

O mecanismo de aceitação dupla é uma prática recomendada ao enviar emails. Ela protege a plataforma contra endereços de email errados ou inválidos, spambots e evita possíveis reclamações de spam.

O princípio é enviar um email para confirmar o acordo do visitante antes de armazená-lo como "perfis" no banco de dados do Campaign: o visitante preenche uma página de aterrissagem online, recebe um email e precisa clicar no link de confirmação para finalizar sua assinatura.

![](assets/optin_mechanism.png)

Para configurar, é necessário:

1. Crie e publique uma página de aterrissagem para que os visitantes possam se registrar e se inscrever. Esta página inicial estará disponível em um site. Os visitantes que preencherem e enviarem essa página inicial serão armazenados no banco de dados, mas "na lista negra", para não receberem nenhuma comunicação antes da validação final (consulte [Gerenciamento da lista negra no Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)).
1. Crie e envie automaticamente o email de aceitação, com um link de confirmação. Esse email direcionará a população que enviou a página de aterrissagem. Ele será baseado em um modelo de e-mail que permite direcionar perfis de "não participação".
1. Redirecionar para uma página inicial de confirmação. Esta página de aterrissagem final irá propor um botão de confirmação: os visitantes precisam clicar nele. Você pode projetar um email de boas-vindas para ser enviado quando a confirmação for feita e, por exemplo, adicionar uma oferta especial no email para novos destinatários.

Essas etapas devem ser configuradas no Adobe Campaign em uma ordem específica para que todos os parâmetros sejam ativados corretamente.

## Etapa 1: Criar a página inicial de confirmação {#step-1--create-the-confirmation-landing-page}

O processo para configurar o mecanismo de aceitação dupla começa com a criação da página inicial de confirmação: esta página será exibida quando os visitantes clicarem no email de confirmação para se registrarem.

Para criar e configurar esta página inicial, é necessário:

1. Projete uma [nova página](../../channels/using/getting-started-with-landing-pages.md) inicial com base no **[!UICONTROL Profile acquisition (acquisition)]** modelo. Digite o rótulo '**CONFIRMATION**'.

   Se precisar usar [serviços](../../audiences/using/about-subscriptions.md), você também poderá usar o **[!UICONTROL Subscription (sub)]** modelo.

1. Edite as propriedades da página inicial e, na **[!UICONTROL Access and loading]** seção, desmarque a opção **[!UICONTROL Authorize unidentified visitors]**, selecione **[!UICONTROL Preload visitor data]** (esta não é obrigatória).

   ![](assets/optin_confirmlp_param.png)

1. Na seção **[!UICONTROL Job]** &gt; **[!UICONTROL Additional data]** , clique **[!UICONTROL Add an element]** e insira o seguinte caminho de contexto:

   /context/profile/blackList

   Defina o valor como **false** e clique em **[!UICONTROL Add]**.

   ![](assets/optin_confirmlp_newelement.png)

   Este contexto remove o campo da lista negra, para poder enviar emails. Veremos mais tarde que a primeira página inicial estava definindo esse campo como **verdadeiro** antes da confirmação, para evitar o envio de emails para perfis não confirmados. Para obter mais informações, consulte a [Etapa 3: Crie a página](#step-3--create-the-acquisition-landing-page)inicial de aquisição.

1. Personalize o conteúdo da página inicial: você pode exibir dados personalizados e alterar o rótulo do botão de confirmação para "Clique aqui para confirmar minha assinatura", por exemplo.

   ![](assets/optin_confirmlp_design.png)

1. Adapte o conteúdo da página de confirmação para informar aos assinantes que eles estão registrados.

   ![](assets/optin_confimlp_page2.png)

1. [Teste e publique](../../channels/using/testing-publishing-landing-page.md) a página de aterrissagem.

## Etapa 2: Criar o email de confirmação {#step-2--create-the-confirmation-email}

Assim que a página inicial de confirmação for criada, você poderá criar o e-mail de confirmação: esse email será enviado automaticamente para todos os visitantes que validarem a página inicial de aquisição. Essa validação é considerada um evento e o e-mail é uma mensagem transacional, vinculada a uma regra de tipologia específica que permite direcionar populações de opção de não participação.

As etapas para criar esses elementos estão descritas abaixo. É necessário segui-los antes de criar a página de aterrissagem de aquisição propriamente dita, pois esse modelo de email será referenciado nele.

### Criar o evento {#create-the-event}

O email de confirmação é uma mensagem [](../../channels/using/about-transactional-messaging.md) transacional, pois reage a um evento: a validação do formulário. Primeiro, você deve criar o evento e depois criar o modelo da mensagem transacional.

1. Crie um evento, no menu **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]** &gt; **[!UICONTROL Event configuration]** , acessível pelo logotipo do Adobe Campaign e digite o rótulo '**CONFIRMAR**'.
1. Selecione a dimensão de **[!UICONTROL Profile]** definição de metas e clique em **[!UICONTROL Create]**.

   ![](assets/optin_eventcreate.png)

1. Na **[!UICONTROL Fields]** seção, clique em **[!UICONTROL Create element]** e adicione o **[!UICONTROL email]** na estrutura de dados para ativar a reconciliação.
1. Na **[!UICONTROL Enrichment]** seção, clique **[!UICONTROL Create element]** e selecione o recurso de **[!UICONTROL Profile]** destino. Em seguida, é possível mapear no **[!UICONTROL email]** campo na **[!UICONTROL Join definition]** seção ou qualquer outra chave de reconciliação composta, dependendo de suas necessidades.

   ![](assets/optin_eventcreate_join.png)

   Se precisar usar serviços, adicione o recurso de **[!UICONTROL Service]** destino e mapeie no **[!UICONTROL serviceName]** campo. Para obter mais informações, consulte .

1. Selecione **[!UICONTROL Profile]** como o **[!UICONTROL Targeting enrichment]** na lista suspensa.
1. Clique em **[!UICONTROL Publish]** para publicar o evento.

O evento está pronto. Agora você pode criar o modelo de email. Este modelo deve incluir um link para a página de aterrissagem de **CONFIRMAÇÃO** criada antes. Para obter mais informações, consulte [Criar a mensagem](#design-the-confirmation-message)de confirmação.

### Criar a regra de tipologia {#create-the-typology-rule}

É necessário criar uma regra [de](../../administration/using/about-typology-rules.md)tipologia específica, duplicando uma predefinida. Esta regra permitirá enviar mensagens a perfis que ainda não confirmaram seu acordo e que ainda estão na lista negra. Por padrão, as regras de tipologia excluem perfis de opção de não participação (ou seja, da lista negra). Para criar essa regra de tipologia, siga estas etapas:

1. No logotipo do Adobe Campaign, selecione **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Typologies]** e clique em **[!UICONTROL Typologies]**.
1. Duplique a tipologia predefinida **[!UICONTROL Transactional message on profile (mcTypologyProfile)]**.
1. Depois que a duplicação for confirmada, edite a nova tipologia e insira o rótulo **TYPOLOGY_PROFILE**.
1. Remova a regra de endereço **da lista** negra.
1. Click **[!UICONTROL Save]**.

Essa tipologia agora pode ser associada ao email de confirmação.

### Projetar a mensagem de confirmação {#design-the-confirmation-message}

O email de confirmação é uma mensagem transacional baseada no evento criado antes. Siga as etapas abaixo para criar esta mensagem:

1. No logotipo do Adobe Campaign, selecione **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]** e clique em **[!UICONTROL Transactional messages]**.
1. Edite o modelo de e-mail **CONFIRM** e personalize-o. Você pode carregar um conteúdo existente ou usar um modelo predefinido.
1. Adicione um link à página de **aterrissagem CONFIRMAÇÃO** e clique **[!UICONTROL Confirm]** para salvar as modificações.

   ![](assets/optin_email_selectlp.png)

1. Edite as propriedades do modelo de email. Na seção **[!UICONTROL Advanced parameters]** &gt; **[!UICONTROL Preparation]** , selecione a tipologia **TYPOLOGY_PROFILE** criada anteriormente.
1. Salve e publique a mensagem transacional.

## Etapa 3: Criar a página inicial de aquisição {#step-3--create-the-acquisition-landing-page}

É necessário criar a página inicial de aquisição: este formulário de aceitação será publicado em seu site.

Para criar e configurar esta página inicial, é necessário:

1. Projete uma [nova página](../../channels/using/getting-started-with-landing-pages.md) inicial com base no **[!UICONTROL Profile acquisition (acquisition)]** modelo. Digite o rótulo '**AQUISIÇÃO**'.
1. Edite as propriedades da página inicial: na seção **[!UICONTROL Job]** &gt; **[!UICONTROL Additional data]** , clique **[!UICONTROL Add an element]** e insira o seguinte caminho de contexto:

   /context/profile/blackList

   e defina o valor como **true**.

   Isso é obrigatório para forçar a lista negra e evitar o envio de mensagens a visitantes que não confirmaram o acordo. A validação da página inicial CONFIRMAÇÃO definirá esse campo como **falso** após a confirmação. Para obter mais informações, consulte a [Etapa 1: Crie a página](#step-1--create-the-confirmation-landing-page)inicial de confirmação.

1. Na seção **[!UICONTROL Job]** &gt; **[!UICONTROL Specific actions]** , selecione a opção **[!UICONTROL Start sending messages]**.
1. Na lista suspensa associada, escolha o modelo de mensagem transacional **CONFIRMAR** que você criou.

   ![](assets/optin_acquisition_startoption.png)

1. Personalize o conteúdo da página de aterrissagem, dependendo da sua marca e dos dados que você precisa adquirir. Você pode exibir dados personalizados e alterar o rótulo do botão de confirmação para **Confirmar minha assinatura** , por exemplo.

   ![](assets/optin_acquisition_page1.png)

1. Personalize a página de confirmação para informar ao novo assinante que ele precisa validar sua assinatura.

   ![](assets/optin_acquisition_page2.png)

1. [Teste e publique](../../channels/using/testing-publishing-landing-page.md) a página de aterrissagem.

O mecanismo de aceitação dupla agora está configurado. Você pode executar e testar o procedimento de ponta a ponta, começando pelo URL público desta **[!UICONTROL ACQUISITION]** página inicial. Esse URL é exibido no painel da página inicial.
