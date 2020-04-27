---
title: Implementação do rastreamento de push
description: Esse documento permite garantir que o rastreamento de notificação por push tenha sido implementado corretamente no iOS e no Android.
page-status-flag: never-activated
uuid: 961aaeb5-6948-4fd2-b8d7-de4510c10566
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: push-notifications
discoiquuid: 23b4212e-e878-4922-be20-50fb7fa88ae8
context-tags: mobileApp,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: efb1f14e0094e200d186423f98bfad65d25cfab2

---


# Implementação do rastreamento de push {#push-tracking}

## Sobre o rastreamento de push {#about-push-tracking}

Para garantir que a notificação por push tenha sido totalmente desenvolvida, é necessário ter certeza de que a parte de rastreamento foi implementada corretamente.

As etapas a seguir permitem garantir que o rastreamento de push tenha sido implementado corretamente. Isso pressupõe que você já tenha implementado as primeiras partes da implementação da Notificação por push: Registrando o usuário do aplicativo e manipulando uma mensagem de notificação por push.

O Rastreamento de push é separado em três tipos:

* **Impressões** por push: quando uma notificação por push é entregue ao dispositivo e está no centro de notificações, mas não foi tocada de forma alguma.  Isso é considerado uma impressão.  Na maioria dos casos, os números de impressões devem ser semelhantes se não forem iguais ao número fornecido. Isso garante que o dispositivo recebeu a mensagem e repassou essas informações para o servidor.

* **Clique** para enviar - quando uma notificação por push for entregue ao dispositivo e o usuário clicar no dispositivo.  O usuário desejava visualização na notificação (que, por sua vez, se moverá para o rastreamento Push Open) ou rejeitar a notificação.

* **Abrir** push - quando uma notificação por push é entregue ao dispositivo e o usuário clica na notificação que faz com que o aplicativo seja aberto.  Isso é semelhante ao clique de push, exceto que a opção Abrir push não será acionada se a notificação for descartada.

Para implementar o rastreamento para o Campaign Standard, o aplicativo móvel precisa incluir o SDK móvel. Esses SDK estão disponíveis no Adobe Mobile Services.

Para enviar informações de rastreamento, há três variáveis que precisam ser enviadas. Dois que são parte dos dados recebidos do Campaign Standard e uma variável de ação que determina se é uma **Impressão**, um **Clique** ou um **Abrir**.

| Variável | Valor |
|:-:|:-:|
| BroadlogId | _mId a partir de dados |
| deliveryId | _dId a partir de dados |
| ação | 1 para Abrir, 2 para Clique e 7 para Impressão |

## Implementação para Android {#implementation-android}

### Como implementar o rastreamento de impressão de push {#push-impression-tracking-android}

Para o rastreamento de impressão, é necessário enviar o valor &quot;7&quot; para a ação ao chamar a função trackAction().

```
@Override
public void onMessageReceived(RemoteMessage remoteMessage) {
....{Handle push messages}....
  if (data.size() > 0) {
    String deliveryId = data.get("_dId");
    String messageId = data.get("_mId");
    HashMap<String, String> contextData = new HashMap<>();
    if (deliveryId != null && messageId != null) {
                contextData.put("deliveryId", deliveryId);
                contextData.put("broadlogId", messageId);
                contextData.put("action", "7");
                MobileCore.trackAction("tracking", contextData);
    }
  }
}
```

### Como implementar o rastreamento de cliques {#push-click-tracking-android}

Para o rastreamento de cliques, é necessário enviar o valor &quot;2&quot; para a ação ao chamar a função trackAction().

Para rastrear cliques, dois cenários precisam ser tratados:

* O usuário visualiza a notificação, mas a apaga.
* O usuário visualiza a notificação e clica nela para torná-la um rastreamento aberto.

Para lidar com isso, você precisa usar dois propósitos: um para clicar na notificação e outro para rejeitar a notificação.

MyFirebaseMessagingService.java

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

