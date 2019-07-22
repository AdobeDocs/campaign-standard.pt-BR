---
title: Configuração de um aplicativo móvel
seo-title: Configuração de um aplicativo móvel
description: Configuração de um aplicativo móvel
seo-description: Descubra como configurar o Adobe Campaign para enviar notificações por push ou mensagens no aplicativo usando o SDK V 4 ou Experience Platform SDK.
page-status-flag: nunca ativado
uuid: 63 e 1476 a -7875-4 f 48-ba 9 e -97 f 1 a 0007 e 42
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuração-canais
discoiquuid: 2 a 14500 f -5 ede -4131-8 b 1 a-b 7 fd 65 b 7 e 3 aa
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b9799c40bd7b6422409456db2c4f694f486b42f8

---


# Configuring a mobile application{#configuring-a-mobile-application}

Notificações por push ou mensagens no aplicativo são recebidas em aplicativos móveis que precisam primeiro ser configurados nos Adobe Mobile Services, dependendo do canal que você deseja usar.

* Para enviar mensagens no aplicativo e notificações por push, seus aplicativos móveis precisam ser configurados no Adobe Campaign aproveitando os sdks da Adobe Experience Platform. See [Using Adobe Experience Platform SDK](#using-adobe-experience-platform-sdk).

* Para enviar somente notificações por push, você pode configurar a integração entre o Adobe Campaign e o Adobe Mobile Service usando o SDK V 4. See [Using SDK V4](#using-sdk-v4).

After your mobile applications are set up in Adobe Campaign by leveraging the Experience Cloud Mobile SDK V4 or Experience Platform SDK, they need to be configured by an administrator under the [!UICONTROL Administration] &gt; [!UICONTROL Channels] &gt; [!UICONTROL Mobile app] menu.

>[!CAUTION]
>
>A notificação por push e as implementações do aplicativo precisam ser executadas por usuários de especialistas. Se precisar ser assistido, entre em contato com seu executivo de contas ou parceiro de serviços profissionais da Adobe.

## Using Adobe Experience Platform SDK {#using-adobe-experience-platform-sdk}

Para enviar notificações por push e mensagens no aplicativo com o aplicativo SDK da Experience Platform, um aplicativo móvel deve ser configurado na Plataforma Experience Platform Experience Platform Experience Platform Launch Platform e configurado no Adobe Campaign. For the detailed steps to configure your mobile application using Experience Platform SDK, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html).

Siga as etapas abaixo para iniciar a configuração:

1. Make sure you can access the **[!UICONTROL Mobile]** channels: Push notification and In-App message in Adobe Campaign. Caso contrário, entre em contato com sua equipe de conta.

   ![](assets/launch_1.png)

1. Crie o aplicativo móvel na Experience Platform Launch criando uma propriedade de tipo móvel. For more info, refer to the [Experience Platform Launch](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#create-a-new-mobile-property) documentation.
1. Install the **[!UICONTROL Adobe Campaign (Beta)]** extension for your mobile application in Experience Platform Launch:

   For more information on extensions, refer to the [Experience Platform Launch](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard-beta) documentation.

1. Configure rules for your application in Adobe Launch, see [Configuring your application in Launch](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#ConfiguringyourapplicationinLaunch)
1. Configure your Adobe Launch application in Adobe Campaign Standard, see [Setting up your Adobe Launch application in Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#SettingupyourAdobeLaunchapplicationinAdobeCampaign).
1. Add channel specific configuration to your Mobile Application set-up, see [Channel-specific application configuration in Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#ChannelspecificapplicationconfigurationinAdobeCampaign).

   ![](assets/launch_2.png)

## Using SDK V4 {#using-sdk-v4}

A notificação por push é suportada pelo SDK V 4 e Adobe Experience Platform sdks, diferente do Dentro do aplicativo. For the detailed steps to use push notifications with your mobile app, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html).

Os aplicativos móveis que recebem notificações por push devem ser configurados por um administrador na interface do Adobe Campaign. Ao configurar o Adobe Campaign e o Adobe Mobile Services, você poderá usar os dados do aplicativo móvel para suas campanhas.

Para enviar notificações por push, é necessário:

1. Make sure you can access the **[!UICONTROL Mobile app]** channel in Adobe Campaign.
1. Configure seu aplicativo móvel em:

   * [Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html#SettingupamobileapplicationinAdobeCampaign).
   * [Adobe Mobile Services](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html#ConfiguringamobileapplicationinAdobeMobileServices).

1. Realize a configuração específica do aplicativo móvel:

   * Empacote o arquivo de configuração baixado da interface do Adobe Mobile Services com o aplicativo móvel.
   * Integre o SDK da Experience Cloud Mobile ao seu aplicativo móvel.

1. Defina os dados que deseja coletar pelos assinantes do aplicativo. Os assinantes do aplicativo móvel que possuem um perfil no banco de dados do Adobe Campaign são conciliados com base nos critérios definidos por você.

   For more on this, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html#Collectingsubscribersdatafromamobileapplication).

1. Certifique-se de que a configuração foi concluída com êxito ao iniciar seu aplicativo móvel no dispositivo e fazer logon. Certifique-se de receber notificações.
1. Then, in Adobe Campaign's advanced menu, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Mobile app]**.
1. Selecione seu aplicativo móvel na lista para exibir suas propriedades. Suas informações de assinatura são exibidas na lista de assinantes.

   ![](assets/push_notif_mobile_app.png)

1. To check the mobile applications a profile has subscribed to, in the **[!UICONTROL Profiles & Audiences > Profiles]** menu, select a profile and click the **[!UICONTROL Edit profile properties]** button on the right. The mobile applications are listed in the **[!UICONTROL Mobile App Subscriptions]** tab.

   ![](assets/push_notif_subscriptions.png)