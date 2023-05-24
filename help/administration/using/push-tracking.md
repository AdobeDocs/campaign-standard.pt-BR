---
title: Implementação do rastreamento de push
description: Saiba como garantir que o rastreamento de notificação por push tenha sido implementado corretamente no iOS e no Android
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 950d24e2-358f-44f8-98ea-643be61d4573
source-git-commit: acbe5f1990738f586e4310d13f0e19baab11d771
workflow-type: tm+mt
source-wordcount: '958'
ht-degree: 0%

---

# Implementação do rastreamento de push {#push-tracking}

## Sobre o rastreamento de push {#about-push-tracking}

Para garantir que a notificação por push tenha sido totalmente desenvolvida, é necessário garantir que a parte de rastreamento tenha sido implementada corretamente, pois nem todas as notificações por push têm o rastreamento ativado. Para ativar isso, os desenvolvedores precisam identificar quais deliveries têm o rastreamento ativado, o Adobe Campaign Standard enviará um sinalizador chamado `_acsDeliveryTracking` com dois valores **em** ou **desligado**. O desenvolvedor do aplicativo deve enviar uma solicitação de rastreamento somente em deliveries que tenham a variável definida como **em**.

>[!IMPORTANT]
>
>Essa variável não está disponível para entregas definidas antes da versão 21.1, nem para entregas que usam modelos personalizados.

O Rastreamento de push é separado em três tipos:

* **Impressões por push** - Quando uma notificação por push foi entregue ao dispositivo e está localizada no centro de notificações, mas não foi tocada.  Isso é considerado uma impressão.  Na maioria dos casos, os números de impressões devem ser semelhantes, se não iguais, ao número entregue. Ele garante que o dispositivo recebeu a mensagem e transmitiu essas informações de volta para o servidor.

* **Clique por push** - Quando uma notificação por push tiver sido entregue ao dispositivo e o usuário tiver clicado nele.  O usuário queria visualizar a notificação (que, por sua vez, passará para o rastreamento de Push Open) ou descartar a notificação.

* **Push aberto** - Quando uma notificação por push é entregue ao dispositivo e o usuário clica na notificação, fazendo com que o aplicativo seja aberto.  Isso é semelhante ao clique por push, exceto que uma abertura por push não será acionada se a notificação tiver sido descartada.

Para implementar o rastreamento do Campaign Standard, o aplicativo móvel precisa incluir os SDKs da Adobe Experience Platform. Esses SDKs estão disponíveis no [Documentação dos SDKs do Adobe Experience Platform](https://github.com/Adobe-Marketing-Cloud/acp-sdks).

Para enviar informações de rastreamento, há três variáveis que precisam ser enviadas. Dois que fazem parte dos dados recebidos do Campaign Standard e uma variável de ação que determina se é um **Impressão**, **Clique em** ou **Abertura**.

| Variável | Valor |
|:-:|:-:|
| broadlogId | _Id dos dados |
| deliveryId | _dId dos dados |
| ação | &quot;1&quot; para Abertura, &quot;2&quot; para Clique e &quot;7&quot; para Impressão |

## Implementação para Android {#implementation-android}

### Como implementar o rastreamento de impressões de push {#push-impression-tracking-android}

Para rastreamento de impressões, você terá que enviar o valor &quot;7&quot; para ação ao chamar `collectMessageInfo()` ou `trackAction()` funções.

Para deliveries criados antes da versão 21.1 ou deliveries com modelo personalizado, consulte este [seção](../../administration/using/push-tracking.md#about-push-tracking).

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
    if( deliveryId != null && messageId != null && acsDeliveryTracking.equals("on")) {
      contextData.put("deliveryId", deliveryId);
      contextData.put("broadlogId", messageId);
      contextData.put("action", "7");

    //If you are using ACPCore v1.4.0 or later, use the next line.
      
      MobileCore.collectMessageInfo(contextData);
      
    //Else comment out the above line and uncomment the line below
        
    //MobileCore.trackAction("tracking", contextData) ;
    }
  }
}
```

### Como implementar o rastreamento de cliques {#push-click-tracking-android}

Para o rastreamento de cliques, é necessário enviar o valor &quot;2&quot; para a ação ao chamar `collectMessageInfo()` ou `trackAction()` funções.
Para rastrear cliques, dois cenários precisam ser manipulados:

* O usuário vê a notificação, mas a apaga.
* O usuário vê a notificação e clica nela, transformando-a em um rastreamento aberto.

Para lidar com isso, você precisa usar dois propósitos: um para clicar na notificação e outro para descartar a notificação.

Para deliveries criados antes da versão 21.1 ou deliveries com modelo personalizado, consulte este [seção](../../administration/using/push-tracking.md#about-push-tracking).

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

A fim de assegurar a **[!UICONTROL BroadcastReceiver]** para funcionar, é necessário registrá-lo na **[!UICONTROL AndroidManifest.xml]**

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
            
        //If you are using ACPCore v1.4.0 or later, use the next line.
        
            MobileCore.collectMessageInfo(contextData);
            
        //Else comment out the above line and uncomment the line below
        
            //MobileCore.trackAction("tracking", contextData);
        }
    }
}
```

### Como implementar o rastreamento aberto {#push-open-tracking-android}

Você precisará enviar &quot;1&quot; e &quot;2&quot; já que o usuário deve clicar em notificação para abrir o aplicativo. Se o aplicativo não for iniciado/aberto por meio da notificação por push, nenhum evento de rastreamento ocorrerá.

