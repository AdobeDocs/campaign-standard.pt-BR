---
title: Envio de uma notificação por push recorrente com um workflow
description: Neste exemplo, uma notificação por push personalizada é enviada todos os primeiros dias do mês às 20h para os assinantes do seu aplicativo móvel, dependendo de seus fusos horários
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: d5e6034c-3673-4069-ac0b-49c7ad07259d
source-git-commit: 0ab950d4124bf459ba889e2f1c2954210dd350e0
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 5%

---

# Envio de uma notificação por push recorrente com um workflow {#sending-a-recurring-push-notification-with-a-workflow}

![](assets/wkf_push_example_1.png)

Neste exemplo, uma notificação por push personalizada é enviada todos os primeiros dias do mês, às 20h, aos assinantes do seu aplicativo móvel, dependendo de seus fusos horários.

Para criar o workflow, siga estas etapas:

1. A variável [Scheduler](../../automating/using/scheduler.md) A atividade permite iniciar o workflow dias antes do início do delivery para poder enviar a notificação a cada assinante às 20h em um determinado fuso horário:

   * No **[!UICONTROL Execution frequency]** selecione Monthly.
   * Selecione 20 horas no **[!UICONTROL Time]** campo.
   * Escolha em que dia o delivery será enviado todos os meses.
   * Selecione uma data de início para o workflow, pelo menos um dia antes do início do delivery. Caso contrário, alguns recipients poderão receber a mensagem um dia depois se a hora selecionada já tiver passado em seus fusos horários.
   * No **[!UICONTROL Execution options]** selecione em qual fuso horário o workflow será iniciado na guia **[!UICONTROL Time zone]** campo. Aqui, por exemplo, o fluxo de trabalho será iniciado às 20h, no horário do Pacífico, uma semana antes do primeiro dia do mês, para permitir que algum tempo para os deliveries sejam criados para todos os fusos horários aplicáveis.

   >[!NOTE]
   >
   >Por padrão, o fuso horário selecionado é o definido nas propriedades do fluxo de trabalho (consulte [Criação de um fluxo de trabalho](../../automating/using/building-a-workflow.md)).

   ![](assets/wkf_push_example_5.png)

1. A variável [Query](../../automating/using/query.md) A atividade permite direcionar clientes de VIP com idade entre 20 e 30 anos, que assinaram seu aplicativo para dispositivos móveis e não abriram o email enviado:

   * Selecione um público-alvo (seus clientes VIP) e filtre por idade.
   * Arraste e solte a **Assinaturas de um aplicativo** elemento no espaço de trabalho. Selecionar **Existe** e selecione o aplicativo móvel que deseja usar.
   * Selecione o email que você enviou aos clientes.
   * Arraste e solte a **Logs do delivery (logs)** elemento no espaço de trabalho e selecione **Existe** para direcionar todos os clientes que receberam o email.
   * Arraste e solte a **Logs de rastreamento (rastreamento)** elemento no espaço de trabalho e selecione **Não existe** para direcionar todos os clientes que não abriram o email.

     ![](assets/wkf_push_example_2.png)

1. A variável [Entrega por notificação por push](../../automating/using/push-notification-delivery.md) A atividade permite inserir o conteúdo da mensagem e selecionar os campos de personalização que deseja usar:

   * Selecione a opção **[!UICONTROL Recurring notification]**.
   * Defina o conteúdo da notificação por push. Para obter mais informações sobre o conteúdo de notificações por push, consulte esta página [seção](../../channels/using/preparing-and-sending-a-push-notification.md).
   * No **[!UICONTROL Schedule]** bloco, selecione **[!UICONTROL Messages to be sent automatically on the time zone specified below]**. Aqui, escolhemos o **[!UICONTROL Time zone of the contact date]** Pacífico como no workflow **[!UICONTROL Scheduler]**.
   * No campo **[!UICONTROL Optimize the sending time per recipient]**, selecione **[!UICONTROL Send at the recipient's time zone]**.

     ![](assets/wkf_push_example_4.png)

1. Clique em **[!UICONTROL Start]** botão para iniciar seu fluxo de trabalho recorrente.

   ![](assets/wkf_push_example_3.png)

Seu fluxo de trabalho está em execução agora. Ele começará na data de início escolhida da **[!UICONTROL Scheduler]** às 20h, horário da Costa Oeste dos EUA, o push recorrente será enviado todos os primeiros dias do mês, às 20h, dependendo do fuso horário do cliente.
