---
title: Configuração de uma página de destino
description: Saiba como configurar as propriedades de uma página de destino.
audience: channels
content-type: reference
topic-tags: landing-pages
context-tags: landingPage,main
feature: Landing Pages
role: User
level: Intermediate
exl-id: 0b9795e9-83e6-4399-a3b1-fc69081f6a82
TQID: https://experienceleague.adobe.com/WGJMzhZXIgXMEioDtea5foDs7hRh70WOLG3XV41irvw
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: d095671a-1355-40aa-8b5f-06c33c68080bid: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 656
ht-degree: 93%

---

# Configuração de uma página de destino {#configuring-landing-page}

## Confirmar o envio de uma landing page {#confirm-a-landing-page-submission}

Quando uma página de destino é enviada por um visitante, você pode configurar as ações acionadas. Para fazer isso:

1. Edite as propriedades de página de destino acessadas pelo ícone ![](assets/edit_darkgrey-24px.png) no painel da página de destino e exiba os parâmetros **[!UICONTROL Job]**.

   ![](assets/lp_edit_properties_button.png)

1. Na seção **[!UICONTROL Specific actions]**, selecione **[!UICONTROL Start sending message]** para determinar o envio de uma mensagem automática, por exemplo, para confirmar a assinatura em um serviço. Em seguida, selecione um modelo da entrega de email.

   Observe que, se uma mensagem de confirmação já estiver configurada no nível de serviço, você não deverá selecionar nenhuma nessa tela para evitar o envio de várias mensagens de confirmação. Consulte [Configurar um serviço](../../audiences/using/creating-a-service.md).

1. Crie **[!UICONTROL Additional data]** para permitir o armazenamento de dados adicionais quando a página de destino estiver sendo enviada. Esses dados não estão visíveis aos visitantes da página. Somente valores constantes são considerados.

   ![](assets/lp_parameters_6.png)

## Vinculação de uma landing page a um serviço {#linking-a-landing-page-to-a-service}

Você pode vincular um formulário a um serviço para que os perfis possam assinar um serviço específico ao validar as páginas de destino.

Os parâmetros para a vinculação de uma página de destino permitem definir o tipo de ação executada e se a página de destino é especificamente vinculada a um único serviço ou se é genérica.

Para selecionar o serviço a ser vinculado, você precisa:

1. Edite as propriedades de página de destino acessadas pelo ícone ![](assets/edit_darkgrey-24px.png) no painel da página de destino e exiba os parâmetros **[!UICONTROL Job]**.

   ![](assets/lp_edit_properties_button.png)

1. Escolha **[!UICONTROL Subscription]** na lista suspensa **[!UICONTROL Specific actions]**.

   ![](assets/lp_parameters_5.png)

1. Selecione **[!UICONTROL Specific service]** para vincular a página de destino a um único serviço. Não selecione essa opção se quiser usar vários serviços com a página de destino.

   Use a opção **[!UICONTROL Specified service in the URL]** para permitir que a página de destino seja usada para vários serviços. Portanto, você deverá indicar a página de destino ao configurar o serviço.

## Configuração de permissões e dados de pré-carregamento {#setting-permissions-and-pre-loading-data}

O acesso a uma página de destino pode ser restrito aos visitantes identificados, que acessam um link em uma mensagem enviada pelo Campaign, por exemplo, ou a uma unidade organizacional específica.
No caso de visitantes identificados, você pode pré-carregar os dados deles na página de destino. Para fazer isso:

1. Edite as propriedades de página de destino acessadas pelo ícone ![](assets/edit_darkgrey-24px.png) no painel da página de destino e exiba os parâmetros **[!UICONTROL Access & loading]**.

   ![](assets/lp_edit_properties_button.png)

1. Selecione **[!UICONTROL Preload visitor data]**.

   Se um visitante da página corresponder a um perfil no banco de dados, os dados dele serão exibidos nos campos do formulário mapeados com os dados do banco de dados e os elementos de personalização da página de destino serão considerados.

   ![](assets/lp_parameters_3_temp.png)

Você também pode autorizar qualquer visitante a acessar a landing page, usando a opção **[!UICONTROL Authorize unidentified visitors]**.

<!--Use the URL parameters to identify the visitors, using the **[!UICONTROL Authorize visitor identification via URL parameters]** option: then you must choose the loading key and map the filter parameters with the parameters of the corresponding URL.-->

As páginas de destino também podem ser vinculadas a uma unidade organizacional. Isso definirá o acesso dos usuários às diferentes páginas de destino. Para atribuir uma unidade organizacional:

1. Acesse as propriedades da sua página de destino pelo ícone **[!UICONTROL Edit properties]**.

   ![](assets/lp_parameters_google3.png)

1. Expanda o **[!UICONTROL Access authorization]**.

1. Clique no menu suspenso e selecione sua unidade organizacional. Para saber mais sobre como criar uma unidade organizacional, consulte esta [página](../../administration/using/organizational-units.md).

   ![](assets/lp_org_unit_2.png)

1. Os campos **[!UICONTROL Created by]**, **[!UICONTROL Created]**, **[!UICONTROL Access authorization]** e **[!UICONTROL Last modified]** são automaticamente preenchidos.

1. Clique em **[!UICONTROL Confirm]** e em **[!UICONTROL Save]**.

Sua página de destino agora só pode ser acessada e gerenciada pelos usuários na unidade organizacional escolhida.

![](assets/lp_org_unit_3.png)

## Configuração do Google reCAPTCHA {#setting-google-recaptcha}

Você pode configurar o Google reCAPTCHA V3 com sua página de destino para protegê-la contra spam e abuso causado por bots. Para poder usá-lo com a página de destino, você precisa primeiro criar uma conta externa. Para saber mais sobre como configurá-lo, consulte esta [seção](../../administration/using/external-accounts.md#google-recaptcha-external-account).

Depois que sua conta externa do Google reCAPTCHA V3 for configurada, você poderá adicioná-la à página de destino:

1. Antes de publicar a página de destino, acesse as propriedades da página pelo ícone ![](assets/edit_darkgrey-24px.png) do painel da página de destino.

   ![](assets/lp_parameters_google3.png)

1. Expanda o menu **[!UICONTROL Access & loading]**.
1. Marque a opção **[!UICONTROL Use reCAPTCHA to protect your site from spam and abuse]**.
1. Selecione a conta externa do Google reCAPTCHA criada anteriormente.

   ![](assets/lp_parameters_google_temp.png)

1. Clique em **[!UICONTROL Confirm]**.

Sua página de destino agora está configurada com o Google reCAPTCHA, localizado na parte inferior da página.

![](assets/lp_parameters_google2.png)

O Google reCAPTCHA retornará uma pontuação com base nas interações dos usuários com sua página. Para verificar sua pontuação, conecte-se ao Admin Console do Google.
