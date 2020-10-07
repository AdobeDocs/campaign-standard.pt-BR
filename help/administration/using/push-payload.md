---
title: Entendendo a estrutura de carga de notificações por push de Campaign Standard
description: Este documento destina-se a descrever a estrutura da carga recebida em aplicativos móveis.
page-status-flag: never-activated
uuid: 961aaeb5-6948-4fd2-b8d7-de4510c10566
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: push-notifications
discoiquuid: 23b4212e-e878-4922-be20-50fb7fa88ae8
context-tags: mobileApp,overview
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '1148'
ht-degree: 4%

---


# Como entender a estrutura de payload das notificações de push do {#push-payload}

A Adobe Campaign permite enviar notificações por push personalizadas e segmentadas em dispositivos móveis iOS e Android para aplicativos móveis (aplicativo móvel).

Cada notificação por push recebida em um aplicativo móvel contém algumas informações que são usadas pelo aplicativo para exibir a notificação por push se uma notificação por push de alerta for enviada e provavelmente também fará mais alguma computação, especialmente se uma notificação por push silenciosa for enviada.

Essas informações são recebidas pelo código do aplicativo móvel em um manipulador de eventos que indica que uma notificação por push foi recebida. Ao enviar notificações por push da Adobe Campaign Standard, as informações recebidas no aplicativo móvel também podem conter informações específicas ao Campaign Standard que podem ser usadas para aproveitar alguns recursos fornecidos pelo Campaign Standard. Além disso, a carga pode conter dados personalizados que podem ser consumidos pelo aplicativo móvel.

Este documento descreve a estrutura da carga recebida em um aplicativo móvel quando uma notificação por push é enviada com êxito para um aplicativo da Adobe Campaign Standard.

>[!NOTE]
>
>A estrutura de carga varia dependendo do tipo de aplicativo móvel (ou seja, aplicativo iOS, aplicativo Android habilitado para FCM).

## Estrutura de carga de push {#push-payload-structure}

Esta seção detalha a estrutura de uma carga de amostra para várias plataformas móveis e descreve os principais atributos contidos nela. Esta é a estrutura da carga recebida no código do aplicativo móvel no manipulador de eventos que indica que uma notificação por push foi recebida.

Os atributos de carga e seus valores variam com base nas configurações fornecidas nas opções avançadas de notificação por push. Esta seção também fornece um mapeamento entre essas configurações na interface do usuário do Campaign Standard e os atributos na carga para esclarecer como a carga será alterada ao configurar uma opção no Campaign Standard.

### Para aplicativos móveis iOS {#payload-structure-ios}

**Amostra de carga enviada do Adobe Campaign para o aplicativo iOS:**

```
{

    "aps":{

            "alert":{

                    "body":"This is the content of my push notification",

                    "title":"Push Notification Title"

            },

            "content-available":1,

            "category":"NEW_MESSAGE_CATEGORY",

            "badge":2,

            "mutable-content":1,

            "sound":"default"

        },

    "custom_field1":"custom_value1",

    "custom_field2":"custom_value2",

    "media-attachment-url":"https://2.img-dpreview.com/files/p/articles/9440145363/Creative_Cloud.jpeg",

    "uri":"https://mydeeplinkurl.com",

    "_dId":"56c4",

    "_mId":"h138a"} 
```

