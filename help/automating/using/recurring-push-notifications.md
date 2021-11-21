---
title: Envio de uma notificação por push recorrente com um workflow
description: Neste exemplo, uma notificação por push personalizada é enviada todos os primeiros dias do mês às 20 horas para os assinantes do aplicativo móvel, dependendo de seus fusos horários.
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: d5e6034c-3673-4069-ac0b-49c7ad07259d
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 5%

---

# Envio de uma notificação por push recorrente com um workflow {#sending-a-recurring-push-notification-with-a-workflow}

![](assets/wkf_push_example_1.png)

Neste exemplo, uma notificação por push personalizada é enviada todos os primeiros dias do mês às 20 horas para os assinantes do aplicativo móvel, dependendo de seus fusos horários.

Para criar o workflow, siga estas etapas:

1. O [Scheduler](../../automating/using/scheduler.md) permite iniciar o workflow dias antes do início do delivery para enviar a notificação a cada assinante às 20 horas em qualquer fuso horário:

   * No **[!UICONTROL Execution frequency]** , selecione Monthly.
   * Selecione 18h no **[!UICONTROL Time]** campo.
   * Escolha em qual dia o delivery será enviado todos os meses.
   * Selecione uma data de início para o workflow, pelo menos um dia antes do início do delivery. Caso contrário, alguns recipients poderão receber a mensagem um dia depois, se a hora selecionada já tiver passado em seus fusos horários.
   * No **[!UICONTROL Execution options]** selecione em qual fuso horário seu fluxo de trabalho será iniciado na **[!UICONTROL Time zone]** campo. Aqui, por exemplo, o workflow começará às 20 horas, hora do Pacífico, uma semana antes do primeiro dia do mês para permitir que algum tempo para os deliveries sejam criados para todos os fusos horários aplicáveis.

   >[!NOTE]
   >
   >Por padrão, o fuso horário selecionado é o definido nas propriedades do fluxo de trabalho (consulte [Criação de um fluxo de trabalho](../../automating/using/building-a-workflow.md)).

   ![](assets/wkf_push_example_5.png)

1. O [Query](../../automating/using/query.md) A atividade permite direcionar seus clientes de VIP com idade entre 20 e 30 anos, que assinaram seu aplicativo móvel e não abriram o email enviado:

   * Selecione um público-alvo (seus clientes VIP) e filtre por sua idade.
   * Arraste e solte a **Assinaturas de um aplicativo** no espaço de trabalho. Selecionar **Existe** e selecione o aplicativo móvel que deseja usar.
   * Selecione o email que você enviou aos clientes.
   * Arraste e solte a **Logs do delivery (logs)** no espaço de trabalho e selecione **Existe** para direcionar todos os clientes que receberam o email.
   * Arraste e solte a **Logs de rastreamento (rastreamento)** no espaço de trabalho e selecione **Não existe** para direcionar todos os clientes que não abriram o email.

      ![](assets/wkf_push_example_2.png)

1. O [Entrega por notificação por push](../../automating/using/push-notification-delivery.md) permite inserir o conteúdo da mensagem e selecionar os campos de personalização que deseja usar:

   * Selecione a opção **[!UICONTROL Recurring notification]**.
   * Defina o conteúdo da notificação por push. Para obter mais informações sobre o conteúdo da notificação por push, consulte esta seção [seção](../../channels/using/preparing-and-sending-a-push-notification.md).
   * No **[!UICONTROL Schedule]** bloco, selecione **[!UICONTROL Messages to be sent automatically on the time zone specified below]**. Aqui, escolhemos o **[!UICONTROL Time zone of the contact date]** Pacífico como no fluxo de trabalho **[!UICONTROL Scheduler]**.
   * No campo **[!UICONTROL Optimize the sending time per recipient]**, selecione **[!UICONTROL Send at the recipient's time zone]**.

      ![](assets/wkf_push_example_4.png)

1. Clique no botão **[!UICONTROL Start]** para iniciar seu fluxo de trabalho recorrente.

   ![](assets/wkf_push_example_3.png)

Seu fluxo de trabalho está em execução. Ele começará na data de início escolhida do **[!UICONTROL Scheduler]** às 20 horas, horário do Pacífico, o push recorrente será enviado todos os primeiros dias do mês às 20 horas, dependendo do fuso horário dos clientes.