Para que BroadcastReceiver funcione, é necessário registrá-lo no AndroidManifest.xml

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
  
        HashMap<String, Object> contextData = new HashMap<>();
  
        //We only send the click tracking since the user dismissed the notification
        if (deliveryId != null && messageId != null) {
            contextData.put("deliveryId", deliveryId);
            contextData.put("broadlogId", messageId);
            contextData.put("action", "1");
            MobileCore.trackAction("tracking", contextData);
        }
    }
}
```

### Como implementar o rastreamento aberto {#push-open-tracking-android}

Você precisará enviar &quot;1&quot; e &quot;2&quot;, pois o usuário precisa clicar na notificação para abrir o aplicativo. Se o aplicativo não for iniciado/aberto por meio da notificação por push, nenhum evento de rastreamento ocorrerá.

Para rastrear a abertura, é necessário criar Propósito. Objetos intencionais permitem que o sistema operacional Android chame seu método quando determinadas ações são realizadas. Nesse caso, clique na notificação para abrir o aplicativo.

Esse código é baseado na implementação do rastreamento de impressão de cliques. Com a Definição de intenção, agora é necessário enviar informações de rastreamento de volta para a Campanha. Nesse caso, é necessário definir o Open Intent para abrir uma determinada visualização no aplicativo, isso chamará o método onResume WITH os dados de notificação no Intent Object.

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
        //Looks it was opened based on the notification, lets get the tracking we passed on.
        String deliveryId = data.getString("_dId");
        String messageId = data.getString("_mId");
  
        HashMap<String, Object> contextData = new HashMap<>();
  
        if (deliveryId != null && messageId != null) {
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

### Como implementar o rastreamento de impressão de push {#push-impression-tracking-iOS}

Para o rastreamento de impressão, é necessário enviar o valor &quot;7&quot; para a ação ao chamar a função trackAction().

Para entender como as notificações do iOS funcionam, os três estados de um aplicativo precisam ser detalhados:

* **Primeiro plano**: quando o aplicativo está ativo no momento e está na tela (em primeiro plano).
* **Plano de fundo**: quando o aplicativo is não está na tela, mas o processo não está fechado. Quando você clica no botão inicial com o duplo, ele geralmente mostra todos os aplicativos que estão em segundo plano.
* **Desligado/fechado**: um aplicativo cujo processo foi morto.

Se um aplicativo for fechado, a Apple não chamará o aplicativo até que ele seja reiniciado. Isso significa que você não poderá saber quando a notificação foi recebida no iOS.

Para que o Rastreamento de impressão ainda funcione enquanto o aplicativo está em segundo plano, precisamos enviar **Conteúdo disponível** para informar ao aplicativo que um rastreamento deve ser feito.

>[!CAUTION]
>
>O Rastreamento de impressão do iOS não é preciso e não deve ser visto como confiável.

O código a seguir público alvo o aplicativo em segundo plano:

```
// In didReceiveRemoteNotification event handler in AppDelegate.m
  
//In order to handle push notification when only in background with content-available: 1
func application(_ application: UIApplication, didReceiveRemoteNotification userInfo: [AnyHashable : Any], fetchCompletionHandler completionHandler: @escaping (UIBackgroundFetchResult) -> Void) {
  
        //Check if the app is not in the foreground right now
        if(UIApplication.shared.applicationState != .active) {
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
               ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])
            }
        }
        completionHandler(UIBackgroundFetchResult.noData)
    }
```

O código a seguir público alvo o aplicativo em primeiro plano:

```
// This will get called when the app is in the foreground
  
func userNotificationCenter(_ center: UNUserNotificationCenter, willPresent notification: UNNotification, withCompletionHandler completionHandler: @escaping (UNNotificationPresentationOptions) -> Void) {
  
  
        let userInfo = notification.request.content.userInfo
        let deliveryId = userInfo["_dId"] as? String
        let broadlogId = userInfo["_mId"] as? String
        if (deliveryId != nil && broadlogId != nil) {
             ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])
        }
        completionHandler([.alert,.sound])
    }
```

### Como implementar o rastreamento de cliques {#push-click-tracking-iOS}

Para o rastreamento de cliques, é necessário enviar o valor &quot;2&quot; para a ação ao chamar a função trackAction().

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

Agora, ao enviar notificações por push, é necessário adicionar uma categoria. Nesse caso, chamamos de &quot;PADRÃO&quot;.

![](assets/tracking_push.png)

Em seguida, para manipular o Dismiss e enviar uma informação de rastreamento, você precisa adicionar o seguinte:

```
func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
        let userInfo = response.notification.request.content.userInfo
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:
            print("Dismiss Action")
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
                ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            ////MORE CODE
        }
        completionHandler()
    }
```

### Como implementar o rastreamento aberto {#push-open-tracking-iOS}

Você precisará enviar &quot;1&quot; e &quot;2&quot;, pois o usuário precisa clicar na notificação para abrir o aplicativo. Se o aplicativo não for iniciado/aberto por meio da notificação por push, nenhum evento de rastreamento ocorrerá.

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
            if (deliveryId != nil && broadlogId != nil) {
                ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            //This is to handle the tracking when the app opens
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
                ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
                ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])
            }
        }
        completionHandler()
    }
}
```
