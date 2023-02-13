---
title: Como entender a estrutura de payload das notificações por push do Campaign Standard
description: Saiba mais sobre a estrutura do payload recebido em aplicativos móveis
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: a6515795-1006-4f27-bc44-5ae8b8edc018
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '1137'
ht-degree: 5%

---

# Como entender a estrutura de carga das notificações por push {#push-payload}

O Adobe Campaign permite enviar notificações por push personalizadas e segmentadas em dispositivos móveis iOS e Android para aplicativos móveis (aplicativo móvel).

Cada notificação por push recebida em um aplicativo móvel contém algumas informações usadas pelo aplicativo para exibir a notificação por push se uma notificação por push de alerta for enviada e provavelmente também fará mais cálculo, especialmente se uma notificação por push silenciosa for enviada.

Essas informações são recebidas pelo código do aplicativo móvel em um manipulador de evento que indica que uma notificação por push foi recebida. Ao enviar notificações por push do Adobe Campaign Standard, as informações recebidas no aplicativo móvel também podem conter informações específicas do Campaign Standard, que podem ser usadas para aproveitar alguns recursos fornecidos pelo Campaign Standard. Além disso, a carga pode conter dados personalizados que podem ser consumidos pelo aplicativo móvel.

Este documento descreve a estrutura da carga útil recebida em um aplicativo móvel quando uma notificação por push é enviada com êxito para um aplicativo da Adobe Campaign Standard.

>[!NOTE]
>
>A estrutura de payload varia dependendo do tipo de aplicativo móvel (ou seja, aplicativo iOS, aplicativo Android habilitado para FCM).

## Estrutura da carga útil de push {#push-payload-structure}

Esta seção detalha a estrutura de uma carga de amostra para várias plataformas móveis e descreve os principais atributos contidos nela. Essa é a estrutura da carga recebida no código do aplicativo móvel no manipulador de eventos que indica que uma notificação por push foi recebida.

Os atributos de carga e seus valores variam com base nas configurações fornecidas nas opções avançadas da notificação por push. Esta seção também fornece um mapeamento entre essas configurações na interface do usuário do Campaign Standard e os atributos na carga útil para esclarecer como a carga será alterada ao configurar uma opção no Campaign Standard.

### Para aplicativo móvel do iOS {#payload-structure-ios}

**Exemplo de carga enviada do Adobe Campaign para o aplicativo iOS:**

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

