---
title: Sobre as mensagens no aplicativo
description: Exibir mensagem ou alerta no aplicativo móvel com mensagens no aplicativo.
page-status-flag: nunca ativado
uuid: 6784cdfc-6db9-41dd-9fbb-2e756a5bcb5f
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: canais
content-type: referência
topic-tags: mensagens no aplicativo
discoiquuid: a4168cfb-22bf-4ab3-b9d8-6e76e1bdc055
context-tags: entrega,acionadores,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Sobre as mensagens no aplicativo{#about-in-app-messaging}

As mensagens no aplicativo são um canal de mensagens que permite exibir uma mensagem quando o usuário está ativo no aplicativo móvel. Esse tipo de mensagem é gratuito para notificações por push que são enviadas ao centro de notificações do telefone dos usuários. For more information on the push notification channel, refer to this [section](../../channels/using/about-push-notifications.md).

Este canal requer que os aplicativos móveis sejam integrados ao SDK da plataforma Adobe Experience. Esses aplicativos devem ser ativados no Adobe Experience Platform Launch antes de estarem disponíveis no Adobe Campaign para entregas no aplicativo.

![](assets/launch_campaign.png)

Para começar a enviar mensagens no aplicativo em aplicativos móveis que utilizam o SDK da plataforma Experience, é necessário atender aos seguintes pré-requisitos:

1. No Adobe Campaign, verifique se você pode acessar o **[!UICONTROL In-App]** canal. Se não conseguir acessar esses canais, entre em contato com a equipe da sua conta.

1. Para aproveitar casos de uso móvel no Adobe Campaign Standard com um aplicativo SDK da Experience Cloud, um aplicativo móvel deve ser criado no Adobe Experience Platform Launch e configurado no Adobe Campaign Standard. Para obter o guia passo a passo, consulte esta [página](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

1. Depois de configurada, você pode preparar sua mensagem no aplicativo. Para obter mais informações, consulte esta [página](../../channels/using/preparing-and-sending-an-in-app-message.md#preparing-your-in-app-message).

1. Em seguida, você pode decidir enviar uma mensagem [](../../channels/using/customizing-an-in-app-message.md) no aplicativo ou um tipo [de mensagem de notificação](../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type)Personalizando local.

1. Sua entrega está pronta para ser enviada. Para saber mais, consulte esta [página](../../channels/using/preparing-and-sending-an-in-app-message.md#sending-your-in-app-message).

**Conteúdo relacionado:**

* [Relatório no aplicativo](../../reporting/using/in-app-report.md)
* [Perguntas frequentes sobre push e no aplicativo](https://helpx.adobe.com/campaign/kb/push_inapp_faq.html)
* [Casos de uso móvel suportados no Adobe Campaign Standard](https://helpx.adobe.com/campaign/kb/configure-launch-rules-acs-use-cases.html)
