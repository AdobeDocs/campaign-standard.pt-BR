---
title: Sobre mensagens no aplicativo
seo-title: Sobre mensagens no aplicativo
description: Sobre mensagens no aplicativo
seo-description: Exibir mensagem ou alerta no aplicativo móvel com mensagens no aplicativo.
page-status-flag: nunca ativado
uuid: 6784 cdfc -6 db 9-41 dd -9 fbb -2 e 756 a 5 bcb 5 f
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canais
content-type: reference
topic-tags: in-app-messaging
discoiquuid: a 4168 cfb -22 bf -4 ab 3-b 9 d 8-6 e 76 e 1 bdc 055
context-tags: entrega, acionadores, voltar
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 74f037ba618639ab61edfb8311adeb44a7a99ebd

---


# About In-App messaging{#about-in-app-messaging}

As mensagens no aplicativo são um canal de mensagens que permite exibir uma mensagem quando o usuário está ativo no aplicativo móvel. Este tipo de mensagem é gratuito para enviar notificações que são enviadas para a central de notificações do telefone dos usuários. For more information on the push notification channel, refer to this [section](../../channels/using/about-push-notifications.md).

Este canal requer que aplicativos móveis sejam integrados com o SDK da Adobe Experience Platform. Esses aplicativos precisam ser ativados na Adobe Experience Platform Launch antes de serem disponibilizados no Adobe Campaign para entregas no aplicativo.

![](assets/launch_campaign.png)

Para começar a enviar mensagens no aplicativo em aplicativos móveis aproveitando o SDK da Experience Platform, você precisa atender a estes pré-requisitos:

1. In Adobe Campaign, make sure you can access the **[!UICONTROL In-App]** channel. Se não conseguir acessar esses canais, entre em contato com sua equipe de conta.
1. Na Experience Platform Launch, crie o aplicativo móvel criando uma propriedade móvel e instrumento seu aplicativo móvel com o SDK da Experience Platform SDK.

   For more information, refer to the [Set up a mobile property](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property) section in Adobe Launch documentation.

1. In Experience Platform Launch, install the **[!UICONTROL Adobe Campaign Standard]** extension for your mobile application in Experience Platform Launch:

   For more on extensions, refer to the [Configure Campaign Standard Extension in Experience Platform Launch](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard) in Experience Platform Launch documentation.

1. In Experience Platform Launch, configure rules and data elements for your application, see [Configuring your application in Experience Platform Launch](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Step1Createdataelements)

1. Configure your Experience Platform Launch application in Adobe Campaign Standard, see [Setting up your Experience Platform Launch application in Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#SettingupyourAdobeLaunchapplicationinAdobeCampaign) .

To learn how to configure Experience Platform SDKs, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

**Conteúdo relacionado:**

* [Como preparar e enviar uma mensagem no aplicativo](../../channels/using/preparing-and-sending-an-in-app-message.md)
* [Personalização de uma mensagem no aplicativo](../../channels/using/customizing-an-in-app-message.md)
* [Personalizar um tipo de mensagem de notificação local](../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type)
* [Envio de uma mensagem no aplicativo dentro de um fluxo de trabalho](../../automating/using/in-app-delivery.md)
* [Perguntas frequentes sobre push e no aplicativo](https://helpx.adobe.com/campaign/kb/push_inapp_faq.html)