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
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '1494'
ht-degree: 98%

---


# Personalização de uma notificação por push{#customizing-a-push-notification}

Para ajustar as notificações por push, o Adobe Campaign permite o acesso a um conjunto de opções avançadas ao projetar uma notificação por push.

Como um usuário especializado, para configurar aplicativos móveis no Adobe Campaign, consulte a seguinte nota técnica [Como entender a estrutura de payload das notificações por push do Campaign Standard](https://helpx.adobe.com/br/campaign/kb/understanding-campaign-standard-push-notifications-payload-struc.html).

![](assets/push_notif_advanced.png)

**Conteúdo relacionado:**

* [Relatório de notificação por push](../../reporting/using/push-notification-report.md)
* [Enviar uma notificação por push em um workflow](../../automating/using/push-notification-delivery.md)

## Reproduzir um som {#play-a-sound}

A função **[!UICONTROL Play a sound]** dá ao aplicativo a capacidade de reproduzir sons em seu dispositivo com a entrega de uma notificação por push quando o aplicativo não está em execução.

Um som alertará os usuários sobre uma notificação por push, dando mais visibilidade a ela. Para incluir um som no seu aplicativo móvel:

1. Abra a notificação por push e acesse a seção **[!UICONTROL Advanced options]**.
1. No campo **[!UICONTROL Play a sound]**, digite o nome do arquivo de som, sem a extensão, que será reproduzido pelo dispositivo móvel quando a notificação for recebida.

   Para obter mais informações sobre formatos de mídia compatíveis, consulte as documentações da [Apple](https://support.apple.com/kb/PH16864?locale=en_US) e do [Android](https://developer.android.com/guide/topics/media/media-formats).

   ![](assets/push_notif_advanced_7.png)

1. O arquivo de som será reproduzido ao fornecer a notificação se estiver definido no pacote desse aplicativo móvel. Caso contrário, o som padrão do dispositivo será reproduzido.

O usuário receberá a notificação por push e o som somente se o telefone não estiver com a função mudo ativada.

## Atualizar o valor do selo {#refresh-the-badge-value}

Um selo é usado para exibir diretamente no ícone do aplicativo o número de novas informações não lidas. O valor do selo desaparecerá assim que o usuário abrir ou ler o novo conteúdo do aplicativo.

Quando uma notificação é recebida em um dispositivo, ela pode atualizar ou adicionar um valor de selo para o aplicativo relacionado. Para enviar um valor de selo no lado do servidor:

1. Abra a notificação por push e acesse a seção **[!UICONTROL Advanced options]**.
1. O valor do selo deve ser um número inteiro e pode ser atualizado de diferentes maneiras:

   * Para atualizar o selo, insira 0 no campo **[!UICONTROL Value of the badge]**. Isso removerá o selo do ícone do aplicativo.
   * Para adicionar um valor de selo, insira qualquer número no campo **[!UICONTROL Value of the badge]**. Esse número aparecerá automaticamente no selo assim que o usuário receber a notificação por push.
   * Se o campo estiver vazio ou não contiver um número inteiro, o valor do selo não será alterado.

   Aqui, inserimos 1 no campo **[!UICONTROL Value of the badge]** para informar aos usuários que eles têm novas informações em seus aplicativos.

   ![](assets/push_notif_advanced_8.png)

1. Após o envio da sua mensagem, os usuários receberão a notificação por push, e seu aplicativo exibirá automaticamente o novo valor do selo.

   ![](assets/push_notif_advanced_1.png)

## Adicionar um deep link {#add-a-deeplink}

Um deeplink permite trazer os usuários diretamente ao conteúdo localizado dentro do aplicativo (em vez de abrir uma página do navegador da web).

Um deeplink pode incluir dados de personalização para uma experiência personalizada no aplicativo. Por exemplo, os nomes dos recipients são automaticamente preenchidos na página para a qual o aplicativo os direciona.

Para adicionar um deeplink em uma notificação por push:

1. Abra a notificação por push e acesse a seção **[!UICONTROL Advanced options]**.
1. Insira o link no campo **[!UICONTROL Add a deeplink]**.

   ![](assets/push_notif_advanced_3.png)

1. Após o envio da mensagem, os usuários receberão a notificação por push e acessarão a página específica do aplicativo por meio da interação com essa notificação, por exemplo, tocando ou clicando no botão de ação.

   ![](assets/push_notif_advanced_4.png)

## Definir uma ação {#define-an-action}

Você pode adicionar uma ID de categoria, se disponível, no aplicativo móvel e, em seguida, exibir botões de ação. Essas notificações fornecem ao usuário uma maneira mais rápida de realizar tarefas diferentes em resposta a uma notificação sem abrir o aplicativo ou navegar até ele.

A caixa de diálogo exibida no telefone do usuário requer uma decisão para prosseguir. Quando o usuário seleciona uma das ações, o sistema notifica o aplicativo para que ele possa realizar qualquer tarefa associada.

Para adicionar uma categoria em uma notificação por push:

1. Abra a notificação por push e acesse a seção **[!UICONTROL Advanced options]**.
1. Insira um nome de categoria predefinido no campo **[!UICONTROL Category]** para exibir botões acionáveis quando a notificação por push for recebida.

   O desenvolvedor do aplicativo móvel deve definir a ID de categoria e o comportamento esperado dos botões no aplicativo. Para obter mais informações, consulte a [documentação para desenvolvedores da Apple](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/SupportingNotificationsinYourApp.html) (seção sobre como **Configurar categorias e notificações acionáveis**) ou a [documentação para desenvolvedores do Android](https://developer.android.com/guide/topics/ui/notifiers/notifications.html).

   ![](assets/push_notif_advanced_9.png)

1. Após o envio da sua notificação por push, os usuários a receberão e precisarão agir com os botões de ação anteriormente configurados.

   ![](assets/push_notif_actionable_buttons.png)

Dependendo da ação do usuário, o aplicativo será notificado para que ele possa realizar qualquer tarefa associada.

## Adicionar uma data de expiração {#add-expiration-date}

Definir uma data de expiração para sua notificação por push permite definir uma data de expiração específica na qual a mensagem não será mais enviada pela Apple ([APNS](https://developer.apple.com/documentation/usernotifications/setting_up_a_remote_notification_server/sending_notification_requests_to_apns)) ou pelo Android ([FCM](https://firebase.google.com/docs/cloud-messaging/concept-options)).

Para adicionar uma data de expiração à sua notificação por push:

1. Check the **[!UICONTROL Expire message]** option: by selecting the **[!UICONTROL Expire message]** option, the duration is automatically set to 0. Se você não alterar o valor, tanto o APNS quanto o FCM tentarão enviar a mensagem imediatamente. Se falhar, a mensagem não será reenviada.

1. No campo **[!UICONTROL Duration]**, selecione a validade da sua notificação por push.

   ![](assets/push_expiration.png)

1. Após o envio da notificação por push, se o usuário não a tiver recebido imediatamente porque o telefone não estava ligado ou estava sem sinal, o push ainda será enviado dentro do período de expiração.

Observe que, se a notificação por push não tiver sido enviada antes da data de expiração, ela será descartada.

## Adicionar campos personalizados {#add-custom-fields}

Campos personalizados permitem transmitir dados personalizados no payload na forma de um par de chave/valor. Essa opção pode ser usada para transmitir dados adicionais ao aplicativo além das chaves predefinidas.

Para fazer isso:

1. Abra a notificação por push e acesse a seção **[!UICONTROL Advanced options]**.
1. Na categoria **[!UICONTROL Custom fields]**, clique no botão **[!UICONTROL Add an element]**.
1. Insira **[!UICONTROL Keys]** e depois o **[!UICONTROL Values]** associado a cada chave.

   ![](assets/push_notif_advanced_10.png)

1. O manuseio e a finalidade de campos personalizados dependem totalmente do aplicativo móvel. Na notificação por push abaixo, campos personalizados foram usados pelo aplicativo para exibir rótulos de botão para a notificação por push.

   ![](assets/push_notif_actionable_buttons.png)

## Adicionar conteúdo de mídia avançada {#add-rich-media-content}

Um conteúdo de mídia avançada permite ter um melhor envolvimento do usuário, o que significa que ele terá mais tendência a abrir a notificação por push.

É possível incluir um arquivo de imagem, gif, áudio ou vídeo, que será reproduzido ou exibido na própria notificação. Os usuários do aplicativo não precisarão abrir o aplicativo para visualizá-lo.

Para incluir mídia avançada na notificação por push:

1. Abra a notificação por push e acesse a seção **[!UICONTROL Advanced options]**.
1. Insira o URL do arquivo no campo **[!UICONTROL Rich media content URL]** para cada formato: iOS e Android.

   No iOS 10 ou superior, você pode inserir arquivos de imagem, gif, áudio e vídeo. Para versões anteriores do iOS, a notificação por push será exibida sem conteúdo avançado. Para obter etapas detalhadas sobre como exibir uma imagem de uma notificação por push do Adobe Campaign em um dispositivo iOS, consulte esta [página](https://helpx.adobe.com/br/campaign/kb/display-image-push.html).

   Para o Android, apenas é possível incluir imagens.

   ![](assets/push_notif_advanced_6.png)

1. Após o envio da sua mensagem, o usuário receberá a notificação por push e poderá visualizar o conteúdo de mídia avançada.

   ![](assets/push_notif_advanced_2.png)

## Alterar o comportamento de notificação do iOS {#change-the-notification-behavior-for-ios}

![](assets/push_notif_advanced_5.png)

Para iOS 10 ou versão superior, duas opções adicionais estão disponíveis na seção **[!UICONTROL Advanced options]** de notificações por push: **[!UICONTROL Mutable content]** e **[!UICONTROL Content available]**.

Quando a opção **[!UICONTROL Mutable content]** estiver marcada e/ou um URL de conteúdo de mídia avançada for adicionado, o sinalizador de conteúdo mutável será enviado no payload por push e permitirá que o conteúdo da notificação por push seja modificado por uma extensão de aplicativo de serviço de notificação fornecida no SDK do iOS. Para saber mais, consulte a [documentação para desenvolvedores da Apple](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/ModifyingNotifications.html).

Em seguida, você poderá otimizar suas extensões de aplicativo móvel para modificar ainda mais o conteúdo ou a apresentação das notificações por push de entrada enviadas pelo Adobe Campaign. Por exemplo, os usuários podem otimizar essa opção para:

* Descriptografar dados que foram entregues em formato criptografado
* Baixar imagens ou outros arquivos de mídia e adicioná-los como anexos a uma notificação
* Alterar o texto do corpo ou do título de uma notificação
* Adicionar um identificador de thread a uma notificação

Quando a opção **[!UICONTROL Content available]** estiver marcada, o sinalizador de conteúdo disponível será enviado no payload por push para garantir que o aplicativo seja reativado assim que receber a notificação por push, o que significa que o aplicativo poderá acessar os dados do payload. Essa opção funcionará mesmo se o aplicativo estiver sendo executado em segundo plano e sem precisar de nenhuma interação do usuário (por exemplo, ao tocar na notificação por push). No entanto, não será aplicável se o aplicativo não estiver em execução. Para obter mais informações, consulte a [documentação para desenvolvedores da Apple](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html).

## Alterar o comportamento de notificação para o Android {#change-the-notification-behavior-for-android}

Para o Android, você pode inserir o URL do arquivo no campo **URL do conteúdo de mídia avançada**. Diferentemente da versão para iOS, para o Android, você só pode incluir imagens, e não arquivos gif, de áudio ou de vídeo.

A caixa de seleção **[!UICONTROL High priority]** permite configurar uma prioridade alta ou normal para suas notificações por push. Para obter mais informações sobre a prioridade da mensagem, consulte a [documentação para desenvolvedor do Google](https://firebase.google.com/docs/cloud-messaging/concept-options#setting-the-priority-of-a-message).

![](assets/push_notif_advanced_11.png)
