---
solution: Campaign Standard
product: campaign
title: Implementação do rastreamento de push
description: Este documento permite garantir que o rastreamento da notificação por push tenha sido implementado corretamente no iOS e Android.
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Configurações de instância
role: Administrador
level: Experienciado
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '730'
ht-degree: 1%

---


# Implementação do rastreamento local {#local-tracking}

## Sobre o rastreamento local {#about-local-tracking}

Nesta página, saiba como garantir que o rastreamento de notificação local tenha sido implementado corretamente. Observe que isso implica que a notificação local já foi configurada.

O rastreamento de notificação local pode ser dividido em três tipos:

* **Impressões locais**  - Quando uma notificação local é entregue ao dispositivo e está sentada no centro de notificações, mas não foi tocada. Na maioria dos casos, o número de impressões deve ser semelhante se não for o mesmo que o número fornecido. Ele garante que o dispositivo recebeu a mensagem e retorna essa informação ao servidor.

* **Clique local**  - Quando uma notificação local for entregue ao dispositivo e o usuário clicar no dispositivo. O usuário quis exibir a notificação (que, por sua vez, mudará para o rastreamento aberto local) ou rejeitar a notificação.

* **Local open**  - Quando uma notificação local é entregue ao dispositivo e o usuário clicou na notificação que causa a abertura do aplicativo. Isso é semelhante ao clique local, exceto que uma abertura local não será acionada se a notificação for descartada.

Para implementar o rastreamento para Adobe Campaign Standard, o aplicativo móvel precisa incluir SDK móvel no aplicativo. Esses SDKs estão disponíveis em [!DNL Adobe Mobile Services].

Para enviar informações de rastreamento, há três variáveis que precisam ser enviadas: dois são parte dos dados recebidos do Adobe Campaign e o outro é uma variável de ação que determina se é uma impressão, clique ou abertura.

| Variável | Valor |
| :-: | :-: |
| deliveryId | &quot;deliveryId&quot; dos dados de entrada (semelhante ao rastreamento de push, onde&quot;_dld&quot; é usado) |
| broadlogId | &quot;broadlogId&quot; dos dados de entrada (semelhante ao rastreamento de push, onde &quot;_mld&quot; é usado) |
| ação | &quot;1&quot; para Abrir, &quot;2&quot; para Clique e &quot;7&quot; para Impressão |

## Implementação do rastreamento de impressão local {#implement-local-impression-tracking}

Para o rastreamento de impressões, é necessário enviar o valor &quot;7&quot; para a ação ao chamar as funções collectMessageInfo() ou trackAction() .

### Para Android {#implement-local-impression-tracking-android}

O SDK do Adobe Experience Platform Mobile inicia o rastreamento de impressões para notificações locais ao acioná-lo.

### Para iOS {#implement-local-impression-tracking-ios}

Para explicar como implementar o rastreamento de impressão, precisamos entender os três estados de um aplicativo:

* **Primeiro plano**: quando o aplicativo estiver ativo no momento e na tela em primeiro plano.

* **Plano de fundo**: quando o aplicativo não estiver na tela, mas o processo também não estiver fechado. Ao clicar duas vezes no botão inicial, ele normalmente mostra todos os aplicativos em segundo plano.

* **Desligado/Fechado**: quando o processo do aplicativo foi interrompido. Se um aplicativo for fechado, a Apple não o chamará até que o aplicativo seja reiniciado. Isso significa que você nunca pode realmente saber quando a notificação foi recebida no iOS.

Para que o rastreamento de impressões continue funcionando enquanto o aplicativo está em segundo plano, precisamos enviar &quot;Content-Available&quot; para informar ao aplicativo que o rastreamento precisa ser feito.

O SDK do Adobe Experience Platform Mobile inicia o rastreamento de impressões para notificações locais ao acioná-lo.

>[!CAUTION]
>
>O rastreamento de impressões do iOS não é preciso e não deve ser observado de forma confiável.

## Implementação do rastreamento de cliques {#implementing-click-tracking}

