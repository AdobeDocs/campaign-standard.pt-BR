---
title: Envio de uma notificação por push recorrente com um workflow
description: Neste exemplo, uma notificação por push personalizada é enviada todos os primeiros dias do mês às 20h para os assinantes do seu aplicativo móvel, dependendo de seus fusos horários
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: d5e6034c-3673-4069-ac0b-49c7ad07259d
source-git-commit: 0ab950d4124bf459ba889e2f1c2954210dd350e0
workflow-type: tm+mt
source-wordcount: '484'
ht-degree: 5%

---

# Envio de uma notificação por push recorrente com um workflow {#sending-a-recurring-push-notification-with-a-workflow}

![](assets/wkf_push_example_1.png)

Neste exemplo, uma notificação por push personalizada é enviada todos os primeiros dias do mês, às 20h, aos assinantes do seu aplicativo móvel, dependendo de seus fusos horários.

Para criar o workflow, siga estas etapas:

1. A atividade [Scheduler](../../automating/using/scheduler.md) permite iniciar o fluxo de trabalho dias antes do início da entrega para poder enviar a notificação a cada assinante às 20 horas em qualquer fuso horário:

   * No campo **[!UICONTROL Execution frequency]**, selecione Monthly.
   * Selecione 20 horas no campo **[!UICONTROL Time]**.
   * Escolha em que dia o delivery será enviado todos os meses.
   * Selecione uma data de início para o workflow, pelo menos um dia antes do início do delivery. Caso contrário, alguns recipients poderão receber a mensagem um dia depois se a hora selecionada já tiver passado em seus fusos horários.
   * Na guia **[!UICONTROL Execution options]**, selecione em qual fuso horário o fluxo de trabalho será iniciado no campo **[!UICONTROL Time zone]**. Aqui, por exemplo, o fluxo de trabalho será iniciado às 20h, no horário do Pacífico, uma semana antes do primeiro dia do mês, para permitir que algum tempo para os deliveries sejam criados para todos os fusos horários aplicáveis.

   >[!NOTE]
   >
   >Por padrão, o fuso horário selecionado é o definido nas propriedades do fluxo de trabalho (consulte [Criação de um fluxo de trabalho](../../automating/using/building-a-workflow.md)).

   ![](assets/wkf_push_example_5.png)

1. A atividade [Query](../../automating/using/query.md) permite direcionar clientes VIP com idade entre 20 e 30 anos, que assinaram seu aplicativo para dispositivos móveis e não abriram o email enviado:

   * Selecione um público-alvo (seus clientes VIP) e filtre por idade.
   * Arraste e solte o elemento **Assinaturas de um aplicativo** no espaço de trabalho. Selecione **Existe** e selecione o aplicativo móvel que você deseja usar.
   * Selecione o email que você enviou aos clientes.
   * Arraste e solte o elemento **Logs (logs)** da entrega no espaço de trabalho e selecione **Existe** para direcionar todos os clientes que receberam o email.
   * Arraste e solte o elemento **Logs de rastreamento (rastreamento)** no espaço de trabalho e selecione **Não existe** para direcionar todos os clientes que não abriram o email.

     ![](assets/wkf_push_example_2.png)

1. A atividade de [Entrega de notificação por push](../../automating/using/push-notification-delivery.md) permite inserir o conteúdo da mensagem e selecionar os campos de personalização que deseja usar:

   * Selecione a opção **[!UICONTROL Recurring notification]**.
   * Defina o conteúdo da notificação por push. Para obter mais informações sobre conteúdo de notificações por push, consulte esta [seção](../../channels/using/preparing-and-sending-a-push-notification.md).
   * No bloco **[!UICONTROL Schedule]**, selecione **[!UICONTROL Messages to be sent automatically on the time zone specified below]**. Aqui, escolhemos o Pacífico **[!UICONTROL Time zone of the contact date]** como no fluxo de trabalho **[!UICONTROL Scheduler]**.
   * No campo **[!UICONTROL Optimize the sending time per recipient]**, selecione **[!UICONTROL Send at the recipient's time zone]**.

     ![](assets/wkf_push_example_4.png)

1. Clique no botão **[!UICONTROL Start]** para iniciar seu fluxo de trabalho recorrente.

   ![](assets/wkf_push_example_3.png)

Seu fluxo de trabalho está em execução agora. Ele começará na data de início escolhida de **[!UICONTROL Scheduler]** às 20h, horário da Costa Oeste dos EUA, e o push recorrente será enviado todos os primeiros dias do mês às 20h, dependendo do fuso horário dos clientes.
