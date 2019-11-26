---
title: Configuração de uma página de aterrissagem
description: Saiba como configurar as propriedades de uma página de aterrissagem.
page-status-flag: never-activated
uuid: 5b222ea2-6628-457f-a618-bfc0e5eb93dd
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: 899c7152-f415-4df9-b4b4-5ff3470a4e32
context-tags: landingPage,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 95e01eb33097fc76caac3f4dd5f5591461b887cf

---


# Configuração de uma página de aterrissagem {#configuring-landing-page}

## Confirmar envio de página inicial {#confirm-a-landing-page-submission}

Quando uma página inicial é enviada por um visitante, você pode configurar as ações acionadas. Para fazer isso:

1. Edite as propriedades da página inicial acessadas pelo ![](assets/edit_darkgrey-24px.png) ícone no painel da página inicial e exiba os **[!UICONTROL Job]** parâmetros.

   ![](assets/lp_edit_properties_button.png)

1. Na **[!UICONTROL Specific actions]** seção, selecione **[!UICONTROL Start sending message]** para determinar o envio de uma mensagem automática, por exemplo, para confirmar a assinatura de um serviço. Você precisa selecionar um modelo de entrega de email.

   Observe que se uma mensagem de confirmação já estiver configurada no nível de serviço, você não deve selecionar uma nessa tela para evitar o envio de várias mensagens de confirmação. Consulte [Configurar um serviço](../../audiences/using/creating-a-service.md).

1. Crie **[!UICONTROL Additional data]** para permitir o armazenamento de dados adicionais quando a página de aterrissagem estiver sendo enviada. Esses dados não estão visíveis para as pessoas que visitam a página. Somente valores constantes são considerados.

   ![](assets/lp_parameters_6.png)

## Vincular uma página de aterrissagem a um serviço {#linking-a-landing-page-to-a-service}

Você pode vincular um formulário a um serviço para que os perfis possam se inscrever em um serviço específico ao validar as páginas iniciais.

Os parâmetros para vincular uma página de aterrissagem permitem especificar o tipo de ação executada e se a página de aterrissagem está especificamente vinculada a um único serviço ou se é genérica.

Para selecionar o serviço a ser vinculado, é necessário:

1. Edite as propriedades da página inicial acessadas pelo ![](assets/edit_darkgrey-24px.png) ícone no painel da página inicial e exiba os **[!UICONTROL Job]** parâmetros.

   ![](assets/lp_edit_properties_button.png)

1. Escolha **[!UICONTROL Subscription]** na lista **[!UICONTROL Specific actions]** suspensa.

   ![](assets/lp_parameters_5.png)

1. Selecione **[!UICONTROL Specific service]** para vincular a página de aterrissagem a um único serviço. Não selecione essa opção se desejar usar vários serviços com a página de aterrissagem.

   Use a **[!UICONTROL Specified service in the URL]** opção para permitir que a página de aterrissagem seja usada para vários serviços. Portanto, é necessário consultar a página de aterrissagem ao configurar o serviço.

## Configuração de permissões e pré-carregamento de dados {#setting-permissions-and-pre-loading-data}

O acesso a uma página de aterrissagem pode ser restrito a visitantes identificados, que vêm de um link em uma mensagem enviada pelo Campaign, por exemplo, ou a uma unidade organizacional específica.
No caso de visitantes identificados, é possível pré-carregar seus dados na página de aterrissagem. Para fazer isso:

1. Edite as propriedades da página inicial acessadas pelo ![](assets/edit_darkgrey-24px.png) ícone no painel da página inicial e exiba os **[!UICONTROL Access & loading]** parâmetros.

   ![](assets/lp_edit_properties_button.png)

1. Select **[!UICONTROL Preload visitor data]**.

   Se um visitante da página corresponde a um perfil no banco de dados, seus dados são exibidos nos campos do formulário que são mapeados com os dados do banco de dados e os elementos de personalização da página inicial são considerados.

   ![](assets/lp_parameters_3.png)

Você também pode:

* Use os parâmetros de URL para identificar os visitantes, usando a **[!UICONTROL Authorize visitor identification via URL parameters]** opção: em seguida, você deve escolher a chave de carregamento e mapear os parâmetros de filtro com os parâmetros do URL correspondente.
* Autorize qualquer visitante a acessar a página de aterrissagem usando a **[!UICONTROL Authorize unidentified visitors]** opção.

As páginas iniciais também podem ser vinculadas a uma unidade organizacional. Isso definirá o acesso dos usuários às diferentes páginas iniciais. Para atribuir uma unidade organizacional:

1. Acesse as propriedades da página inicial por meio do **[!UICONTROL Edit properties]** ícone.

   ![](assets/lp_parameters_google3.png)

1. Desdobre o **[!UICONTROL Access authorization]**.

1. Clique no menu suspenso e selecione sua unidade organizacional. Para obter mais informações sobre como criar a unidade organizacional, consulte esta [página](../../administration/using/organizational-units.md).

   ![](assets/lp_org_unit_2.png)

1. Os campos **[!UICONTROL Created by]**, **[!UICONTROL Created]** e **[!UICONTROL Access authorization]** e **[!UICONTROL Last modified]** são automaticamente concluídos.

1. Clique em **[!UICONTROL Confirm]** e em **[!UICONTROL Save]**.

Sua página inicial agora só pode ser acessada e gerenciada por usuários na unidade organizacional escolhida.

![](assets/lp_org_unit_3.png)

## Configuração do Google reCAPTCHA {#setting-google-recaptcha}

Você pode configurar o Google reCAPTCHA V3 com sua página inicial para protegê-lo de spam e abuso causado por bots. Para poder usá-lo com sua página de aterrissagem, primeiro é necessário criar uma conta externa. Para obter mais informações sobre como configurá-lo, consulte esta [seção](../../administration/using/external-accounts.md#google-recaptcha-external-account).

Depois que sua conta externa do Google reCAPTCHA V3 for configurada, você poderá adicioná-la à sua página inicial:

1. Antes de publicar sua página inicial, acesse as propriedades da página acessadas pelo ![](assets/edit_darkgrey-24px.png) ícone do painel da página de aterrissagem.

   ![](assets/lp_parameters_google3.png)

1. Desdobre o **[!UICONTROL Access & loading]** menu.
1. Marque a **[!UICONTROL Use reCAPTCHA to protect your site from spam and abuse]** opção.
1. Selecione sua conta externa do Google reCAPTCHA criada anteriormente.

   ![](assets/lp_parameters_google.png)

1. Click **[!UICONTROL Confirm]**.

Sua página inicial agora está configurada com o Google reCAPTCHA, que pode ser visto na parte inferior da página.

![](assets/lp_parameters_google2.png)

O Google reCAPTCHA retornará uma pontuação com base nas interações dos usuários com sua página. Para verificar sua pontuação, conecte-se ao seu console [de administração do](https://g.co/recaptcha/admin)Google.
