---
title: Configuração das regras de tag para oferecer suporte a casos de uso do Adobe Campaign Standard
description: Saiba como configurar regras de tag para suportar casos de uso do Adobe Campaign Standard
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Instance Settings
role: Admin
level: Experienced
exl-id: b5f4f612-ea23-4007-b427-069777ecdd58
source-git-commit: 597ece8d833a216f0540f801461b08fdc9865024
workflow-type: tm+mt
source-wordcount: '983'
ht-degree: 2%

---

# Configuração das regras de tag para oferecer suporte a casos de uso do Adobe Campaign Standard {#configuring-rules-launch}

Na interface da Coleção de Dados, crie elementos de dados e regras para enviar PII e outros dados de aplicativos móveis para [!DNL Adobe Campaign Standard].

Para garantir que todas as alterações de configuração na interface da Coleção de dados tenham efeito, publique essas alterações. Para obter mais informações, consulte [Publicação](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/#publish-the-configuration).

Para criar regras na interface da Coleção de dados, siga estas etapas:

1. [Criação de elementos de dados](../../administration/using/configuring-rules-launch.md#create-data-elements)
2. [Criando regras](../../administration/using/configuring-rules-launch.md#create-data-elements) para casos de uso aos quais você deseja oferecer suporte:
   * [Postback de PII](../../administration/using/configuring-rules-launch.md#pii-postback)
   * [Postback de rastreamento no aplicativo](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
   * [Postback de rastreamento de notificações por push](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
   * [Postback de localização](../../administration/using/configuring-rules-launch.md#location-postback)

## Criação de elementos de dados {#create-data-elements}

Estes são os elementos de dados que recomendamos criar na interface da Coleção de dados.
Você pode criar elementos de dados adicionais de acordo com suas necessidades.

* **[!UICONTROL Experience Cloud ID]**
* **[!UICONTROL Pkey]**
* **[!UICONTROL Campaign server]**

Para criar esses elementos de dados:

1. Na interface da Coleção de dados, no painel do aplicativo móvel, clique na guia **[!UICONTROL Data Elements]**.

1. Para criar o elemento de dados **[!UICONTROL Experience Cloud ID]**, clique em **[!UICONTROL Create New Data Element]**.

1. No campo **[!UICONTROL Name]**, por exemplo, digite **mcid**.

1. No menu suspenso **[!UICONTROL Extension]**, selecione **[!UICONTROL Mobile Core]**. Depois **[!UICONTROL Experience Cloud ID]** no menu suspenso de tipos **[!UICONTROL Data element]**.

   ![](assets/do-not-localize/rules_1.png)

1. Para criar o elemento de dados Pkey, clique em **[!UICONTROL Add data element]**.

1. No campo **[!UICONTROL Name]**, por exemplo, digite **pkey**.

1. No menu suspenso **[!UICONTROL Extension]**, selecione **[!UICONTROL Adobe Campaign Standard]**. Depois **[!UICONTROL pkey]** no menu suspenso de tipos **[!UICONTROL Data element]**.

1. Para criar o elemento de dados do servidor do Campaign, clique em **[!UICONTROL Add data element]**.

1. No campo **[!UICONTROL Name]**, digite um nome, por exemplo, **camp-server**.

1. No menu suspenso **[!UICONTROL Extension]**, selecione **[!UICONTROL Adobe Campaign Standard]**. Em seguida, **[!UICONTROL Campaign Server]** no menu suspenso de tipos **[!UICONTROL Data element]**.

## Criação de regras {#creating-rules}

Você deve criar regras para o seguinte:

* [Postback de PII](../../administration/using/configuring-rules-launch.md#pii-postback)
* [Postback de rastreamento no aplicativo](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
* [Postback de rastreamento de notificações por push](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
* [Postback de localização](../../administration/using/configuring-rules-launch.md#location-postback)

### Postback de PII {#pii-postback}

>[!NOTE]
>
>Para enviar informações de PII de um aplicativo móvel para o Adobe Campaign, é necessário implementar uma API do SDK. Para obter mais informações, vá para [CollectPII](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#collectpii).

Para enviar dados de PII para [!DNL Adobe Campaign Standard], crie uma regra na interface da Coleção de Dados:

1. Na interface da Coleção de dados, no painel do aplicativo móvel, clique na guia **[!UICONTROL Rules]** e depois em **[!UICONTROL Create New Rule]**.

1. Digite um nome, por exemplo, **Mobile Core - Coletar PII**.

1. Na seção **[!UICONTROL Events]**, clique em **[!UICONTROL Add]**.

1. No menu suspenso **[!UICONTROL Extension]**, selecione **[!UICONTROL Mobile Core]**. Em seguida, **[!UICONTROL Collect PII]** no menu suspenso **[!UICONTROL Event type]**.

1. Clique em **[!UICONTROL Keep changes]**.

1. Na seção **[!UICONTROL Actions]**, clique em **[!UICONTROL Add]**.

1. No menu suspenso **[!UICONTROL Extension]**, selecione **[!UICONTROL Mobile Core]**. Em seguida, **[!UICONTROL Send PII]** no menu suspenso **[!UICONTROL Action type]**.

1. Em **[!UICONTROL URL]**, insira a seguinte URL:

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/subscriptions/{%%mcid%%}
   ```

1. Marque a caixa de seleção **[!UICONTROL Add Post Body]**.

1. Em **[!UICONTROL Post Body]**, digite o seguinte:

   ```
   {
   "marketingCloudId":
   "{%%mcid%%}",
   "pushPlatform":
   "{%contextdata.pushPlatform%}",
   "cusEmail":
   "{%contextdata.email%}",
   "cusFirstName":
   "{%contextdata.firstName%}",
   "cusLastName":
   "{%contextdata.lastName%}" }
   ```

   A marketingCloudId permite reconciliar os assinantes de aplicativo com os recipients no banco de dados e, como resultado, é necessária. Você pode especificar outros pares de valor-chave de acordo com suas necessidades comerciais. No exemplo acima, Email, Nome e Sobrenome estão sendo transmitidos do aplicativo.

   As chaves (por exemplo cusEmail, cusFirstName e cusLastName) devem corresponder às IDs de campo definidas no recurso personalizado na instância do Adobe Campaign Standard. As variáveis de valor (por exemplo, email, firstName e LastName) devem corresponder às chaves nos dados JSON enviados pelo aplicativo móvel ao chamar a API collectPII do AMS a partir do código do aplicativo.

   Você também pode enviar dados do ciclo de vida no postback Coletar PII ou em um postback diferente, dependendo dos acionadores do Evento. este é um exemplo do JSON de dados do ciclo de vida:

   ```
   {
   "marketingCloudId":"{%%mcid%%}",
   "pushPlatform":"{%contextdata.pushPlatform%}",
   "cusDayslastlaunch": "{%%DaysSinceLastUse%%}", 
   "cusDaysfirstlaunch": "{%%DaysSinceFirstUse%%}", 
   "cusLaunches": "{%%Launches%%}"
   }
   ```

   Os elementos de dados definidos na interface da Coleção de dados devem ser colocados em porcentagens duplas, por exemplo `%%mcid%%`, e as variáveis de contexto do aplicativo devem ser colocadas em porcentagens únicas, por exemplo %contextdata.email%.

1. Em **[!UICONTROL Content Type]**, digite **application/json**.

1. Em **[!UICONTROL Timeout]**, selecione 0.

   ![](assets/do-not-localize/rules_2.png)

Os dados do usuário agora estão configurados para serem enviados ao Campaign.

### Postback de rastreamento no aplicativo {#inapp-tracking-postback}

>[!NOTE]
>
>Se estiver usando o Android ACPCore v1.4.0 ou posterior/ iOS ACPCore v2.3.0 ou posterior, não será necessário configurar o rastreamento de postbacks.

Para enviar dados de rastreamento ao [!DNL Adobe Campaign Standard] para relatórios sobre como os usuários interagem com mensagens no aplicativo em seu aplicativo móvel, crie a seguinte regra na interface da Coleção de Dados:

1. Na interface da Coleção de Dados, no painel do aplicativo móvel, selecione a guia **[!UICONTROL Rules]** e clique em **[!UICONTROL Add Rule]**.

1. Digite um nome, por exemplo, **Adobe Campaign - Rastreamento de cliques no aplicativo**.

1. Na seção **[!UICONTROL Events]**, clique em **[!UICONTROL Add]**.

1. No menu suspenso **[!UICONTROL Extension]**, selecione **[!UICONTROL Adobe Campaign Standard]**. Em seguida, **[!UICONTROL In-App click tracking]** no menu suspenso **[!UICONTROL Event type]**.

1. Clique em **[!UICONTROL Keep changes]**.

1. Na seção **[!UICONTROL Actions]**, clique em **[!UICONTROL Add]**.

1. No menu suspenso **[!UICONTROL Extension]**, selecione **[!UICONTROL Mobile Core]**. Em seguida, **[!UICONTROL Send postback]** no menu suspenso **[!UICONTROL Event type]**.

1. Em **[!UICONTROL URL]**, digite a seguinte URL:

   ```
   https://{%%camp-server%%}/r/?id={%id%}&mcid={%%mcid%%}
   ```

1. Marque a caixa de seleção **[!UICONTROL Add post body]**.

1. Em **[!UICONTROL Post Body]**, digite **{}**.

1. Em **[!UICONTROL Content Type]**, digite **application/json**.

1. Em **[!UICONTROL Timeout]**, selecione 0.

   ![](assets/do-not-localize/rules_3.png)

### Postback de rastreamento de notificações por push {#push-tracking-postback}

>[!NOTE]
>
>Se estiver usando o Android ACPCore v1.4.0 ou posterior/ iOS ACPCore v2.3.0 ou posterior, não será necessário configurar o rastreamento de postbacks.

Para enviar dados de rastreamento para o [!DNL Adobe Campaign Standard], que ajuda a rastrear as entregas de notificação por push e a interação dos usuários com o aplicativo móvel, é necessário criar uma regra na interface da Coleção de dados.

Para obter mais informações sobre o rastreamento de push, consulte [Rastreamento de push](../../administration/using/push-tracking.md).

Para rastrear as ações do aplicativo, use a API trackAction. Para obter mais informações, consulte [Rastrear ações do aplicativo](https://app.gitbook.com/@aep-sdks/s/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions).

1. Na interface da Coleção de dados, no painel do aplicativo móvel, clique na guia **[!UICONTROL Rules]** e em **[!UICONTROL Add Rule]**.

1. Digite um nome, por exemplo, **Adobe Campaign - rastreamento de cliques por push**.

1. Na seção **[!UICONTROL Events]**, clique em **[!UICONTROL Add]**.

1. No menu suspenso **[!UICONTROL Extension]**, selecione **[!UICONTROL Mobile Core]**. Em seguida, **[!UICONTROL Track Action]** no menu suspenso **[!UICONTROL Event type]**.

1. Na lista suspensa **[!UICONTROL Action]**, selecione **[!UICONTROL Action]**, selecione **[!UICONTROL equals]** e digite **tracking**.

1. Clique em **[!UICONTROL Keep changes]**. Na seção **[!UICONTROL Actions]**, clique em **[!UICONTROL Add]**.

1. No menu suspenso **[!UICONTROL Extension]**, selecione **[!UICONTROL Mobile Core]**. Em seguida, **[!UICONTROL Send postback]** no menu suspenso **[!UICONTROL Action type]**.

1. Em **[!UICONTROL URL]**, insira a seguinte URL:

   ```
   https://{%%camp-server%%}/r/?id={%contextdata.broadlogId%},{%contextdata.deliveryId%},{%contextdata.action%}&mcId={%%mcid%%}
   ```

1. Marque a caixa de seleção **[!UICONTROL Add post body]**.

1. Adicione o corpo da publicação, por exemplo, { }.

1. Em **[!UICONTROL Content Type]**, digite **application/json**.

1. Em **[!UICONTROL Timeout]**, selecione 0.

### Postback de localização {#location-postback}

1. Na interface da Coleção de dados, no painel do aplicativo móvel, clique na guia **[!UICONTROL Rules]** e em **[!UICONTROL Add Rule]**.

1. Digite um nome, por exemplo, **Postback de localização**.

1. Na seção **[!UICONTROL Events]**, clique em **[!UICONTROL Add]**.

1. Crie um evento, por exemplo, Enter POI ou Exit POI. No menu suspenso **[!UICONTROL Extension]**, selecione **Places - Beta**. Em seguida, **Insira o POI** ou **Saia do POI** no menu suspenso **[!UICONTROL Event type]**.

1. Insira um nome, por exemplo, **Places - Beta - Insira o POI** ou **Saia do POI**.

1. Na seção **[!UICONTROL Actions]**, clique em **[!UICONTROL Add]**.

1. No menu suspenso **[!UICONTROL Extension]**, selecione **[!UICONTROL Mobile Core]**. Em seguida, **[!UICONTROL Send postback]** no menu suspenso **[!UICONTROL Action type]**.

1. Insira um nome, por exemplo, **Mobile Core - Enviar postback de localização**.

1. Em **[!UICONTROL URL]**, insira a seguinte URL:

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/locations/
   ```

1. Marque a caixa de seleção **[!UICONTROL Add post body]** e adicione o corpo da publicação, por exemplo:

   ```
   {
   "locationData": {
       "distances": "{%%Distance%%}",
       "poiLabel": "{%%POILabel%%}",
       "latitude": "{%%Latitude%%}",
       "longitude": "{%%Longitude%%}",
       "appId": "{%%AppId%%}",
       "marketingCloudId": "{%%ECID%%}"
   }
   }
   ```

   >[!NOTE]
   >
   >No exemplo acima, os elementos de dados no lado direito devem ser configurados na interface da Coleção de Dados aproveitando as etapas em [Criação de elementos de dados](../../administration/using/configuring-rules-launch.md#create-data-elements). Os elementos de dados no lado esquerdo são compatíveis com o [!DNL Adobe Campaign Standard] e não precisam de configuração. Se você precisar de dados adicionais, deverá executar extensões de recursos personalizadas no [!DNL Adobe Campaign Standard].

1. Em **[!UICONTROL Content Type]**, digite **application/json**.

1. Em **[!UICONTROL Timeout]**, selecione 5.

   ![](assets/do-not-localize/rules_4.png)
