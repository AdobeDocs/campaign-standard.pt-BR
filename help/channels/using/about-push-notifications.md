---
title: Sobre notificações por push
seo-title: Sobre notificações por push
description: Sobre notificações por push
seo-description: Descubra as principais especificidades do canal de notificação por push no Adobe Campaign.
page-status-flag: nunca ativado
uuid: 961 aaeb 5-6948-4 fd 2-b 8 d 7-de 4510 c 10566
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canais
content-type: reference
topic-tags: notificações por push
discoiquuid: 23 b 4212 e-e 878-4922-be 20-50 fb 7 fa 88 ae 8
context-tags: Mobileapp, visão geral
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 80e65c3fedc5452105c296144a683948daa69150

---


# About push notifications{#about-push-notifications}

>[!CAUTION]
>
>A implementação de notificação por push deve ser executada por usuários de especialistas. Se precisar ser assistido, entre em contato com seu executivo de contas ou parceiro de serviços profissionais da Adobe. A notificação por push é um recurso opcional. Verifique seu contrato de licença e entre em contato com seu executivo de contas para ativá-lo.

O Adobe Campaign permite enviar notificações por push personalizadas e segmentadas para dispositivos móveis iOS e Android.

Essas mensagens são recebidas em aplicativos móveis configurados no Adobe Campaign, aproveitando o SDK da Experience Cloud Mobile SDK V 4 ou da Experience Platform SDK. For more information on this, refer to [Configuring a mobile application using SDK V4](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html) and [Configuring a mobile application using Adobe Experience Platform SDKs](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

In Adobe Campaign, mobile profile attributes data sent from mobile device are stored in **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** resource which allows you to define the data that you want to collect from your applications' subscribers.

Esse recurso precisa ser estendido para coletar dados que pretende enviar do dispositivo móvel para o Adobe Campaign. To do so, refer to this [page](../../developing/using/extending-the-subscriptions-to-an-application-resource.md) for the detailed steps.

Dois tipos de notificação por push estão disponíveis no Adobe Campaign:

* **[!UICONTROL Alert/Message/Badge]** permitem que você envie mensagens padrão baseadas em texto com conteúdo adicional (som, badge, deeplink, etc.) that you can define in the **[!UICONTROL Advanced options]** section.

   Esses tipos de notificação permitem que você adicione um título e uma mensagem na qual você pode usar campos de personalização. To be able to personalize your message, make sure you select the **[!UICONTROL Send push on profiles]** template.

* **[!UICONTROL Silent push]** as notificações de tipo são usadas para notificar silenciosamente o aplicativo sem nenhuma mensagem ou conteúdo para o usuário final. Um caso de uso típico para esse tipo de mensagem seria tornar o aplicativo ciente de que há conteúdo disponível no servidor para ser baixado.

Algumas configurações específicas podem ser configuradas para definir o comportamento das notificações. For more on this, refer to [this section](../../channels/using/customizing-a-push-notification.md).

As an expert user, to define these specific configurations, refer to the mobile app [technotes](https://helpx.adobe.com/campaign/kb/acs-article-list.html).

>[!NOTE]
>
>As leis relacionadas à privacidade diferem por país. Alguns países exigem que você informe aos usuários os tipos de dados coletados por aplicativos móveis. Verifique as leis pertencentes a aplicativos móveis em seu país. Certifique-se de que as notificações por push enviadas para aplicativos móveis cumpram os pré-requisitos e as condições especificadas pela Apple (Serviço de notificação por push da Apple) e Google (Google Cloud Messaging ou Firebase Cloud Messaging).

**Conteúdo relacionado:**

* [Como preparar e enviar uma notificação por push](../../channels/using/preparing-and-sending-a-push-notification.md)
* [Criação de uma notificação por push multilíngue](../../channels/using/creating-a-multilingual-push-notification.md)
* [Envio de uma notificação por push em um fluxo de trabalho](../../automating/using/push-notification-delivery.md)
* [Perguntas frequentes sobre push e no aplicativo](https://helpx.adobe.com/campaign/kb/push_inapp_faq.html)

## Prerequisites {#prerequisites}

>[!NOTE]
>Para aproveitar o recurso de notificação por push do Campaign, é necessário fornecer um certificado de push válido no formato. pem sem senhas.
Se você tiver um certificado p 12 válido, poderá convertê-lo facilmente em um arquivo. pem usando recursos online.

Primeiro, para poder começar a enviar notificações por push, você precisa configurar seu aplicativo móvel usando o SDK V 4. Você também pode configurar seu aplicativo móvel usando sdks da Experience Platform. For more on this, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

Antes de enviar suas notificações por push, você deve:

1. Make sure you can access the **[!UICONTROL Mobile app]** channel in Adobe Campaign.
1. Configure seu aplicativo móvel em:

   * Adobe Campaign
   * A interface do Adobe Mobile Services

1. Realize a configuração específica do aplicativo móvel:

   * Empacote o arquivo de configuração baixado da interface do Adobe Mobile Services com o aplicativo móvel.
   * Integre o SDK da Experience Cloud Mobile ao seu aplicativo móvel.

1. Defina os dados que deseja coletar pelos assinantes do aplicativo. Os assinantes do aplicativo móvel que possuem um perfil no banco de dados do Adobe Campaign são conciliados com base nos critérios definidos por você.

Depois de configurar seu aplicativo móvel, você pode começar a preparar e enviar suas mensagens no aplicativo. For more on this, refer to [Preparing and sending a push notification](../../channels/using/preparing-and-sending-a-push-notification.md).
