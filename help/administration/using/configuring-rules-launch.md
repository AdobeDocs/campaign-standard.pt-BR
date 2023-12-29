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

Na interface da Coleção de dados, crie elementos de dados e regras para enviar PII e outros dados de aplicativos móveis para o [!DNL Adobe Campaign Standard].

Para garantir que todas as alterações de configuração na interface da Coleção de dados tenham efeito, publique essas alterações. Para obter mais informações, consulte [Publicação](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/#publish-the-configuration).

Para criar regras na interface da Coleção de dados, siga estas etapas:

1. [Criação de elementos de dados](../../administration/using/configuring-rules-launch.md#create-data-elements)
2. [Criação de regras](../../administration/using/configuring-rules-launch.md#create-data-elements) para casos de uso que você deseja suportar:
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

1. Na interface da Coleção de dados, no painel do aplicativo móvel, clique na **[!UICONTROL Data Elements]** guia.

1. Para criar o **[!UICONTROL Experience Cloud ID]** elemento de dados, clique em **[!UICONTROL Create New Data Element]**.

1. No **[!UICONTROL Name]** por exemplo, digite em **mcid**.

1. No **[!UICONTROL Extension]** selecione **[!UICONTROL Mobile Core]**. Depois **[!UICONTROL Experience Cloud ID]** no **[!UICONTROL Data element]** menu suspenso de tipo.

   ![](assets/do-not-localize/rules_1.png)

1. Para criar o elemento de dados Pkey, clique em **[!UICONTROL Add data element]**.

1. No **[!UICONTROL Name]** por exemplo, digite em **pkey**.

1. No **[!UICONTROL Extension]** selecione **[!UICONTROL Adobe Campaign Standard]**. Depois **[!UICONTROL pkey]** no **[!UICONTROL Data element]** menu suspenso de tipo.

1. Para criar o elemento de dados do servidor do Campaign, clique em **[!UICONTROL Add data element]**.

1. No **[!UICONTROL Name]** digite um nome, por exemplo, **camp-server**.

1. No **[!UICONTROL Extension]** selecione **[!UICONTROL Adobe Campaign Standard]**. Em seguida, **[!UICONTROL Campaign Server]** no **[!UICONTROL Data element]** menu suspenso de tipo.

## Criação de regras {#creating-rules}

Você deve criar regras para o seguinte:

* [Postback de PII](../../administration/using/configuring-rules-launch.md#pii-postback)
* [Postback de rastreamento no aplicativo](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
* [Postback de rastreamento de notificações por push](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
* [Postback de localização](../../administration/using/configuring-rules-launch.md#location-postback)

### Postback de PII {#pii-postback}

>[!NOTE]
>
>Para enviar informações de PII de um aplicativo móvel para o Adobe Campaign, é necessário implementar uma API do SDK. Para obter mais informações, acesse [CollectPII](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#collectpii).

Para enviar dados de PII para o [!DNL Adobe Campaign Standard], crie uma regra na interface da Coleção de dados:

1. Na interface da Coleção de dados, no painel do aplicativo móvel, clique na **[!UICONTROL Rules]** depois guia **[!UICONTROL Create New Rule]**.

1. Digite um nome, por exemplo, **Mobile Core - Coletar PII**.

1. No **[!UICONTROL Events]** clique em **[!UICONTROL Add]**.

1. No **[!UICONTROL Extension]** selecione **[!UICONTROL Mobile Core]**. Em seguida, **[!UICONTROL Collect PII]** no **[!UICONTROL Event type]** menu suspenso.

1. Clique em **[!UICONTROL Keep changes]**.

1. No **[!UICONTROL Actions]** clique em **[!UICONTROL Add]**.

1. No **[!UICONTROL Extension]** selecione **[!UICONTROL Mobile Core]**. Em seguida, **[!UICONTROL Send PII]** no **[!UICONTROL Action type]** menu suspenso.

1. Entrada **[!UICONTROL URL]**, insira o seguinte URL:

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/subscriptions/{%%mcid%%}
   ```

1. Selecione o **[!UICONTROL Add Post Body]** caixa de seleção

1. Entrada **[!UICONTROL Post Body]**, digite o seguinte:

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

   Os elementos de dados definidos na interface da Coleção de dados devem ser colocados em porcentagens duplas, por exemplo `%%mcid%%`As variáveis de contexto e do aplicativo devem ser colocadas em porcentagens únicas, por exemplo %contextdata.email%.

1. Entrada **[!UICONTROL Content Type]**, tipo **application/json**.

1. Entrada **[!UICONTROL Timeout]**, selecione 0.

   ![](assets/do-not-localize/rules_2.png)

Os dados do usuário agora estão configurados para serem enviados ao Campaign.

### Postback de rastreamento no aplicativo {#inapp-tracking-postback}

>[!NOTE]
>
>Se você estiver usando o Android ACPCore v1.4.0 ou posterior/ iOS ACPCore v2.3.0 ou posterior, não é necessário configurar o rastreamento de postbacks.

Para enviar dados de rastreamento ao [!DNL Adobe Campaign Standard] para criar relatórios sobre como os usuários interagem com mensagens no aplicativo móvel, crie a seguinte regra na interface da Coleção de dados:

1. Na interface da Coleção de dados, no painel do aplicativo móvel, selecione a variável **[!UICONTROL Rules]** e clique em **[!UICONTROL Add Rule]**.

1. Digite um nome, por exemplo, **Adobe Campaign - Rastreamento de cliques no aplicativo**.

1. No **[!UICONTROL Events]** clique em **[!UICONTROL Add]**.

1. No **[!UICONTROL Extension]** selecione **[!UICONTROL Adobe Campaign Standard]**. Em seguida, **[!UICONTROL In-App click tracking]** no **[!UICONTROL Event type]** menu suspenso.

1. Clique em **[!UICONTROL Keep changes]**.

1. No **[!UICONTROL Actions]** clique em **[!UICONTROL Add]**.

1. No **[!UICONTROL Extension]** selecione **[!UICONTROL Mobile Core]**. Em seguida, **[!UICONTROL Send postback]** no **[!UICONTROL Event type]** menu suspenso.

1. Entrada **[!UICONTROL URL]**, digite o seguinte URL:

   ```
   https://{%%camp-server%%}/r/?id={%id%}&mcid={%%mcid%%}
   ```

1. Selecione o **[!UICONTROL Add post body]** caixa de seleção

1. Entrada **[!UICONTROL Post Body]**, tipo **{}**.

1. Entrada **[!UICONTROL Content Type]**, tipo **application/json**.

1. Entrada **[!UICONTROL Timeout]**, selecione 0.

   ![](assets/do-not-localize/rules_3.png)

### Postback de rastreamento de notificações por push {#push-tracking-postback}

>[!NOTE]
>
>Se você estiver usando o Android ACPCore v1.4.0 ou posterior/ iOS ACPCore v2.3.0 ou posterior, não é necessário configurar o rastreamento de postbacks.

Para enviar dados de rastreamento ao [!DNL Adobe Campaign Standard], que ajuda a rastrear os deliveries de notificação por push e a interação dos usuários com o aplicativo móvel, é necessário criar uma regra na interface da Coleção de dados.

Para obter mais informações sobre o rastreamento de push, consulte [Rastreamento por push](../../administration/using/push-tracking.md).

Para rastrear as ações do aplicativo, use a API trackAction. Para obter mais informações, consulte [Rastrear ações do aplicativo](https://app.gitbook.com/@aep-sdks/s/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions).

1. Na interface da Coleção de dados, no painel do aplicativo móvel, clique na **[!UICONTROL Rules]** e clique em **[!UICONTROL Add Rule]**.

1. Digite um nome, por exemplo, **Adobe Campaign - rastreamento de cliques por push**.

1. No **[!UICONTROL Events]** clique em **[!UICONTROL Add]**.

1. No **[!UICONTROL Extension]** selecione **[!UICONTROL Mobile Core]**. Em seguida, **[!UICONTROL Track Action]** no **[!UICONTROL Event type]** menu suspenso.

1. No **[!UICONTROL Action]** selecione **[!UICONTROL Action]**, selecione **[!UICONTROL equals]**, e digite **rastreamento**.

1. Clique em **[!UICONTROL Keep changes]**. Em seguida, no **[!UICONTROL Actions]** clique em **[!UICONTROL Add]**.

1. No **[!UICONTROL Extension]** selecione **[!UICONTROL Mobile Core]**. Em seguida, **[!UICONTROL Send postback]** no **[!UICONTROL Action type]** menu suspenso.

1. Entrada **[!UICONTROL URL]**, insira o seguinte URL:

   ```
   https://{%%camp-server%%}/r/?id={%contextdata.broadlogId%},{%contextdata.deliveryId%},{%contextdata.action%}&mcId={%%mcid%%}
   ```

1. Selecione o **[!UICONTROL Add post body]** caixa de seleção

1. Adicione o corpo da publicação, por exemplo, { }.

1. Entrada **[!UICONTROL Content Type]**, tipo **application/json**.

1. Entrada **[!UICONTROL Timeout]**, selecione 0.

### Postback de localização {#location-postback}

1. Na interface da Coleção de dados, no painel do aplicativo móvel, clique na **[!UICONTROL Rules]** e clique em **[!UICONTROL Add Rule]**.

1. Digite um nome, por exemplo, **Postback de localização**.

1. No **[!UICONTROL Events]** clique em **[!UICONTROL Add]**.

1. Crie um evento, por exemplo, Enter POI ou Exit POI. No **[!UICONTROL Extension]** selecione **Places - Beta**. Em seguida, **Inserir POI** ou **POI de saída** no **[!UICONTROL Event type]** menu suspenso.

1. Insira um nome, por exemplo, **Places - Beta - Inserir POI** ou **POI de saída**.

1. No **[!UICONTROL Actions]** clique em **[!UICONTROL Add]**.

1. No **[!UICONTROL Extension]** selecione **[!UICONTROL Mobile Core]**. Em seguida, **[!UICONTROL Send postback]** do **[!UICONTROL Action type]** menu suspenso.

1. Insira um nome, por exemplo, **Mobile Core - Enviar postback de localização**.

1. Entrada **[!UICONTROL URL]**, insira o seguinte URL:

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/locations/
   ```

1. Selecione o **[!UICONTROL Add post body]** e adicione o corpo da publicação, por exemplo:

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
   >No exemplo acima, os elementos de dados no lado direito devem ser configurados na interface da Coleção de dados aproveitando as etapas em [Criação de elementos de dados](../../administration/using/configuring-rules-launch.md#create-data-elements). Os elementos de dados no lado esquerdo são compatíveis com o [!DNL Adobe Campaign Standard] e não precisam de configuração. Se precisar de dados adicionais, você deverá fazer extensões de recursos personalizadas no [!DNL Adobe Campaign Standard].

1. Entrada **[!UICONTROL Content Type]**, tipo **application/json**.

1. Entrada **[!UICONTROL Timeout]**, selecione 5.

   ![](assets/do-not-localize/rules_4.png)
