---
solution: Campaign Standard
product: campaign
title: Configuração da integração de dados do Campaign com os Pontos de interesse
description: Saiba como configurar o recurso de dados de Pontos de interesse no Adobe Campaign para enviar mensagens personalizadas com base na localização dos assinantes.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '1340'
ht-degree: 3%

---


# Configuração da integração de dados do Campaign com os Pontos de interesse{#configuring-campaign-points-of-interest-data-integration}

## Configuração da integração de dados de Pontos de Campanha de interesse com SDKs Adobe Experience Platform {#configuring-campaign-poi-aep-sdk}

>[!NOTE]
>
>Seu aplicativo móvel já deve estar configurado no Adobe Campaign Standard usando o Adobe Experience Platform SDK. For the detailed steps, refer to this [page](https://helpx.adobe.com/br/campaign/kb/configuring-app-sdk.html).

Os aplicativos móveis usados para coletar dados de localização devem ser configurados por um **administrador** na interface do Adobe Campaign.

Para poder usar os Adobe Experience Platform Location Services com aplicativos móveis configurados com o Adobe Experience Platform SDK, é necessário:

1. Adicione as extensões **[!UICONTROL Places]** e **[!UICONTROL Places Monitor]** à configuração do aplicativo móvel no Adobe Experience Platform Launch. Configure seu aplicativo móvel no Adobe Campaign. Consulte [Instalar a extensão de Locais no Adobe Experience Platform Launch](https://docs.adobe.com/content/help/en/places/using/places-ext-aep-sdks/places-extension/places-extension.html#install-the-places-extension-in-adobe-experience-platform-launch) e [Instalar a extensão do Monitor de Lugares no Experience Platform Launch](https://docs.adobe.com/content/help/en/places/using/places-ext-aep-sdks/places-monitor-extension/using-places-monitor-extension.html#install-the-places-monitor-extension-in-experience-platform-launch).

1. Depois que suas extensões forem configuradas, crie elementos de dados dentro **[!UICONTROL Adobe Experience Platform Launch]** para recuperar dados dessas extensões. Consulte esta [página](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Step1Createdataelements) para criar seus elementos de dados.

1. Em seguida, em **[!UICONTROL Adobe Experience Platform Launch]**, é necessário criar regras para suportar casos de uso móvel entre Ponto de interesse e Adobe Campaign.\
   Essa regra será acionada quando um usuário entrar em uma área delimitada geograficamente **[!UICONTROL Point of Interest]**. Consulte esta [página](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Locationpostback) para criar sua regra.

1. Defina o seu **[!UICONTROL Points of Interest]** em Locais. Consulte [Criar um ponto de interesse](https://docs.adobe.com/content/help/en/places/using/poi-mgmt-ui/create-a-poi-ui.html).

1. Certifique-se de acessar o aplicativo móvel e os dados de localização coletados no Adobe Campaign. Consulte [Acessar aplicativos móveis usados para coletar dados](#accessing-mobile-apps-used-to-collect-location-data) de localização e [Acessar dados](#accessing-collected-location-data)de localização coletados.

## Configuração da integração de dados de Pontos de Campanha de interesse usando o SDK V4 {#configuring-campaign-poi-sdkv4}

Os aplicativos móveis usados para coletar dados de localização devem ser configurados por um **administrador** na interface do Adobe Campaign.

Para usar o recurso de dados Ponto de interesse com aplicativos móveis configurados com SDK V4, é necessário:

1. Tenha acesso ao Adobe Analytics para dispositivos móveis. Verifique seu contrato de licença ou entre em contato com o executivo da sua Conta Adobe para obter mais informações.
1. Configure seu aplicativo móvel no Adobe Campaign. Consulte [Configurar um aplicativo móvel na Campaign](#setting-up-a-mobile-app-in-campaign).
1. Configure seu aplicativo móvel na interface do Adobe Mobile Services. Isso permite garantir que os dados coletados pelo Adobe Mobile Services sejam enviados para a Adobe Campaign. Consulte [Configurar um aplicativo móvel no Adobe Mobile Services](#configuring-a-mobile-app-in-adobe-mobile-services).
1. Execute a configuração específica do aplicativo móvel:

   * Compacte o arquivo de configuração baixado da interface do Adobe Mobile Services com o aplicativo móvel.
   * Integre o SDK do Experience Cloud Mobile ao seu aplicativo móvel. Consulte [Integrar o SDK a um aplicativo](#integrating-the-sdk-into-a-mobile-application)móvel.

1. Defina Pontos de interesse na interface do Adobe Mobile Services. Consulte [Definição de pontos de interesse no Adobe Mobile Services](#defining-points-of-interest-in-adobe-mobile-services).
1. Defina os dados que deseja coletar dos assinantes do aplicativo móvel. Consulte [Coletando dados](#collecting-subscribers--points-of-interest-data)de Pontos de interesse dos assinantes.
1. Certifique-se de acessar o aplicativo móvel e os dados de localização coletados no Adobe Campaign. Consulte [Acessar aplicativos móveis usados para coletar dados](#accessing-mobile-apps-used-to-collect-location-data) de localização e [Acessar dados](#accessing-collected-location-data)de localização coletados.

### Configuração de um aplicativo móvel no Adobe Campaign usando o SDK V4 {#setting-up-a-mobile-app-in-campaign}

Para poder coletar dados de Pontos de interesse com a Adobe Campaign, é necessário configurar o aplicativo móvel do qual a Adobe Campaign receberá dados.

1. Clique no logotipo **[!UICONTROL Adobe Campaign]**, no canto superior esquerdo, em seguida selecione **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app]**.
1. Clique em **[!UICONTROL Create]** para configurar um aplicativo.
1. Enter a name in the **[!UICONTROL Application name]** field and click **[!UICONTROL Create]**.

   Não preencha a **[!UICONTROL Device-specific settings]** seção. Isso se aplica somente à configuração de aplicativos que recebem notificações por push.

Na **[!UICONTROL Mobile application properties]** seção, dois URLs são listados: **[!UICONTROL Collect PII endpoint]** e **[!UICONTROL Location Services endpoint]**. Eles serão usados na interface do Adobe Mobile Services. Consulte [Configurar um aplicativo móvel no Adobe Mobile Services](#configuring-a-mobile-app-in-adobe-mobile-services).

* O **[!UICONTROL Collect PII endpoint]** URL é usado para coletar as IDs de Experience Cloud dos usuários e os tokens de registro do aplicativo móvel quando ele é iniciado. Quando um usuário entra no aplicativo usando credenciais como email, nome, sobrenome etc., esses dados também são coletados e usados para reconciliar o token de registro do usuário com um perfil Adobe Campaign.
* O **[!UICONTROL Location Services endpoint]** URL é usado para coletar dados de localização, como latitude, longitude e raio de um usuário de um Ponto de interesse.

Agora você pode usar esses valores no Adobe Mobile Services para concluir a configuração, como explicado na seção [Configuração de um aplicativo móvel na seção Adobe Mobile Services](#configuring-a-mobile-app-in-adobe-mobile-services) .

![](assets/poi_mobile_app_properties.png)

### Configuração de um aplicativo móvel V4 no Adobe Mobile Services {#configuring-a-mobile-app-in-adobe-mobile-services}

Para enviar os dados coletados pelo Adobe Mobile Services para a Adobe Campaign, você deve configurar postbacks na interface do Mobile Services.

Você precisará de informações específicas que possam ser encontradas nos parâmetros do aplicativo móvel definidos no Adobe Campaign (consulte [Configuração de um aplicativo móvel na Campanha](#setting-up-a-mobile-app-in-campaign)):

* **[!UICONTROL IMS Organization ID]**
* **[!UICONTROL Collect PII Endpoint]**
* **[!UICONTROL Location Services endpoint]**

É necessário ter acesso ao Adobe Analytics para fazer a seguinte configuração. Se você não for um usuário do Adobe Analytics, entre em contato com o administrador do Adobe Campaign.

1. Faça logon em [mobilemarketing.adobe.com](https://mobilemarketing.adobe.com/).
1. Crie o aplicativo ou selecione um existente.
1. Go to the **[!UICONTROL Manage App Settings]** page.
1. Na seção Serviço **de ID de** Visitante, marque **Ativar** e selecione sua organização na lista suspensa. Clique em **Save**.

   >[!CAUTION]
   >
   >Essa organização deve ser a mesma usada na instância do Adobe Campaign.

1. Clique em **[!UICONTROL Manage Postbacks]**.
1. Crie um postback.

   * Selecione **[!UICONTROL PII]** como o **[!UICONTROL Postback Type]**.
   * No **[!UICONTROL URL]** campo, copie o **[!UICONTROL Collect PII Endpoint]** URL do aplicativo móvel que você configurou na interface do Adobe Campaign, precedido pelo nome do servidor. Consulte [Configurar um aplicativo móvel na Campaign](#setting-up-a-mobile-app-in-campaign).
   * Preencha o **[!UICONTROL Post Body]** campo da seguinte forma:

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

   * Defina Tipo **** de conteúdo como **[!UICONTROL application/json]**.
   * Em **Quais tags de dados acionam o postback?**, selecione qualquer evento, normalmente **[!UICONTROL Launched]** e **[!UICONTROL exists]**.
   * Clique em **[!UICONTROL Save & Activate]**.

1. Crie um segundo postback.

   * Selecione **[!UICONTROL Postback]** como o **[!UICONTROL Postback Type]**.
   * No **[!UICONTROL URL]** campo, copie o **[!UICONTROL Location Services Endpoint]** URL do aplicativo móvel que você configurou na interface do Adobe Campaign, precedido pelo nome do servidor. Consulte [Configurar um aplicativo móvel na Campaign](#setting-up-a-mobile-app-in-campaign).
   * Preencha o **[!UICONTROL Post Body]** campo da seguinte forma:

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

   * Defina Tipo **** de conteúdo como **[!UICONTROL application/json]**.
   * Em **Quais tags de dados acionam o postback?**, selecione **[!UICONTROL campaign.test]** e **[!UICONTROL exists]**.
   * Clique em **[!UICONTROL Save & Activate]**.

>[!NOTE]
>
>Para obter informações detalhadas sobre como configurar postbacks, consulte a documentação [do](https://docs.adobe.com/content/help/en/mobile-services/using/manage-app-settings-ug/configuring-app/signals.html)Adobe Mobile Services.

### Integrating the SDK into a mobile application {#integrating-the-sdk-into-a-mobile-application}

O kit de desenvolvimento de software (SDK) do Mobile Core Service facilita a integração de um aplicativo móvel ao Adobe Campaign.

Esta etapa está descrita nesta [página](https://helpx.adobe.com/br/campaign/kb/configuring-app-sdkv4.html).

### Definição de pontos de interesse no Adobe Mobile Services {#defining-points-of-interest-in-adobe-mobile-services}

Para definir os Pontos de interesse usados para coletar dados de localização:

1. Vá para a interface do Adobe Mobile Services.
1. Adicione seu aplicativo.

   Para obter mais informações sobre como gerenciar aplicativos no Mobile Services, consulte a documentação [do](https://docs.adobe.com/content/help/en/mobile-services/using/manage-apps-ug/t-new-app.html)Adobe Mobile Services.

1. Defina os Pontos de interesse.

   Para obter mais informações sobre como gerenciar pontos de interesse, consulte a documentação [do](https://docs.adobe.com/content/help/en/mobile-services/using/location-ug/t-manage-points.html)Adobe Mobile Services.

### Recolha de dados sobre os pontos de interesse dos assinantes {#collecting-subscribers--points-of-interest-data}

Um recurso personalizado específico permite que você defina os dados que deseja coletar dos assinantes de seus aplicativos.

Esta etapa é descrita em [Configuração de um aplicativo móvel usando a página SDK V4](https://helpx.adobe.com/br/campaign/kb/configuring-app-sdkv4.html) .


## Acessar aplicativos móveis usados para coletar dados de localização {#accessing-mobile-apps-used-to-collect-location-data}

Para acessar os aplicativos criados com êxito no Adobe Campaign:

1. Click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner.
1. Selecione **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK v4)]** ou **[!UICONTROL Mobile app (AEP SDK)]** dependendo do SDK.
1. Selecione um aplicativo móvel na lista para exibir suas propriedades.

   ![](assets/poi_mobile_app_subscribers.png)

Uma lista dos assinantes do aplicativo também é exibida na guia **[!UICONTROL Mobile application subscribers]** . Os assinantes são todos os usuários que instalaram o aplicativo em seu dispositivo móvel. Os perfis do banco de dados Adobe Campaign são identificados com um token de registro.

## Acessar dados de localização coletados {#accessing-collected-location-data}

Quando a configuração estiver concluída, os dados coletados de Pontos de interesse serão listados na **[!UICONTROL Places]** guia de cada perfil. Para acessar a lista:

1. Selecione um perfil.
1. Click the **[!UICONTROL Edit profile properties]** button on the right.
1. Selecione a guia **[!UICONTROL Places]**.

   ![](assets/poi_profile_places.png)

Os dados de Pontos de interesse coletados para o perfil atual são listados. Os dados de localização são armazenados no banco de dados da Adobe Campaign por seis meses.

Para obter mais informações sobre como acessar e editar perfis, consulte [Perfis](../../audiences/using/about-profiles.md).
