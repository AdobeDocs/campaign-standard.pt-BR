---
title: Personalização de uma notificação por push
description: Saiba como personalizar suas notificações por push com várias opções avançadas.
page-status-flag: never-activated
uuid: 8cf74cad-b1ba-4aad-83bd-7289cb22d5f4
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: push-notifications
discoiquuid: dc944c85-2059-46df-b396-676fe3617dd1
context-tags: delivery,mobileAppContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d4ac80810a77c0a6b512b3ed4c925fa0fb8a219c
workflow-type: tm+mt
source-wordcount: '1494'
ht-degree: 0%

---


# Personalização de uma notificação por push{#customizing-a-push-notification}

Para ajustar sua notificação por push, o Adobe Campaign permite que você acesse um conjunto de opções avançadas ao projetar uma notificação por push.

Como um usuário especialista, para configurar aplicativos móveis no Adobe Campaign, consulte a seguinte nota técnica [Entendendo a estrutura](https://helpx.adobe.com/campaign/kb/understanding-campaign-standard-push-notifications-payload-struc.html)de carga das notificações por push do Campaign Standard.

![](assets/push_notif_advanced.png)

**Conteúdo relacionado:**

* [Relatório de notificação por push](../../reporting/using/push-notification-report.md)
* [Envio de uma notificação por push em um fluxo de trabalho](../../automating/using/push-notification-delivery.md)

## Reproduzir um som {#play-a-sound}

A função **[!UICONTROL Play a sound]** dá ao aplicativo a capacidade de reproduzir sons em seu dispositivo com o delivery de uma notificação por push, quando o aplicativo não está em execução.

Um som alertará os usuários sobre uma notificação por push, dando-lhe mais visibilidade. Para incluir um som no aplicativo móvel:

1. Abra a notificação por push e acesse a **[!UICONTROL Advanced options]** seção.
1. No **[!UICONTROL Play a sound]** campo, digite o nome do arquivo de som, sem a extensão, a ser reproduzido pelo dispositivo móvel quando a notificação for recebida.

   Para obter mais informações sobre formatos de mídia suportados, consulte as documentações da [Apple](https://support.apple.com/kb/PH16864?locale=en_US) e do [Android](https://developer.android.com/guide/topics/media/media-formats) .

   ![](assets/push_notif_advanced_7.png)

1. O arquivo de som é reproduzido ao fornecer a notificação se o arquivo estiver definido no pacote do aplicativo móvel. Caso contrário, o som padrão do dispositivo será reproduzido.

O usuário receberá a notificação por push e o som somente se o telefone não estiver com áudio.

## Atualizar o valor do selo {#refresh-the-badge-value}

Um selo é usado para exibir diretamente no ícone do aplicativo o número de novas informações não lidas. O valor do selo desaparecerá assim que o usuário abrir ou ler o novo conteúdo do aplicativo.

Quando uma notificação é recebida em um dispositivo, ela pode atualizar ou adicionar um valor de crachá para o aplicativo relacionado. Para enviar um valor de crachá do lado do servidor:

1. Abra a notificação por push e acesse a **[!UICONTROL Advanced options]** seção.
1. O valor do selo deve ser um número inteiro e pode ser atualizado de diferentes maneiras:

   * Para atualizar o crachá, digite 0 no **[!UICONTROL Value of the badge]** campo. Isso removerá o selo do ícone do aplicativo.
   * Para adicionar um valor de crachá, insira qualquer número no **[!UICONTROL Value of the badge]** campo. Esse número aparecerá automaticamente no crachá assim que o usuário receber a notificação por push.
   * Se o campo estiver vazio ou não contiver um número inteiro, o valor do selo não será alterado.
   Aqui, inserimos 1 no **[!UICONTROL Value of the badge]** campo para informar aos usuários que eles têm novas informações em seus aplicativos.

   ![](assets/push_notif_advanced_8.png)

1. Depois de enviar sua mensagem, os usuários receberão a notificação por push e seu aplicativo exibirá automaticamente o novo valor do crachá.

   ![](assets/push_notif_advanced_1.png)

## Adicionar um deep link {#add-a-deeplink}

Um deep link permite que você traga os usuários diretamente para o conteúdo localizado dentro do aplicativo (em vez de abrir uma página do navegador da Web).

Um deep link pode incluir dados de personalização para uma experiência personalizada no aplicativo. Por exemplo, os nomes dos primeiros recipient são automaticamente preenchidos na página para a qual o aplicativo os direciona.

Para adicionar um deep link em uma notificação por push:

1. Abra a notificação por push e acesse a **[!UICONTROL Advanced options]** seção.
1. Digite o link no **[!UICONTROL Add a deeplink]** campo.

   ![](assets/push_notif_advanced_3.png)

1. Depois de enviar sua mensagem, os usuários receberão a notificação por push e acessarão a página específica do aplicativo interagindo com a notificação, por exemplo, tocando ou clicando no botão de ação chamada.

   ![](assets/push_notif_advanced_4.png)

## Definir uma ação {#define-an-action}

Você pode adicionar uma ID de categoria se disponível no aplicativo móvel e, em seguida, exibir os botões de ação. Essas notificações fornecem ao usuário uma maneira mais rápida de executar tarefas diferentes em resposta a uma notificação sem abrir ou navegar no aplicativo.

A caixa de diálogo exibida no telefone do usuário requer uma decisão para prosseguir. Quando o usuário seleciona uma das ações, o sistema notifica o aplicativo para que ele possa executar qualquer tarefa associada.

Para adicionar uma categoria em uma notificação por push:

1. Abra a notificação por push e acesse a **[!UICONTROL Advanced options]** seção.
1. Insira um nome de categoria predefinido no **[!UICONTROL Category]** campo para exibir botões acionáveis quando a notificação por push for recebida.

   O desenvolvedor do aplicativo móvel deve definir a ID da categoria e o comportamento esperado dos botões no aplicativo. Para obter mais informações, consulte a documentação [do](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/SupportingNotificationsinYourApp.html) Apple Developer (seção **Configuração de Categoria e Notificações** acionáveis) ou a documentação [do](https://developer.android.com/guide/topics/ui/notifiers/notifications.html)Android Developer.

   ![](assets/push_notif_advanced_9.png)

1. Depois de enviar sua notificação por push, os usuários a recebem e precisam agir com os botões acionáveis configurados anteriormente.

   ![](assets/push_notif_actionable_buttons.png)

Dependendo da ação do usuário, o aplicativo será notificado para que possa executar qualquer tarefa associada.

## Adicionar uma data de expiração {#add-expiration-date}

A definição de uma data de expiração para sua notificação por push permite definir uma data de expiração específica na qual a mensagem não será mais enviada pela Apple ([APNS](https://developer.apple.com/documentation/usernotifications/setting_up_a_remote_notification_server/sending_notification_requests_to_apns)) ou Android ([FCM](https://firebase.google.com/docs/cloud-messaging/concept-options)).

Para adicionar uma data de expiração à sua notificação por push:

1. Check the **[!UICONTROL Expire message]** option.

   >[!NOTE]
   >
   >Ao selecionar a **[!UICONTROL Expire message]** opção, a duração é automaticamente definida como 0. Se você não alterar o valor, tanto o APNS quanto o FCM tentarão enviar a mensagem imediatamente. Se falhar, a mensagem não será reenviada.

1. No **[!UICONTROL Duration]** campo, selecione a validade da sua notificação por push.

   ![](assets/push_expiration.png)

1. Depois de enviar sua notificação por push, se o usuário não a recebeu imediatamente devido ao telefone não estar ligado ou não ter um sinal, o push ainda será enviado dentro do período de validade.

Observe que se a notificação por push não tiver sido enviada antes da data de expiração, ela será descartada.

## Adicionar campos personalizados {#add-custom-fields}

Campos personalizados permitem que você passe dados personalizados na carga na forma de um par de valores chave. Essa opção pode ser usada para passar dados adicionais para o aplicativo além das chaves predefinidas.

Para fazer isso:

1. Abra a notificação por push e acesse a **[!UICONTROL Advanced options]** seção.
1. Na **[!UICONTROL Custom fields]** categoria, clique no **[!UICONTROL Add an element]** botão.
1. Insira **[!UICONTROL Keys]** e depois o **[!UICONTROL Values]** associado a cada chave.

   ![](assets/push_notif_advanced_10.png)

1. O manuseio e a finalidade dos campos personalizados dependem totalmente do aplicativo móvel. Na notificação por push abaixo, campos personalizados foram usados pelo aplicativo para exibir rótulos de botão para a notificação por push.

   ![](assets/push_notif_actionable_buttons.png)

## Adicionar conteúdo de mídia avançada {#add-rich-media-content}

O conteúdo de mídia avançada permite que você tenha um melhor envolvimento do usuário, o que significa que o usuário terá mais tendência a abrir sua notificação por push.

Você pode incluir um arquivo de imagem, gif, áudio ou vídeo que será reproduzido ou exibido na própria notificação. Os usuários do aplicativo não precisarão abrir o aplicativo para visualizá-lo.

Para incluir mídia avançada na notificação por push:

1. Abra a notificação por push e acesse a **[!UICONTROL Advanced options]** seção.
1. Digite o URL do arquivo no **[!UICONTROL Rich media content URL]** campo para cada formato: iOS e Android.

   No iOS 10 ou superior, você pode inserir arquivos de imagem, gif, áudio e vídeo. Para versões anteriores do iOS, a notificação por push será exibida sem conteúdo avançado. Para obter etapas detalhadas sobre como exibir uma imagem de uma notificação por push de Adobe Campaign em um dispositivo iOS, consulte esta [página](https://helpx.adobe.com/campaign/kb/display-image-push.html).

   Para Android, você só pode incluir imagens.

   ![](assets/push_notif_advanced_6.png)

1. Depois de enviar sua mensagem, o usuário receberá sua notificação por push e poderá visualização no conteúdo de mídia avançada.

   ![](assets/push_notif_advanced_2.png)

## Alterar o comportamento de notificação do iOS {#change-the-notification-behavior-for-ios}

![](assets/push_notif_advanced_5.png)

Para iOS 10 ou superior, duas opções adicionais estão disponíveis na **[!UICONTROL Advanced options]** seção de notificações por push: **[!UICONTROL Mutable content]** e **[!UICONTROL Content available]**.

Quando a **[!UICONTROL Mutable content]** opção estiver marcada e/ou um URL de conteúdo de mídia avançada for adicionado, o sinalizador de conteúdo mutável será enviado na carga de push e permitirá que o conteúdo da notificação por push seja modificado por uma extensão de aplicativo de serviço de notificação fornecida no SDK do iOS. For more on this, refer to [Apple developer documentation](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/ModifyingNotifications.html).

Em seguida, você pode aproveitar as extensões do aplicativo móvel para modificar ainda mais o conteúdo ou a apresentação das notificações por push recebidas enviadas do Adobe Campaign. Por exemplo, os usuários podem aproveitar essa opção para:

* Descriptografar dados que foram entregues em um formato criptografado
* Baixar imagens ou outros arquivos de mídia e adicioná-los como anexos a uma notificação
* Alterar o texto do corpo ou do título de uma notificação
* Adicionar um identificador de thread a uma notificação

Quando **[!UICONTROL Content available]** estiver marcado, o sinalizador de conteúdo disponível será enviado na carga de push para garantir que o aplicativo seja acordado assim que receber a notificação por push, o que significa que o aplicativo poderá acessar os dados da carga. Isso funciona mesmo se o aplicativo estiver sendo executado em segundo plano e sem precisar de nenhuma interação do usuário (por exemplo, ao tocar na notificação por push), no entanto, isso não se aplica se o aplicativo não estiver em execução. For more on this, refer to the [Apple developer documentation](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html).

## Alterar o comportamento de notificação para Android {#change-the-notification-behavior-for-android}

Para Android, você pode inserir o URL do arquivo no campo URL **do conteúdo de mídia** avançada. Enquanto com a versão iOS, para Android, você pode incluir apenas imagens e não arquivos gif, áudio ou vídeo.

A **[!UICONTROL High priority]** caixa de seleção permite configurar uma prioridade alta ou normal para suas notificações por push. Para obter mais informações sobre a prioridade da mensagem, consulte a documentação [do desenvolvedor do](https://firebase.google.com/docs/cloud-messaging/concept-options#setting-the-priority-of-a-message)Google.

![](assets/push_notif_advanced_11.png)

