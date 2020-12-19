---
solution: Campaign Standard
product: campaign
title: Envio de uma notificação por push recorrente com um fluxo de trabalho
description: Neste exemplo, uma notificação por push personalizada é enviada todos os primeiros dias do mês, às 20 horas, aos assinantes do aplicativo móvel, dependendo de seus fusos horários.
audience: automating
content-type: reference
topic-tags: channel-activities
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 5%

---


# Envio de uma notificação por push recorrente com um fluxo de trabalho {#sending-a-recurring-push-notification-with-a-workflow}

![](assets/wkf_push_example_1.png)

Neste exemplo, uma notificação por push personalizada é enviada todos os primeiros dias do mês, às 20 horas, aos assinantes do aplicativo móvel, dependendo de seus fusos horários.

Para criar o fluxo de trabalho, siga estas etapas:

1. A atividade [Scheduler](../../automating/using/scheduler.md) permite que você start os dias de fluxo de trabalho antes do start do delivery para poder enviar a notificação a cada assinante às 20 horas em qualquer fuso horário:

   * No campo **[!UICONTROL Execution frequency]**, selecione Mensalmente.
   * Selecione 8 pm no campo **[!UICONTROL Time]**.
   * Escolha em que dia o delivery será enviado todos os meses.
   * Selecione uma data de start para o seu fluxo de trabalho, pelo menos um dia antes do start do delivery. Caso contrário, alguns recipient poderão receber a mensagem um dia depois se a hora selecionada já tiver passado em seus fusos horários.
   * Na guia **[!UICONTROL Execution options]**, selecione em qual fuso horário seu fluxo de trabalho será start no campo **[!UICONTROL Time zone]**. Aqui, por exemplo, o fluxo de trabalho será start às 20 horas, hora do Pacífico, uma semana antes do primeiro dia do mês para permitir que os delivery sejam criados para todos os fusos horários aplicáveis.

   >[!NOTE]
   >
   >Por padrão, o fuso horário selecionado é o definido nas propriedades do fluxo de trabalho (consulte [Criação de um fluxo de trabalho](../../automating/using/building-a-workflow.md)).

   ![](assets/wkf_push_example_5.png)

1. A atividade [Query](../../automating/using/query.md) permite que você público alvo seus clientes VIP com idade entre 20 e 30 anos, que se inscreveram em seu aplicativo móvel e que não abriram o email enviado:

   * Selecione uma audiência (seus clientes VIP) e filtre na idade.
   * Arraste e solte as **Subscrições em um elemento application** no espaço de trabalho. Selecione **Exists** e selecione o aplicativo móvel que deseja usar.
   * Selecione o email que você enviou aos seus clientes.
   * Arraste e solte o elemento **Logs do delivery (registros)** no espaço de trabalho e selecione **Exists** para público alvo de todos os clientes que receberam o email.
   * Arraste e solte o elemento **Logs de rastreamento (rastreamento)** no espaço de trabalho e selecione **Não existe** para público alvo todos os clientes que não abriram o email.

      ![](assets/wkf_push_example_2.png)

1. A atividade [delivery de notificação por push](../../automating/using/push-notification-delivery.md) permite que você insira o conteúdo de sua mensagem e selecione os campos de personalização que deseja usar:

   * Selecione a opção **[!UICONTROL Recurring notification]**.
   * Defina o conteúdo da notificação por push. Para obter mais informações sobre o conteúdo da notificação por push, consulte esta [seção](../../channels/using/preparing-and-sending-a-push-notification.md).
   * No bloco **[!UICONTROL Schedule]**, selecione **[!UICONTROL Messages to be sent automatically on the time zone specified below]**. Aqui, escolhemos o **[!UICONTROL Time zone of the contact date]** Pacífico como no fluxo de trabalho **[!UICONTROL Scheduler]**.
   * No campo **[!UICONTROL Optimize the sending time per recipient]**, selecione **[!UICONTROL Send at the recipient's time zone]**.

      ![](assets/wkf_push_example_4.png)

1. Clique no botão **[!UICONTROL Start]** para start do fluxo de trabalho recorrente.

   ![](assets/wkf_push_example_3.png)

Seu fluxo de trabalho está em execução. Ele será start na data escolhida para o start das **[!UICONTROL Scheduler]** às 20 horas, hora do Pacífico, o envio periódico será enviado todos os primeiros dias do mês às 20 horas, dependendo do fuso horário do cliente.
