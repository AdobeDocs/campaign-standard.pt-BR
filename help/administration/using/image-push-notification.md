---
title: Exibir uma imagem a partir de uma notificação por push do Adobe Campaign Standard
description: Saiba como exibir uma imagem de uma notificação por push de Adobe Campaign em um dispositivo iOS.
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
source-git-commit: 6c5cf90211451587537b9a6121430fc4f352384c
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 8%

---


# Adicionar imagens e vídeos ao iOS {#image-push}

>[!NOTE]
>
>Este documento se aplica somente a dispositivos iOS.

Neste documento, saiba como exibir uma imagem de uma notificação por push do iOS Adobe Campaign Standard.

## Etapa 1: Configurar notificação por push {#set-up-push}

A notificação por push é suportada pelos SDKs Experience Platform.

Os aplicativos móveis que recebem notificações por push devem ser configurados por um administrador na interface do Adobe Campaign.

Ao configurar o Adobe Campaign e o Adobe Mobile Services, você poderá usar os dados de seu aplicativo móvel para suas campanhas. Para obter mais informações, consulte esta [página](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

Para enviar notificações por push com um aplicativo Experience Cloud SDK, um aplicativo móvel deve ser configurado no Adobe Experience Platform Launch e configurado no Adobe Campaign. Para obter mais informações, consulte esta [página](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#ChannelspecificapplicationconfigurationinAdobeCampaign).

## Etapa 2: Personalize sua notificação por push no Adobe Campaign {#customize-push}

Para ajustar sua notificação por push, o Adobe Campaign permite que você acesse um conjunto de opções avançadas ao projetar uma notificação por push.

1. Crie uma notificação por push. Para obter mais informações, consulte esta [página](../../channels/using/preparing-and-sending-a-push-notification.md).

1. Na página de conteúdo da notificação por push, acesse a **[!UICONTROL Advanced options]** seção.

1. Insira o URL do arquivo no **[!UICONTROL Rich media content URL]** campo.
No iOS 10 ou superior, você pode inserir arquivos de imagem, gif, áudio e vídeo.

   ![](assets/push_notif_advanced_6.png)

1. Pré-visualização e salve sua notificação por push.

## Etapa 3: Adapte o código do aplicativo móvel {#mobile-app-code}

Depois de personalizar sua notificação por push no Adobe Campaign, é necessário configurar seu aplicativo móvel para exibir a imagem em dispositivos.

>[!NOTE]
>
>Se seu aplicativo estiver no Objetivo C, consulte a seguinte [documentação](https://docs.adobe.com/content/help/en/mobile-services/ios/messaging-ios/push-messaging/c-set-up-rich-push-notif-ios.html).

Se seu aplicativo estiver em [!DNL Swift], siga as etapas abaixo:

1. Abra seu projeto [DNL Xcode] .

1. No projeto [DNL Xcode] , selecione **[!UICONTROL File]** > **[!UICONTROL New]** > **[!UICONTROL Target]**.

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

O dispositivo móvel deve receber a seguinte carga enquanto a notificação é enviada.

O URL da imagem é mapeado com o principal media-attachment-url. Esse é o par de chave/valor que você precisa manipular da perspectiva do código do aplicativo para baixar e exibir a imagem.

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

## Etapa 4: Teste de envio do push {#test-send-push}

Agora você pode testar a criação do aplicativo e do delivery criado na etapa 2 acima. Para obter mais informações sobre como preparar e enviar sua notificação por push, consulte esta [página](../../channels/using/preparing-and-sending-a-push-notification.md).

![](assets/push_notif_advanced_34.png)

