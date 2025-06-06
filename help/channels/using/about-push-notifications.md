---
title: Sobre as notificações por push
description: Descubra as principais especificidades do canal de notificação por push no Adobe Campaign.
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Push
role: User
level: Intermediate
exl-id: e61daed6-a0ec-49d8-b1ad-77590fafb496
source-git-commit: 597ece8d833a216f0540f801461b08fdc9865024
workflow-type: tm+mt
source-wordcount: '1206'
ht-degree: 39%

---

# Sobre notificações por push{#about-push-notifications}

>[!CAUTION]
>
>A implementação da notificação por push deve ser executada por usuários especialistas. Se precisar de auxílio, entre em contato com o executivo da sua conta da Adobe ou com o parceiros de serviços Professional. A notificação por push é um recurso opcional. Verifique seu contrato de licença e entre em contato com o executivo da sua conta para ativá-la.

O Adobe Campaign permite enviar notificações por push personalizadas e segmentadas para dispositivos móveis iOS e Android.

Essas mensagens são recebidas nos aplicativos móveis que você configurou no Adobe Campaign por meio do SDK da Experience Platform. Para saber mais, consulte [Configuração de um aplicativo móvel usando SDKs da Adobe Experience Platform](../../administration/using/configuring-a-mobile-application.md).

No Adobe Campaign, os dados de atributos do perfil móvel enviados de dispositivo móvel são armazenados no recurso **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]**, que permite definir os dados que você deseja coletar dos assinantes de aplicativos.

Esse recurso precisa ser estendido para coletar os dados que você pretende enviar do dispositivo móvel para o Adobe Campaign. Para fazer isso, consulte esta [página](../../developing/using/extending-the-subscriptions-to-an-application-resource.md) para conhecer as etapas detalhadas.

Dois tipos de notificações por push estão disponíveis no Adobe Campaign:

* As notificações do tipo **[!UICONTROL Alert/Message/Badge]** permitem enviar mensagens padrão baseadas em texto com conteúdo adicional (som, selo, deeplink etc.) que você pode definir na seção **[!UICONTROL Advanced options]**.

  Esses tipos de notificação permitem adicionar um título e uma mensagem na qual você pode usar campos de personalização. Para personalizar a mensagem, selecione o template **[!UICONTROL Send push on profiles]**.

* As notificações do tipo **[!UICONTROL Silent push]** são usadas para notificar silenciosamente o aplicativo sem qualquer mensagem ou conteúdo para o usuário final. Um caso de uso típico desse tipo de mensagem seria tornar o aplicativo ciente de que há conteúdo disponível a ser baixado do servidor.

Algumas configurações específicas podem ser configuradas para definir o comportamento das notificações. Para obter mais informações, consulte [esta seção](../../channels/using/customizing-a-push-notification.md).

>[!NOTE]
>
>As leis de privacidade diferem de um país para outro. Alguns países exigem que você informe os usuários sobre os tipos de dados coletados pelos aplicativos móveis. Consulte as leis sobre aplicativos móveis do seu país. Verifique se as notificações por push enviadas para os aplicativos móveis atendem aos pré-requisitos e condições especificados pela Apple (serviço Apple Push Notification) e pelo Google (Google Cloud Messaging ou Firebase Cloud Messaging).

**Conteúdo relacionado:**

* [Preparação e envio de uma notificação por push](../../channels/using/preparing-and-sending-a-push-notification.md)
* [Criação de uma notificação por push multilíngue](../../channels/using/creating-a-multilingual-push-notification.md)
* [Relatório de notificação por push](../../reporting/using/push-notification-report.md)
* [Guia do Campaign Standard Mobile](../../channels/using/get-started-communication-channels.md)

## Pré-requisitos {#prerequisites}

>[!NOTE]
>Para aproveitar o recurso de notificação por push do Campaign, você precisa fornecer um certificado de push válido no formato .pem sem senhas.
>
>Se você tiver um certificado p12 válido, poderá convertê-lo facilmente em um arquivo .pem usando os recursos online.

Antes de enviar as notificações por push, você deve:

1. No Adobe Campaign, confirme se você pode acessar o canal **[!UICONTROL Push notification]**. Se não conseguir acessar esses canais, entre em contato com sua equipe de conta.

1. Verifique se o usuário tem as permissões necessárias no Adobe Campaign Standard e nas tags na Adobe Experience Platform.

1. Na interface da Coleção de dados, crie uma propriedade móvel. Para saber mais, consulte [Configurar uma propriedade móvel](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/).

1. Na interface da Coleção de Dados, instale a extensão **[!UICONTROL Adobe Campaign Standard]**.

