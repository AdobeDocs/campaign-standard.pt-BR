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
source-git-commit: f9632e88b49c2280c76e709376cfb7a7a27abc1f
workflow-type: tm+mt
source-wordcount: '1280'
ht-degree: 6%

---


# Sobre as notificações por push{#about-push-notifications}

>[!CAUTION]
>
>A implementação da notificação por push deve ser executada por usuários especialistas. Se precisar de auxílio, entre em contato com seu executivo de conta da Adobe ou com os parceiros de serviços Professional. A notificação por push é um recurso opcional. Verifique seu contrato de licença e entre em contato com o executivo da sua conta para ativá-lo.

O Adobe Campaign permite enviar notificações por push personalizadas e segmentadas para dispositivos móveis iOS e Android.

Essas mensagens são recebidas em aplicativos móveis que você configurou no Adobe Campaign, aproveitando o SDK do Experience Platform. Para obter mais informações sobre isso, consulte [Configuração de um aplicativo móvel usando SDKs](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html)Adobe Experience Platform.

In Adobe Campaign, mobile profile attributes data sent from mobile device are stored in **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** resource which allows you to define the data that you want to collect from your applications&#39; subscribers.

Esse recurso precisa ser estendido para coletar dados que você pretende enviar do dispositivo móvel para o Adobe Campaign. Para fazer isso, consulte esta [página](../../developing/using/extending-the-subscriptions-to-an-application-resource.md) para obter as etapas detalhadas.

Dois tipos de notificação por push estão disponíveis no Adobe Campaign:

* **[!UICONTROL Alert/Message/Badge]** as notificações de tipo permitem que você envie mensagens padrão baseadas em texto com conteúdo adicional (som, emblema, deep link etc.) que você pode definir na **[!UICONTROL Advanced options]** seção.

   Esses tipos de notificação permitem que você adicione um título e uma mensagem na qual você pode usar campos de personalização. Para personalizar sua mensagem, selecione o **[!UICONTROL Send push on profiles]** modelo.

* **[!UICONTROL Silent push]** as notificações de tipo são usadas para notificar silenciosamente o aplicativo sem qualquer mensagem ou conteúdo para o usuário final. Um caso típico de uso para esse tipo de mensagem seria tornar o aplicativo ciente de que há conteúdo disponível no servidor a ser baixado.

Algumas configurações específicas podem ser configuradas para definir o comportamento das notificações. Para obter mais informações, consulte [esta seção](../../channels/using/customizing-a-push-notification.md).

