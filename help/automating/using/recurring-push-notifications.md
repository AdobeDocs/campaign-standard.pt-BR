---
title: Envio de uma notificação por push recorrente com um fluxo de trabalho
description: Neste exemplo, uma notificação por push personalizada é enviada todos os primeiros dias do mês, às 20 horas, aos assinantes do aplicativo móvel, dependendo de seus fusos horários.
page-status-flag: never-activated
uuid: 994d8fe3-29f0-4b5c-89ee-c6be7c60a31b
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: e61bdaee-4b48-4845-a2a5-574b577ea796
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 5%

---


# Envio de uma notificação por push recorrente com um fluxo de trabalho {#sending-a-recurring-push-notification-with-a-workflow}

![](assets/wkf_push_example_1.png)

Neste exemplo, uma notificação por push personalizada é enviada todos os primeiros dias do mês, às 20 horas, aos assinantes do aplicativo móvel, dependendo de seus fusos horários.

Para criar o fluxo de trabalho, siga estas etapas:

1. A atividade do [Scheduler](../../automating/using/scheduler.md) permite que você start os dias do fluxo de trabalho antes do start do delivery para poder enviar a notificação a cada assinante às 20 horas em qualquer fuso horário:

   * In the **[!UICONTROL Execution frequency]** field, select Monthly.
   * Selecione 20 horas no **[!UICONTROL Time]** campo.
   * Escolha em que dia o delivery será enviado todos os meses.
   * Selecione uma data de start para o seu fluxo de trabalho, pelo menos um dia antes do start do delivery. Caso contrário, alguns recipient poderão receber a mensagem um dia depois se a hora selecionada já tiver passado em seus fusos horários.
   * Na **[!UICONTROL Execution options]** guia, selecione em qual fuso horário seu fluxo de trabalho será start no **[!UICONTROL Time zone]** campo. Aqui, por exemplo, o fluxo de trabalho será start às 20 horas, hora do Pacífico, uma semana antes do primeiro dia do mês para permitir que os delivery sejam criados para todos os fusos horários aplicáveis.

   >[!NOTE]
   >
   >Por padrão, o fuso horário selecionado é o definido nas propriedades do fluxo de trabalho (consulte [Criação de um fluxo de trabalho](../../automating/using/building-a-workflow.md)).

   ![](assets/wkf_push_example_5.png)

1. A atividade do [Query](../../automating/using/query.md) permite público alvo de seus clientes VIP com idade entre 20 e 30 anos, que se inscreveram em seu aplicativo móvel e que não abriram o e-mail enviado:

   * Selecione uma audiência (seus clientes VIP) e filtre na idade.
   * Arraste e solte as **Subscrições em um elemento de aplicativo** no espaço de trabalho. Selecione **Existe** e selecione o aplicativo móvel que deseja usar.
   * Selecione o email que você enviou aos seus clientes.
   * Arraste e solte o elemento **Logs do delivery (logs)** no espaço de trabalho e selecione **Existe** para público alvo de todos os clientes que receberam o email.
   * Arraste e solte o elemento **Logs de rastreamento (rastreamento)** no espaço de trabalho e selecione **Não existe** para público alvo de todos os clientes que não abriram o email.

      ![](assets/wkf_push_example_2.png)

1. A atividade de delivery [de notificação por](../../automating/using/push-notification-delivery.md) push permite que você insira o conteúdo de sua mensagem e selecione os campos de personalização que deseja usar:

   * Selecione a opção **[!UICONTROL Recurring notification]**.
   * Defina o conteúdo da notificação por push. For more information on push notification content, refer to this [section](../../channels/using/preparing-and-sending-a-push-notification.md).
   * In the **[!UICONTROL Schedule]** block, select **[!UICONTROL Messages to be sent automatically on the time zone specified below]**. Aqui, escolhemos o **[!UICONTROL Time zone of the contact date]** Pacífico como no fluxo de trabalho **[!UICONTROL Scheduler]**.
   * No campo **[!UICONTROL Optimize the sending time per recipient]**, selecione **[!UICONTROL Send at the recipient's time zone]**.

      ![](assets/wkf_push_example_4.png)

1. Clique no **[!UICONTROL Start]** botão para start de seu fluxo de trabalho recorrente.

   ![](assets/wkf_push_example_3.png)

Seu fluxo de trabalho está em execução. Ele será start na data escolhida para o start às 20 horas, horário do Pacífico, **[!UICONTROL Scheduler]** o envio periódico será enviado todos os primeiros dias do mês, às 20 horas, dependendo do fuso horário do cliente.