**Carga de amostra JSON a ser usada com [Testador APNS iOS](https://pushtry.com/)**

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

A seção mais importante do payload é o dicionário aps, que contém chaves definidas pelo Apple e é usado para determinar como o sistema que recebe a notificação deve alertar o usuário, se for o caso. Esta seção contém chaves predefinidas usadas pelo aplicativo móvel para formular o comportamento da notificação por push.

Detalhes detalhados sobre os atributos nos aplicativos podem ser encontrados nos documentos do desenvolvedor do Apple: [Criação da carga de notificação remota](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html#//apple_ref/doc/uid/TP40008194-CH10-SW1).

### Para aplicativo Android {#payload-structure-android}

**Exemplo de carga enviada do Adobe Campaign para o aplicativo Android**

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

**Carga de amostra JSON para usar [Testador Google FCM](https://pushtry.com/)**

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

Para entender os aspectos de uma carga do android, consulte [Conceitos e opções de mensagens (fcm)](https://firebase.google.com/docs/cloud-messaging/concept-options).

>[!NOTE]
>
>O suporte para mensagens de notificação no payload do Android foi removido em janeiro de 2018 para habilitar a ativação do aplicativo e transmitir o controle para o aplicativo móvel sem precisar que o usuário interaja com o aplicativo.

### Mapeamento entre configurações de Campaign Standard e atributos de carga {#mapping-payload}

| Configuração da campanha | Atributo afetado no iOS | Atributo afetado no Android | Descrição |
|:-:|:-:|:-:|:-:|
| Título da mensagem <br>Corpo da mensagem | alerta → título <br> alerta → corpo | título <br>corpo | Esses dados contêm especificidades da mensagem de alerta.<br>O título e as chaves de corpo fornecem o conteúdo do alerta. |
| Reproduzir um som | som | som | Um som personalizado para reproduzir com o alerta. |
| Valor do selo | emblema | emblema | Um valor inteiro a ser usado para marcar o ícone do aplicativo. |
| Adicionar um deep link | uri | NA | Um deeplink permite trazer os usuários diretamente ao conteúdo localizado dentro do aplicativo (em vez de abrir uma página do navegador da web). |
| Categoria | categoria | categoria | Para exibir ações personalizadas com uma notificação remota. <br>A tecla de categoria ajuda o sistema a exibir as ações dessa categoria como botões na interface de alerta. |
| Campos personalizados | custom_field1, custom_field2 ... | custom_field1, custom_field2 ... | Quaisquer dados personalizados que você deseja enviar para seu aplicativo. |
| URL de conteúdo de mídia avançada (arquivos de imagem, gif, áudio e vídeo)<br>(Aplicável somente para iOS 10 ou superior) | media-attachment-url | NA | URL dos seus arquivos de mídia para adicionar conteúdo avançado à sua notificação. <br>Ao fornecer um valor para esse URL, o sinalizador de conteúdo mutável é enviado automaticamente para o payload. <br> (Aplicável somente para iOS 10 ou superior) |
| Conteúdo variável <br> (Aplicável somente para iOS 10 ou superior) | mutable-content | NA | A extensão do serviço de notificação no aplicativo interceptará todas as notificações remotas com a chave de conteúdo mutável e permitirá manipular/manipular o conteúdo da carga da solicitação, que pode ser usada para personalizar a notificação. Os casos de uso desse recurso incluem o download e a exibição de várias mídias, a descriptografia de quaisquer dados criptografados presentes na carga de push. Mais informações podem ser encontradas em [Modificar a carga de uma notificação remota](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/ModifyingNotifications.html). <br>(Aplicável somente para iOS 10 ou superior) |
| Conteúdo disponível | conteúdo disponível | NA | Selecionar essa opção permite ativar um aplicativo do iOS enquanto ele estiver em segundo plano/suspenso. A ativação implica que o aplicativo é executado em segundo plano e o manipulador de eventos apropriado responsável por receber a carga de dados da notificação por push obtém um controle e pode usar os dados para fazer qualquer cálculo, incluindo, entre outros, a criação de notificações por push personalizadas e a exibição da mesma. Mais informações podem ser encontradas em [Ativar aplicativo com entrega de notificação](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html). |
| URL de conteúdo de mídia avançada (arquivos de imagem)<br>(Aplicável somente para Android) | NA | media-attachment-url | URL dos arquivos de imagem para adicionar conteúdo avançado à sua notificação. |
| NA | _mId<br>_dId | _mId <br>_dId | Valores de broadlogId e deliveryId.<br>Esses atributos são necessários se o aplicativo quiser chamar um postback de rastreamento para rastrear quando a notificação por push foi clicada/aberta. Essas informações são computadas e enviadas internamente pelo servidor de aplicativos sem a intervenção do usuário.<br>Informações sobre postbacks podem ser encontradas neste [página](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback). |

### Como recuperar informações de carga no código de aplicativo móvel {#payload-information}

As informações de carga enviadas pelo servidor de aplicativos são recebidas pelo código do aplicativo móvel em um manipulador de eventos que indica que uma notificação por push foi recebida. Esse evento varia com base na plataforma móvel em andamento e também se baseia em se o aplicativo está sendo executado em primeiro ou segundo plano. A documentação a seguir ajuda a identificar o manipulador de eventos que você deseja manipular com base no seu caso de uso.

* Aplicativos iOS: **Manipular notificações remotas** seção em [Notificações remotas](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/HandlingRemoteNotifications.html).
* Aplicativos Android: [Recebendo mensagens em um aplicativo cliente Android](https://firebase.google.com/docs/cloud-messaging/android/receive)

**Exemplo para o aplicativo móvel do iOS**

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

**Exemplo de aplicativo FCM para dispositivos móveis Android**

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
