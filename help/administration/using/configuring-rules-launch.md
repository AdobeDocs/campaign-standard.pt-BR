---
solution: Campaign Standard
product: campaign
title: Configuração das regras do Adobe Experience Platform Launch para suportar casos de uso do Adobe Campaign Standard
description: Configuração das regras do Adobe Experience Platform Launch para suportar casos de uso do Adobe Campaign Standard
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Instance Settings
role: Administrator
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '918'
ht-degree: 5%

---


# Configuração das regras do Launch para suportar casos de uso do Adobe Campaign Standard {#configuring-rules-launch}

Em [!DNL Adobe Experience Platform Launch], é necessário criar elementos de dados e regras para enviar PII e outros dados de aplicativos móveis para [!DNL Adobe Campaign Standard].

Para garantir que todas as alterações de configuração em [!DNL Adobe Experience Platform Launch] entrem em vigor, você deve publicar essas alterações. Para obter mais informações, consulte [Publicação](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#publish-the-configuration).

Para criar regras em [!DNL Experience Platform Launch], siga estas etapas:

1. [Criação de elementos de dados](../../administration/using/configuring-rules-launch.md#create-data-elements)
2. [Criando ](../../administration/using/configuring-rules-launch.md#create-data-elements) regras para casos de uso que você deseja suportar:
   * [Postback PII](../../administration/using/configuring-rules-launch.md#pii-postback)
   * [Postback de rastreamento no aplicativo](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
   * [Postback de rastreamento de notificações por push](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
   * [Postback de localização](../../administration/using/configuring-rules-launch.md#location-postback)

## Criação de elementos de dados {#create-data-elements}

Aqui estão os elementos de dados que recomendamos que você crie em [!DNL Experience Platform Launch].
Você pode criar elementos de dados adicionais de acordo com suas necessidades.

* **[!UICONTROL Experience Cloud ID]**
* **[!UICONTROL Pkey]**
* **[!UICONTROL Campaign server]**

Para criar esses elementos de dados:

1. Em [!DNL Experience Platform Launch], no painel do aplicativo móvel, clique na guia **[!UICONTROL Data Elements]** .

1. Para criar o elemento de dados **[!UICONTROL Experience Cloud ID]**, clique em **[!UICONTROL Create New Data Element]**.

1. No campo **[!UICONTROL Name]**, por exemplo, digite **mcid**.

1. No menu suspenso **[!UICONTROL Extension]**, selecione **[!UICONTROL Mobile Core]**. Em seguida, **[!UICONTROL Experience Cloud ID]** no menu suspenso **[!UICONTROL Data element]** tipo .

   ![](assets/do-not-localize/rules_1.png)

1. Para criar o elemento de dados Pkey , clique em **[!UICONTROL Add data element]**.

1. No campo **[!UICONTROL Name]**, por exemplo, digite **chave**.

1. No menu suspenso **[!UICONTROL Extension]**, selecione **[!UICONTROL Adobe Campaign Standard]**. Em seguida, **[!UICONTROL pkey]** no menu suspenso **[!UICONTROL Data element]** tipo .

1. Para criar o elemento de dados do servidor do Campaign, clique em **[!UICONTROL Add data element]**.

1. No campo **[!UICONTROL Name]**, digite um nome, por exemplo, **camp-server**.

1. No menu suspenso **[!UICONTROL Extension]**, selecione **[!UICONTROL Adobe Campaign Standard]**. Em seguida, **[!UICONTROL Campaign Server]** no menu suspenso **[!UICONTROL Data element]** tipo .

## Criando regras {#creating-rules}

Você precisa criar regras para o seguinte:

* [Postback PII](../../administration/using/configuring-rules-launch.md#pii-postback)
* [Postback de rastreamento no aplicativo](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
* [Postback de rastreamento de notificações por push](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
* [Postback de localização](../../administration/using/configuring-rules-launch.md#location-postback)

### Postback PII {#pii-postback}

>[!NOTE]
>
>Para enviar informações de PII de um aplicativo móvel para o Adobe Campaign, é necessário implementar uma API do SDK. Para obter mais informações, vá para [CollectPII](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#collect-pii).

Para enviar dados PII para [!DNL Adobe Campaign Standard], crie uma regra em [!DNL Experience Platform Launch]:

1. Em [!DNL Experience Platform Launch], no painel do aplicativo móvel, clique na guia **[!UICONTROL Rules]** e em **[!UICONTROL Create New Rule]**.

1. Digite um nome, por exemplo, **Mobile Core - Collect PII**.

1. Na seção **[!UICONTROL Events]**, clique em **[!UICONTROL Add]**.

1. No menu suspenso **[!UICONTROL Extension]**, selecione **[!UICONTROL Mobile Core]**. Em seguida, **[!UICONTROL Collect PII]** no menu suspenso **[!UICONTROL Event type]**.

1. Clique em **[!UICONTROL Keep changes]**.

1. Na seção **[!UICONTROL Actions]**, clique em **[!UICONTROL Add]**.

1. No menu suspenso **[!UICONTROL Extension]**, selecione **[!UICONTROL Mobile Core]**. Em seguida, **[!UICONTROL Send PII]** no menu suspenso **[!UICONTROL Action type]**.

1. Em **[!UICONTROL URL]**, insira o seguinte URL:

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/subscriptions/{%%mcid%%}
   ```

1. Marque a caixa de seleção **[!UICONTROL Add Post Body]** .

1. Em **[!UICONTROL Post Body]**, digite o seguinte:

   ```
   {
   "marketingCloudId":
   "{%%mcid%%}",
   "cusEmail":
   "{%contextdata.email%}",
   "cusFirstName":
   "{%contextdata.firstName%}",
   "cusLastName":
   "{%contextdata.lastName%}" }
   ```

   O marketingCloudId permite reconciliar os assinantes do aplicativo com os recipients no banco de dados e, como resultado, é necessário. Você pode especificar outros pares de valores chave de acordo com as necessidades de sua empresa. No exemplo acima, Email, Nome e Sobrenome são transmitidos do aplicativo.

   As chaves (por exemplo, cusEmail, cusFirstName e cusLastName) devem corresponder às IDs de campo definidas no recurso personalizado na instância do Adobe Campaign Standard. As variáveis de valor (por exemplo, email, nome e sobrenome) devem corresponder às chaves nos dados JSON enviados do aplicativo móvel ao chamar a API collectPII do AMS do código de aplicativo.

   Você também pode passar os dados do ciclo de vida no postback Coletar PII ou em um postback diferente, dependendo dos acionadores de Evento . este é um exemplo do JSON de dados do ciclo de vida:

   ```
   {
   "marketingCloudId":"{%%mcid%%}",
   "cusDayslastlaunch": "{%%DaysSinceLastUse%%}", 
   "cusDaysfirstlaunch": "{%%DaysSinceFirstUse%%}", 
   "cusLaunches": "{%%Launches%%}"
   }
   ```

   Os elementos de dados definidos em [!DNL Experience Platform Launch] devem ser colocados em porcentagens duplas, por exemplo %%mcid%%, e as variáveis de contexto do aplicativo devem ser colocadas em porcentagens únicas, por exemplo %contextdata.email%.

1. Em **[!UICONTROL Content Type]**, digite **application/json**.

1. Em **[!UICONTROL Timeout]**, selecione 0.

   ![](assets/do-not-localize/rules_2.png)

Os dados do usuário estão configurados para serem enviados ao Campaign.

### Postback de rastreamento no aplicativo {#inapp-tracking-postback}

Para enviar dados de rastreamento para [!DNL Adobe Campaign Standard] para gerar relatórios sobre como seus usuários interagem com mensagens no aplicativo em seu aplicativo móvel, crie a seguinte regra em [!DNL Experience Platform Launch]:

1. Em [!DNL Experience Platform Launch], no painel do aplicativo móvel, selecione a guia **[!UICONTROL Rules]** e clique em **[!UICONTROL Add Rule]**.

1. Digite um nome, por exemplo, **Adobe Campaign - Rastreamento de cliques no aplicativo**.

1. Na seção **[!UICONTROL Events]**, clique em **[!UICONTROL Add]**.

1. No menu suspenso **[!UICONTROL Extension]**, selecione **[!UICONTROL Adobe Campaign Standard]**. Em seguida, **[!UICONTROL In-App click tracking]** no menu suspenso **[!UICONTROL Event type]**.

1. Clique em **[!UICONTROL Keep changes]**.

1. Na seção **[!UICONTROL Actions]**, clique em **[!UICONTROL Add]**.

1. No menu suspenso **[!UICONTROL Extension]**, selecione **[!UICONTROL Mobile Core]**. Em seguida, **[!UICONTROL Send postback]** no menu suspenso **[!UICONTROL Event type]**.

1. Em **[!UICONTROL URL]**, digite o seguinte URL:

   ```
   https://{%%camp-server%%}/r/?id={%id%}&mcid={%%mcid%%}
   ```

1. Marque a caixa de seleção **[!UICONTROL Add post body]** .

1. Em **[!UICONTROL Post Body]**, digite **{}**.

1. Em **[!UICONTROL Content Type]**, digite **application/json**.

1. Em **[!UICONTROL Timeout]**, selecione 0.

   ![](assets/do-not-localize/rules_3.png)

### Notificações por push rastreando postback {#push-tracking-postback}

Para enviar dados de rastreamento para [!DNL Adobe Campaign Standard], que ajuda a rastrear os deliveries da notificação por push e a interação dos usuários com seu aplicativo móvel, é necessário criar uma regra em [!DNL Experience Platform Launch].

Para obter mais informações sobre o rastreamento de push, consulte [Rastreamento de push](../../administration/using/push-tracking.md).

Para rastrear ações do aplicativo, use a API trackAction . Para obter mais informações, consulte [Rastrear ações do aplicativo](https://app.gitbook.com/@aep-sdks/s/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions).

1. Em [!DNL Experience Platform Launch], no painel do aplicativo móvel, clique na guia **[!UICONTROL Rules]** e em **[!UICONTROL Add Rule]**.

1. Digite um nome, por exemplo, **Adobe Campaign - rastreamento de cliques por push**.

1. Na seção **[!UICONTROL Events]**, clique em **[!UICONTROL Add]**.

1. No menu suspenso **[!UICONTROL Extension]**, selecione **[!UICONTROL Mobile Core]**. Em seguida, **[!UICONTROL Track Action]** no menu suspenso **[!UICONTROL Event type]**.

1. Na lista suspensa **[!UICONTROL Action]**, selecione **[!UICONTROL Action]**, selecione **[!UICONTROL equals]** e digite **tracking**.

1. Clique em **[!UICONTROL Keep changes]**. Em seguida, na seção **[!UICONTROL Actions]**, clique em **[!UICONTROL Add]**.

1. No menu suspenso **[!UICONTROL Extension]**, selecione **[!UICONTROL Mobile Core]**. Em seguida, **[!UICONTROL Send postback]** no menu suspenso **[!UICONTROL Action type]**.

1. Em **[!UICONTROL URL]**, insira o seguinte URL:

   ```
   https://{%%camp-server%%}/r/?id={%contextdata.broadlogId%},{%contextdata.deliveryId%},{%contextdata.action%}&mcId={%%mcid%%}
   ```

1. Marque a caixa de seleção **[!UICONTROL Add post body]** .

1. Adicione o corpo da publicação, por exemplo, { }.

1. Em **[!UICONTROL Content Type]**, digite **application/json**.

1. Em **[!UICONTROL Timeout]**, selecione 0.

### Postback de localização {#location-postback}

1. Em [!DNL Experience Platform Launch], no painel do aplicativo móvel, clique na guia **[!UICONTROL Rules]** e em **[!UICONTROL Add Rule]**.

1. Digite um nome, por exemplo, **Location postback**.

1. Na seção **[!UICONTROL Events]**, clique em **[!UICONTROL Add]**.

1. Crie um evento, por exemplo, Inserir POI ou Sair do POI. Na lista suspensa **[!UICONTROL Extension]**, selecione **Places - Beta**. Em seguida, **Insira POI** ou **Saída do POI** no menu suspenso **[!UICONTROL Event type]**.

1. Insira um nome, por exemplo, **Places - Beta - Digite POI** ou **Sair do POI**.

1. Na seção **[!UICONTROL Actions]**, clique em **[!UICONTROL Add]**.

1. No menu suspenso **[!UICONTROL Extension]**, selecione **[!UICONTROL Mobile Core]**. Em seguida, **[!UICONTROL Send postback]** no menu suspenso **[!UICONTROL Action type]**.

1. Insira um nome, por exemplo, **Mobile Core - Send Location Postback**.

1. Em **[!UICONTROL URL]**, insira o seguinte URL:

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/locations/
   ```

1. Marque a caixa de seleção **[!UICONTROL Add post body]** e adicione o corpo da postagem, por exemplo:

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
   >No exemplo acima, os elementos de dados no lado direito precisam ser configurados em [!DNL Experience Platform Launch] aproveitando as etapas em [Criação de elementos de dados](../../administration/using/configuring-rules-launch.md#create-data-elements). Os elementos de dados no lado esquerdo são suportados em [!DNL Adobe Campaign Standard] e não precisam de configuração. Se você precisar de dados adicionais, precisará realizar extensões de recursos personalizados em [!DNL Adobe Campaign Standard].

1. Em **[!UICONTROL Content Type]**, digite **application/json**.

1. Em **[!UICONTROL Timeout]**, selecione 5.

   ![](assets/do-not-localize/rules_4.png)
