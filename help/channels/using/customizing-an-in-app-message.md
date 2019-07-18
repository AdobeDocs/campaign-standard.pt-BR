---
title: Personalização de uma mensagem no aplicativo
seo-title: Personalização de uma mensagem no aplicativo
description: Personalização de uma mensagem no aplicativo
seo-description: Saiba como personalizar suas mensagens no aplicativo com várias opções.
page-status-flag: nunca ativado
uuid: 1 d 9 c 08 ed -4 de 5-440 d-bf 51-4 a 437 eec 67 d 5
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canais
content-type: reference
topic-tags: in-app-messaging
discoiquuid: c 9 c 3 e 033-e 319-447 b -8 d 87-ff 7 dd 4941876
context-tags: entrega, inappcontent, voltar
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6df0e764750a31f29d6fe3ec4d92e19b3f07f728

---


# Customizing an In-App message{#customizing-an-in-app-message}

Para ajustar a mensagem no aplicativo, o Adobe Campaign permite acessar um conjunto de opções avançadas durante a criação de um aplicativo.

O editor de conteúdo dentro do aplicativo permite escolher entre dois modos de mensagens no aplicativo:

* [Modelo de mensagem](../../channels/using/customizing-an-in-app-message.md#customizing-with-a-message-template): este modelo permite que você personalize totalmente o seu aplicativo com imagens ou vídeos e botões de ação.
* [Mensagem personalizada](../../channels/using/customizing-an-in-app-message.md#customizing-with-a-custom-html-message): este modelo permite importar HTML personalizado.

![](assets/inapp_customize_1.png)

**Tópicos relacionados:**

* [Enviar sua mensagem no aplicativo](../../channels/using/preparing-and-sending-an-in-app-message.md#sending-your-in-app-message)
* [Relatório no aplicativo](../../reporting/using/in-app-report.md)

## Customizing with a message template {#customizing-with-a-message-template}

### Layout {#layout}

The **[!UICONTROL Layout]** drop-down provides you with four different options to choose from depending on your messaging needs:

* **[!UICONTROL Full page]**: Esse tipo de layout cobre toda a tela de seus dispositivos de público-alvo.

   Suporta mídia (imagem, vídeo), texto e componentes de botão.

* **[!UICONTROL Large modal]**: Esse layout aparece em uma janela de estilo de alerta grande, enquanto seu aplicativo ainda está visível em segundo plano.

   Suporta mídia (imagem, vídeo), texto e componentes de botão.

* **[!UICONTROL Small modal]**: Esse layout aparece como uma pequena janela de tipo de alerta, seu aplicativo ainda está visível em segundo plano.

   Suporta mídia (imagem, vídeo), texto e componentes de botão.

* **[!UICONTROL Alert]**: Esse tipo de layout aparece como uma mensagem de alerta nativa do SO.

   Ele pode suportar apenas os componentes de texto e botão.

* **[!UICONTROL Local notification]**: Esse tipo de layout aparece como uma mensagem de banner.

   Ele só pode suportar som, texto e destino. For more on local notification, refer to [Customizing a local notification message type](../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type).

Cada tipo de layouts pode ser visualizado em diferentes dispositivos como telefone, tablet, plataforma por exemplo Android ou iOS e orientação, por exemplo, paisagem ou retrato na janela direita do editor de conteúdo.

![](assets/inapp_customize_4.png)

### Media {#media}

The **[!UICONTROL Media]** drop-down allows you to add media to your In-App message to create a compelling experience for end user.

1. Select your **[!UICONTROL Media Type]** between image and video.
1. For the **[!UICONTROL Image]** media type, enter your URL in the **[!UICONTROL Media URL]** field based on the supported formats.

   If needed, you can also enter the path to a **[!UICONTROL Bundled image]** which can be used if the device is offline.

   ![](assets/inapp_customize_5.png)

1. For the **[!UICONTROL Video]** media type, enter your URL in the **[!UICONTROL Media URL]** field.

   Then, enter your **[!UICONTROL Video poster]** to be used while the video is downloading on the audience devices or until users tap the play button.

   ![](assets/inapp_customize_6.png)

### Text {#text}

Se necessário, você também pode adicionar um título de mensagem e conteúdo à sua mensagem no aplicativo. Para personalizar melhor sua mensagem no aplicativo, você pode adicionar diferentes campos de personalização, blocos de conteúdo e texto dinâmico ao seu conteúdo.

1. In the **[!UICONTROL Text]** drop-down, add a title in the **[!UICONTROL Message title]** field.

   ![](assets/inapp_customize_9.png)

1. Add your content in the **[!UICONTROL Message content]** field.
1. To further personalize your text, click the ![](assets/edit_darkgrey-24px.png) icon to add personalization fields.

   ![](assets/inapp_customize_8.png)

1. Digite o conteúdo da mensagem e adicione seus campos de personalização, se necessário.

   For more information on personalization field, refer to this [section](../../designing/using/inserting-a-personalization-field.md).

   ![](assets/inapp_customize_10.png)

1. Verifique o conteúdo da mensagem na janela de visualização.

   ![](assets/inapp_customize_11.png)

### Buttons {#buttons}

Você pode adicionar até dois botões à mensagem no aplicativo.

1. In the **[!UICONTROL Buttons]** drop-down, enter the text of your first button in the **[!UICONTROL Primary]** category.

   ![](assets/inapp_customize_12.png)

1. Choose which of the two actions **[!UICONTROL Dismiss]** and **[!UICONTROL Redirect]** will be assigned to your primary button.
1. In the **[!UICONTROL Secondary]** category, add a second button to your In-App if needed by entering your text.
1. Selecione a ação associada ao segundo botão.
1. If you chose the **[!UICONTROL Redirect]** action, enter your web URL or deeplink in the **[!UICONTROL Destination URL]** field.

   ![](assets/inapp_customize_13.png)

1. Enter your web URL or deeplink in the **[!UICONTROL Destination URL]** field, if you chose the **[!UICONTROL Redirect]** action,
1. Verifique o conteúdo da mensagem na janela de visualização ou clique no botão Visualizar.

   Refer to the [Previewing the In-App message](../../channels/using/customizing-an-in-app-message.md#previewing-the-in-app-message) page.

   ![](assets/inapp_customize_11.png)

### Settings {#settings}

1. In the **[!UICONTROL Settings]** category, select your background color between light and dark.
1. Choose to display or not a close button with the **[!UICONTROL Show close button]** option to provide users a way to dismiss the In-App message.
1. Select if your button alignment will be horizontal or vertical with the **[!UICONTROL Button alignment]** option.
1. Escolha se a mensagem no aplicativo pode ser fechada automaticamente ou não após alguns segundos.

   ![](assets/inapp_customize_7.png)

## Customizing a local notification message type {#customizing-a-local-notification-message-type}

As notificações locais podem ser acionadas somente por um aplicativo em um determinado momento e dependendo de um evento. Eles alertarão os usuários a que algo está acontecendo em seu aplicativo mesmo sem ter acesso à Internet.

Para personalizar uma notificação local:

1. From your **[!UICONTROL Content]** page, select **[!UICONTROL Local notification]** in the **[!UICONTROL Layout]** category

   ![](assets/inapp_customize_17.png)

1. Under the **[!UICONTROL Text]** category, type down your **[!UICONTROL Message title]** and **[!UICONTROL Message content]**.

   ![](assets/inapp_customize_18.png)

1. Under the **[!UICONTROL Advanced option]** category, in the **[!UICONTROL Wait to display]** field, choose how long in seconds your local notification will be displayed on screen once your event is triggered.
1. In the **[!UICONTROL Sound]** field, enter the filename of the sound file, without the extension, to be played by the mobile device when the local notification is received.

   O arquivo de som é reproduzido ao entregar a notificação se o arquivo estiver definido no pacote do aplicativo móvel. Caso contrário, o som padrão do dispositivo será reproduzido.

   ![](assets/inapp_customize_19.png)

1. Specify a destination to redirect your users when they interact with your local notification in the **[!UICONTROL Deeplink URL]** field.
1. Para transmitir dados personalizados na carga na forma de um par de valor chave, você pode adicionar campos personalizados à notificação local. In the **[!UICONTROL Custom fields]** category, click the **[!UICONTROL Create an element]** button.
1. Enter your **[!UICONTROL Keys]** then the **[!UICONTROL Values]** associated with each key.

   Observe que a manipulação e a finalidade dos campos personalizados está totalmente no aplicativo móvel.

1. In the **[!UICONTROL Apple options]** category, fill in the **[!UICONTROL Category]** fields to add a category ID for custom actions if available in your Apple mobile application.

## Customizing with a custom HTML message {#customizing-with-a-custom-html-message}

>[!NOTE]
>
>A mensagem HTML personalizada não suporta a personalização de conteúdo.

The **[!UICONTROL Custom message]** mode allows you to directly import one of your pre-configured HTML message.

Para fazer isso, basta arrastar e soltar ou selecionar o arquivo do computador.

Your file must have a specific layout which can be found by clicking the **Download the sample file** option.

![](assets/inapp_customize_16.png)

Você também pode encontrar uma lista de requisitos de HTML personalizados para uma importação bem-sucedida no Adobe Campaign.

![](assets/inapp_customize_3.png)

Após a importação do HTML, você pode encontrar uma visualização do arquivo em diferentes dispositivos na janela de visualização.

## Previewing the In-App message {#previewing-the-in-app-message}

Antes de enviar a mensagem no aplicativo, você pode testar com seus perfis de teste para verificar o que será visto pelo público-alvo quando eles receberem sua entrega.

1. Click the **[!UICONTROL Preview]** button.

   ![](assets/inapp_sending_2.png)

1. Click the **[!UICONTROL Select a test profile]** button and select one of your test profiles to start previewing your delivery. For more information on test profiles, refer to this [section](../../sending/using/managing-test-profiles-and-sending-proofs.md).
1. Verifique a mensagem em dispositivos diferentes, como Android, telefones para iphone ou até mesmo tablets. Você também pode verificar se os campos de personalização estão recuperando os dados corretos.

   ![](assets/inapp_sending_3.png)

1. Agora você pode enviar sua mensagem e medir seu impacto com os relatórios de entrega. For more on reporting, refer to [this section](../../reporting/using/in-app-report.md).