Para rastrear aberturas, é necessário criar a intenção. Os objetos de intenção permitem que o Android OS chame seu método quando determinadas ações forem executadas. Nesse caso, clicar na notificação para abrir o aplicativo.

Este código é baseado na implementação do rastreamento de impressão de cliques. Com **[!UICONTROL Intent]** Agora é necessário enviar as informações de rastreamento de volta para a Adobe Campaign Standard. Nesse caso, é necessário definir a variável **[!UICONTROL Open Intent]** para abrir para uma determinada exibição no aplicativo, isso chamará o método onResume com os dados de notificação no **[!UICONTROL Intent Object]**.

Para deliveries criados antes da versão 21.1 ou deliveries com modelo personalizado, consulte este [seção](../../administration/using/push-tracking.md#about-push-tracking).

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
            contextData.put("action", "2");
            
            //Send Click Tracking since the user did click on the notification
              
                //If you are using ACPCore v1.4.0 or later, use the next line.

                MobileCore.collectMessageInfo(contextData);
                  
                //Else comment out the above line and uncomment the line below
        
                //MobileCore.trackAction("tracking", contextData);
 
                //Send Open Tracking since the user opened the app
            
                contextData.put("action", "1");
                
                //If you are using ACPCore v1.4.0 or later, use the next line.

                MobileCore.collectMessageInfo(contextData);
                //Else comment out the above line and uncomment the line below
        
                //MobileCore.trackAction("tracking", contextData);
        }
    }
}
```

## Implementação do iOS {#implementation-iOS}

### Como implementar o rastreamento de impressões de push {#push-impression-tracking-iOS}

Para rastreamento de impressões, você terá que enviar o valor &quot;7&quot; para ação ao chamar `collectMessageInfo()` ou `trackAction()` funções.

Para entender como as notificações do iOS funcionam, os três estados de um aplicativo precisam ser detalhados:

* **Primeiro plano**: quando o aplicativo está ativo no momento e está na tela (em primeiro plano).
* **Histórico**: quando o aplicativo is não está na tela, mas o processo não está fechado. Quando você clica duas vezes no botão Início, ele geralmente mostra todos os aplicativos que estão em segundo plano.
* **Desligado/fechado**: um aplicativo cujo processo foi interrompido.

A fim de continuar a ter **[!UICONTROL Impression]** rastreamento funcionando enquanto o aplicativo está em segundo plano que precisamos enviar **[!UICONTROL Content-Available]** para que o aplicativo saiba que um rastreamento deve ser feito.

>[!CAUTION]
>
> Se um aplicativo estiver fechado, o Apple não chamará o aplicativo até que ele seja reiniciado. Isso significa que você não poderá saber quando a notificação foi recebida no iOS. </br> Por esse motivo, o rastreamento de impressões do iOS pode não ser preciso e não deve ser visto como confiável.

Para deliveries criados antes da versão 21.1 ou deliveries com modelo personalizado, consulte este [seção](../../administration/using/push-tracking.md#about-push-tracking).

O código a seguir é direcionado ao aplicativo em segundo plano:

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

            //If you are using ACPCore v2.3.0 or later, use the next line.

                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])
                
            //Else comment out the above line and uncomment the line below
        
                //ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])
            }
        }
        completionHandler(UIBackgroundFetchResult.noData)
    }
```

O código a seguir é direcionado ao aplicativo de primeiro plano:

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

            //If you are using ACPCore v2.3.0 or later, use the next line.

                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])
                
            //Else comment out the above line and uncomment the line below
        
                //ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])        
            }
        completionHandler([.alert,.sound])
    }
```

### Como implementar o rastreamento de cliques {#push-click-tracking-iOS}

Para o rastreamento de cliques, é necessário enviar o valor &quot;2&quot; para a ação ao chamar `collectMessageInfo()` ou `trackAction()` funções.
Para deliveries criados antes da versão 21.1 ou deliveries com modelo personalizado, consulte este [seção](../../administration/using/push-tracking.md#about-push-tracking).

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

Em seguida, para lidar com **[!UICONTROL Dismiss]** e enviar uma informação de rastreamento, é necessário adicionar o seguinte:

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

            //If you are using ACPCore v2.3.0 or later, use the next line.

                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
                
            //Else comment out the above line and uncomment the line below
        
                //ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])   
            }
        default:
            ////MORE CODE
        }
        completionHandler()
    }
```

### Como implementar o rastreamento aberto {#push-open-tracking-iOS}

Você precisará enviar &quot;1&quot; e &quot;2&quot; já que o usuário deve clicar em notificação para abrir o aplicativo. Se o aplicativo não for iniciado/aberto por meio da notificação por push, nenhum evento de rastreamento ocorrerá.

Para deliveries criados antes da versão 21.1 ou deliveries com modelo personalizado, consulte este [seção](../../administration/using/push-tracking.md#about-push-tracking).

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

            //If you are using ACPCore v2.3.0 or later, use the next line.

                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
                
            //Else comment out the above line and uncomment the line below
        
                //ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])

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
            //If you are using ACPCore v2.3.0 or later, use the next line.

                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
                
            //Else comment out the above line and uncomment the line below
        
                //ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])                
                
            //If you are using ACPCore v2.3.0 or later, use the next line.

                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])
                
            //Else comment out the above line and uncomment the line below
        
                //ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])
                
            }
        }
        completionHandler()
    }
}
```
