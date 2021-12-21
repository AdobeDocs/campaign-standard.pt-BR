---
title: Implementação do rastreamento de push
description: Este documento permite garantir que o rastreamento da notificação por push tenha sido implementado corretamente no iOS e Android.
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 950d24e2-358f-44f8-98ea-643be61d4573
source-git-commit: 95d4b9fbb41f5204f387971be3710817a281a8c4
workflow-type: tm+mt
source-wordcount: '954'
ht-degree: 1%

---

# Implementação do rastreamento de push {#push-tracking}

## Sobre o rastreamento de push {#about-push-tracking}

Para garantir que a notificação por push tenha sido totalmente desenvolvida, verifique se a parte de rastreamento foi implementada corretamente, pois nem todas as notificações por push têm o rastreamento ativado. Para habilitar isso, os desenvolvedores precisam identificar quais deliveries têm o rastreamento ativado, o Adobe Campaign Standard enviará um sinalizador chamado `_acsDeliveryTracking` com dois valores **on** ou **off**. O desenvolvedor do aplicativo deve enviar uma solicitação de rastreamento somente nos deliveries que têm a variável definida como **on**.

>[!IMPORTANT]
>
>Essa variável não está disponível para deliveries definidos antes da versão 21.1 ou deliveries que usam templates personalizados.

O Rastreamento de push é separado em três tipos:

* **Impressões por push** - Quando uma notificação por push é entregue ao dispositivo e está sentado no centro de notificações, mas não foi tocada.  Isso é considerado uma impressão.  Na maioria dos casos, os números de impressões devem ser semelhantes se não forem iguais ao número entregue. Ele garante que o dispositivo recebeu a mensagem e reenviou essas informações ao servidor.

* **Clique por push** - Quando uma notificação por push for entregue ao dispositivo e o usuário clicar no dispositivo.  O usuário deseja exibir a notificação (que, por sua vez, será movida para o rastreamento Push Open) ou ignorar a notificação.

* **Empurrar Abertura** - Quando uma notificação por push é entregue ao dispositivo e o usuário clica na notificação que faz com que o aplicativo seja aberto.  Isso é semelhante ao Clique de push, exceto que a opção Abrir por push não será acionada se a notificação for descartada.

Para implementar o rastreamento para o Campaign Standard, o aplicativo móvel precisa incluir SDK móvel. Esses SDK estão disponíveis no Adobe Mobile Services. Para obter mais informações, consulte esta [página](../../administration/using/configuring-a-mobile-application.md).

Para enviar informações de rastreamento, há três variáveis que precisam ser enviadas. Dois que fazem parte dos dados recebidos do Campaign Standard e uma variável de ação que determina se é um **Impressão**, **Clique em** ou **Abrir**.

| Variável | Valor |
|:-:|:-:|
| broadlogId | _mId de dados |
| deliveryId | _dId a partir de dados |
| ação | 1 para Abrir, 2 para Clique e 7 para Impressão |

## Implementação para Android {#implementation-android}

### Como implementar o rastreamento de impressões de push {#push-impression-tracking-android}

Para o rastreamento de impressões, é necessário enviar o valor &quot;7&quot; para a ação ao chamar **[!UICONTROL trackAction()]** .

