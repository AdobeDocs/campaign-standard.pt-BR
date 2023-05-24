---
title: Casos de uso de publicação de conteúdo para dispositivos móveis compatíveis com o Adobe Campaign Standard usando os SDKs da Adobe Experience Platform
description: Saiba como dar suporte a casos de uso de dispositivos móveis
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 3cd8d756-a271-4e53-8ed0-984ce20298bc
source-git-commit: 597ece8d833a216f0540f801461b08fdc9865024
workflow-type: tm+mt
source-wordcount: '947'
ht-degree: 1%

---

# Casos de uso para dispositivos móveis compatíveis com o Adobe Campaign Standard {#mobile-use-cases}

Nesta página, você encontrará a lista de todos os casos de uso de dispositivos móveis compatíveis com o [!DNL Adobe Campaign Standard] usando o [!DNL Adobe Experience Platform SDKs]. Observe que o suporte a esses casos de uso envolve a instalação e configuração do [!DNL Adobe Experience Platform SDKs], [!DNL tags in Adobe Experience Platform], e [!DNL Adobe Campaign Standard]. Para obter mais informações sobre essas operações, consulte esta [página](../../administration/using/configuring-a-mobile-application.md).

O Adobe Campaign Standard é compatível com os seguintes casos de uso:

* [Registrar um perfil móvel no Campaign Standard](../../administration/using/supported-mobile-use-cases.md#register-mobile-profile)
* [Enviar um token de push para o Campaign Standard](../../administration/using/supported-mobile-use-cases.md#send-push-token)
* [Enriqueça um perfil móvel com dados personalizados do seu aplicativo](../../administration/using/supported-mobile-use-cases.md#enrich-mobile-profile-custom)
* [Enriqueça um perfil móvel com dados do ciclo de vida do seu aplicativo](../../administration/using/supported-mobile-use-cases.md#enrich-mobile-profile-lifecycle)
* [Rastrear a interação do usuário com notificações por push](../../administration/using/supported-mobile-use-cases.md#track-user-push)
* [Implementar um evento personalizado no aplicativo móvel para acionar mensagens no aplicativo](../../administration/using/supported-mobile-use-cases.md#custom-event-inapp)
* [Definir campos de vinculação para autenticação adicional para o modelo de perfil baseado em mensagens no aplicativo](../../administration/using/supported-mobile-use-cases.md#linkage-fields-inapp)

Para configurar esses casos de uso, você precisa das seguintes extensões:

* **[!DNL Adobe Campaign Standard]** <br>Para instalar e configurar a extensão Campaign Standard, consulte [Configurar a extensão Campaign Standard na interface da coleção de dados](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/#configure-the-campaign-standard-extension).
* **[!DNL Mobile Core]**, que é instalado automaticamente. <br>Para obter mais informações sobre a extensão Mobile Core, consulte [Núcleo móvel](https://developer.adobe.com/client-sdks/documentation/mobile-core/).
* **[!DNL Profile]**, que é instalado automaticamente. <br>Para obter mais informações sobre a extensão Profile, consulte [Perfil](https://developer.adobe.com/client-sdks/documentation/profile/).

## Registrar um perfil móvel no Campaign Standard {#register-mobile-profile}

### Com o iOS {#register-mobile-profile-ios}

No iOS, as seguintes [!DNL Experience Platform APIs] são obrigatórios:

* **[!UICONTROL Lifecycle Start]**, quando o aplicativo for iniciado e quando estiver em primeiro plano.
* **[!UICONTROL Lifecycle Pause]**, quando o aplicativo estiver em segundo plano.

Para obter mais informações, consulte [Extensão de ciclo de vida no iOS](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/ios/).

Este é um exemplo de implementação deste caso de uso com o iOS:

```
 func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
  
  
 ACPCore.setLogLevel(.debug)
 appId = SettingsBundle.getLaunchAppId()
   
 //===== START Set up Adobe SDK =====
 ACPCore.configure(withAppId: appId)
   
 ACPCampaign.registerExtension()
 ACPIdentity.registerExtension()
 ACPLifecycle.registerExtension()
 ACPUserProfile.registerExtension()
 ACPSignal.registerExtension()
 ACPCore.start()
 ACPCore.lifecycleStart(nil)
   
 return true
 }
  
func applicationDidEnterBackground(_ application: UIApplication) {
 ACPCore.lifecyclePause()
 }
   
 func applicationDidBecomeActive(_ application: UIApplication) {
 // Workaround until jira AMSDK-7411 is fixed.
 sleep(2)
 ACPCore.lifecycleStart(nil)
 }
```

### Com Android {#register-mobile-profile-android}

No Android, as seguintes [!DNL Experience Platform APIs] são obrigatórios:

* **[!UICONTROL OnResume]**
* **[!UICONTROL OnPause]**

Para obter mais informações, consulte [Extensão de ciclo de vida no Android](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/android/).

Esta é uma amostra de implementação para este caso de uso com o Android:

```
@Override
  
public void onResume() {
 super.onResume();
 MobileCore.setApplication(getApplication());
 MobileCore.lifecycleStart(null);
 handleOpenTracking();
 }
  
 @Override
 public void onPause() {
 super.onPause();
 MobileCore.lifecyclePause();
 }
```

## Enviar um token de push para o Adobe Campaign Standard {#send-push-token}

### Com o iOS {#send-push-token-ios}

No iOS, as seguintes [!DNL Experience Platform SDK] é obrigatório:

* **[!UICONTROL setPushIdentifier]** <br>Para obter mais informações, consulte [setPushIdentifier](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/).

Este é o exemplo de implementação para este caso de uso com o iOS:

```
func application(_ application: UIApplication, didRegisterForRemoteNotificationsWithDeviceToken deviceToken: Data) {
  
 // Register Device Token
 ACPCore.setPushIdentifier(deviceToken)
```

### Com Android {#send-push-token-android}

No Android, as seguintes [!DNL Experience Platform SDK] é obrigatório:

* **[!UICONTROL setPushIdentifier]** <br>Para obter mais informações, consulte [setPushIdentifier](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/).

Este é o exemplo de implementação para este caso de uso com o Android:

```
@Override
public void onNewToken(String token) {
    Log.d(TAG, "Refreshed token: " + token);
    MobileCore.setPushIdentifier(token);
}
```

## Enriqueça um perfil móvel com dados personalizados do seu aplicativo {#enrich-mobile-profile-custom}

Para que esse caso de uso funcione, é necessário criar regras para postbacks de PII. Para obter mais informações, consulte [Postbacks de PII](../../administration/using/configuring-rules-launch.md#pii-postback).

### Com o iOS {#enrich-mobile-profile-custom-ios}

No iOS, as seguintes [!DNL Experience Platform API] é obrigatório:

* collectPII <br> Para obter mais informações, consulte collectPII.

Este é um exemplo de implementação deste caso de uso com o iOS:

```
ACPCore.collectPii(["pushPlatform":"apns", "email":email, "firstName":firstName, "lastName":lastName])
```

### Com Android {#enrich-mobile-profile-custom-android}

No Android, as seguintes [!DNL Experience Platform API] é obrigatório:

* collectPII <br> Para obter mais informações, consulte collectPII.

Esta é uma amostra de implementação para este caso de uso com o Android:

```
HashMap<String, String> data = new HashMap<>();
data.put("pushPlatform", "gcm");
data.put("firstName", firstNameText); 
data.put("lastName", lastNameText); 
data.put("email", emailText); 
MobileCore.collectPii(data);
```

## Enriqueça um perfil móvel com dados do ciclo de vida do seu aplicativo {#enrich-mobile-profile-lifecycle}

Para que esse caso de uso funcione, é necessário criar regras para postbacks de PII. Para obter mais informações, consulte [Postbacks de PII](../../administration/using/configuring-rules-launch.md#pii-postback).

>[!NOTE]
>
>A Adobe Campaign não distingue dados personalizados ou dados de ciclo de vida do aplicativo móvel. Ambos os tipos de dados podem ser enviados para o servidor usando uma regra de postback collectPii em resposta a um evento no aplicativo móvel.

### Com o iOS {#enrich-mobile-profile-lifecycle-ios}

No iOS, as seguintes [!DNL Experience Platform APIs] são obrigatórios:

* **[!UICONTROL Lifecycle Start]**, quando o aplicativo for iniciado e quando estiver em primeiro plano.
* **[!UICONTROL Lifecycle Pause]**, quando o aplicativo estiver em segundo plano.

Para obter mais informações, consulte [Extensão de ciclo de vida no iOS](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/ios/).

Este é um exemplo de implementação deste caso de uso com o iOS:

```
func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
  
  
 ACPCore.setLogLevel(.debug)
 appId = SettingsBundle.getLaunchAppId()
   
 //===== START Set up Adobe SDK =====
 ACPCore.configure(withAppId: appId)
   
 ACPCampaign.registerExtension()
 ACPIdentity.registerExtension()
 ACPLifecycle.registerExtension()
 ACPUserProfile.registerExtension()
 ACPSignal.registerExtension()
 ACPCore.start()
 ACPCore.lifecycleStart(nil)
   
 return true
 }
  
func applicationDidEnterBackground(_ application: UIApplication) {
 ACPCore.lifecyclePause()
 }
   
 func applicationDidBecomeActive(_ application: UIApplication) {
 // Workaround until jira AMSDK-7411 is fixed.
 sleep(2)
 ACPCore.lifecycleStart(nil)
 }
```

### Com Android {#enrich-mobile-profile-lifecycle-android}

No Android, as seguintes [!DNL Experience Platform APIs] são obrigatórios:

* **[!UICONTROL OnResume]**
* **[!UICONTROL OnPause]**

Para obter mais informações, consulte [Extensão de ciclo de vida no Android](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/android/).

Esta é uma amostra de implementação para este caso de uso com o Android:

```
@Override
  
public void onResume() {
 super.onResume();
 MobileCore.setApplication(getApplication());
 MobileCore.lifecycleStart(null);
 handleOpenTracking();
 }
  
 @Override
 public void onPause() {
 super.onPause();
 MobileCore.lifecyclePause();
 }
```

## Rastrear a interação do usuário com notificações por push {#track-user-push}

Você precisa criar regras para o postback de rastreamento de notificações por push. Para obter mais informações, consulte [Postback de rastreamento de notificações por push](../../administration/using/configuring-rules-launch.md#push-tracking-postback).

### Com o iOS {#track-user-push-ios}

No iOS, as seguintes [!DNL Experience Platform SDK] é obrigatório:

* **[!UICONTROL trackAction]**. Para obter mais informações, consulte [Rastrear ações do aplicativo](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#trackaction).

Este é um exemplo de implementação deste caso de uso com o iOS:

```
let deliveryId = userInfo["_dId"] as? String
let broadlogId = userInfo["_mId"] as? String
if (deliveryId != nil && broadlogId != nil) {
    ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
}
```

### Com Android {#track-user-push-android}

No Android, as seguintes [!DNL Experience Platform SDK] é obrigatório:

* **[!UICONTROL trackAction]**
Para obter mais informações, consulte [Rastrear ações do aplicativo](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#trackaction).

Esta é uma amostra de implementação para este caso de uso com o Android:

```
contextData.put("deliveryId", deliveryId);
contextData.put("broadlogId", messageId);
contextData.put("action", "2");
MobileCore.trackAction("tracking", contextData);
```

## Implementar um evento personalizado no aplicativo para acionar mensagens no aplicativo {#custom-event-inapp}

### Com o iOS {#custom-event-inapp-ios}

No iOS, as seguintes [!DNL Experience Platform SDK] é obrigatório:

* **[!UICONTROL trackAction]**. Para obter mais informações, consulte [Rastrear ações do aplicativo](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#trackaction).

Este é um exemplo de implementação deste caso de uso com o iOS:

```
ACPCore.trackAction(mobileEventName, data: [:] )
```

### Com Android {#custom-event-inapp-android}

No Android, as seguintes [!DNL Experience Platform SDK] é obrigatório:

* **[!UICONTROL trackAction]**
Para obter mais informações, consulte [Rastrear ações do aplicativo](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#trackaction).

Esta é uma amostra de implementação para este caso de uso com o Android:

```
MobileCore.trackAction(mobileEventText, new HashMap<String,String>());
```

## Definir campos de vinculação para autenticação adicional {#linkage-fields-inapp}

### Com o iOS {#linkage-fields-inapp-ios}

Para definir campos de vinculação para autenticação adicional para o modelo de perfil baseado em mensagens no aplicativo no iOS, faça o seguinte [!DNL Experience Platform SDK] é obrigatório:

* Definir campos de vinculação <br>Para obter mais informações, consulte [Definir campos de vinculação](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/#setlinkagefields).
* Redefinir campos de vínculo <br>Para obter mais informações, consulte [Redefinir campos de vínculo](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/#setlinkagefields).

Estas são algumas implementações de exemplo deste caso de uso com o iOS.

Para definir campos de vinculação:

```
var linkageFields = [String: String]()
linkageFields["cusEmail"] = "john.doe@email.com"
ACPCampaign.setLinkageFields(linkageFields)
```

Para redefinir campos de vínculo:

```
ACPCampaign.resetLinkageFields(linkageFields)
```

### Com Android {#linkage-fields-inapp-android}

Para definir campos de vinculação para autenticação adicional para o modelo de perfil baseado em mensagens no aplicativo no Android, é necessário o seguinte SDK do Experience Platform:

* Definir campos de vinculação <br>Para obter mais informações, consulte [Definir campos de vinculação](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/#setlinkagefields).
* Redefinir campos de vínculo <br>Para obter mais informações, consulte [Redefinir campos de vínculo](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/#resetlinkagefields).

Estas são algumas implementações de exemplo deste caso de uso com o Android.

Para definir campos de vinculação:

```
HashMap<String, String> linkageFields = new HashMap<String, String>();
linkageFields.put("cusEmail", "john.doe@email.com");
Campaign.setLinkageFields(linkageFields);
```

Para redefinir campos de vínculo:

```
Campaign.resetLinkageFields()
```
