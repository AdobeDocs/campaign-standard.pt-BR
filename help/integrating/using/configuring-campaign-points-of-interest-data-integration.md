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
source-git-commit: 60365021e10d3d0e3197f57c6e410af3b8ec0c1d

---


# Configuring Campaign-Points of Interest data integration{#configuring-campaign-points-of-interest-data-integration}

## Configuring Campaign-Points of Interest data integration with Adobe Experience Platform SDKs {#configuring-campaign-poi-aep-sdk}

>[!NOTE]
>
>Seu aplicativo móvel já deve estar configurado no Adobe Campaign Standard usando o SDK da Adobe Experience Platform. For the detailed steps, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

The mobile applications used to collect location data must be configured by an **administrator** in the Adobe Campaign interface.

Para poder usar os Serviços de localização da Adobe Experience Platform com aplicativos móveis configurados com o SDK da Adobe Experience Platform, é necessário:

1. Add the **[!UICONTROL Places]** and **[!UICONTROL Places Monitor]** extensions to your mobile app configuration in Adobe Experience Platform Launch. Configure seu aplicativo móvel no Adobe Campaign. See [Install the Places extension in Adobe Experience Platform Launch](https://placesdocs.com/places-services-by-adobe-documentation/configure-places-in-the-sdk/places-extension#install-the-places-extension-in-adobe-experience-platform-launch) and [Install the Places Monitor extension in Experience Platform Launch](https://placesdocs.com/places-services-by-adobe-documentation/configure-places-in-the-sdk/places-monitor-extension/using-the-places-monitor-extension).

1. Once your extensions are set up, create data elements within **[!UICONTROL Adobe Experience Platform Launch]** to retrieve data from these extensions. Refer to this [page](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Step1Createdataelements) to create your data elements.

1. Then, in **[!UICONTROL Adobe Experience Platform Launch]**, you need to create rules to support mobile use cases between Point of Interests and Adobe Campaign.\
   This rule will be triggered when a user enters a geo-fenced **[!UICONTROL Point of Interest]**. Refer to this [page](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Locationpostback) to create your rule.

1. Define your **[!UICONTROL Points of Interest]** in Places. See [Create a Point of Interest](https://placesdocs.com/places-services-by-adobe-documentation/places-database-management-1/managing-pois-in-the-places-ui#create-a-poi).

1. Certifique-se de acessar o aplicativo móvel e os dados de localização coletados no Adobe Campaign. See [Accessing mobile apps used to collect location data](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#accessing-mobile-apps-used-to-collect-location-data) and [Accessing collected location data](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#accessing-collected-location-data).

## Configuring Campaign-Points of Interest data integration using SDK V4 {#configuring-campaign-poi-sdkv4}

The mobile applications used to collect location data must be configured by an **administrator** in the Adobe Campaign interface.

Para usar o recurso de dados do Ponto de interesse com aplicativos móveis configurados com o SDK V 4, é necessário:

1. Tenha acesso ao Adobe Analytics para dispositivos móveis. Verifique seu contrato de licença ou entre em contato com seu executivo de contas da Adobe para obter mais informações.
1. Configure seu aplicativo móvel no Adobe Campaign. See [Setting up a mobile app in Campaign](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#setting-up-a-mobile-app-in-campaign).
1. Configure seu aplicativo móvel na interface do Adobe Mobile Services. Isso permite garantir que os dados coletados pelo Adobe Mobile Services sejam enviados para o Adobe Campaign. See [Configuring a mobile app in Adobe Mobile Services](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#configuring-a-mobile-app-in-adobe-mobile-services).
1. Realize a configuração específica do aplicativo móvel:

   * Empacote o arquivo de configuração baixado da interface do Adobe Mobile Services com o aplicativo móvel.
   * Integre o SDK da Experience Cloud Mobile ao seu aplicativo móvel. See [Integrating the SDK into a mobile application](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#integrating-the-sdk-into-a-mobile-application).

1. Defina Pontos de interesse na interface do Adobe Mobile Services. See [Defining Points of Interest in Adobe Mobile Services](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#defining-points-of-interest-in-adobe-mobile-services).
1. Defina os dados que deseja coletar pelos assinantes do aplicativo móvel. See [Collecting subscribers' Points of interest data](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#collecting-subscribers--points-of-interest-data).
1. Certifique-se de acessar o aplicativo móvel e os dados de localização coletados no Adobe Campaign. See [Accessing mobile apps used to collect location data](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#accessing-mobile-apps-used-to-collect-location-data) and [Accessing collected location data](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#accessing-collected-location-data).

### Setting up a mobile app in Adobe Campaign using SDK V4 {#setting-up-a-mobile-app-in-campaign}

Para poder coletar dados de Pontos de interesse com o Adobe Campaign, configure o aplicativo móvel do qual o Adobe Campaign receberá dados.

1. Click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner, then select **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Mobile app]**.
1. Click **[!UICONTROL Create]** to set up an application.
1. Enter a name in the **[!UICONTROL Application name]** field and click **[!UICONTROL Create]**.

   Do not fill in the **[!UICONTROL Device-specific settings]** section. Isso se aplica somente à configuração de aplicativos que recebem notificações por push.

In the **[!UICONTROL Mobile application properties]** section, two URLs are listed: **[!UICONTROL Collect PII endpoint]** and **[!UICONTROL Location Services endpoint]**. Eles serão usados na interface do Adobe Mobile Services. See [Configuring a mobile app in Adobe Mobile Services](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#configuring-a-mobile-app-in-adobe-mobile-services).

* **[!UICONTROL Collect PII endpoint]** O URL é usado para coletar as IDs da Experience Cloud de usuários e tokens de registro do aplicativo móvel quando ele é iniciado. Quando um usuário entra no aplicativo usando credenciais como email, nome, sobrenome etc., esses dados também são coletados e usados para reconciliar o token de registro do usuário com um perfil do Adobe Campaign.
* The **[!UICONTROL Location Services endpoint]** URL is used to collect location data such as a user's latitude, longitude and radius from a Point of Interest.

You can now use these values in Adobe Mobile Services to finish the configuration, as explained in the [Configuring a mobile app in Adobe Mobile Services](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#configuring-a-mobile-app-in-adobe-mobile-services) section.

![](assets/poi_mobile_app_properties.png)

### Configuring a V4 mobile app in Adobe Mobile Services {#configuring-a-mobile-app-in-adobe-mobile-services}

Para enviar os dados coletados pelo Adobe Mobile Services para o Adobe Campaign, você deve configurar postbacks na interface do Mobile Services.

You will need specific information that you can find in the mobile application parameters set in Adobe Campaign (see [Setting up a mobile app in Campaign](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#setting-up-a-mobile-app-in-campaign)):

* **[!UICONTROL IMS Organization ID]**
* **[!UICONTROL Collect PII Endpoint]**
* **[!UICONTROL Location Services endpoint]**

Você deve ter acesso ao Adobe Analytics para fazer a seguinte configuração. Se você não for um usuário do Adobe Analytics, entre em contato com o administrador do Adobe Campaign.

1. Log into [mobilemarketing.adobe.com](http://mobilemarketing.adobe.com/).
1. Crie o aplicativo ou selecione uma existente.
1. Go to the **[!UICONTROL Manage App Settings]** page.
1. In the **Visitor ID Service ** section, check **Enable** and select your organization from the drop-down list. Click **Save**.

   >[!CAUTION]
   >
   >Essa organização deve ser a mesma que você usa na instância do Adobe Campaign.

1. Click **[!UICONTROL Manage Postbacks]**.
1. Crie um postback.

   * Select **[!UICONTROL PII]** as the **[!UICONTROL Postback Type]**.
   * In the **[!UICONTROL URL]** field, copy the **[!UICONTROL Collect PII Endpoint]** URL from the mobile application that you configured in the Adobe Campaign interface, preceded by the server name. See [Setting up a mobile app in Campaign](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#setting-up-a-mobile-app-in-campaign).
   * Fill in the **[!UICONTROL Post Body]** field as follows:

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

   * Set **Content Type** as **[!UICONTROL application/json]**.
   * In the **Which Data Tags Trigger the Postback?**, selecione qualquer evento, normalmente **[!UICONTROL Launched]** e **[!UICONTROL exists]**.
   * Click **[!UICONTROL Save & Activate]**.

1. Crie um segundo postback.

   * Select **[!UICONTROL Postback]** as the **[!UICONTROL Postback Type]**.
   * In the **[!UICONTROL URL]** field, copy the **[!UICONTROL Location Services Endpoint]** URL from the mobile application that you configured in the Adobe Campaign interface, preceded by the server name. See [Setting up a mobile app in Campaign](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#setting-up-a-mobile-app-in-campaign).
   * Fill in the **[!UICONTROL Post Body]** field as follows:

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

   * Set **Content Type** as **[!UICONTROL application/json]**.
   * In the **Which Data Tags Trigger the Postback?**, selecione **[!UICONTROL campaign.test]** e **[!UICONTROL exists]**.
   * Click **[!UICONTROL Save & Activate]**.

>[!NOTE]
>
>For detailed information on configuring postbacks, refer to the [Adobe Mobile Services documentation](https://marketing.adobe.com/resources/help/en_US/mobile/signals_.html).

### Integrating the SDK into a mobile application {#integrating-the-sdk-into-a-mobile-application}

O kit de desenvolvimento de software (SDK) do serviço principal do Mobile Mobile facilita a integração de um aplicativo móvel no Adobe Campaign.

This step is described in this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html).

### Defining Points of Interest in Adobe Mobile Services {#defining-points-of-interest-in-adobe-mobile-services}

Para definir os Pontos de interesse usados para coletar dados de localização:

1. Vá para a interface do Adobe Mobile Services.
1. Adicione seu aplicativo.

   For more information on managing applications in Mobile Services, refer to the [Adobe Mobile Services documentation](https://marketing.adobe.com/resources/help/en_US/mobile/t_new_app.html).

1. Defina os Pontos de interesse.

   For more information on managing Points of Interest, refer to the [Adobe Mobile Services documentation](https://marketing.adobe.com/resources/help/en_US/mobile/t_manage_points.html).

### Collecting subscribers' Points of interest data {#collecting-subscribers--points-of-interest-data}

Um recurso personalizado específico permite que você defina os dados que deseja coletar pelos assinantes dos aplicativos.

This step is described in the [Configuring a mobile application using SDK V4](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html) page.


## Accessing mobile apps used to collect location data {#accessing-mobile-apps-used-to-collect-location-data}

Para acessar os aplicativos criados com êxito no Adobe Campaign:

1. Click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner.
1. Select **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Mobile app (SDK v4)]** or **[!UICONTROL Mobile app (AEP SDK)]** depending on the SDK.
1. Selecione um aplicativo móvel na lista para exibir suas propriedades.

   ![](assets/poi_mobile_app_subscribers.png)

A list of the application's subscribers is also displayed in the **[!UICONTROL Mobile application subscribers]** tab. Os assinantes são todos os usuários que instalaram o aplicativo em seu dispositivo móvel. Os perfis de banco de dados do Adobe Campaign são identificados com um token de registro.

## Accessing collected location data {#accessing-collected-location-data}

Once the setup is done, the collected Points of Interest data is listed in the **[!UICONTROL Places]** tab of each profile. Para acessar a lista:

1. Selecione um perfil.
1. Click the **[!UICONTROL Edit profile properties]** button on the right.
1. Select the **[!UICONTROL Places]** tab.

   ![](assets/poi_profile_places.png)

Os dados de Pontos de interesse coletados para o perfil atual são listados. Os dados de localização são armazenados no banco de dados do Adobe Campaign por seis meses.

For more information on accessing and editing profiles, see [Profiles](../../audiences/using/about-profiles.md).
