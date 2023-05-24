---
title: Publicação de um evento transacional
description: Saiba como visualizar, publicar, cancelar a publicação e excluir uma configuração de evento transacional.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: 6bcd8dcd-d710-4ca3-937d-bf4339f36069
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 6%

---

# Publicação de um evento transacional {#publishing-transactional-event}

Uma vez [configuração](../../channels/using/configuring-transactional-event.md) estiver concluído, o evento estará pronto para ser publicado. As etapas para visualizar, publicar, cancelar a publicação e excluir um evento são descritas abaixo.

>[!IMPORTANT]
>
>Somente [Administradores funcionais](../../administration/using/users-management.md#functional-administrators) <!--being part of the **[!UICONTROL All]** [organizational unit](../../administration/using/organizational-units.md) -->Ter os direitos apropriados para publicar configurações de evento.

Um gráfico que ilustra todo o processo de publicação de mensagens transacionais, incluindo a publicação e o cancelamento da publicação de configurações de eventos, está disponível em [nesta seção](../../channels/using/publishing-transactional-message.md).

Quando a publicação estiver concluída:
* A mensagem transacional correspondente é criada automaticamente. Consulte [Edição de mensagens transacionais](../../channels/using/editing-transactional-message.md).
* A API que será usada pelo desenvolvedor do site é implantada e os eventos transacionais agora podem ser enviados. Consulte [Integrar o acionamento de eventos](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger).

## Pré-visualizar e publicar um evento {#previewing-and-publishing-the-event}

Antes de poder usar o evento, você deve visualizá-lo e publicá-lo.

1. Clique em **[!UICONTROL API preview]** botão para ver uma simulação da API REST que será usada pelo desenvolvedor do site antes de ser publicada.

   Depois que o evento é publicado, esse botão também permite que você veja uma pré-visualização da API em produção. Consulte [Integrar o acionamento de eventos](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger).

   ![](assets/message-center_api_preview.png)

   >[!NOTE]
   >
   >A API REST varia de acordo com o canal selecionado e o targeting dimension selecionado. Para obter mais informações sobre as várias configurações, consulte [nesta seção](../../channels/using/configuring-transactional-event.md#transactional-event-specific-configurations).

1. Clique em **[!UICONTROL Publish]** para iniciar a publicação.

   ![](assets/message-center_pub.png)

   A API que será usada pelo desenvolvedor do site é implantada e os eventos transacionais agora podem ser enviados.

1. Você pode exibir os logs de publicação na guia correspondente.

   ![](assets/message-center_logs.png)

   >[!IMPORTANT]
   >
   >Toda vez que você modificar o evento, deverá clicar em **[!UICONTROL Publish]** novamente para gerar a API REST atualizada que será usada pelo desenvolvedor do site.

   Depois que o evento for publicado, uma [mensagem transacional](../../channels/using/editing-transactional-message.md) vinculado ao novo evento é criado automaticamente.

1. Você pode acessar diretamente essa mensagem transacional pelo link localizado na área à esquerda.

   ![](assets/message-center_messagegeneration.png)

   >[!NOTE]
   >
   >Para que o evento acione o envio de uma mensagem transacional, você deve modificar e publicar a mensagem que acabou de ser criada. Consulte [Edição](../../channels/using/editing-transactional-message.md) e [Publicação de mensagem transacional](../../channels/using/publishing-transactional-message.md) seções. Também é necessário [integrar este evento de acionador](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger) no seu site.

1. Depois que o Adobe Campaign começar a receber eventos relacionados a essa configuração de evento, você poderá clicar no link **[!UICONTROL Latest transactional events]** no link **[!UICONTROL History]** para acessar os eventos mais recentes enviados pelo seu serviço de terceiros e processados pela Adobe Campaign.

![](assets/message-center_latest-events.png)

Os eventos (no formato JSON) são listados do mais recente para o mais antigo. Essa lista permite verificar dados, como o conteúdo ou o status de um evento, para fins de controle e depuração.

## Desfazer a publicação de um evento {#unpublishing-an-event}

A variável **[!UICONTROL Unpublish]** permite cancelar a publicação do evento, o que exclui da API REST o recurso correspondente ao evento criado anteriormente.

Agora, mesmo que o evento seja acionado pelo seu site, as mensagens correspondentes não serão mais enviadas e não serão armazenadas no banco de dados.

![](assets/message-center_unpublish.png)

>[!NOTE]
>
>Se você já tiver publicado a mensagem transacional correspondente, a publicação da mensagem transacional também será cancelada. Consulte [Cancelamento de publicação de uma mensagem transacional](../../channels/using/publishing-transactional-message.md#unpublishing-a-transactional-message).

Clique em **[!UICONTROL Publish]** botão para gerar uma nova API REST.

<!--## Transactional messaging publication process {#transactional-messaging-pub-process}

The chart below illustrates the transactional messaging publication process.

![](assets/message-center_pub-process.png)

For more on publishing, pausing and unpublishing a transactional message, see [this section](../../channels/using/publishing-transactional-message.md).-->

## Excluir um evento {#deleting-an-event}

Quando a publicação de um evento for desfeita ou se um evento ainda não tiver sido publicado, você poderá excluí-lo da lista de configuração do evento. Para fazer isso:

1. Clique em **Adobe** no canto superior esquerdo e selecione **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**.
1. Passe o mouse sobre a configuração de evento de sua escolha e selecione o **[!UICONTROL Delete element]** botão.

   ![](assets/message-center_delete-button.png)

   >[!NOTE]
   >
   >Verifique se a configuração do evento tem o **[!UICONTROL Draft]** status, caso contrário, você não poderá excluí-lo. A variável **[!UICONTROL Draft]** status se aplica a um evento que ainda não foi publicado ou que foi [não publicado](#unpublishing-an-event).

1. Clique no botão **[!UICONTROL Confirm]**.

   ![](assets/message-center_delete-confirm.png)

>[!IMPORTANT]
>
>A exclusão de uma configuração de evento que foi publicada e já usada também excluirá as mensagens transacionais correspondentes e seus logs de rastreamento e envio.
