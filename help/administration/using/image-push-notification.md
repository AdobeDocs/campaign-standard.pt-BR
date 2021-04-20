---
solution: Campaign Standard
product: campaign
title: Exibir uma imagem a partir de uma notificação por push do Adobe Campaign Standard
description: Saiba aqui como exibir uma imagem de uma notificação por push do Adobe Campaign em um dispositivo iOS.
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
source-wordcount: '432'
ht-degree: 20%

---


# Adicionar imagens e vídeos ao iOS {#image-push}

>[!NOTE]
>
>Este documento se aplica somente ao dispositivo iOS.

Neste documento, saiba como exibir uma imagem de uma notificação por push do Adobe Campaign Standard iOS.

## Etapa 1: Configurar notificação por push {#set-up-push}

A notificação por push é compatível com SDKs do Experience Platform.

Os aplicativos móveis que recebem notificações por push devem ser configurados por um administrador na interface da Adobe Campaign.

Ao configurar o Adobe Campaign e o Adobe Mobile Services, você poderá usar os dados do seu aplicativo móvel para suas campanhas. Para obter mais informações, consulte esta [página](https://helpx.adobe.com/br/campaign/kb/configuring-app-sdk.html).

Para enviar notificações por push com um aplicativo SDK do Experience Cloud, um aplicativo para dispositivos móveis deve ser configurado no Adobe Experience Platform Launch e ser configurado no Adobe Campaign. Para obter mais informações, consulte esta [página](https://helpx.adobe.com/br/campaign/kb/configuring-app-sdk.html#ChannelspecificapplicationconfigurationinAdobeCampaign).

## Etapa 2: Personalizar sua notificação por push no Adobe Campaign {#customize-push}

Para ajustar as notificações por push, o Adobe Campaign permite o acesso a um conjunto de opções avançadas ao projetar uma notificação por push.

1. Criar uma notificação por push. Para obter mais informações, consulte esta [página](../../channels/using/preparing-and-sending-a-push-notification.md).

1. Na página de conteúdo da notificação por push, acesse a seção **[!UICONTROL Advanced options]** .

1. Insira o URL do arquivo no campo **[!UICONTROL Rich media content URL]** .
No iOS 10 ou superior, você pode inserir arquivos de imagem, gif, áudio e vídeo.

   ![](assets/push_notif_advanced_6.png)

1. Visualize e salve sua notificação por push.

## Etapa 3: Adapte o código do aplicativo móvel {#mobile-app-code}

Após personalizar sua notificação por push no Adobe Campaign, é necessário configurar seu aplicativo móvel para exibir a imagem em dispositivos.

>[!NOTE]
>
>Se seu aplicativo estiver em Objetive-C, consulte a seguinte [documentação](https://docs.adobe.com/content/help/en/mobile-services/ios/messaging-ios/push-messaging/c-set-up-rich-push-notif-ios.html).

Se o aplicativo estiver em [!DNL Swift], siga as etapas abaixo:

1. Abra o projeto [!DNL Xcode].

1. No projeto [!DNL Xcode], selecione **[!UICONTROL File]** > **[!UICONTROL New]** > **[!UICONTROL Target]**.

1. Selecione **[!UICONTROL Notification Service Extension]**.

   ![](assets/push_notif_advanced_12.png)

1. Verifique se a classe de arquivo **NotificationService.swift** foi criada.

1. Edite essa classe e substitua o conteúdo padrão pelo seguinte.
Isso permite que o aplicativo manipule o parâmetro de entrada com o URL da imagem, analise-o, copie-o localmente e, em seguida, exiba-o da notificação por push.

   ```
   import UserNotifications
   
   class NotificationService: UNNotificationServiceExtension {
   
   var contentHandler: ((UNNotificationContent) -> Void)?
   var bestAttemptContent: UNMutableNotificationContent?
   
   override func didReceive(_ request: UNNotificationRequest, withContentHandler contentHandler: @escaping (UNNotificationContent) -> Void) {
       self.contentHandler = contentHandler
       bestAttemptContent = (request.content.mutableCopy() as? UNMutableNotificationContent)
   
       if let bestAttemptContent = bestAttemptContent {
           var urlString:String? = nil
           if let urlImageString = request.content.userInfo["media-attachment-url"] as? String {
               urlString = urlImageString
           }
   
           if urlString != nil, let fileUrl = URL(string: urlString!) {
               print("fileUrl: \(fileUrl)")
   
               // Download the attachment
               URLSession.shared.downloadTask(with: fileUrl) { (location, response, error) in
                   if let location = location {
                       // Move temporary file to remove .tmp extension
                       if (error == nil) {
                           let tmpDirectory = NSTemporaryDirectory()
                           let tmpFile = "file://".appending(tmpDirectory).appending(fileUrl.lastPathComponent)
                           let tmpUrl = URL(string: tmpFile)!
                           try! FileManager.default.moveItem(at: location, to: tmpUrl)
   
                           // Add the attachment to the notification content
                           if let attachment = try? UNNotificationAttachment(identifier: fileUrl.lastPathComponent, url: tmpUrl) {
                               bestAttemptContent.attachments = [attachment]
                               }
                       }
                       if(error != nil) {
                           print("Failed to download attachment: \(error.debugDescription)")
                       }
                   }
                   // Serve the notification content
                   contentHandler(bestAttemptContent)
               }.resume()
           }
       }
   }
   
   override func serviceExtensionTimeWillExpire() {
       // Called just before the extension will be terminated by the system.
       // Use this as an opportunity to deliver your "best attempt" at modified content, otherwise the original push payload will be used.
       if let contentHandler = contentHandler, let bestAttemptContent = bestAttemptContent {
           contentHandler(bestAttemptContent)
       }
   }
   
   }
   ```

O celular deve receber a seguinte carga enquanto a notificação é enviada.

O URL da imagem é mapeado com a mídia-attachment-url principal. Esse é o par chave/valor que você precisa lidar com a perspectiva do código do aplicativo para baixar e exibir a imagem.

```
userInfo: [AnyHashable("media-attachment-url"): https://pbs.twimg.com/profile_images/876737835314950144/zPTs9b7o.jpg, AnyHashable("_dId"): 1de3ef93, AnyHashable("_mId"): h280a5, AnyHashable("aps"): {
 
    alert =     {
 
        body = "Message Body here";
 
        title = "This a push from Campaign";
 
    };
 
    badge = 1;
 
    "mutable-content" = 1;
 
}]
```

## Etapa 4: Teste o envio do push {#test-send-push}

Agora é possível testar a criação do aplicativo e o delivery criado na etapa 2 acima. Para obter mais informações sobre como preparar e enviar a notificação por push, consulte esta [página](../../channels/using/preparing-and-sending-a-push-notification.md).

![](assets/push_notif_advanced_34.png)

