---
solution: Campaign Standard
product: campaign
title: Envio de uma notificação por push recorrente com um workflow
description: Neste exemplo, uma notificação por push personalizada é enviada todos os primeiros dias do mês às 20 horas para os assinantes do aplicativo móvel, dependendo de seus fusos horários.
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Workflows
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 5%

---


# Envio de uma notificação por push recorrente com um workflow {#sending-a-recurring-push-notification-with-a-workflow}

![](assets/wkf_push_example_1.png)

Neste exemplo, uma notificação por push personalizada é enviada todos os primeiros dias do mês às 20 horas para os assinantes do aplicativo móvel, dependendo de seus fusos horários.

Para criar o workflow, siga estas etapas:

1. A atividade [Scheduler](../../automating/using/scheduler.md) permite iniciar os dias do workflow antes do início do delivery para poder enviar a notificação para cada assinante às 20 horas em qualquer fuso horário:

   * No campo **[!UICONTROL Execution frequency]**, selecione Mensalmente.
   * Selecione 20h no campo **[!UICONTROL Time]**.
   * Escolha em qual dia o delivery será enviado todos os meses.
   * Selecione uma data de início para o workflow, pelo menos um dia antes do início do delivery. Caso contrário, alguns recipients poderão receber a mensagem um dia depois, se a hora selecionada já tiver passado em seus fusos horários.
   * Na guia **[!UICONTROL Execution options]** , selecione em qual fuso horário o workflow começará no campo **[!UICONTROL Time zone]**. Aqui, por exemplo, o workflow começará às 20 horas, hora do Pacífico, uma semana antes do primeiro dia do mês para permitir que algum tempo para os deliveries sejam criados para todos os fusos horários aplicáveis.

   >[!NOTE]
   >
   >Por padrão, o fuso horário selecionado é o definido nas propriedades do fluxo de trabalho (consulte [Criação de um fluxo de trabalho](../../automating/using/building-a-workflow.md)).

   ![](assets/wkf_push_example_5.png)

1. A atividade [Query](../../automating/using/query.md) permite direcionar seus clientes de VIP entre 20 e 30 anos, que assinaram seu aplicativo móvel e que não abriram o email enviado:

   * Selecione um público-alvo (seus clientes VIP) e filtre por sua idade.
   * Arraste e solte o elemento **Subscriptions to an application** no espaço de trabalho. Selecione **Exists** e selecione o aplicativo móvel que deseja usar.
   * Selecione o email que você enviou aos clientes.
   * Arraste e solte o elemento **Delivery logs (logs)** no espaço de trabalho e selecione **Exists** para direcionar todos os clientes que receberam o email.
   * Arraste e solte o elemento **Tracking logs (tracking)** no espaço de trabalho e selecione **Does not exist** para direcionar todos os clientes que não abriram o email.

      ![](assets/wkf_push_example_2.png)

1. A atividade [Push notification delivery](../../automating/using/push-notification-delivery.md) permite inserir o conteúdo da mensagem e selecionar os campos de personalização que deseja usar:

   * Selecione a opção **[!UICONTROL Recurring notification]**.
   * Defina o conteúdo da notificação por push. Para obter mais informações sobre o conteúdo da notificação por push, consulte esta [seção](../../channels/using/preparing-and-sending-a-push-notification.md).
   * No bloco **[!UICONTROL Schedule]**, selecione **[!UICONTROL Messages to be sent automatically on the time zone specified below]**. Aqui, escolhemos o **[!UICONTROL Time zone of the contact date]** Pacífico como no workflow **[!UICONTROL Scheduler]**.
   * No campo **[!UICONTROL Optimize the sending time per recipient]**, selecione **[!UICONTROL Send at the recipient's time zone]**.

      ![](assets/wkf_push_example_4.png)

1. Clique no botão **[!UICONTROL Start]** para iniciar seu fluxo de trabalho recorrente.

   ![](assets/wkf_push_example_3.png)

Seu fluxo de trabalho está em execução. Ele começará na data de início escolhida para **[!UICONTROL Scheduler]** às 20 horas, horário do Pacífico, o push recorrente será enviado todos os primeiros dias do mês às 20 horas, dependendo do fuso horário dos clientes.