Para deliveries criados antes da versão 21.1 ou deliveries com modelo personalizado, consulte esta seção [seção](../../administration/using/push-tracking.md#about-push-tracking).

```
@Override
public void onMessageReceived(RemoteMessage remoteMessage) {
....{Handle push messages}....
  if (data.size() > 0) {
    String deliveryId = data.get("_dId");
    String messageId = data.get("_mId");
    String acsDeliveryTracking = data.get("_acsDeliveryTracking");
 
    /*
    This is to handle deliveries created before 21.1 release or deliveries with custom template
    where acsDeliveryTracking is not available.
    */
    if( acsDeliveryTracking == null ) {
        acsDeliveryTracking = "on";
    }
 
    HashMap<String, String> contextData = new HashMap<>();
    if (deliveryId != null && messageId != null && acsDeliveryTracking.equals("on")) {
                contextData.put("deliveryId", deliveryId);
                contextData.put("broadlogId", messageId);
                contextData.put("action", "7");
                MobileCore.trackAction("tracking", contextData);
    }
  }
}
```

### Como implementar o rastreamento de cliques {#push-click-tracking-android}

Para o rastreamento de cliques, é necessário enviar o valor &quot;2&quot; para a ação ao chamar **[!UICONTROL trackAction()]** .

Para rastrear cliques, dois cenários precisam ser tratados:

* O usuário vê a notificação, mas a limpa.
* O usuário vê a notificação e clica nela, tornando-a um rastreamento aberto.

Para lidar com isso, você precisa usar duas intenções: um para clicar na notificação e outro para descartar a notificação.

Para deliveries criados antes da versão 21.1 ou deliveries com modelo personalizado, consulte esta seção [seção](../../administration/using/push-tracking.md#about-push-tracking).

**[!UICONTROL MyFirebaseMessagingService.java]**

```
private void sendNotification(Map<String, String> data) {
    Intent openIntent = new Intent(this, CollectPIIActivity.class);
    Intent dismissIntent = new Intent(this, NotificationDismissedReceiver.class);
    openIntent.addFlags(Intent.FLAG_ACTIVITY_CLEAR_TOP);
  
    //put the data map into the intent to track clickthroughs
    Bundle pushData = new Bundle();
    Set<String> keySet = data.keySet();
    for (String key : keySet) {
        pushData.putString(key, data.get(key));
    }
    openIntent.putExtras(pushData);
    dissmissIntent.putExtras(pushData);
  
  
    PendingIntent pendingIntent = PendingIntent.getActivity(this, 0, openIntent,
        PendingIntent.FLAG_UPDATE_CURRENT);
    PendingIntent onDismissPendingIntent = PendingIntent.getBroadcast(this.getApplicationContext(), 0, dismissIntent, 0);
  
    //<BUILD NOTIFICATION using notification builder>
    //Add both Intents to the notification
    notificationBuilder.setContentIntent(pendingIntent);
    notificationBuilder.setDeleteIntent(onDismissPendingIntent);
}
```

Para **[!UICONTROL BroadcastReceiver]** para trabalhar, você precisa registrá-lo no **[!UICONTROL AndroidManifest.xml]**

```
<manifest>
    <application>
        <receiver android:name=".NotificationDismissedReceiver">
        </receiver>
    </application>
</manifest>
```

NotificationDismessedReceiver.java

```
public class NotificationDismissedReceiver extends BroadcastReceiver {
    private static final String TAG = NotificationDismissedReceiver.class.getSimpleName();
    @Override
    public void onReceive(Context context, Intent intent) {
        Bundle data = intent.getExtras();
        String deliveryId = data.getString("_dId");
        String messageId = data.getString("_mId");
        String acsDeliveryTracking = data.get("_acsDeliveryTracking");
         
        /*
        This is to handle deliveries created before 21.1 release or deliveries with custom template
        where acsDeliveryTracking is not available.
        */
        if( acsDeliveryTracking == null ) {
            acsDeliveryTracking = "on";
        }
 
        HashMap<String, Object> contextData = new HashMap<>();
 
        //We only send the click tracking since the user dismissed the notification
        if (deliveryId != null && messageId != null && acsDeliveryTracking.equals("on")) {
            contextData.put("deliveryId", deliveryId);
            contextData.put("broadlogId", messageId);
            contextData.put("action", "2");
            MobileCore.trackAction("tracking", contextData);
        }
    }
}
```

### Como implementar o rastreamento aberto {#push-open-tracking-android}

Será necessário enviar &quot;1&quot; e &quot;2&quot;, pois o usuário deve clicar na notificação para abrir o aplicativo. Se o aplicativo não for iniciado/aberto por meio da notificação por push, nenhum evento de rastreamento ocorrerá.

Para rastrear a abertura, é necessário criar Propósito. Os objetos de intenção permitem que o sistema operacional Android chame o método quando determinadas ações forem executadas. Nesse caso, clicando na notificação para abrir o aplicativo.

Esse código é baseado na implementação do rastreamento de impressões de cliques. Com **[!UICONTROL Intent]** , agora é necessário enviar informações de rastreamento para o Adobe Campaign Standard. Nesse caso, é necessário definir a variável **[!UICONTROL Open Intent]** para abrir para uma determinada exibição no aplicativo, isso chamará o método onResume com os dados de notificação no **[!UICONTROL Intent Object]**.

Para deliveries criados antes da versão 21.1 ou deliveries com modelo personalizado, consulte esta seção [seção](../../administration/using/push-tracking.md#about-push-tracking).

```
@Override
protected void onResume() {
    super.onResume();
    handleTracking();
}
 
 
private void handleTracking() {
    //Check to see if this view was opened based on a notification
    Intent intent = getIntent();
    Bundle data = intent.getExtras();
 
    if (data != null) {
        //This was opened based on the notification, you need to get the tracking that was passed on.
        String deliveryId = data.getString("_dId");
        String messageId = data.getString("_mId");
        String acsDeliveryTracking = data.get("_acsDeliveryTracking");
        /*
        This is to handle deliveries created before 21.1 release or deliveries with custom template
        where acsDeliveryTracking is not available.
        */
        if( acsDeliveryTracking == null) {
            acsDeliveryTracking = "on";
        }
 
        HashMap<String, String> contextData = new HashMap<>();
 
        if (deliveryId != null && messageId != null && acsDeliveryTracking.equals("on")) {
            contextData.put("deliveryId", deliveryId);
            contextData.put("broadlogId", messageId);
 
            //Send Click Tracking since the user did click on the notification
            contextData.put("action", "2");
            MobileCore.trackAction("tracking", contextData);
 
            //Send Open Tracking since the user opened the app
            contextData.put("action", "1");
            MobileCore.trackAction("tracking", contextData);
        }
    }
}
```

## Implementação para iOS {#implementation-iOS}

### Como implementar o rastreamento de impressões de push {#push-impression-tracking-iOS}

Para o rastreamento de impressões, é necessário enviar o valor &quot;7&quot; para a ação ao chamar **[!UICONTROL trackAction()]** .

Para entender como as notificações do iOS funcionam, os três estados de um aplicativo precisam ser detalhados:

* **Primeiro plano**: quando o aplicativo está ativo no momento e está na tela (em primeiro plano).
* **Histórico**: quando o aplicativo is não está na tela, mas o processo não está fechado. Ao clicar duas vezes no botão inicial, ele normalmente mostrará todos os aplicativos que estão em segundo plano.
* **Desligado/fechado**: um aplicativo cujo processo foi interrompido.

Para ainda ter **[!UICONTROL Impression]** rastreamento funcionando enquanto o aplicativo está em segundo plano, precisamos enviar **[!UICONTROL Content-Available]** para que o aplicativo saiba que um rastreamento deve ser feito.

>[!CAUTION]
>
> Se um aplicativo for fechado, a Apple não chamará o aplicativo até que ele seja reiniciado. Isso significa que você não poderá saber quando a notificação foi recebida no iOS. </br> Por esse motivo, o rastreamento de impressões do iOS pode não ser preciso e não deve ser considerado confiável.

Para deliveries criados antes da versão 21.1 ou deliveries com modelo personalizado, consulte esta seção [seção](../../administration/using/push-tracking.md#about-push-tracking).

O código a seguir direciona o aplicativo em segundo plano:

```
// In didReceiveRemoteNotification event handler in AppDelegate.m
 
//In order to handle push notification when only in background with content-available: 1
func application(_ application: UIApplication, didReceiveRemoteNotification userInfo: [AnyHashable : Any], fetchCompletionHandler completionHandler: @escaping (UIBackgroundFetchResult) -> Void) {
 
        //Check if the app is not in the foreground right now
        if(UIApplication.shared.applicationState != .active) {
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            let acsDeliveryTracking = userInfo["_acsDeliveryTracking"] as? String
            /*
            This is to handle deliveries created before 21.1 release or deliveries with custom template where acsDeliveryTracking is not available.
            */
            if( acsDeliveryTracking == nil ) {
                acsDeliveryTracking = "on";
            }
            if (deliveryId != nil && broadlogId != nil && acsDeliveryTracking?.caseInsensitiveCompare("on") == ComparisonResult.orderedSame) {
               ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])
            }
        }
        completionHandler(UIBackgroundFetchResult.noData)
    }
```

O código a seguir direciona o aplicativo em primeiro plano:

```
// This will get called when the app is in the foreground
 
func userNotificationCenter(_ center: UNUserNotificationCenter, willPresent notification: UNNotification, withCompletionHandler completionHandler: @escaping (UNNotificationPresentationOptions) -> Void) {
 
 
        let userInfo = notification.request.content.userInfo
        let deliveryId = userInfo["_dId"] as? String
        let broadlogId = userInfo["_mId"] as? String
        let acsDeliveryTracking = userInfo["_acsDeliveryTracking"] as? String
        /*
        This is to handle deliveries created before 21.1 release or deliveries with custom template where acsDeliveryTracking is not available.
        */
        if( acsDeliveryTracking == nil ) {
            acsDeliveryTracking = "on";
        }
        if (deliveryId != nil && broadlogId != nil && acsDeliveryTracking?.caseInsensitiveCompare("on") == ComparisonResult.orderedSame) {
             ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])
        }
        completionHandler([.alert,.sound])
    }
```

### Como implementar o rastreamento de cliques {#push-click-tracking-iOS}

Para o rastreamento de cliques, é necessário enviar o valor &quot;2&quot; para a ação ao chamar **[!UICONTROL trackAction()]** .
Para deliveries criados antes da versão 21.1 ou deliveries com modelo personalizado, consulte esta seção [seção](../../administration/using/push-tracking.md#about-push-tracking).

```
// AppDelegate.swift
...
import os.log
import UserNotifications
...
  
func registerForPushNotifications() {
        let center = UNUserNotificationCenter.current()
        center.delegate = notificationDelegate
        //Here we are creating a new Category that allows us to handle Dismiss Actions
        let defaultCategory = UNNotificationCategory(identifier: "DEFAULT", actions: [], intentIdentifiers: [], options: .customDismissAction)
        //Add it to our array of Category, in this case we only have one
        center.setNotificationCategories([defaultCategory])
        center.requestAuthorization(options: [.alert, .sound, .badge]) {
            (granted, error) in
            os_log("Permission granted: %{public}@", type:. debug, granted.description)
            if error != nil {
                return
            }
            if granted {
                os_log("Notifications allowed", type: .debug)
            }
            else {
                os_log("Notifications denied", type: .debug)
            }
  
            // 2. Attempt registration for remote notifications on the main thread
            DispatchQueue.main.async {
                UIApplication.shared.registerForRemoteNotifications()
            }
        }
    }
```

Agora, ao enviar notificações por push, é necessário adicionar uma categoria. Nesse caso, o chamamos de &quot;PADRÃO&quot;.

![](assets/tracking_push.png)

Em seguida, manipule o **[!UICONTROL Dismiss]** e envie uma informação de rastreamento que você precisa adicionar o seguinte:

```
func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
        let userInfo = response.notification.request.content.userInfo
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:
            print("Dismiss Action")
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            let acsDeliveryTracking = userInfo["_acsDeliveryTracking"] as? String
            /*
            This is to handle deliveries created before 21.1 release or deliveries with custom template where acsDeliveryTracking is not available.
            */
            if( acsDeliveryTracking == nil ) {
                acsDeliveryTracking = "on";
            }
            if (deliveryId != nil && broadlogId != nil && acsDeliveryTracking?.caseInsensitiveCompare("on") == ComparisonResult.orderedSame) {
                ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            ////MORE CODE
        }
        completionHandler()
    }
```

### Como implementar o rastreamento aberto {#push-open-tracking-iOS}

Será necessário enviar &quot;1&quot; e &quot;2&quot;, pois o usuário deve clicar na notificação para abrir o aplicativo. Se o aplicativo não for iniciado/aberto por meio da notificação por push, nenhum evento de rastreamento ocorrerá.

Para deliveries criados antes da versão 21.1 ou deliveries com modelo personalizado, consulte esta seção [seção](../../administration/using/push-tracking.md#about-push-tracking).

```
import Foundation
import UserNotifications
import UserNotificationsUI
 
class NotificationDelegate: NSObject, UNUserNotificationCenterDelegate {
 
    // Called when user clicks the push notification or also called from willPresent()
    func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
 
        let userInfo = response.notification.request.content.userInfo
        os_log("App push data %{public}@, in userNotificationCenter:didReceive()", type: .debug, userInfo)
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:
            //This is to handle the Dismiss Action
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            let acsDeliveryTracking = userInfo["_acsDeliveryTracking"] as? String
            /*
            This is to handle deliveries created before 21.1 release or deliveries with custom template where acsDeliveryTracking is not available.
            */
            if( acsDeliveryTracking == nil ) {
                acsDeliveryTracking = "on";
            }
            if (deliveryId != nil && broadlogId != nil && acsDeliveryTracking?.caseInsensitiveCompare("on") == ComparisonResult.orderedSame) {
                ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            //This is to handle the tracking when the app opens
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            let acsDeliveryTracking = userInfo["_acsDeliveryTracking"] as? String
            /*
            This is to handle deliveries created before 21.1 release or deliveries with custom template where acsDeliveryTracking is not available.
            */
            if( acsDeliveryTracking == nil ) {
                acsDeliveryTracking = "on";
            }
            if (deliveryId != nil && broadlogId != nil && acsDeliveryTracking?.caseInsensitiveCompare("on") == ComparisonResult.orderedSame) {
                ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
                ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])
            }
        }
        completionHandler()
    }
}
```
