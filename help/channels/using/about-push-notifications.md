---
title: Sobre as notificações por push
description: Descubra as principais especificidades do canal de notificação por push no Adobe Campaign.
page-status-flag: never-activated
uuid: 961aaeb5-6948-4fd2-b8d7-de4510c10566
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: push-notifications
discoiquuid: 23b4212e-e878-4922-be20-50fb7fa88ae8
context-tags: mobileApp,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5ed46987a3778dfa100639de8be9b6d5ac5348b4

---


# Sobre as notificações por push{#about-push-notifications}

>[!CAUTION]
>
>A implementação da notificação por push deve ser executada por usuários especialistas. Se precisar de auxílio, entre em contato com seu executivo de conta da Adobe ou com os parceiros de serviços Professional. A notificação por push é um recurso opcional. Verifique seu contrato de licença e entre em contato com o executivo da sua conta para ativá-lo.

O Adobe Campaign permite que você envie notificações por push personalizadas e segmentadas para dispositivos móveis iOS e Android.

Essas mensagens são recebidas em aplicativos móveis que você configurou no Adobe Campaign, aproveitando o SDK da plataforma de experiência. Para obter mais informações sobre isso, consulte [Configuração de um aplicativo móvel usando SDKs](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html)da plataforma Adobe Experience.

In Adobe Campaign, mobile profile attributes data sent from mobile device are stored in **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** resource which allows you to define the data that you want to collect from your applications&#39; subscribers.

Esse recurso precisa ser estendido para coletar dados que você pretende enviar do dispositivo móvel para o Adobe Campaign. Para fazer isso, consulte esta [página](../../developing/using/extending-the-subscriptions-to-an-application-resource.md) para obter as etapas detalhadas.

Dois tipos de notificação por push estão disponíveis no Adobe Campaign:

* **[!UICONTROL Alert/Message/Badge]** as notificações de tipo permitem que você envie mensagens padrão baseadas em texto com conteúdo adicional (som, emblema, deep link etc.) que você pode definir na **[!UICONTROL Advanced options]** seção.

   Esses tipos de notificação permitem que você adicione um título e uma mensagem na qual você pode usar campos de personalização. Para personalizar sua mensagem, selecione o **[!UICONTROL Send push on profiles]** modelo.

* **[!UICONTROL Silent push]** as notificações de tipo são usadas para notificar silenciosamente o aplicativo sem qualquer mensagem ou conteúdo para o usuário final. Um caso típico de uso para esse tipo de mensagem seria tornar o aplicativo ciente de que há conteúdo disponível no servidor a ser baixado.

Algumas configurações específicas podem ser configuradas para definir o comportamento das notificações. Para obter mais informações, consulte [esta seção](../../channels/using/customizing-a-push-notification.md).

Como usuário especialista, para definir essas configurações específicas, consulte as [notas técnicas](https://helpx.adobe.com/campaign/kb/acs-article-list.html)do aplicativo móvel.

>[!NOTE]
>
>As leis sobre privacidade diferem de país para país. Alguns países exigem que você informe os usuários sobre os tipos de dados coletados por aplicativos móveis. Verifique as leis referentes aos aplicativos móveis em seu país. Certifique-se de que as notificações por push enviadas para aplicativos móveis atendam aos pré-requisitos e condições especificados pela Apple (Apple Push Notification Service) e Google (Google Cloud Messaging ou Firebase Cloud Messaging).

**Conteúdo relacionado:**

* [Preparação e envio de uma notificação por push](../../channels/using/preparing-and-sending-a-push-notification.md)
* [Criação de uma notificação por push multilíngue](../../channels/using/creating-a-multilingual-push-notification.md)
* [Relatório de notificação por push](../../reporting/using/push-notification-report.md)
* [Guia móvel do Campaign Standard](https://helpx.adobe.com/campaign/kb/acs-mobile.html)

## Pré-requisitos {#prerequisites}

>[!NOTE]
>Para aproveitar o recurso de notificação por push do Campaign, é necessário fornecer um certificado de push válido no formato .pem sem senhas.
Se você tiver um certificado p12 válido, poderá convertê-lo facilmente em um arquivo .pem usando recursos online.

Primeiro, para começar a enviar notificações por push, é necessário configurar seu aplicativo móvel usando os SDKs da plataforma Experience. Para obter mais informações, consulte esta [página](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

Antes de enviar suas notificações por push, você deve:

1. Verifique se você pode acessar o **[!UICONTROL Mobile app]** canal no Adobe Campaign.
1. Configure seu aplicativo móvel em:

   * Adobe Campaign
   * A interface do Adobe Mobile Services

1. Execute a configuração específica do aplicativo móvel:

   * Compacte o arquivo de configuração baixado da interface do Adobe Mobile Services com o aplicativo móvel.
   * Integre o Experience Cloud Mobile SDK ao seu aplicativo móvel.

1. Defina os dados que deseja coletar dos assinantes do aplicativo. Os assinantes do aplicativo móvel que têm um perfil no banco de dados do Adobe Campaign são reconciliados com base nos critérios definidos.

Depois de configurar seu aplicativo móvel, você pode começar a preparar e enviar suas mensagens no aplicativo. Para obter mais informações, consulte [Preparação e envio de uma notificação](../../channels/using/preparing-and-sending-a-push-notification.md)por push.