Como usuário especialista, para definir essas configurações específicas, consulte as [notas técnicas](https://helpx.adobe.com/br/campaign/kb/acs-article-list.html)do aplicativo móvel.

>[!NOTE]
>
>As leis sobre privacidade diferem de país para país. Alguns países exigem que você informe os usuários sobre os tipos de dados coletados por aplicativos móveis. Verifique as leis referentes aos aplicativos móveis em seu país. Certifique-se de que as notificações por push enviadas para aplicativos móveis atendam aos pré-requisitos e condições especificados pela Apple (Apple Push Notification Service) e Google (Google Cloud Messaging ou Firebase Cloud Messaging).

**Conteúdo relacionado:**

* [Preparação e envio de uma notificação por push](../../channels/using/preparing-and-sending-a-push-notification.md)
* [Criação de uma notificação por push multilíngue](../../channels/using/creating-a-multilingual-push-notification.md)
* [Relatório de notificação por push](../../reporting/using/push-notification-report.md)
* [Guia móvel Campaign Standard](https://helpx.adobe.com/br/campaign/kb/acs-mobile.html)

## Pré-requisitos {#prerequisites}

>[!NOTE]
>Para aproveitar o recurso de notificação por push da Campanha, é necessário fornecer um certificado de push válido no formato .pem sem senhas.
Se você tiver um certificado p12 válido, poderá convertê-lo facilmente em um arquivo .pem usando recursos online.

Antes de enviar suas notificações por push, você deve:

1. No Adobe Campaign, verifique se você pode acessar o **[!UICONTROL Push notification]** canal. Se não conseguir acessar esses canais, entre em contato com a equipe da sua conta.

1. Verifique se o usuário tem as permissões necessárias no Adobe Campaign Standard e no Experience Platform Launch.

1. No Experience Platform Launch, crie uma propriedade móvel. Para obter mais informações, consulte [Configurar uma propriedade](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)móvel.

1. No Experience Platform Launch, instale a **[!UICONTROL Adobe Campaign Standard]** extensão.

1. No Adobe Campaign Standard, configure a propriedade mobile que você criou no Experience Platform Launch. Para obter mais informações, consulte [Configuração do aplicativo Experience Platform Launch no Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#SettingupyourAdobeExperiencePlatformLaunchapplicationinAdobeCampaign).

1. Adicione a configuração específica do canal à configuração do aplicativo móvel. Para obter mais informações, consulte Configuração do aplicativo específico para o [Canal](../../administration/using/configuring-a-mobile-application.md#channel-specific-config).

1. Para suportar implementações de casos de uso móvel, consulte as instruções detalhadas sobre extensões, regras de Experience Platform Launch e a implementação do SDK em casos de uso do [Mobile suportados no Adobe Campaign Standard usando os SDKs](https://helpx.adobe.com/campaign/kb/configure-launch-rules-acs-use-cases.html)do Adobe Experience Platform.

## Perguntas frequentes sobre notificações por push {#push-faq}

### Quais seriam algumas recomendações de recursos úteis para saber mais sobre o canal de push? {#resource-push}

Confira os recursos abaixo:

* [Tutoriais em vídeo](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/mobile/push/creating-a-push-notification.html)
* [Documentação do produto](../../channels/using/about-push-notifications.md)
* Configurar usando a [documentação do AEP SDK](../../administration/using/configuring-a-mobile-application.md)
* [Página da comunidade](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-standard/ct-p/adobe-campaign-standard-community)

### O que devo fazer para adquirir um token de push na Campanha? {#push-token-acquisition}

Verifique se a equipe de provisionamento concluiu o provisionamento do canal de push no Adobe Campaign Standard. Implemente a API setPushIdentifier do SDK. Para obter mais informações, consulte esta [página](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#set-up-push-messaging).

### Depois que eu tiver o token de push e o ECID na Campanha, o que mais preciso para enviar uma notificação por push? {#sending-push}

Os clientes precisam fornecer um certificado Push válido no formato .pem para enviar uma notificação Push. Você não precisa de uma senha para este certificado.

### E se eu tiver um certificado .p12 em vez de um certificado .pem? {#certificates}

Você pode converter um certificado .p12 em um certificado .pem executando o comando abaixo no terminal. Há vários recursos on-line também disponíveis para instruções de conversão.

```
openssl pkcs12 -in pushcert.p12 -out pushcert.pem -nodes -clcerts
```

### Como faço para saber se o upload do certificado é bem-sucedido? {#certificate-upload}

Você verá a seguinte mensagem.

![](assets/faq_2.png)

### É possível fazer upload de certificados de produção e sandbox ao mesmo tempo para aplicativos iOS (N/A para Android)? {#prod-sandbox-certificate}

Não, os aplicativos funcionarão na caixa de proteção ou no modo de produção e não poderão ser alterados para o outro (ou seja, caixa de proteção para o aplicativo de produção) depois da configuração. Recomendamos que você teste seu aplicativo no modo de caixa de proteção primeiro e depois faça a transição para o modo de produção.

Para mudar para o modo de produção, será necessário criar outro aplicativo. Certifique-se também de não marcar a caixa de seleção da caixa de proteção e de fazer upload de um certificado de produção.

### Posso carregar as credenciais do iOS e do Android ao mesmo tempo? {#ios-android-credentials}

Sim, a Campanha suporta ambas as plataformas ao mesmo tempo e permite que você carregue credenciais para ambas as plataformas.

### Carreguei certificados de push com êxito, mas nenhuma mensagem de push é enviada. {#push-certificates-upload}

Certifique-se de que seus certificados de push sejam válidos testando-os [aqui](https://pushtry.com/).

### Posso enviar notificações por push com êxito do pushtry.com, mas não por Campanha. {#push-not-sending}

Verifique se você está seguindo as instruções de carga de push fornecidas [aqui](../../administration/using/push-payload.md).

Observe que para Android, a Campanha suporta apenas a carga de dados e não a carga de notificação

### Configurei um aplicativo na seção Administração do Adobe Campaign Standard, mas o aplicativo móvel não está disponível nas propriedades do Delivery. {#mobile-app-unavailable}

Um aplicativo precisa ter um certificado de push válido carregado também antes de poder ser disponibilizado nas propriedades do delivery.

### Tentei todas as instruções nesta página e, no entanto, não consigo enviar o Push da Campanha. {#push-troubleshoot}

Abra um ticket de atendimento ao cliente.

### As notificações por push são entregues pela Campanha, mas o arquivo de mídia não é exibido.{#media-file-unavailable}

Os desenvolvedores de aplicativos móveis precisam lidar com o suporte para arquivos de mídia no aplicativo. Às vezes, a largura de banda da rede também pode impedir a renderização de um arquivo de mídia. Consulte esta [página](../../administration/using/image-push-notification.md) para obter mais ponteiros.

### O que devo fazer para habilitar o relatórios de push na Campanha? {#push-reporting-enable}

Siga as etapas abaixo:

* Configure um postback de rastreamento de push. Instructions can be found [here](../../administration/using/configuring-a-mobile-application.md).
* Implemente a API trackAction do Mobile Core. Refer to this [page](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference) for more information.

Instruções mais detalhadas podem ser encontradas nesta [página](../../administration/using/push-tracking.md).

### Quais relatórios estão disponíveis para o canal de push? {#push-report-available}

Um relatório pronto para uso está disponível no Adobe Campaign para canal de push. Refer to this [documentation](../../reporting/using/push-notification-report.md).

Consulte esta [página](../../reporting/using/indicator-calculation.md#push-notification-delivery) para entender como cada métrica de push é calculada.

### Os deep links são suportados em mensagens de push e no aplicativo? {#deeplink-push}

Sim, os deep links são suportados em mensagens de push. Os deep links devem incluir:

* idioma que declara que o rastreamento de delivery precisa ser desativado para que os deep links funcionem.
* Appsflyer com Branch como parceiros que podem fazer o rastreamento de deep link. Para obter mais informações sobre a integração de Ramificação e Adobe Campaign Standard, consulte esta [página](https://help.branch.io/using-branch/docs/adobe-campaign-standard-1).