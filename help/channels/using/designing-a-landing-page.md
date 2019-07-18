---
title: Criar uma página de aterrissagem
seo-title: Criar uma página de aterrissagem
description: Criar uma página de aterrissagem
seo-description: Siga estas etapas para projetar o conteúdo de uma página de aterrissagem e vinculá-lo a um serviço.
page-status-flag: nunca ativado
uuid: de 6 fe 190-835 c -40 fd -8101-a 809 b 430 b 423
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canais
content-type: reference
topic-tags: páginas de aterrissagem
discoiquuid: bd 77 d 6 f 0-3143-4030-a 91 b -988 a 2 bebc 534
context-tags: Landingpage, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b0cf437ec97153b53bd4502171b24286abb25731

---


# Designing a landing page{#designing-a-landing-page}

## About content design {#about-content-design}

Landing pages are created as any [marketing activity](../../start/using/marketing-activities.md#about-marketing-activities).

Ao projetar uma página de aterrissagem, é necessário definir o conteúdo de:

* a própria página,
* a página de confirmação,
* a página de erro.

Use o alternador na barra de ação para exibir e configurar cada uma dessas páginas.

O conteúdo dessas páginas é projetado pelo editor de conteúdo da campanha. Refer to [Design content](../../designing/using/about-landing-page-content-design.md).

## Mapping form fields {#mapping-form-fields}

Campos de entrada são usados para armazenar ou atualizar dados no banco de dados da Campanha. Para isso, é necessário vincular os campos do banco de dados com zona de entrada, botão de opção ou blocos de tipo de caixa de seleção. Para fazer isso:

1. Selecione um bloco na página de aterrissagem.
1. Complete the **[!UICONTROL Form data]** part in the palette.

   ![](assets/editing_lp_content_4.png)

1. Choose a database field to link with the form field in the **[!UICONTROL Field]** selection zone.

   When the **[!UICONTROL Mandatory]** option is checked, the page can only be submitted if the user has completed this field. Se um campo obrigatório não for concluído, uma mensagem de erro aparecerá quando o usuário validar a página.

   >[!NOTE]
   >
   >Landing pages can only be mapped with **Profiles**.

1. Define the field type by choosing, for example **[!UICONTROL Text]**, **[!UICONTROL Number]**,or **[!UICONTROL Date]** in the **[!UICONTROL HTML type of the field]** selection area.

>[!NOTE]
>
>Os campos padrão das páginas iniciais incorporadas são pré-configurados. Você pode modificá-las conforme necessário.

## Submitting the form {#submitting-the-form}

Você pode selecionar a ação a ser executada quando o visitante clicar no botão Enviar. Para fazer isso:

1. Selecione o botão de envio da página de aterrissagem.
1. Selecione a ação na lista suspensa no painel esquerdo. Possible actions are: **[!UICONTROL Refresh]** (to refresh the page) and **[!UICONTROL Next page]** (to display the confirmation page).

   ![](assets/editing_lp_content_5.png)

Além disso, você pode alterar o rótulo do botão ou configurar um link específico. Para fazer isso:

1. Selecione o botão de envio.
1. Click on the ![](assets/lp_link_properties.png) button in the left panel.
1. Digite o rótulo do botão, selecione o tipo de link, suas propriedades e o destino.

   ![](assets/lp_link_custom.png)

## Linking a form to a service {#linking-a-form-to-a-service}

É possível vincular um formulário a um serviço para que os perfis possam assinar um serviço específico ao validar as páginas iniciais.

Os parâmetros para vincular uma página de aterrissagem permitem especificar o tipo de ação executada e se a página de aterrissagem está especificamente vinculada a um único serviço ou se é genérica.

Para selecionar o serviço a ser vinculado, é necessário:

1. Edit the landing page properties accessed via the ![](assets/edit_darkgrey-24px.png) icon in the landing page dashboard, and display the **[!UICONTROL Job]** parameters.

   ![](assets/lp_edit_properties_button.png)

1. Choose **[!UICONTROL Subscription]** in the **[!UICONTROL Specific actions]** drop-down list.

   ![](assets/lp_parameters_5.png)

1. Select **[!UICONTROL Specific service]** to link the landing page to a single service. Não selecione essa opção se você deseja usar vários serviços com a página de aterrissagem.

   Use the **[!UICONTROL Specified service in the URL]** option to allow the landing page to be used for several services. Portanto, você deve fazer referência à página de aterrissagem ao configurar o serviço.

### Confirm a landing page submission {#confirm-a-landing-page-submission}

Quando uma página de aterrissagem é enviada por um visitante, é possível configurar as ações acionadas. Para fazer isso:

1. Edit the landing page properties accessed via the ![](assets/edit_darkgrey-24px.png) icon in the landing page dashboard, and display the **[!UICONTROL Job]** parameters.

   ![](assets/lp_edit_properties_button.png)

1. Under the **[!UICONTROL Specific actions]** section, select **[!UICONTROL Start sending message]** to determine the sending of an automatic message, for example to confirm subscription to a service. Você precisa selecionar um modelo de entrega de email.

   Observe que, se uma mensagem de confirmação já estiver configurada no nível de serviço, você não deve selecionar uma nesta tela para evitar o envio de várias mensagens de confirmação. Refer to [Configure a service](../../audiences/using/creating-a-service.md).

1. Create **[!UICONTROL Additional data]** to enable storing additional data when the landing page is being submitted. Esses dados não estão visíveis para pessoas que visitam a página. Somente os valores constantes são considerados.

   ![](assets/lp_parameters_6.png)

## Setting permissions and pre-loading data {#setting-permissions-and-pre-loading-data}

O acesso a uma página de aterrissagem pode ser restrito a visitantes identificados, que vêm de um link em uma mensagem enviada por campanha. Nesse caso, você pode pré-carregar seus dados na página de aterrissagem. Para fazer isso:

1. Edit the landing page properties accessed via the ![](assets/edit_darkgrey-24px.png) icon in the landing page dashboard, and display the **[!UICONTROL Access & loading]** parameters.

   ![](assets/lp_edit_properties_button.png)

1. Select **[!UICONTROL Preload visitor data]**.

   Se um visitante da página corresponde a um perfil no banco de dados, seus dados são exibidos nos campos do formulário que estão mapeados com os dados do banco de dados e os elementos de personalização da página de aterrissagem são considerados.

   ![](assets/lp_parameters_3.png)

Também é possível:

* Use the URL parameters to identify the visitors, using the **[!UICONTROL Authorize visitor identification via URL parameters]** option: then you must choose the loading key and map the filter parameters with the parameters of the corresponding URL.
* Authorize any visitor to access the landing page, using the **[!UICONTROL Authorize unidentified visitors]** option.

## Setting Google reCAPTCHA {#setting-google-recaptcha}

Você pode configurar o Google recaptcha V 3 com sua página inicial para protegê-la de spam e abuso causado por bots. Para poder usá-lo com a página de aterrissagem, primeiro é necessário criar uma conta externa. For more information on how to configure it, refer to this [section](../../administration/using/external-accounts.md#google-recaptcha-external-account).

Após a configuração da sua conta externa do Google recaptcha V 3, você pode adicioná-la à página de aterrissagem:

1. Before publishing your landing page, access the page properties accessed via the ![](assets/edit_darkgrey-24px.png) icon from you landing page dashboard.

   ![](assets/lp_parameters_google3.png)

1. Unfold the **[!UICONTROL Access & loading]** menu.
1. Check the **[!UICONTROL Use reCAPTCHA to protect your site from spam and abuse]** option.
1. Selecione a conta externa do Google recaptcha criada anteriormente.

   ![](assets/lp_parameters_google.png)

1. Click **[!UICONTROL Confirm]**.

Sua página inicial agora é configurada com o Google recaptcha, que pode ser visualizada na parte inferior da página.

![](assets/lp_parameters_google2.png)

O Google recaptcha retornará uma pontuação com base nas interações dos usuários com sua página. To check your score, connect to your [Google admin console](https://g.co/recaptcha/admin).
