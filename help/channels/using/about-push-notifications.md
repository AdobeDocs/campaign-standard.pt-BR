---
solution: Campaign Standard
product: campaign
title: Sobre as notificações por push
description: Descubra as principais especificidades do canal de notificação por push no Adobe Campaign.
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Push
role: Business Practitioner
level: Intermediate
exl-id: e61daed6-a0ec-49d8-b1ad-77590fafb496
source-git-commit: 7272d2ca2b499069e00a3ded1cb6693147c64dfc
workflow-type: tm+mt
source-wordcount: '1279'
ht-degree: 50%

---

# Sobre as notificações por push{#about-push-notifications}

>[!CAUTION]
>
>A implementação da notificação por push deve ser executada por usuários especialistas. Se precisar de auxílio, entre em contato com o executivo da sua conta da Adobe ou com o parceiros de serviços Professional. A notificação por push é um recurso opcional. Verifique seu contrato de licença e entre em contato com o executivo da sua conta para ativá-la.

O Adobe Campaign permite enviar notificações por push personalizadas e segmentadas para dispositivos móveis iOS e Android.

Essas mensagens são recebidas nos aplicativos móveis que você configurou no Adobe Campaign por meio do SDK da Experience Platform. Para saber mais, consulte [Configuração de um aplicativo móvel usando SDKs da Adobe Experience Platform](https://helpx.adobe.com/br/campaign/kb/configuring-app-sdk.html).

No Adobe Campaign, os dados de atributos do perfil móvel enviados de dispositivo móvel são armazenados no recurso **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]**, que permite definir os dados que você deseja coletar dos assinantes de aplicativos.

Esse recurso precisa ser estendido para coletar os dados que você pretende enviar do dispositivo móvel para o Adobe Campaign. Para fazer isso, consulte esta [página](../../developing/using/extending-the-subscriptions-to-an-application-resource.md) para conhecer as etapas detalhadas.

Dois tipos de notificações por push estão disponíveis no Adobe Campaign:

* As notificações do tipo **[!UICONTROL Alert/Message/Badge]** permitem enviar mensagens padrão baseadas em texto com conteúdo adicional (som, selo, deeplink etc.) que você pode definir na seção **[!UICONTROL Advanced options]**.

   Esses tipos de notificação permitem adicionar um título e uma mensagem na qual você pode usar campos de personalização. Para personalizar a mensagem, selecione o template **[!UICONTROL Send push on profiles]**.

* As notificações do tipo **[!UICONTROL Silent push]** são usadas para notificar silenciosamente o aplicativo sem qualquer mensagem ou conteúdo para o usuário final. Um caso de uso típico desse tipo de mensagem seria tornar o aplicativo ciente de que há conteúdo disponível a ser baixado do servidor.

Algumas configurações específicas podem ser configuradas para definir o comportamento das notificações. Para obter mais informações, consulte [esta seção](../../channels/using/customizing-a-push-notification.md).

