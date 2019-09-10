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
source-git-commit: 3b7da7df5092476be4c6acc21b2ad2472a80da83

---


# Configuração de um aplicativo móvel{#configuring-a-mobile-application}

Notificações por push ou mensagens no aplicativo são recebidas em aplicativos móveis que precisam primeiro ser configurados nos Adobe Mobile Services, dependendo do canal que você deseja usar.

* Para enviar mensagens no aplicativo e notificações por push, seus aplicativos móveis precisam ser configurados no Adobe Campaign aproveitando os sdks da Adobe Experience Platform. Consulte [Uso do Adobe Experience Platform SDK](#using-adobe-experience-platform-sdk).

* Para enviar somente notificações por push, você pode configurar a integração entre o Adobe Campaign e o Adobe Mobile Service usando o SDK V 4. Consulte [Usando o SDK V 4](#using-sdk-v4).

Depois que seus aplicativos móveis são configurados no Adobe Campaign, aproveitando o SDK da Experience Cloud Mobile SDK V 4 ou Experience Platform SDK, eles precisam ser configurados por um administrador em [!UICONTROL Administration] &gt; [!UICONTROL Channels] &gt; [!UICONTROL Mobile app] menu.

>[!CAUTION]
>
>A notificação por push e as implementações do aplicativo precisam ser executadas por usuários de especialistas. Se precisar ser assistido, entre em contato com seu executivo de contas ou parceiro de serviços profissionais da Adobe.

Depois que um aplicativo móvel é configurado, é possível recuperar os dados PII coletados para criar ou atualizar perfis do banco de dados. Para obter mais informações sobre isso, consulte esta seção: [Criação e atualização de informações de perfil com base em dados de aplicativos móveis](../../channels/using/updating-profile-with-mobile-app-data.md).

## Uso do SDK da Adobe Experience Platform {#using-adobe-experience-platform-sdk}

>[!Note]
>
>Para saber mais sobre os diferentes casos de uso móvel compatíveis com o Adobe Campaign Standard usando os sdks da Adobe Experience Platform, consulte esta [página](https://helpx.adobe.com/campaign/kb/configure-launch-rules-acs-use-cases.html).

Para enviar notificações por push e mensagens no aplicativo com o aplicativo SDK da Experience Platform, um aplicativo móvel deve ser configurado na Plataforma Experience Platform Experience Platform Experience Platform Launch Platform e configurado no Adobe Campaign. Para obter as etapas detalhadas para configurar seu aplicativo móvel usando o SDK da Experience Platform, consulte esta [página](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html).

Siga as etapas abaixo para iniciar a configuração:

1. Verifique se você pode acessar os **[!UICONTROL Mobile]** canais: Notificação por push e mensagem no aplicativo no Adobe Campaign. Caso contrário, entre em contato com sua equipe de conta.

   ![](assets/launch_1.png)

1. Crie o aplicativo móvel na Experience Platform Launch criando uma propriedade de tipo móvel. Para obter mais informações, consulte a [documentação Launch](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#create-a-new-mobile-property) Platform Launch.
1. Instale **[!UICONTROL Adobe Campaign Standard]** a extensão para seu aplicativo móvel na Experience Platform Launch:

   Para obter mais informações sobre extensões, consulte a [documentação Launch](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard) Platform Launch.

1. Configurar regras para seu aplicativo no Adobe Launch, consulte [Configurar seu aplicativo no Launch](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Step1Createdataelements)
1. Configure seu aplicativo Adobe Launch no Adobe Campaign Standard, consulte [Configuração do aplicativo Adobe Launch no Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#SettingupyourAdobeLaunchapplicationinAdobeCampaign).
1. Adicione a configuração específica do canal à configuração do aplicativo móvel, consulte [Configuração de aplicativos específicos do canal no Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#ChannelspecificapplicationconfigurationinAdobeCampaign).

   ![](assets/launch_2.png)

## Uso do SDK V 4 {#using-sdk-v4}

A notificação por push é suportada pelo SDK V 4 e Adobe Experience Platform sdks, diferente do Dentro do aplicativo. Para obter as etapas detalhadas para usar notificações por push com seu aplicativo móvel, consulte esta [página](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html).

Os aplicativos móveis que recebem notificações por push devem ser configurados por um administrador na interface do Adobe Campaign. Ao configurar o Adobe Campaign e o Adobe Mobile Services, você poderá usar os dados do aplicativo móvel para suas campanhas.

Para enviar notificações por push, é necessário:

1. Certifique-se de acessar o **[!UICONTROL Mobile app]** canal no Adobe Campaign.
1. Configure seu aplicativo móvel em:

   * [Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html#SettingupamobileapplicationinAdobeCampaign).
   * [Adobe Mobile Services](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html#ConfiguringamobileapplicationinAdobeMobileServices).

1. Realize a configuração específica do aplicativo móvel:

   * Empacote o arquivo de configuração baixado da interface do Adobe Mobile Services com o aplicativo móvel.
   * Integre o SDK da Experience Cloud Mobile ao seu aplicativo móvel.

1. Defina os dados que deseja coletar pelos assinantes do aplicativo. Os assinantes do aplicativo móvel que possuem um perfil no banco de dados do Adobe Campaign são conciliados com base nos critérios definidos por você.

   Para saber mais sobre isso, consulte esta [página](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html#Collectingsubscribersdatafromamobileapplication).

1. Certifique-se de que a configuração foi concluída com êxito ao iniciar seu aplicativo móvel no dispositivo e fazer logon. Certifique-se de receber notificações.
1. Em seguida, no menu avançado do Adobe Campaign, selecione **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Mobile app]**.
1. Selecione seu aplicativo móvel na lista para exibir suas propriedades. Suas informações de assinatura são exibidas na lista de assinantes.

   ![](assets/push_notif_mobile_app.png)

1. Para verificar os aplicativos móveis que um perfil assinou, no **[!UICONTROL Profiles & Audiences > Profiles]** menu, selecione um perfil e clique no **[!UICONTROL Edit profile properties]** botão à direita. Os aplicativos móveis estão listados na **[!UICONTROL Mobile App Subscriptions]** guia.

   ![](assets/push_notif_subscriptions.png)