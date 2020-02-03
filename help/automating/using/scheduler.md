---
title: Agendador
description: A atividade do Agendador permite agendar quando um fluxo de trabalho ou uma atividade é iniciada.
page-status-flag: never-activated
uuid: f5e50a11-8dc9-4d98-9531-024c0fb3f7da
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 0fb16cea-3941-404f-899c-33f81ced4ed5
context-tags: schedule,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 41ba6fa44807541dd749f4effca44ae2b4d147ae

---


# Agendador{#scheduler}

## Descrição {#description}

![](assets/scheduler.png)

A **[!UICONTROL Scheduler]**atividade permite programar quando um fluxo de trabalho ou uma atividade é iniciada.

## Contexto de utilização {#context-of-use}

The **[!UICONTROL Scheduler]**activity should be considered as a scheduled start. The activity positioning rules within the chart are the same as for the**[!UICONTROL Start]** activity. Esta atividade não deve ter uma transição de entrada.

Ao criar seu fluxo de trabalho, use apenas uma **[!UICONTROL Scheduler]**atividade por ramificação e lembre-se de definir um fuso horário. Isso permite iniciar o fluxo de trabalho em um fuso horário específico, caso contrário, o fluxo de trabalho será executado no fuso horário definido nas propriedades do fluxo de trabalho (consulte[Criação de um fluxo de trabalho](../../automating/using/building-a-workflow.md)).

>[!CAUTION]
>
>A atividade **[!UICONTROL Repetition frequency]**não pode ser inferior a 10 minutos. Isso significa que um fluxo de trabalho não pode ser executado automaticamente mais de uma vez a cada 10 minutos.

## Configuração {#configuration}

1. Arraste e solte uma **[!UICONTROL Scheduler]**atividade em seu fluxo de trabalho.
1. Selecione a atividade e abra-a usando o ![](assets/edit_darkgrey-24px.png) botão das ações rápidas que aparecem.
1. Especifique o **[!UICONTROL Execution frequency]**:

   * **[!UICONTROL Once]**: o fluxo de trabalho é executado uma única vez.
   * **[!UICONTROL Several times a day]**: o fluxo de trabalho é executado regularmente várias vezes ao dia. Você pode configurar execuções em momentos específicos ou periodicamente.
   * **[!UICONTROL Daily]**: o fluxo de trabalho é executado em um horário específico, uma vez por dia.
   * **[!UICONTROL Weekly]**: o fluxo de trabalho é executado em um momento especificado, uma ou várias vezes por semana.
   * **[!UICONTROL Monthly]**: o fluxo de trabalho é executado em um momento especificado, uma ou várias vezes por mês. Você pode selecionar meses quando precisar que o fluxo de trabalho seja executado. Você também pode configurar execuções em determinados dias da semana do mês, como a segunda terça do mês.
   * **[!UICONTROL Yearly]**: o fluxo de trabalho é executado em um momento especificado, uma ou várias vezes por ano.

1. Defina os detalhes da execução de acordo com a frequência selecionada. Os campos de detalhes podem variar dependendo da frequência usada (tempo, frequência de repetição, dias especificados etc.).

   >[!NOTE]
   >
   >O **[!UICONTROL Repetition frequency]**campo permite que você esvazie as horas em que o fluxo de trabalho é acionado. Por exemplo, se você selecionar um período de execução diária e a frequência de repetição for definida em** 2 **(dias), o fluxo de trabalho será acionado a cada dois dias. Não pode ser inferior a 10 minutos. Se a frequência de repetição for definida como** 0 **(também o valor padrão), essa opção não será considerada e o fluxo de trabalho será executado de acordo com a frequência de execução especificada.

1. Especifique quando a execução expirará:

   * **[!UICONTROL Never]**: o fluxo de trabalho será executado, de acordo com a frequência especificada, sem limites para o período ou número de iterações.
   * **[!UICONTROL After a certain number of iterations]**: o fluxo de trabalho será executado de acordo com a frequência especificada, até que o limite de** X **seja atingido. É, pois, necessário**[!UICONTROL Number of iterations]** especificar esse aspecto.
   * **[!UICONTROL On a specific date]**: o fluxo de trabalho será executado de acordo com a frequência especificada, até uma data específica. O prazo de execução deverá, por conseguinte, ser especificado.

1. Verifique a programação das próximas dez execuções do fluxo de trabalho clicando em **[!UICONTROL Preview next executions]**.

1. Na **[!UICONTROL Execution options]**guia, configure o fuso horário para seu programador no**[!UICONTROL Time zone]** campo.

   Para obter mais informações sobre como enviar a entrega, dependendo do fuso horário do destinatário, consulte esta [seção](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md) ou este [exemplo](../../automating/using/push-notification-delivery.md#sending-a-recurring-push-notification-with-a-workflow) de um fluxo de trabalho recorrente.

1. Confirme a configuração da atividade e salve o fluxo de trabalho.

## Exemplo {#example}

No exemplo a seguir, a atividade é configurada para que inicie o fluxo de trabalho semanalmente, a cada segunda às 7h, por uma duração indeterminada.

![](assets/wkf_scheduler_example.png)

