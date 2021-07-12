---
solution: Campaign Standard
product: campaign
title: Casos de uso de publicação de conteúdo para dispositivos móveis compatíveis com o Adobe Campaign Standard por meio dos SDKs do Adobe Experience Platform
description: Este documento fornece informações sobre como suportar casos de uso de dispositivos móveis.
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Configurações de instância
role: Admin
level: Experienced
exl-id: 3cd8d756-a271-4e53-8ed0-984ce20298bc
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '955'
ht-degree: 1%

---

# Casos de uso para dispositivos móveis compatíveis com o Adobe Campaign Standard {#mobile-use-cases}

Nesta página, você encontrará a lista de todos os casos de uso de dispositivos móveis suportados em [!DNL Adobe Campaign Standard] usando o [!DNL Adobe Experience Platform SDKs]. Observe que o suporte a esses casos de uso envolve instalar e configurar os [!DNL Adobe Experience Platform SDKs], [!DNL Adobe Experience Platform Launch] e [!DNL Adobe Campaign Standard]. Para obter mais informações sobre essas operações, consulte esta [página](../../administration/using/configuring-a-mobile-application.md).

O Adobe Campaign Standard oferece suporte para os seguintes casos de uso:

* [Registrar um perfil móvel no Campaign Standard](../../administration/using/supported-mobile-use-cases.md#register-mobile-profile)
* [Enviar um token de push para o Campaign Standard](../../administration/using/supported-mobile-use-cases.md#send-push-token)
* [Enriqueça um perfil móvel com dados personalizados do seu aplicativo](../../administration/using/supported-mobile-use-cases.md#enrich-mobile-profile-custom)
* [Enriqueça um perfil móvel com dados do ciclo de vida de seu aplicativo](../../administration/using/supported-mobile-use-cases.md#enrich-mobile-profile-lifecycle)
* [Rastrear a interação do usuário com notificações por push](../../administration/using/supported-mobile-use-cases.md#track-user-push)
* [Implementar um evento personalizado no aplicativo móvel para acionar mensagens no aplicativo](../../administration/using/supported-mobile-use-cases.md#custom-event-inapp)
* [Definir campos de vinculação para autenticação adicional para o modelo de perfil que é baseado em mensagens no aplicativo](../../administration/using/supported-mobile-use-cases.md#linkage-fields-inapp)

Para configurar esses casos de uso, você precisa das seguintes extensões de [!DNL Experience Platform Launch]:

* **[!DNL Adobe Campaign Standard]** <br>Para instalar e configurar a extensão do Campaign Standard, consulte  [Configurar a extensão do Campaign Standard no Experience Platform Launch](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#configure-the-campaign-standard-extension-in-experience-platform-launch).
* **[!DNL Mobile Core]**, que é instalado automaticamente. <br>Para obter mais informações sobre a extensão Mobile Core, consulte  [Mobile Core](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core).
* **[!DNL Profile]**, que é instalado automaticamente. <br>Para obter mais informações sobre a extensão Profile, consulte  [Perfil](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/profile).

## Registrar um perfil móvel no Campaign Standard {#register-mobile-profile}

### Com iOS {#register-mobile-profile-ios}

No iOS, os seguintes [!DNL Experience Platform APIs] são necessários:

* **[!UICONTROL Lifecycle Start]**, quando o aplicativo é iniciado e quando ele está em primeiro plano.
* **[!UICONTROL Lifecycle Pause]**, quando o aplicativo estiver em segundo plano.

Para obter mais informações, consulte [Extensão do ciclo de vida no iOS](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-ios).

Esta é uma amostra da implementação deste caso de uso com o iOS:

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

No Android, os seguintes [!DNL Experience Platform APIs] são necessários:

* **[!UICONTROL OnResume]**
* **[!UICONTROL OnPause]**

Para obter mais informações, consulte [Extensão do ciclo de vida no Android](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-android).

Esta é uma amostra de implementação para este caso de uso com Android:

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

### Com iOS {#send-push-token-ios}

No iOS, o seguinte [!DNL Experience Platform SDK] é necessário:

* **[!UICONTROL setPushIdentifier]** <br>Para obter mais informações, consulte  [setPushIdentifier](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#setpushidentifier).

Esta é a amostra de implementação para este caso de uso com iOS:

```
func application(_ application: UIApplication, didRegisterForRemoteNotificationsWithDeviceToken deviceToken: Data) {
  
 // Register Device Token
 ACPCore.setPushIdentifier(deviceToken)
```

### Com Android {#send-push-token-android}

No Android, o seguinte [!DNL Experience Platform SDK] é necessário:

* **[!UICONTROL setPushIdentifier]** <br>Para obter mais informações, consulte  [setPushIdentifier](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#setpushidentifier).

Esta é a amostra de implementação para este caso de uso com Android:

```
@Override
public void onNewToken(String token) {
    Log.d(TAG, "Refreshed token: " + token);
    MobileCore.setPushIdentifier(token);
}
```

## Enriqueça um perfil móvel com dados personalizados do seu aplicativo {#enrich-mobile-profile-custom}

Para que esse caso de uso funcione, é necessário criar regras para postbacks de PII. Para obter mais informações, consulte [PII Postbacks](../../administration/using/configuring-rules-launch.md#pii-postback).

### Com iOS {#enrich-mobile-profile-custom-ios}

No iOS, o seguinte [!DNL Experience Platform API] é necessário:

* collectPII <br> Para obter mais informações, consulte collectPII.

Esta é uma amostra da implementação deste caso de uso com o iOS:

```
ACPCore.collectPii(["email":email, "firstName":firstName, "lastName":lastName])
```

### Com Android {#enrich-mobile-profile-custom-android}

No Android, o seguinte [!DNL Experience Platform API] é necessário:

* collectPII <br> Para obter mais informações, consulte collectPII.

Esta é uma amostra de implementação para este caso de uso com Android:

```
HashMap<String, String> data = new HashMap<>();
data.put("firstName", firstNameText);
data.put("lastName", lastNameText);
data.put("email", emailText);
MobileCore.collectPii(data);
```

## Enriqueça um perfil móvel com dados do ciclo de vida de seu aplicativo {#enrich-mobile-profile-lifecycle}

Para que esse caso de uso funcione, é necessário criar regras para postbacks de PII. Para obter mais informações, consulte [PII Postbacks](../../administration/using/configuring-rules-launch.md#pii-postback).

>[!NOTE]
>
>O Adobe Campaign não faz distinção entre dados personalizados ou dados de ciclo de vida do aplicativo móvel. Ambos os tipos de dados podem ser enviados para o servidor usando uma regra de postback collectPii em resposta a um evento no aplicativo móvel.

### Com iOS {#enrich-mobile-profile-lifecycle-ios}

No iOS, os seguintes [!DNL Experience Platform APIs] são necessários:

* **[!UICONTROL Lifecycle Start]**, quando o aplicativo é iniciado e quando ele está em primeiro plano.
* **[!UICONTROL Lifecycle Pause]**, quando o aplicativo estiver em segundo plano.

Para obter mais informações, consulte [Extensão do ciclo de vida no iOS](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-ios).

Esta é uma amostra da implementação deste caso de uso com o iOS:

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

No Android, os seguintes [!DNL Experience Platform APIs] são necessários:

* **[!UICONTROL OnResume]**
* **[!UICONTROL OnPause]**

Para obter mais informações, consulte [Extensão do ciclo de vida no Android](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-android).

Esta é uma amostra de implementação para este caso de uso com Android:

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

É necessário criar regras para notificações por push rastreando postback. Para obter mais informações, consulte [Push notifications tracking postback](../../administration/using/configuring-rules-launch.md#push-tracking-postback).

### Com iOS {#track-user-push-ios}

No iOS, o seguinte [!DNL Experience Platform SDK] é necessário:

* **[!UICONTROL trackAction]**. Para obter mais informações, consulte [Rastrear ações do aplicativo](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions).

Esta é uma amostra da implementação deste caso de uso com o iOS:

```
let deliveryId = userInfo["_dId"] as? String
let broadlogId = userInfo["_mId"] as? String
if (deliveryId != nil && broadlogId != nil) {
    ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
}
```

### Com Android {#track-user-push-android}

No Android, o seguinte [!DNL Experience Platform SDK] é necessário:

* **[!UICONTROL trackAction]**
Para obter mais informações, consulte  [Rastrear ações do aplicativo](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions).

Esta é uma amostra de implementação para este caso de uso com Android:

```
contextData.put("deliveryId", deliveryId);
contextData.put("broadlogId", messageId);
contextData.put("action", "2");
MobileCore.trackAction("tracking", contextData);
```

## Implementar um evento personalizado no aplicativo para acionar mensagens no aplicativo {#custom-event-inapp}

### Com iOS {#custom-event-inapp-ios}

No iOS, o seguinte [!DNL Experience Platform SDK] é necessário:

* **[!UICONTROL trackAction]**. Para obter mais informações, consulte [Rastrear ações do aplicativo](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions).

Esta é uma amostra da implementação deste caso de uso com o iOS:

```
ACPCore.trackAction(mobileEventName, data: [:] )
```

### Com Android {#custom-event-inapp-android}

No Android, o seguinte [!DNL Experience Platform SDK] é necessário:

* **[!UICONTROL trackAction]**
Para obter mais informações, consulte  [Rastrear ações do aplicativo](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions).

Esta é uma amostra de implementação para este caso de uso com Android:

```
MobileCore.trackAction(mobileEventText, new HashMap<String,String>());
```

## Definir campos de vinculação para autenticação adicional {#linkage-fields-inapp}

### Com iOS {#linkage-fields-inapp-ios}

Para definir campos de vinculação para autenticação adicional para o modelo de perfil baseado em mensagens no aplicativo no iOS, é necessário o seguinte [!DNL Experience Platform SDK]:

* Definir campos de vinculação <br>Para obter mais informações, consulte [Definir campos de vinculação](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#set-linkage-fields).
* Redefinir campos de vinculação <br>Para obter mais informações, consulte [Redefinir campos de vinculação](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#reset-linkage-fields).

Veja a seguir exemplos de implementações desse caso de uso com o iOS.

Para definir campos de vinculação:

```
var linkageFields = [String: String]()
linkageFields["cusEmail"] = "john.doe@email.com"
ACPCampaign.setLinkageFields(linkageFields)
```

Para redefinir campos de vinculação:

```
ACPCampaign.resetLinkageFields(linkageFields)
```

### Com Android {#linkage-fields-inapp-android}

Para definir campos de vinculação para autenticação adicional para o modelo de perfil baseado em mensagens no aplicativo no Android, o seguinte SDK do Experience Platform é necessário:

* Definir campos de vinculação <br>Para obter mais informações, consulte [Definir campos de vinculação](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#set-linkage-fields).
* Redefinir campos de vinculação <br>Para obter mais informações, consulte [Redefinir campos de vinculação](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#reset-linkage-fields).

Veja a seguir exemplos de implementações desse caso de uso com o Android.

Para definir campos de vinculação:

```
HashMap<String, String> linkageFields = new HashMap<String, String>();
linkageFields.put("cusEmail", "john.doe@email.com");
Campaign.setLinkageFields(linkageFields);
```

Para redefinir campos de vinculação:

```
Campaign.resetLinkageFields()
```