Para o rastreamento de cliques, é necessário enviar o valor &quot;2&quot; para a ação ao chamar as funções collectMessageInfo() ou trackAction() .

### Para Android {#implement-click-tracking-android}

Para rastrear cliques, dois cenários precisam ser tratados:

* O usuário vê a notificação, mas a limpa.

* O usuário vê a notificação e clica nela, isso se transformará em um rastreamento aberto.

O primeiro cenário de clique é rastreado pelo Adobe Experience Platform Mobile SDK.

### Para iOS {#implement-click-tracking-ios}

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

Em seguida, para lidar com o descarte e enviar uma informação de rastreamento, é necessário adicionar o seguinte:

```
func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
        let userInfo = response.notification.request.content.userInfo
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:
            print("Dismiss Action")
            let deliveryId = userInfo["deliveryId"] as? String
            let broadlogId = userInfo["broadlogId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
                // If you're using  ACPCore v2.3.0 or later, use the line below.
                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
                // Else comment out the above line and uncomment the line below
                // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            ////MORE CODE
        }
        completionHandler()
    }
```

## Implementação do rastreamento aberto {#implement-open-tracking}

É necessário enviar &quot;1&quot; e &quot;2&quot;, pois o usuário deve clicar na notificação para abrir o aplicativo. Se o aplicativo não for iniciado/aberto por meio da notificação local, nenhum evento de rastreamento ocorrerá.

### Para Android {#implement-open-tracking-android}

Para rastrear a abertura, precisamos criar intenção. Os objetos de intenção permitem que o sistema operacional Android chame o método quando determinadas ações forem executadas, nesse caso clicando na notificação para abrir o aplicativo.

Esse código é baseado na implementação do rastreamento de impressões de cliques. Com a intenção definida, agora é necessário enviar informações de rastreamento de volta ao Adobe Campaign. Nesse caso, o Android View([!DNL Activity]) que acionou a notificação será aberto ou trazido para o primeiro plano como resultado do clique por usuário. O objeto intent em [!DNL Activity] contém os dados de notificação que podem ser usados para rastrear aberturas.

MainActivity.java (estende [!DNL Activity])

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
        Map<String, String> notificationData = (Map<String, Object>)data.getSerializableExtra("NOTIFICATION_USER_INFO");
        String deliveryId = (String)notificationData.get("deliveryId");
        String messageId = (String)notificationData.get("broadlogId");
  
  
  
        if (deliveryId != null && messageId != null) {
            HashMap<String, String> contextData = new HashMap<>();
            contextData.put("deliveryId", deliveryId);
            contextData.put("broadlogId", messageId);
  
            //Send Click Tracking since the user did click on the notification
            contextData.put("action", "2");
            // If you're using  ACPCore v1.4.0 or later, use the next line.
            MobileCore.collectMessageInfo(contextData);
            // Else comment out the above line and uncomment the line below
            // MobileCore.trackAction("tracking", contextData);
  
            //Send Open Tracking since the user opened the app
            contextData.put("action", "1");
            // If you're using  ACPCore v1.4.0 or later, use the next line.
            MobileCore.collectMessageInfo(contextData);
            // Else comment out the above line and uncomment the line below
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
  
    // Called when user clicks the local notification or also called from willPresent()
    func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
  
        let userInfo = response.notification.request.content.userInfo
        os_log("App push data %{public}@, in userNotificationCenter:didReceive()", type: .debug, userInfo)
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:
            //This is to handle the Dismiss Action
            let deliveryId = userInfo["deliveryId"] as? String
            let broadlogId = userInfo["broadlogId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
            // If you're using  ACPCore v2.3.0 or later, use the line below.
                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            // Else comment out the above line and uncomment the line below
            // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            //This is to handle the tracking when the app opens
            let deliveryId = userInfo["deliveryId"] as? String
            let broadlogId = userInfo["broadlogId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
               // If you're using  ACPCore v2.3.0 or later, use the line below.
               ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
               ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])
               // Else comment out the above line and uncomment the line below
               // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
               // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])
            }
        }
        completionHandler()
    }
}
```