Como usuário especialista, consulte as [notas técnicas](https://helpx.adobe.com/br/campaign/kb/acs-article-list.html) do aplicativo móvel para definir essas configurações específicas.

>[!NOTE]
>
>As leis de privacidade diferem de um país para outro. Alguns países exigem que você informe os usuários sobre os tipos de dados coletados pelos aplicativos móveis. Consulte as leis sobre aplicativos móveis do seu país. Verifique se as notificações por push enviadas para os aplicativos móveis atendem aos pré-requisitos e condições especificados pela Apple (serviço Apple Push Notification) e pelo Google (Google Cloud Messaging ou Firebase Cloud Messaging).

**Conteúdo relacionado:**

* [Preparação e envio de uma notificação por push](../../channels/using/preparing-and-sending-a-push-notification.md)
* [Criação de uma notificação por push multilíngue](../../channels/using/creating-a-multilingual-push-notification.md)
* [Relatório de notificação por push](../../reporting/using/push-notification-report.md)
* [Guia para Aplicativos de dispositivos móveis no Campaign Standard](https://helpx.adobe.com/br/campaign/kb/acs-mobile.html)

## Pré-requisitos {#prerequisites}

>[!NOTE]
>Para usar o recurso de notificação por push do Campaign, você precisa fornecer um certificado de push válido no formato .pem sem senhas.
>
>Se você tiver um certificado p12 válido, poderá convertê-lo facilmente em um arquivo .pem usando os recursos online.

Antes de enviar as notificações por push, você deve:

1. No Adobe Campaign, confirme se você pode acessar o canal **[!UICONTROL Push notification]**. Se não conseguir acessar esses canais, entre em contato com sua equipe de conta.

1. Verifique se o usuário tem as permissões necessárias no Adobe Campaign Standard e no Experience Platform Launch.

1. No Experience Platform Launch, crie uma propriedade móvel. Para saber mais, consulte [Configurar uma propriedade móvel](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property).

1. No Experience Platform Launch, instale a extensão **[!UICONTROL Adobe Campaign Standard]**.

1. No Adobe Campaign Standard, configure a propriedade móvel que você criou no Experience Platform Launch. Para saber mais, consulte [Configuração do aplicativo Experience Platform Launch no Adobe Campaign](https://helpx.adobe.com/br/campaign/kb/configuring-app-sdk.html#SettingupyourAdobeExperiencePlatformLaunchapplicationinAdobeCampaign).

1. Adicione a configuração específica do canal à configuração do aplicativo móvel. Para saber mais, consulte [Configuração do aplicativo específico do canal no Adobe Campaign](../../administration/using/configuring-a-mobile-application.md#channel-specific-config).

1. Para saber mais sobre as implementações dos casos de uso móveis, consulte as instruções detalhadas sobre extensões, as regras do Experience Platform Launch e a implementação do SDK em [Casos de uso móveis com suporte no Adobe Campaign Standard usando SDKs da Adobe Experience Platform](https://helpx.adobe.com/br/campaign/kb/configure-launch-rules-acs-use-cases.html).

## Perguntas frequentes sobre notificação por push {#push-faq}

### Quais seriam algumas recomendações úteis de recursos para saber mais sobre o canal de push? {#resource-push}

Confira os recursos abaixo:

* [Tutoriais em vídeo](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/communication-channels/mobile/push/creating-a-push-notification.html)
* [Documentação do produto](../../channels/using/about-push-notifications.md)
* Configurar usando o SDK do AEP [documentação](../../administration/using/configuring-a-mobile-application.md)
* [Página da comunidade](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-standard/ct-p/adobe-campaign-standard-community)

### O que preciso fazer para adquirir um token de push no Campaign? {#push-token-acquisition}

Certifique-se de que a equipe de provisionamento concluiu o provisionamento do canal de push no Adobe Campaign Standard. Implemente a API setPushIdentifier do SDK. Para obter mais informações, consulte esta [página](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#set-up-push-messaging).

### Depois que eu tiver o token de push e o ECID no Campaign, o que mais preciso para enviar uma notificação por push? {#sending-push}

Os clientes precisam fornecer um certificado Push válido no formato .pem para enviar uma notificação por push. Você não precisa de uma senha para este certificado.

### E se eu tiver um certificado .p12 em vez de um certificado .pem? {#certificates}

Você pode converter um certificado .p12 em um certificado .pem executando o comando abaixo no terminal. Há vários recursos online também disponíveis para instruções de conversão.

```
openssl pkcs12 -in pushcert.p12 -out pushcert.pem -nodes -clcerts
```

### Como faço para saber se o upload do certificado foi bem-sucedido? {#certificate-upload}

Você verá a seguinte mensagem.

![](assets/faq_2.png)

### É possível fazer upload de certificados de Produção e de Sandbox ao mesmo tempo para aplicativos iOS (N/A para Android)? {#prod-sandbox-certificate}

Não, os aplicativos funcionarão no modo de sandbox ou de produção e não poderão ser alterados para o outro (ou seja, sandbox para aplicativo de produção) após a configuração. Recomendamos que você teste seu aplicativo no modo sandbox primeiro e depois faça a transição para o modo de produção.

Para mudar para o modo de produção, será necessário criar outro aplicativo. Certifique-se também de não marcar a caixa de seleção sandbox e fazer upload de um certificado de produção.

### Posso fazer upload das credenciais do iOS e do Android ao mesmo tempo? {#ios-android-credentials}

Sim, o Campaign suporta ambas as plataformas ao mesmo tempo e permite carregar credenciais para ambas as plataformas.

### Fiz upload de certificados de push com êxito, mas nenhuma mensagem de push é enviada. {#push-certificates-upload}

Certifique-se de que seus certificados de push sejam válidos testando-os [aqui](https://pushtry.com/).

### Posso enviar notificações por push com êxito de pushtry.com, mas não por meio do Campaign. {#push-not-sending}

Certifique-se de que você está seguindo as instruções de carga de push fornecidas [aqui](../../administration/using/push-payload.md).

Observe que para Android, o Campaign só oferece suporte à carga de dados e não à carga de notificação

### Eu configurei um aplicativo na seção Administração do Adobe Campaign Standard, mas o Aplicativo móvel não está disponível nas propriedades de Delivery. {#mobile-app-unavailable}

Um aplicativo precisa ter um certificado de push válido carregado antes que ele possa ser disponibilizado nas propriedades de delivery.

### Tentei todas as instruções nesta página e, no entanto, não consigo enviar Push do Campaign. {#push-troubleshoot}

Abra um tíquete de atendimento ao cliente.

### As notificações por push estão sendo entregues pelo Campaign, mas o arquivo de mídia não está sendo exibido.{#media-file-unavailable}

Os desenvolvedores de aplicativos móveis precisam lidar com o suporte para arquivos de mídia no aplicativo. Às vezes, a largura de banda da rede também pode impedir a renderização de um arquivo de mídia. Consulte esta [página](../../administration/using/image-push-notification.md) para obter mais ponteiros.

### O que preciso fazer para ativar o Relatório de push no Campaign? {#push-reporting-enable}

Siga as etapas abaixo:

* Configure um postback de rastreamento de push. Instruções podem ser encontradas [aqui](../../administration/using/configuring-a-mobile-application.md).
* Implemente a API trackAction a partir do Mobile Core. Consulte esta [página](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference) para obter mais informações.

Instruções mais detalhadas podem ser encontradas neste [page](../../administration/using/push-tracking.md).

### Quais relatórios estão disponíveis para o Canal de push? {#push-report-available}

Um relatório pronto para uso está disponível no Adobe Campaign for Push channel. Consulte esta [documentação](../../reporting/using/push-notification-report.md).

Consulte esta [página](../../reporting/using/indicator-calculation.md#push-notification-delivery) para entender como cada métrica de push é calculada.

### Os deep links são suportados em mensagens de push e no aplicativo? {#deeplink-push}

Sim, os deep links são suportados nas mensagens de push. Os deep links devem incluir:

* Idioma que declara que o rastreamento de delivery precisa ser desativado para que os deep links funcionem.
* Appsflyer com Ramificação como parceiros que podem fazer o rastreamento de deep link. Para obter mais informações sobre a integração do Branch e do Adobe Campaign Standard, consulte esta [página](https://help.branch.io/using-branch/docs/adobe-campaign-standard-1).
