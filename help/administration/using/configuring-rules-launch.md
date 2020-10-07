---
title: Configuração de regras do Adobe Experience Platform Launch para suportar casos de uso do Adobe Campaign Standard
description: Configuração de regras do Adobe Experience Platform Launch para suportar casos de uso do Adobe Campaign Standard
page-status-flag: never-activated
uuid: 961aaeb5-6948-4fd2-b8d7-de4510c10566
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: push-notifications
discoiquuid: 23b4212e-e878-4922-be20-50fb7fa88ae8
context-tags: mobileApp,overview
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '914'
ht-degree: 1%

---


# Configuração das regras do Launch para suportar casos de uso do Adobe Campaign Standard {#configuring-rules-launch}

Em [!DNL Adobe Experience Platform Launch], é necessário criar elementos de dados e regras para enviar PII e outros dados de aplicativos móveis para [!DNL Adobe Campaign Standard].

Para garantir que todas as alterações de configuração [!DNL Adobe Experience Platform Launch] entrem em vigor, é necessário publicar essas alterações. Para obter mais informações, consulte [Publicação](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#publish-the-configuration).

Para criar regras em [!DNL Experience Platform Launch], siga estas etapas:

1. [Criação de elementos de dados](../../administration/using/configuring-rules-launch.md#create-data-elements)
2. [Criando regras](../../administration/using/configuring-rules-launch.md#create-data-elements) para casos de uso que você deseja suportar:
   * [PII postback](../../administration/using/configuring-rules-launch.md#pii-postback)
   * [Postback de rastreamento no aplicativo](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
   * [Postback de rastreamento de notificações por push](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
   * [Postback de localização](../../administration/using/configuring-rules-launch.md#location-postback)

## Criação de elementos de dados {#create-data-elements}

Estes são os elementos de dados que recomendamos criar no [!DNL Experience Platform Launch].
Você pode criar elementos de dados adicionais de acordo com suas necessidades.

* **[!UICONTROL Experience Cloud ID]**
* **[!UICONTROL Pkey]**
* **[!UICONTROL Campaign server]**

Para criar esses elementos de dados:

1. Em [!DNL Experience Platform Launch], no painel do aplicativo móvel, clique na **[!UICONTROL Data Elements]** guia.

1. Para criar o elemento de **[!UICONTROL Experience Cloud ID]** dados, clique em **[!UICONTROL Create New Data Element]**.

1. No **[!UICONTROL Name]** campo, por exemplo, digite **mcid**.

1. From the **[!UICONTROL Extension]** drop-down, select **[!UICONTROL Mobile Core]**. Em seguida, **[!UICONTROL Experience Cloud ID]** na lista suspensa **[!UICONTROL Data element]** de tipos.

   ![](assets/do-not-localize/rules_1.png)

1. Para criar o elemento de dados da chave, clique em **[!UICONTROL Add data element]**.

1. No **[!UICONTROL Name]** campo, por exemplo, digite **pkey**.

1. From the **[!UICONTROL Extension]** drop-down, select **[!UICONTROL Adobe Campaign Standard]**. Em seguida, **[!UICONTROL pkey]** na lista suspensa **[!UICONTROL Data element]** de tipos.

1. Para criar o elemento de dados do servidor de Campanha, clique em **[!UICONTROL Add data element]**.

1. No **[!UICONTROL Name]** campo, digite um nome, por exemplo, **camp-server**.

1. From the **[!UICONTROL Extension]** drop-down, select **[!UICONTROL Adobe Campaign Standard]**. Em seguida, **[!UICONTROL Campaign Server]** na lista suspensa **[!UICONTROL Data element]** de tipos.

## Criação de regras {#creating-rules}

É necessário criar regras para o seguinte:

* [PII postback](../../administration/using/configuring-rules-launch.md#pii-postback)
* [Postback de rastreamento no aplicativo](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
* [Postback de rastreamento de notificações por push](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
* [Postback de localização](../../administration/using/configuring-rules-launch.md#location-postback)

### PII postback {#pii-postback}

>[!NOTE]
>
>Para enviar informações de PII de um aplicativo móvel para a Adobe Campaign, é necessário implementar uma API do SDK. Para obter mais informações, acesse [CollectPII](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#collect-pii).

Para enviar dados de PII para [!DNL Adobe Campaign Standard], crie uma regra em [!DNL Experience Platform Launch]:

1. Em [!DNL Experience Platform Launch], no painel do aplicativo móvel, clique na **[!UICONTROL Rules]** guia e depois **[!UICONTROL Create New Rule]**.

1. Digite um nome, por exemplo, **Mobile Core - Collect PII**.

1. In the **[!UICONTROL Events]** section, click **[!UICONTROL Add]**.

1. From the **[!UICONTROL Extension]** drop-down, select **[!UICONTROL Mobile Core]**. Then, **[!UICONTROL Collect PII]** in the **[!UICONTROL Event type]** drop-down.

1. Clique em **[!UICONTROL Keep changes]**.

1. In the **[!UICONTROL Actions]** section, click **[!UICONTROL Add]**.

1. From the **[!UICONTROL Extension]** drop-down, select **[!UICONTROL Mobile Core]**. Then, **[!UICONTROL Send PII]** in the **[!UICONTROL Action type]** drop-down.

1. Em **[!UICONTROL URL]**, insira o seguinte URL:

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/subscriptions/{%%mcid%%}
   ```

1. Marque a caixa de **[!UICONTROL Add Post Body]** seleção.

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

   A marketingCloudId permite que você reconcilie os assinantes do aplicativo com os recipient no banco de dados e, como resultado, é obrigatório. Você pode especificar outros pares de valor chave de acordo com as necessidades de sua empresa. No exemplo acima, Email, Nome e Sobrenome estão sendo transmitidos do aplicativo.

   As chaves (por exemplo, cusEmail, cusFirstName e cusLastName) devem corresponder às IDs de campo definidas no recurso personalizado na instância do Adobe Campaign Standard. As variáveis de valor (por exemplo, email, firstName e LastName) devem corresponder às chaves nos dados JSON enviados do aplicativo móvel ao chamar a API collectPII do AMS a partir do código do aplicativo.

   Você também pode passar os dados do ciclo de vida no postback Coletar PII ou em um postback diferente dependendo dos acionadores do Evento. este é um exemplo do JSON Lifecycle Data:

   ```
   {
   "marketingCloudId":"{%%mcid%%}",
   "cusDayslastlaunch": "{%%DaysSinceLastUse%%}", 
   "cusDaysfirstlaunch": "{%%DaysSinceFirstUse%%}", 
   "cusLaunches": "{%%Launches%%}"
   }
   ```

   Os elementos de dados definidos no aplicativo [!DNL Experience Platform Launch] devem estar entre porcentagens de duplo, por exemplo %%mcid%%, e as variáveis de contexto do aplicativo devem estar entre porcentagens únicas, por exemplo %contextdata.email%.

1. Em **[!UICONTROL Content Type]**, digite **application/json**.

1. In **[!UICONTROL Timeout]**, select 0.

   ![](assets/do-not-localize/rules_2.png)

Seus dados de usuário agora estão configurados para serem enviados para a Campanha.

### Postback de rastreamento no aplicativo {#inapp-tracking-postback}

Para enviar dados de rastreamento para [!DNL Adobe Campaign Standard] relatórios sobre como seus usuários interagem com mensagens no aplicativo em seu aplicativo móvel, crie a seguinte regra em [!DNL Experience Platform Launch]:

1. Em [!DNL Experience Platform Launch], no painel do aplicativo móvel, selecione a **[!UICONTROL Rules]** guia e clique em **[!UICONTROL Add Rule]**.

1. Digite um nome, por exemplo, **Adobe Campaign - No aplicativo, clique no rastreamento**.

1. In the **[!UICONTROL Events]** section, click **[!UICONTROL Add]**.

1. From the **[!UICONTROL Extension]** drop-down, select **[!UICONTROL Adobe Campaign Standard]**. Then, **[!UICONTROL In-App click tracking]** in the **[!UICONTROL Event type]** drop-down.

1. Clique em **[!UICONTROL Keep changes]**.

1. In the **[!UICONTROL Actions]** section, click **[!UICONTROL Add]**.

1. From the **[!UICONTROL Extension]** drop-down, select **[!UICONTROL Mobile Core]**. Then, **[!UICONTROL Send postback]** in the **[!UICONTROL Event type]** drop-down.

1. Em **[!UICONTROL URL]**, digite o seguinte URL:

   ```
   https://{%%camp-server%%}/r/?id={%id%}&mcid={%%mcid%%}
   ```

1. Marque a caixa de **[!UICONTROL Add post body]** seleção.

1. Em **[!UICONTROL Post Body]**, digite **{}**.

1. Em **[!UICONTROL Content Type]**, digite **application/json**.

1. In **[!UICONTROL Timeout]**, select 0.

   ![](assets/do-not-localize/rules_3.png)

### Postback de rastreamento de notificações por push {#push-tracking-postback}

Para enviar dados de rastreamento para [!DNL Adobe Campaign Standard], que ajudam a rastrear seus delivery de notificação por push e a interação dos usuários com seu aplicativo móvel, é necessário criar uma regra no [!DNL Experience Platform Launch].

Para obter mais informações sobre o rastreamento de push, consulte [Rastreamento](../../administration/using/push-tracking.md)de push.

Para rastrear ações do aplicativo, use a API trackAction. Para obter mais informações, consulte [Rastrear ações](https://app.gitbook.com/@aep-sdks/s/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions)do aplicativo.

1. Em [!DNL Experience Platform Launch], no painel do aplicativo móvel, clique na **[!UICONTROL Rules]** guia e clique em **[!UICONTROL Add Rule]**.

1. Digite um nome, por exemplo, **Adobe Campaign - rastreamento** de cliques por push.

1. In the **[!UICONTROL Events]** section, click **[!UICONTROL Add]**.

1. From the **[!UICONTROL Extension]** drop-down, select **[!UICONTROL Mobile Core]**. Then, **[!UICONTROL Track Action]** in the **[!UICONTROL Event type]** drop-down.

1. Na **[!UICONTROL Action]** lista suspensa, selecione **[!UICONTROL Action]**, selecione **[!UICONTROL equals]** e digite **rastreamento**.

1. Clique em **[!UICONTROL Keep changes]**. Then, in the **[!UICONTROL Actions]** section, click **[!UICONTROL Add]**.

1. From the **[!UICONTROL Extension]** drop-down, select **[!UICONTROL Mobile Core]**. Then, **[!UICONTROL Send postback]** in the **[!UICONTROL Action type]** drop-down.

1. Em **[!UICONTROL URL]**, insira o seguinte URL:

   ```
   https://{%%camp-server%%}/r/?id={%contextdata.broadlogId%},{%contextdata.deliveryId%},{%contextdata.action%}&mcId={%%mcid%%}
   ```

1. Marque a caixa de **[!UICONTROL Add post body]** seleção.

1. Adicione seu corpo da publicação, por exemplo, { }.

1. Em **[!UICONTROL Content Type]**, digite **application/json**.

1. In **[!UICONTROL Timeout]**, select 0.

### Postback de localização {#location-postback}

1. Em [!DNL Experience Platform Launch], no painel do aplicativo móvel, clique na **[!UICONTROL Rules]** guia e clique em **[!UICONTROL Add Rule]**.

1. Digite um nome, por exemplo, **Local postback**.

1. In the **[!UICONTROL Events]** section, click **[!UICONTROL Add]**.

1. Crie um evento, por exemplo, Enter POI ou Exit POI. Na **[!UICONTROL Extension]** lista suspensa, selecione **Locais - Beta**. Em seguida, **digite POI** ou **saia do POI** no **[!UICONTROL Event type]** menu suspenso.

1. Insira um nome, por exemplo, **Locais - Beta - Insira o POI** ou **Saia do POI**.

1. In the **[!UICONTROL Actions]** section, click **[!UICONTROL Add]**.

1. From the **[!UICONTROL Extension]** drop-down, select **[!UICONTROL Mobile Core]**. Então, **[!UICONTROL Send postback]** do **[!UICONTROL Action type]** menu suspenso.

1. Digite um nome, por exemplo, **Móvel Core - Enviar postback** de localização.

1. Em **[!UICONTROL URL]**, insira o seguinte URL:

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/locations/
   ```

1. Marque a caixa de **[!UICONTROL Add post body]** seleção e adicione o corpo da publicação, por exemplo:

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
   >No exemplo acima, os elementos de dados no lado direito precisam ser configurados [!DNL Experience Platform Launch] aproveitando as etapas em [Criar elementos](../../administration/using/configuring-rules-launch.md#create-data-elements)de dados. Os elementos de dados no lado esquerdo são suportados em [!DNL Adobe Campaign Standard] e não precisam de nenhuma configuração. Se você precisar de dados adicionais, será necessário realizar extensões de recursos personalizados em [!DNL Adobe Campaign Standard].

1. Em **[!UICONTROL Content Type]**, digite **application/json**.

1. In **[!UICONTROL Timeout]**, select 5.

   ![](assets/do-not-localize/rules_4.png)
