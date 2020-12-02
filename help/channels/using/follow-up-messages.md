---
solution: Campaign Standard
product: campaign
title: Mensagens de acompanhamento
description: Saiba como criar e publicar uma mensagem de acompanhamento.
audience: channels
content-type: reference
topic-tags: transactional-messaging
translation-type: tm+mt
source-git-commit: a0ad969c86a5047f3f967a21fdc2d6040d7d939f
workflow-type: tm+mt
source-wordcount: '722'
ht-degree: 5%

---


# Mensagens de acompanhamento{#follow-up-messages}

Você pode enviar uma mensagem de acompanhamento aos clientes que receberam um mensagen transacional específico. Para fazer isso, é necessário configurar um fluxo de trabalho direcionado ao evento correspondente.

Vamos reutilizar o exemplo descrito na seção [Princípio operacional de mensagens transacionais](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle): um e-mail de abandono de carrinho é enviado para os usuários do site que adicionaram produtos ao carrinho, mas deixaram o site sem precisar fazer compras.

Você deseja enviar um lembrete amigável a todos os clientes que receberam a notificação de abandono do carrinho, mas que não a abriram após três dias.

Cada cliente em questão receberá então uma mensagem de acompanhamento com base nos mesmos dados que foram usados no primeiro email enviado.

## Acessar as mensagens de acompanhamento {#accessing-the-follow-up-messages}

Depois de criar e publicar um evento (o abandono do carrinho como de acordo com [exemplo](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle) acima), o mensagen transacional e a mensagem de acompanhamento correspondentes são criados automaticamente.

As etapas de configuração são apresentadas na seção [Configurar um evento para enviar uma mensagem de acompanhamento](../../administration/using/configuring-transactional-messaging.md#configuring-an-event-to-send-a-follow-up-message).

Para lidar com um evento em um fluxo de trabalho, um template do delivery é necessário. No entanto, ao publicar o evento, o [mensagen transacional](../../channels/using/event-transactional-messages.md) criado não pode ser usado como modelo. Portanto, é necessário criar um template do delivery de acompanhamento específico projetado para suportar esse tipo de evento e ser usado como modelo em um fluxo de trabalho.

Para acessar este modelo:

1. Clique no logotipo **[!UICONTROL Adobe Campaign]**, no canto superior esquerdo.
1. Selecione **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**.
1. Marque a caixa **[!UICONTROL Follow-up messages]** no painel esquerdo.

   ![](assets/message-center_follow-up-search.png)

Somente as mensagens de acompanhamento são exibidas.

>[!NOTE]
>
>Para acessar mensagens transacionais, você deve fazer parte do grupo de segurança **[!UICONTROL Administrators (all units)]**.

## Envio de uma mensagem de acompanhamento {#sending-a-follow-up-message}

Depois de criar o template do delivery de acompanhamento, você pode usá-lo em um fluxo de trabalho para enviar uma mensagem de acompanhamento.

1. Acesse a lista da atividade de marketing e crie um novo fluxo de trabalho.

   Consulte [Criação de um workflow](../../automating/using/building-a-workflow.md#creating-a-workflow).

1. Arraste e solte uma atividade **[!UICONTROL Scheduler]** no seu fluxo de trabalho e abra-a. Defina a frequência de execução como uma vez por dia.

   A atividade do Scheduler é apresentada na seção [Scheduler](../../automating/using/scheduler.md).

1. Arraste e solte uma atividade **[!UICONTROL Query]** no seu fluxo de trabalho e abra-a.

   A atividade do Query é apresentada na seção [Query](../../automating/using/query.md).

1. Para executar o query em um recurso diferente do recurso do perfil, vá para a guia **[!UICONTROL Properties]** da atividade e clique na lista suspensa **[!UICONTROL Resource]**.

   ![](assets/message-center_follow-up-query-properties.png)

   >[!NOTE]
   >
   >Por padrão, a atividade é pré-configurada para procurar perfis.

1. Selecione o evento que deseja público alvo para que você acesse apenas os dados desse evento.

   ![](assets/message-center_follow-up-query-resource.png)

1. Vá para a guia atividade **[!UICONTROL Target]** e arraste e solte o elemento **[!UICONTROL Delivery logs (logs)]** da paleta no espaço de trabalho.

   ![](assets/message-center_follow-up-delivery-logs.png)

   Selecione **[!UICONTROL Exists]** para público alvo de todos os clientes que receberam o email.

   ![](assets/message-center_follow-up-delivery-logs-exists.png)

1. Mova o elemento **[!UICONTROL Tracking logs (tracking)]** da paleta para o espaço de trabalho e selecione **[!UICONTROL Does not exist]** para público alvo de todos os clientes que não abriram o email.

   ![](assets/message-center_follow-up-delivery-and-tracking-logs.png)

1. Arraste e solte o evento direcionado (**abandono do carrinho** neste exemplo) da paleta para o espaço de trabalho. Em seguida, defina uma regra para público alvo de todas as mensagens enviadas três dias atrás.

   ![](assets/message-center_follow-up-created.png)

   Isso significa que todos os recipient que receberam o mensagen transacional três dias antes da execução do fluxo de trabalho e ainda não o abriram são direcionados.

   Clique em **[!UICONTROL Confirm]** para salvar o query.

1. Arraste e solte uma atividade **delivery de e-mail** no seu fluxo de trabalho.

   A atividade delivery de email é apresentada na seção [delivery de email](../../automating/using/email-delivery.md).

   ![](assets/message-center_follow-up-workflow.png)

   Você também pode usar um atividade [SMS](../../automating/using/sms-delivery.md) ou um delivery [do aplicativo móvel](../../automating/using/push-notification-delivery.md). Nesse caso, selecione o canal **[!UICONTROL Mobile (SMS)]** ou **[!UICONTROL Mobile application]** ao criar a configuração do evento. Consulte [Criação de um evento](../../administration/using/configuring-transactional-messaging.md#creating-an-event).

1. Abra a atividade **delivery de e-mail**. No assistente de criação, marque a caixa **[!UICONTROL Follow-up messages]** e selecione o template do delivery de acompanhamento criado após a publicação do evento.

   ![](assets/message-center_follow-up-template.png)

1. No conteúdo da mensagem de acompanhamento, você pode aproveitar o conteúdo do seu evento adicionando campos de personalização.

   ![](assets/message-center_follow-up-content.png)

1. Encontre os campos que você definiu ao criar seu evento selecionando **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**. Consulte [Personalizando um mensagen transacional](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message).

   ![](assets/message-center_follow-up-personalization.png)

   Isso significa que você pode aproveitar o mesmo conteúdo, incluindo dados enriquecidos, que foi usado na primeira vez que o evento foi enviado, para criar um lembrete personalizado.

1. Salve a atividade e o start do fluxo de trabalho.

Quando o fluxo de trabalho for iniciado, todos os clientes que tiverem recebido sua notificação de abandono do carrinho três dias atrás, mas não a tiverem aberto, receberão uma mensagem de acompanhamento com base nos mesmos dados.

>[!NOTE]
>
>Se você selecionou o targeting dimension **[!UICONTROL Profile]** ao criar a configuração do evento, a mensagem de acompanhamento também impulsionará o banco de dados de marketing da Adobe Campaign. Consulte [Mensagens transacionais de perfil](../../channels/using/profile-transactional-messages.md).
