---
title: Exibir uma imagem a partir de uma notificação por push do Adobe Campaign Standard
description: Saiba aqui como exibir uma imagem de uma notificação por push do Adobe Campaign em um dispositivo iOS
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 474c8002-4263-4617-9480-6a9b603bde8e
source-git-commit: 7767b39a48502f97e2b3af9d21a3f49b9283ab2e
workflow-type: tm+mt
source-wordcount: '415'
ht-degree: 18%

---

# Adição de imagens e vídeos ao iOS {#image-push}

>[!NOTE]
>
>Este documento se aplica somente ao dispositivo iOS.

Neste documento, saiba como exibir uma imagem de uma notificação por push do Adobe Campaign Standard iOS.

## Etapa 1: configurar notificação por push {#set-up-push}

Os SDKs do Experience Platform oferecem suporte à notificação por push.

Os aplicativos móveis que recebem notificações por push devem ser configurados por um administrador na interface do Adobe Campaign.

Ao configurar o Adobe Campaign e o Adobe Mobile Services, é possível usar os dados do aplicativo móvel para suas campanhas. Para obter mais informações, consulte esta [página](../../administration/using/configuring-a-mobile-application.md).

Para enviar notificações por push com um aplicativo SDK do Experience Cloud, um aplicativo móvel deve ser configurado na interface da Coleção de dados e no Adobe Campaign. Para obter mais informações, consulte esta [página](../../administration/using/configuring-a-mobile-application.md#channel-specific-config).

## Etapa 2: personalizar sua notificação por push no Adobe Campaign {#customize-push}

Para ajustar as notificações por push, o Adobe Campaign permite o acesso a um conjunto de opções avançadas ao projetar uma notificação por push.

1. Criar uma notificação por push. Para obter mais informações, consulte esta [página](../../channels/using/preparing-and-sending-a-push-notification.md).

1. Na página de conteúdo da notificação por push, acesse a **[!UICONTROL Advanced options]** seção.

1. Insira o URL do arquivo na caixa **[!UICONTROL Rich media content URL]** campo.
No iOS 10 ou superior, você pode inserir arquivos de imagem, gif, áudio e vídeo.

   ![](assets/push_notif_advanced_6.png)

1. Visualize e salve a notificação por push.

## Etapa 3: adaptar o código do aplicativo móvel {#mobile-app-code}

Depois de personalizar a notificação por push no Adobe Campaign, é necessário configurar o aplicativo móvel para exibir a imagem nos dispositivos.

>[!NOTE]
>
>Se o aplicativo estiver em Objetive-C, consulte o seguinte [documentação](https://experienceleague.adobe.com/docs/mobile-services/ios/messaging-ios/push-messaging/c-set-up-rich-push-notif-ios.html).

Se o aplicativo estiver em [!DNL Swift], siga as etapas abaixo:

1. Abra o [!DNL Xcode] projeto.

1. No seu [!DNL Xcode] projeto, selecione **[!UICONTROL File]** > **[!UICONTROL New]** > **[!UICONTROL Target]**.

1. Selecione **[!UICONTROL Notification Service Extension]**.

   ![](assets/push_notif_advanced_12.png)

1. Verifique se **NotificationService.swift** classe de arquivo é criada.

1. Edite essa classe e substitua o conteúdo padrão pelo seguinte.
Isso permite que o aplicativo manipule o parâmetro de entrada com o URL da imagem, analise-o, copie-o localmente e depois exiba-o da notificação por push.

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

O dispositivo móvel deve receber a carga a seguir enquanto a notificação é enviada.

O URL da imagem é mapeado com o URL de anexo de mídia principal. Esse é o par chave/valor que você precisa manipular da perspectiva do código do aplicativo para baixar e exibir a imagem.

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

## Etapa 4: testar o envio do push {#test-send-push}

Agora você pode testar a criação do aplicativo e o delivery criado na etapa 2 acima. Para obter mais informações sobre como preparar e enviar sua notificação por push, consulte esta página [página](../../channels/using/preparing-and-sending-a-push-notification.md).

![](assets/push_notif_advanced_34.png)
