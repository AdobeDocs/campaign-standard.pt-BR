---
title: Implementação de rastreamento local
description: Saiba como garantir que o rastreamento de notificação por push tenha sido implementado corretamente no iOS e Android
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: b983d0a3-c345-44d4-bc82-202bf6ed26ab
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '568'
ht-degree: 1%

---

# Implementação de rastreamento local {#local-tracking}

## Sobre o rastreamento local {#about-local-tracking}

Nesta página, saiba como garantir que o rastreamento de notificação local tenha sido implementado corretamente. Observe que isso implica que a notificação local já foi configurada.

O rastreamento de notificação local pode ser dividido em três tipos:

* **Impressões locais** - Quando uma notificação local é entregue ao dispositivo e está sentado no centro de notificações, mas não foi tocada. Na maioria dos casos, o número de impressões deve ser semelhante se não for o mesmo que o número fornecido. Ele garante que o dispositivo recebeu a mensagem e retorna essa informação ao servidor.

* **Clique local** - Quando uma notificação local for entregue ao dispositivo e o usuário clicar na notificação. O usuário quis exibir a notificação (que, por sua vez, mudará para o rastreamento aberto local) ou rejeitar a notificação.

* **Abertura local** - Quando uma notificação local é entregue ao dispositivo e o usuário clica na notificação que causa a abertura do aplicativo. Isso é semelhante ao clique local, exceto que uma abertura local não será acionada se a notificação for descartada.

Para implementar o rastreamento para Adobe Campaign Standard, o aplicativo móvel precisa incluir SDK móvel no aplicativo. Esses SDKs estão disponíveis em [!DNL Adobe Mobile Services].

Para enviar informações de rastreamento, há três variáveis que devem ser enviadas: dois são parte dos dados recebidos do Adobe Campaign e o outro é uma variável de ação que determina se é uma impressão, clique ou abertura.

| Variável | Valor |
| :-: | :-: |
| deliveryId | `deliveryId` dos dados recebidos (semelhante ao rastreamento por push em que `_dld` é usado) |
| broadlogId | `broadlogId` dos dados recebidos (semelhante ao rastreamento por push em que `_mld` é usado) |
| ação | &quot;1&quot; para Abrir, &quot;2&quot; para Clique e &quot;7&quot; para Impressão |

## Implementar o rastreamento de impressão local {#implement-local-impression-tracking}

O SDK do Adobe Experience Platform Mobile enviará automaticamente o evento de impressão para Android e iOS sem qualquer configuração adicional.

## Implementar o rastreamento de cliques {#implementing-click-tracking}

Para o rastreamento de cliques, você deve enviar o valor &quot;2&quot; para a ação ao chamar `collectMessageInfo()` ou `trackAction()` funções.

### Para Android {#implement-click-tracking-android}

Para rastrear cliques, dois cenários devem ser implementados:

* O usuário vê a notificação, mas a limpa.

   Para rastrear o clique em caso de desativação, adicione o receptor da transmissão `NotificationDismissalHandler` no arquivo AndroidManifest do módulo de aplicativo.

   ```
   <receiver
   android:name="com.adobe.marketing.mobile.NotificationDismissalHandler">
   </receiver>
   ```

* O usuário vê a notificação e clica nela, isso se transformará em um rastreamento aberto.

   Esse cenário deve produzir um clique e uma abertura. O rastreamento desse clique fará parte da implementação necessária para rastrear a abertura. Consulte [Implementação do rastreamento aberto](#implement-open-tracking).

### Para iOS {#implement-click-tracking-ios}

Para enviar as informações de rastreamento de cliques, você deve adicionar o seguinte:

```
class NotificationDelegate: NSObject, UNUserNotificationCenterDelegate {

   func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
        let userInfo = response.notification.request.content.userInfo
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:
            print("Dismiss Action")
            let deliveryId = userInfo["deliveryId"] as? String
            let broadlogId = userInfo["broadlogId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
                
                //If you are using ACPCore v2.3.0 or later, use the next line.
                
                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
                
                //Else comment out the above line and uncomment the line below
                
                // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            
            ////MORE CODE
        }
        completionHandler()
    }
}
```

## Implementar o rastreamento aberto {#implement-open-tracking}

Você deve enviar &quot;1&quot; e &quot;2&quot;, pois o usuário deve clicar na notificação para abrir o aplicativo. Se o aplicativo não for iniciado/aberto por meio da notificação local, nenhum evento de rastreamento ocorrerá.

### Para Android {#implement-open-tracking-android}

Para rastrear aberturas, devemos criar intenções. Os objetos de intenção permitem que o sistema operacional Android chame o método quando determinadas ações forem executadas, nesse caso clicando na notificação para abrir o aplicativo.

Esse código é baseado na implementação do rastreamento de impressões de cliques. Com a intenção definida, agora você deve enviar informações de rastreamento de volta ao Adobe Campaign. Nesse caso, Android View([!DNL Activity]) que acionou a notificação que será aberta ou trazida para o primeiro plano como resultado do clique por usuário. O objeto de intenção em [!DNL Activity] contém os dados de notificação que podem ser usados para rastrear aberturas.

MainActivity.java (estende) [!DNL Activity])

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

        //Opened based on the notification, you must get the tracking that was passed on.

        Map<String, String> notificationData = (Map<String, Object>)data.getSerializableExtra("NOTIFICATION_USER_INFO");
        String deliveryId = (String)notificationData.get("deliveryId");
        String messageId = (String)notificationData.get("broadlogId");

        if (deliveryId != null && messageId != null) {
            HashMap<String, String> contextData = new HashMap<>();
            contextData.put("deliveryId", deliveryId);
            contextData.put("broadlogId", messageId);
 
            //Send click tracking since the user did click on the notification

            contextData.put("action", "2");

            //If you are using ACPCore v1.4.0 or later, use the next line.
    
            MobileCore.collectMessageInfo(contextData);

            //Else comment out the above line and uncomment the line below

            // MobileCore.trackAction("tracking", contextData);
 
            //Send open tracking since the user opened the app

            contextData.put("action", "1");

            //If you are using  ACPCore v1.4.0 or later, use the next line.

            MobileCore.collectMessageInfo(contextData);

            //Else comment out the above line and uncomment the line below

            // MobileCore.trackAction("tracking", contextData);
        }
    }
}
```

### Para iOS {#implement-open-tracking-ios}

```
import os.log
import Foundation
import UserNotifications
import UserNotificationsUI
import ACPCore
 
class NotificationDelegate: NSObject, UNUserNotificationCenterDelegate {
 
    //Called when user clicks the local notification or also called from willPresent()

    func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
 
        let userInfo = response.notification.request.content.userInfo
        os_log("App push data %{public}@, in userNotificationCenter:didReceive()", type: .debug, userInfo)
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:

            //This is to handle the Dismiss action

            let deliveryId = userInfo["deliveryId"] as? String
            let broadlogId = userInfo["broadlogId"] as? String
            if (deliveryId != nil && broadlogId != nil) {

                //If you are using ACPCore v2.3.0 or later, use the next line.

                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])

                //Else comment out the above line and uncomment the line below

                // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            //This is to handle the tracking when the app opens
            let deliveryId = userInfo["deliveryId"] as? String
            let broadlogId = userInfo["broadlogId"] as? String
            if (deliveryId != nil && broadlogId != nil) {

               //If you are using ACPCore v2.3.0 or later, use the next line.

               ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
               ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])

               //Else comment out the above line and uncomment the line below

               // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
               // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])
            }
        }
        completionHandler()
    }
}
```
