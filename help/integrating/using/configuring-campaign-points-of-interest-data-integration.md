---
title: Configuração da integração de dados de Pontos de interesse de campanha
seo-title: Configuração da integração de dados de Pontos de interesse de campanha
description: Configuração da integração de dados de Pontos de interesse de campanha
seo-description: Saiba como configurar o recurso de dados de Pontos de interesse no Adobe Campaign para enviar mensagens personalizadas com base na localização dos assinantes.
page-status-flag: nunca ativado
uuid: 0689 a 06 c-cc 1 a -442 f -95 b 8-a 07 fcec 85 d 79
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
discoiquuid: a 967 c 6 cc-c 53 b -41 b 4-866 b -90860 d 78 f 463
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d857bee3e7cb54ec179a73d9c256a14771cbd474

---


# Configuração da integração de dados de Pontos de interesse de campanha{#configuring-campaign-points-of-interest-data-integration}

## Configuração da integração de dados de pontos de interesse de campanha com os sdks da Adobe Experience Platform {#configuring-campaign-poi-aep-sdk}

>[!NOTE]
>
>Seu aplicativo móvel já deve estar configurado no Adobe Campaign Standard usando o SDK da Adobe Experience Platform. Para obter as etapas detalhadas, consulte esta [página](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

Os aplicativos móveis usados para coletar dados de localização devem ser configurados por um **administrador** na interface do Adobe Campaign.

Para poder usar os Serviços de localização da Adobe Experience Platform com aplicativos móveis configurados com o SDK da Adobe Experience Platform, é necessário:

1. Adicione as **[!UICONTROL Places]****[!UICONTROL Places Monitor]** extensões à configuração do aplicativo móvel na Adobe Experience Platform Launch. Configure seu aplicativo móvel no Adobe Campaign. Consulte [Instalar a extensão Locais na Adobe Experience Platform Launch](https://placesdocs.com/places-services-by-adobe-documentation/configure-places-in-the-sdk/places-extension#install-the-places-extension-in-adobe-experience-platform-launch) e [Instalar a extensão do Monitor de locais na Experience Platform Launch](https://placesdocs.com/places-services-by-adobe-documentation/configure-places-in-the-sdk/places-monitor-extension/using-the-places-monitor-extension).

1. Depois de configurar suas extensões, crie elementos de dados dentro **[!UICONTROL Adobe Experience Platform Launch]** para recuperar dados dessas extensões. Consulte esta [página](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Step1Createdataelements) para criar seus elementos de dados.

1. Em **[!UICONTROL Adobe Experience Platform Launch]** seguida, você precisa criar regras para suportar casos de uso móvel entre Ponto de interesse e Adobe Campaign.\
   Essa regra será acionada quando um usuário digitar uma localização geográfica **[!UICONTROL Point of Interest]**. Consulte esta [página](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Locationpostback) para criar sua regra.

1. Defina seu **[!UICONTROL Points of Interest]** em Locais. Consulte [Criar um ponto de interesse](https://placesdocs.com/places-services-by-adobe-documentation/places-database-management-1/managing-pois-in-the-places-ui#create-a-poi).

1. Certifique-se de acessar o aplicativo móvel e os dados de localização coletados no Adobe Campaign. Consulte [Acessar aplicativos móveis usados para coletar dados de localização](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#accessing-mobile-apps-used-to-collect-location-data) e [Acessar os dados de localização coletados](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#accessing-collected-location-data).

## Configuração da integração de dados de Pontos de interesse de campanha usando o SDK V 4 {#configuring-campaign-poi-sdkv4}

Os aplicativos móveis usados para coletar dados de localização devem ser configurados por um **administrador** na interface do Adobe Campaign.

Para usar o recurso de dados do Ponto de interesse com aplicativos móveis configurados com o SDK V 4, é necessário:

1. Tenha acesso ao Adobe Analytics para dispositivos móveis. Verifique seu contrato de licença ou entre em contato com seu executivo de contas da Adobe para obter mais informações.
1. Configure seu aplicativo móvel no Adobe Campaign. Consulte [Configuração de um aplicativo para dispositivos móveis no Campaign](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#setting-up-a-mobile-app-in-campaign).
1. Configure seu aplicativo móvel na interface do Adobe Mobile Services. Isso permite garantir que os dados coletados pelo Adobe Mobile Services sejam enviados para o Adobe Campaign. Consulte [Configuração de um aplicativo para dispositivos móveis no Adobe Mobile Services](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#configuring-a-mobile-app-in-adobe-mobile-services).
1. Realize a configuração específica do aplicativo móvel:

   * Empacote o arquivo de configuração baixado da interface do Adobe Mobile Services com o aplicativo móvel.
   * Integre o SDK da Experience Cloud Mobile ao seu aplicativo móvel. Consulte [Integração do SDK em um aplicativo móvel](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#integrating-the-sdk-into-a-mobile-application).

1. Defina Pontos de interesse na interface do Adobe Mobile Services. Consulte [Definição de pontos de interesse no Adobe Mobile Services](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#defining-points-of-interest-in-adobe-mobile-services).
1. Defina os dados que deseja coletar pelos assinantes do aplicativo móvel. Consulte [Coleta dos dados de interesse dos assinantes](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#collecting-subscribers--points-of-interest-data).
1. Certifique-se de acessar o aplicativo móvel e os dados de localização coletados no Adobe Campaign. Consulte [Acessar aplicativos móveis usados para coletar dados de localização](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#accessing-mobile-apps-used-to-collect-location-data) e [Acessar os dados de localização coletados](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#accessing-collected-location-data).

### Configuração de um aplicativo para dispositivos móveis no Adobe Campaign usando o SDK V 4 {#setting-up-a-mobile-app-in-campaign}

Para poder coletar dados de Pontos de interesse com o Adobe Campaign, configure o aplicativo móvel do qual o Adobe Campaign receberá dados.

1. Clique no **[!UICONTROL Adobe Campaign]** logotipo, no canto superior esquerdo e selecione **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Mobile app]**.
1. Clique **[!UICONTROL Create]** em para configurar um aplicativo.
1. Digite um nome no **[!UICONTROL Application name]** campo e clique **[!UICONTROL Create]** em.

   Não preencha a **[!UICONTROL Device-specific settings]** seção. Isso se aplica somente à configuração de aplicativos que recebem notificações por push.

Na **[!UICONTROL Mobile application properties]** seção, dois urls estão listados: **[!UICONTROL Collect PII endpoint]** e **[!UICONTROL Location Services endpoint]**. Eles serão usados na interface do Adobe Mobile Services. Consulte [Configuração de um aplicativo para dispositivos móveis no Adobe Mobile Services](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#configuring-a-mobile-app-in-adobe-mobile-services).

* **[!UICONTROL Collect PII endpoint]** O URL é usado para coletar as IDs da Experience Cloud de usuários e tokens de registro do aplicativo móvel quando ele é iniciado. Quando um usuário entra no aplicativo usando credenciais como email, nome, sobrenome etc., esses dados também são coletados e usados para reconciliar o token de registro do usuário com um perfil do Adobe Campaign.
* O **[!UICONTROL Location Services endpoint]** URL é usado para coletar dados de localização, como latitude, longitude e raio do usuário a partir de um Ponto de interesse.

Agora é possível usar esses valores no Adobe Mobile Services para concluir a configuração, como explicado na seção [Configurar um aplicativo móvel na seção Adobe](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#configuring-a-mobile-app-in-adobe-mobile-services) Mobile Services.

![](assets/poi_mobile_app_properties.png)

### Configuração de um aplicativo para dispositivos móveis V 4 no Adobe Mobile Services {#configuring-a-mobile-app-in-adobe-mobile-services}

Para enviar os dados coletados pelo Adobe Mobile Services para o Adobe Campaign, você deve configurar postbacks na interface do Mobile Services.

Você precisará de informações específicas que podem ser encontradas nos parâmetros de aplicativos móveis definidos no Adobe Campaign (consulte [Configuração de um aplicativo móvel no Campaign](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#setting-up-a-mobile-app-in-campaign)):

* **[!UICONTROL IMS Organization ID]**
* **[!UICONTROL Collect PII Endpoint]**
* **[!UICONTROL Location Services endpoint]**

Você deve ter acesso ao Adobe Analytics para fazer a seguinte configuração. Se você não for um usuário do Adobe Analytics, entre em contato com o administrador do Adobe Campaign.

1. Faça logon em [mobilemarketing.adobe.com](http://mobilemarketing.adobe.com/).
1. Crie o aplicativo ou selecione uma existente.
1. Vá para **[!UICONTROL Manage App Settings]** a página.
1. Na **seção Serviço** de ID de visitante, marque **Ativar** e selecione a organização na lista suspensa. Clique **em Salvar**.

   >[!CAUTION]
   >
   >Essa organização deve ser a mesma que você usa na instância do Adobe Campaign.

1. Click **[!UICONTROL Manage Postbacks]**.
1. Crie um postback.

   * Selecione **[!UICONTROL PII]** como o **[!UICONTROL Postback Type]**.
   * No **[!UICONTROL URL]** campo, copie o **[!UICONTROL Collect PII Endpoint]** URL do aplicativo móvel configurado na interface do Adobe Campaign, precedido pelo nome do servidor. Consulte [Configuração de um aplicativo para dispositivos móveis no Campaign](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#setting-up-a-mobile-app-in-campaign).
   * Preencha **[!UICONTROL Post Body]** o campo da seguinte maneira:

      Para iOS:

      ```
      {
      "userKey": "{userKey}",
      "pushPlatform":"apns",
      "marketingCloudId":"{%mcid%}",
      "cusEmail":"{email}",
      "cusFirstName":"{firstName}",
      "cusLastName":"{lastName}"
      }
      ```

      Para Android:

      ```
      {
      "userKey": "{userKey}",
      "pushPlatform":"gcm",
      "marketingCloudId":"{%mcid%}",
      "cusEmail":"{email}",
      "cusFirstName":"{firstName}",
      "cusLastName":"{lastName}"
      }
      ```

   * Definir **tipo de conteúdo** como **[!UICONTROL application/json]**.
   * Em **quais tags de dados acionam o postback?**, selecione qualquer evento, normalmente **[!UICONTROL Launched]** e **[!UICONTROL exists]**.
   * Click **[!UICONTROL Save & Activate]**.

1. Crie um segundo postback.

   * Selecione **[!UICONTROL Postback]** como o **[!UICONTROL Postback Type]**.
   * No **[!UICONTROL URL]** campo, copie o **[!UICONTROL Location Services Endpoint]** URL do aplicativo móvel configurado na interface do Adobe Campaign, precedido pelo nome do servidor. Consulte [Configuração de um aplicativo para dispositivos móveis no Campaign](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#setting-up-a-mobile-app-in-campaign).
   * Preencha **[!UICONTROL Post Body]** o campo da seguinte maneira:

      ```
      {
      "locationData":{
      "distances":"{a.loc.dist}",
      "poiLabel":"{a.loc.poi}",
      "latitude.a":"{a.loc.lat.a}",
      "latitude.b":"{a.loc.lat.b}",
      "latitude.c":"{a.loc.lat.c}",
      "longitude.a":"{a.loc.lon.a}",
      "longitude.b":"{a.loc.lon.b}",
      "longitude.c":"{a.loc.lon.c}",
      "appId":"{a.appid}",
      "marketingCloudId":"{mid}"
      }
      }
      ```

   * Definir **tipo de conteúdo** como **[!UICONTROL application/json]**.
   * Em **quais tags de dados acionam o postback?**, selecione **[!UICONTROL campaign.test]** e **[!UICONTROL exists]**.
   * Click **[!UICONTROL Save & Activate]**.

>[!NOTE]
>
>Para obter informações detalhadas sobre como configurar postbacks, consulte a documentação do [Adobe Mobile Services](https://marketing.adobe.com/resources/help/en_US/mobile/signals_.html).

### Integração do SDK em um aplicativo móvel {#integrating-the-sdk-into-a-mobile-application}

O kit de desenvolvimento de software (SDK) do serviço principal do Mobile Mobile facilita a integração de um aplicativo móvel no Adobe Campaign.

Esta etapa é descrita nesta [página](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html).

### Definição de pontos de interesse no Adobe Mobile Services {#defining-points-of-interest-in-adobe-mobile-services}

Para definir os Pontos de interesse usados para coletar dados de localização:

1. Vá para a interface do Adobe Mobile Services.
1. Adicione seu aplicativo.

   Para obter mais informações sobre o gerenciamento de aplicativos no Mobile Services, consulte a documentação do [Adobe Mobile Services](https://marketing.adobe.com/resources/help/en_US/mobile/t_new_app.html).

1. Defina os Pontos de interesse.

   Para obter mais informações sobre como gerenciar Pontos de interesse, consulte a documentação do [Adobe Mobile Services](https://marketing.adobe.com/resources/help/en_US/mobile/t_manage_points.html).

### Coleta de dados de interesse dos assinantes {#collecting-subscribers--points-of-interest-data}

Um recurso personalizado específico permite que você defina os dados que deseja coletar pelos assinantes dos aplicativos.

Esta etapa é descrita em [Configurar um aplicativo móvel usando](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html) a página SDK V 4.


## Acessar aplicativos móveis usados para coletar dados de localização {#accessing-mobile-apps-used-to-collect-location-data}

Para acessar os aplicativos criados com êxito no Adobe Campaign:

1. Clique no **[!UICONTROL Adobe Campaign]** logotipo, no canto superior esquerdo.
1. Selecione **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Mobile app (SDK v4)]** ou **[!UICONTROL Mobile app (AEP SDK)]** dependa do SDK.
1. Selecione um aplicativo móvel na lista para exibir suas propriedades.

   ![](assets/poi_mobile_app_subscribers.png)

Uma lista dos assinantes do aplicativo também é exibida na **[!UICONTROL Mobile application subscribers]** guia. Os assinantes são todos os usuários que instalaram o aplicativo em seu dispositivo móvel. Os perfis de banco de dados do Adobe Campaign são identificados com um token de registro.

## Acessar os dados de localização coletados {#accessing-collected-location-data}

Após a configuração ser feita, os dados Coletados de Pontos de interesse são listados na **[!UICONTROL Places]** guia de cada perfil. Para acessar a lista:

1. Selecione um perfil.
1. Clique no **[!UICONTROL Edit profile properties]** botão à direita.
1. Selecione a **[!UICONTROL Places]** guia.

   ![](assets/poi_profile_places.png)

Os dados de Pontos de interesse coletados para o perfil atual são listados. Os dados de localização são armazenados no banco de dados do Adobe Campaign por seis meses.

Para obter mais informações sobre como acessar e editar perfis, consulte [Perfis](../../audiences/using/about-profiles.md).