1. No Adobe Campaign Standard, configure a propriedade móvel que você criou na interface da coleção de dados. Para obter mais informações, consulte [Configurando seu aplicativo de marcas na Adobe Campaign](../../administration/using/configuring-a-mobile-application.md#set-up-campaign).

1. Adicione a configuração específica do canal à configuração do aplicativo móvel. Para saber mais, consulte [Configuração do aplicativo específico do canal no Adobe Campaign](../../administration/using/configuring-a-mobile-application.md#channel-specific-config).

1. Para saber mais sobre as implementações dos casos de uso móveis, consulte as instruções detalhadas sobre extensões, regras de tags e a implementação do SDK em [Casos de uso móveis com suporte no Adobe Campaign Standard com SDKs da Adobe Experience Platform](../../administration/using/configuring-rules-launch.md).

## Perguntas frequentes sobre notificação por push {#push-faq}

### Quais seriam algumas recomendações de recursos úteis para saber mais sobre o canal push? {#resource-push}

Confira os recursos abaixo:

* [Tutorials de vídeo](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/communication-channels/mobile/push/creating-a-push-notification.html?lang=pt-BR)
* [Documentação do produto](../../channels/using/about-push-notifications.md)
* Configurar usando a [documentação](../../administration/using/configuring-a-mobile-application.md) do SDK da AEP
* [Página da comunidade](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-standard/ct-p/adobe-campaign-standard-community?profile.language=pt)

### O que devo fazer para adquirir um token de push no Campaign? {#push-token-acquisition}

Verifique se a equipe de provisionamento concluiu o provisionamento do canal Push na Adobe Campaign Standard. Implementar a API setPushIdentifier do SDK. Para obter mais informações, consulte esta [página](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/#set-up-push-messaging).

### Depois que tenho o token de push e a ECID no Campaign, o que mais preciso para enviar uma notificação por push? {#sending-push}

Os clientes precisam fornecer um certificado push válido em formato .pem para enviar uma notificação por push. Você não precisa de uma senha para este certificado.

### E se eu tiver um certificado .p12 em vez de um certificado .pem? {#certificates}

Você pode converter um certificado .p12 em um certificado .pem executando o comando abaixo no terminal. Há vários recursos online também disponíveis para instruções de conversão.

```
openssl pkcs12 -in pushcert.p12 -out pushcert.pem -nodes -clcerts
```

### Como saber se o upload do certificado foi bem-sucedido? {#certificate-upload}

Você verá a seguinte mensagem.

![](assets/faq_2.png)

### É possível fazer upload de certificados de Produção e de Sandbox ao mesmo tempo para aplicativos iOS (N/A para Android)? {#prod-sandbox-certificate}

Não, os aplicativos funcionarão no modo de sandbox ou produção e não poderão ser alterados para o outro (ou seja, sandbox para aplicativo de produção) após a configuração. Recomendamos que você teste seu aplicativo no modo de sandbox primeiro e, em seguida, faça a transição para o modo de produção.

Para alterar para o modo de produção, será necessário criar outro aplicativo. Além disso, não marque a caixa de seleção da sandbox e faça upload de um certificado de produção.

### Posso fazer upload das credenciais do iOS e do Android ao mesmo tempo? {#ios-android-credentials}

Sim, o Campaign oferece suporte a ambas as plataformas ao mesmo tempo e permite fazer upload das credenciais para ambas as plataformas.

### Carregei certificados de push com êxito, mas nenhuma mensagem de push foi enviada. {#push-certificates-upload}

Certifique-se de que seus certificados de push são válidos testando-os [aqui](https://pushtry.com/).

### Posso enviar notificações por push com êxito do pushtry.com, mas não pelo Campaign. {#push-not-sending}

Certifique-se de que você está seguindo as instruções da carga de push fornecidas [aqui](../../administration/using/push-payload.md).

Observe que para o Android, o Campaign é compatível apenas com o conteúdo de dados, não com o conteúdo de notificação

### Eu configurei um aplicativo na seção Administração do Adobe Campaign Standard, mas o aplicativo móvel não está disponível nas Propriedades de delivery. {#mobile-app-unavailable}

Um aplicativo também deve ter um certificado Push válido carregado antes de ser disponibilizado nas propriedades de delivery.

### Tentei todas as instruções nesta página e ainda não consigo enviar o Push do Campaign. {#push-troubleshoot}

Abra um tíquete de atendimento ao cliente.

### As notificações por push estão sendo entregues pelo Campaign, mas o arquivo de mídia não está sendo exibido.{#media-file-unavailable}

Os desenvolvedores de aplicativos móveis precisam lidar com o suporte para arquivos de mídia no aplicativo. Às vezes, a largura de banda da rede também pode impedir a renderização de um arquivo de mídia. Consulte esta [página](../../administration/using/image-push-notification.md) para obter ponteiros adicionais.

### O que devo fazer para habilitar os relatórios de push no Campaign? {#push-reporting-enable}

Siga as etapas abaixo:

* Configure um postback de rastreamento de push. As instruções podem ser encontradas [aqui](../../administration/using/configuring-a-mobile-application.md).
* Implementar a API trackAction a partir do Mobile Core. Consulte esta [página](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/) para obter mais informações.

Instruções mais detalhadas podem ser encontradas nesta [página](../../administration/using/push-tracking.md).

### Quais relatórios estão disponíveis para o canal de push? {#push-report-available}

Um relatório pronto para uso está disponível no Adobe Campaign para canal por push. Consulte esta [documentação](../../reporting/using/push-notification-report.md).

Consulte esta [página](../../reporting/using/indicator-calculation.md#push-notification-delivery) para entender como cada métrica de push é calculada.

### Os deeplinks são compatíveis com mensagens de push e no aplicativo? {#deeplink-push}

Sim, os deeplinks são compatíveis com mensagens de push. Os deeplinks devem incluir:

* Idioma que declara que o rastreamento de delivery precisa ser desativado para que os deeplinks funcionem.
* AppScript com Ramificação como parceiros que podem fazer o rastreamento de deep link. Para obter mais informações sobre a integração de Ramificação e Adobe Campaign Standard, consulte esta [página](https://help.branch.io/using-branch/docs/adobe-campaign-standard-1).