**Carga de amostra JSON a ser usada com o[iOS APNS Tester](https://pushtry.com/)**

```
{

  "aps": {

    "alert": {

      "title": "Push Notification Title",

      "body": "body of push"

    },

    "badge": 33,

    "sound": "default"

  },

  "custom_field1": "custom_value1",

  "uri": "https://mydeeplinkurl.com"

}
```

A seção mais importante da carga é o dicionário aps, que contém as chaves definidas pela Apple e é usado para determinar como o sistema que recebe a notificação deve alertar o usuário, se for o caso. Esta seção contém chaves predefinidas que são usadas pelo aplicativo móvel para formular o comportamento da notificação por push.

Detalhes aprofundados sobre os atributos no aplicativo podem ser encontrados em documentos do desenvolvedor da Apple: [Criando a carga](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html#//apple_ref/doc/uid/TP40008194-CH10-SW1)de notificação remota.

### Para aplicativo Android {#payload-structure-android}

**Amostra de envio de carga do aplicativo Adobe Campaign para Android**

```
{

  "collapseKey": "1476005",

  "priority": "high",

  "data": {

    "_dId": "d57fd6",

    "_mId": "h1685a5",

    "body": "adobe body 123",

    "category": "adobe category 123",

    "custom key 1": "value 1",

    "custom key 2": "test value 2",

    "custom key 3": "foo bar android",

    "media-attachment-url": "http://adobegiphy.com?test=123",

    "sound": "http://testcampaign.instance.com/r/?id=s1685a5,d57fd6,d57ff5",

    "title": "adobe title 123",

    "uri": "http://testcampaign.instance.com/r/?id=d1685a5,d57fd6,d57ff6",

    "badge": 1817

  }

}
```

**Carga de amostra JSON para usar o testador do[Google FCM](https://pushtry.com/)**

```
{

  "to": "<==========ENTER your device token==============>",

  "collapseKey": "1476005",

  "priority": "high",

  "data": {

    "_dId": "d57fd6",

    "_mId": "h1685a5",

    "title": "adobe title 123",

    "body": "adobe body 123",

    "category": "adobe category 123",

    "custom key 1": "value 1",

    "custom key 2": "test value 2",

    "custom key 3": "foo bar android",

    "media-attachment-url": "http://adobegiphy.com?test=123",

    "sound": "http://testcampaign.instance.com/r/?id=s1685a5,d57fd6,d57ff5",

    "uri": "http://testcampaign.instance.com/r/?id=d1685a5,d57fd6,d57ff6",

    "badge": 1817

  }

}
```

A carga contém uma mensagem de dados que inclui todo o conteúdo do delivery de notificação por push, incluindo os pares de chave/valor personalizados, e o aplicativo cliente deve manipular a mensagem para criar e mostrar a notificação por push, se necessário, ou então adicionar qualquer outra lógica comercial.

Para entender os aspectos de uma carga do Android, consulte Conceitos e opções de [mensagens (fcm)](https://firebase.google.com/docs/cloud-messaging/concept-options).

>[!NOTE]
>
>O suporte para mensagens de notificação na carga do Android foi removido a partir de janeiro de 2018 para permitir a ativação do aplicativo e a transmissão do controle para o aplicativo móvel sem a necessidade de interação do usuário com o aplicativo.

### Mapeamento entre configurações de Campaign Standard e atributos de carga {#mapping-payload}

| Configuração da campanha | Atributo afetado no iOS | Atributo afetado no Android | Descrição |
|:-:|:-:|:-:|:-:|
| Título da mensagem Corpo <br>da mensagem | alerta → alerta de título <br> → corpo | título <br>de corpo | Esses dados contêm detalhes específicos da mensagem de alerta.<br>O título e as chaves de corpo fornecem o conteúdo do alerta. |
| Reproduzir um som | som | som | Um som personalizado para reproduzir com o alerta. |
| Valor do crachá | emblema | emblema | Um valor inteiro a ser usado para marcar o ícone do aplicativo. |
| Adicionar um deep link | uri | NA | Um deeplink permite trazer os usuários diretamente ao conteúdo localizado dentro do aplicativo (em vez de abrir uma página do navegador da web). |
| Categoria | categoria | categoria | Para exibir ações personalizadas com uma notificação remota. <br>A tecla categoria ajuda o sistema a exibir as ações para essa categoria como botões na interface de alerta. |
| Campos personalizados | custom_field1, custom_field2 ... | custom_field1, custom_field2 ... | Todos os dados personalizados que você deseja enviar ao seu aplicativo. |
| URL de conteúdo de mídia avançada (arquivos de imagem, gif, áudio e vídeo)<br>(aplicável somente para iOS 10 ou superior) | media-attachment-url | NA | URL dos arquivos de mídia para adicionar conteúdo avançado à sua notificação. <br>Ao fornecer um valor para esse URL, o sinalizador de conteúdo mutável é enviado automaticamente para a carga. <br> (Aplicável somente para iOS 10 ou superior) |
| Conteúdo variável <br> (aplicável somente para iOS 10 ou superior) | mutable-content | NA | A extensão do serviço de notificação no aplicativo interceptará todas as notificações remotas com a chave de conteúdo mutável e permitirá que você manipule/manipule o conteúdo da carga da solicitação, que pode ser usada para personalizar a notificação. Os casos de uso desse recurso incluem baixar e exibir várias mídias, descriptografando quaisquer dados criptografados presentes na carga de push. Mais informações podem ser encontradas em [Modificar a carga de uma Notificação](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/ModifyingNotifications.html)Remota. <br>(Aplicável somente para iOS 10 ou superior) |
| Conteúdo disponível | conteúdo disponível | NA | Selecionar essa opção ativa a ativação de um aplicativo iOS enquanto ele estiver em segundo plano/suspenso. A ativação implica que o aplicativo seja executado em segundo plano e o manipulador de eventos apropriado responsável por receber a carga de dados da notificação por push obtenha um controle e possa usar os dados para fazer qualquer cálculo, incluindo, mas não limitado a, criar notificação por push personalizada e exibir o mesmo. Mais informações podem ser encontradas no [aplicativo de ativação com delivery](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html)de notificação. |
| URL de conteúdo de mídia avançada (arquivos de imagem)<br>(aplicável somente para Android) | NA | media-attachment-url | URL dos arquivos de imagem para adicionar conteúdo avançado à sua notificação. |
| NA | _mId<br>_dId | _mId <br>_dId | Valores de BroadlogId e deliveryId.<br>Esses atributos são necessários se o aplicativo desejar chamar um postback de rastreamento para rastrear quando a notificação por push foi clicada/aberta. Essas informações são computadas e enviadas internamente pelo servidor do aplicativo sem a intervenção do usuário.<br>Informações sobre postbacks podem ser encontradas nesta [página](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#PIIpostback). |

### Como recuperar informações de carga no código do aplicativo móvel {#payload-information}

As informações de carga enviadas pelo servidor do aplicativo são recebidas pelo código do aplicativo móvel em um manipulador de eventos que indica que uma notificação por push foi recebida. Esse evento varia com base na plataforma móvel em que o aplicativo está sendo trabalhado e também se baseia em se o aplicativo está sendo executado em primeiro ou segundo plano. A documentação a seguir o ajudará a identificar o manipulador de eventos que você deseja manipular com base no caso de uso.

* Aplicativos iOS: **Manuseio da seção Notificações** Remotas em Notificações [](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/HandlingRemoteNotifications.html)Remotas.
* Aplicativos Android: [Recebendo mensagens em um aplicativo cliente Android](https://firebase.google.com/docs/cloud-messaging/android/receive)

**Amostra para o aplicativo móvel iOS**

```
 - (void)application:(UIApplication *)application

didReceiveRemoteNotification:(NSDictionary *)userInfo {

    

    NSDictionary *apsDict = [userInfo objectForKey:@"aps"];

    NSDictionary *alertDict = [apsDict objectForKey:@"alert"];

    NSString *title = [alertDict objectForKey:@"title"];

    NSString *body = [alertDict objectForKey:@"body"];

    NSString *category = [apsDict objectForKey:@"category"];

    NSString *deliveryId = userInfo[@"_dId"];

    NSString *broadlogId = userInfo[@"_mId"];

    NSString *mediaAttachmentURL = userInfo[@"media-attachment-url"];

    NSString *deeplinkURL = userInfo[@"uri"];

    NSString *customValue1 = userInfo[@"custom_field1"];   

}
```

**Amostra para o aplicativo FCM do Android Mobile**

```
public void onMessageReceived(RemoteMessage message) {

    Map<String, String> dataMap = message.getData();

     

    String title = dataMap.get("title");

    String body = dataMap.get("body");

    String category = dataMap.get("category");

    String deliveryId = dataMap.get("_dId");

    String broadlogId = dataMap.get("_mId");

    String mediaAttachmentURL = dataMap.get("media-attachment-url");

    String deeplinkURL = dataMap.get("uri");

    String customValue1 = dataMap.get("custom_field1");

}
```
