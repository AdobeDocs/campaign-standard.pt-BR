---
title: Scheduler
description: A atividade Scheduler permite programar quando um fluxo de trabalho ou uma atividade será iniciada.
page-status-flag: never-activated
uuid: f5e50a11-8dc9-4d98-9531-024c0fb3f7da
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 0fb16cea-3941-404f-899c-33f81ced4ed5
context-tags: schedule,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '555'
ht-degree: 97%

---


# Scheduler{#scheduler}

## Descrição {#description}

![](assets/scheduler.png)

A atividade **[!UICONTROL Scheduler]** permite programar quando um fluxo de trabalho ou uma atividade será iniciada.

## Contexto de uso {#context-of-use}

A atividade **[!UICONTROL Scheduler]** deve ser considerada como um início agendado. As regras de posicionamento de atividades no gráfico são iguais para a atividade **[!UICONTROL Start]**. Esta atividade não deve ter uma transição de entrada.

Ao criar seu fluxo de trabalho, use apenas uma atividade **[!UICONTROL Scheduler]** por ramificação e lembre-se de definir um fuso horário. Isso permite que você inicie seu fluxo de trabalho em um fuso horário específico, caso contrário, ele será executado no fuso horário definido nas propriedades do fluxo de trabalho (consulte [Criação de um fluxo de trabalho](../../automating/using/building-a-workflow.md)).

>[!CAUTION]
>
>A **[!UICONTROL Repetition frequency]** da atividade não pode ser inferior a 10 minutos. Isso significa que um fluxo de trabalho não pode ser executado automaticamente mais de uma vez a cada 10 minutos.

**Tópicos relacionados:**

* [Caso de uso: Criação de delivery na data de criação dos perfis](../../automating/using/workflow-creation-date-query.md)
* [Caso de uso: Criação de um delivery de email todas as terças-feiras](../../automating/using/workflow-weekly-offer.md)

## Configuração {#configuration}

1. Arraste e solte uma atividade **[!UICONTROL Scheduler]** no seu fluxo de trabalho.
1. Selecione e abra a atividade usando o botão ![](assets/edit_darkgrey-24px.png) das ações rápidas exibidas.
1. Especifique a **[!UICONTROL Execution frequency]**:

   * **[!UICONTROL Once]**: o fluxo de trabalho é executado uma única vez.
   * **[!UICONTROL Several times a day]**: o fluxo de trabalho é executado regularmente várias vezes ao dia. Você pode configurar as execuções em horários específicos ou periodicamente.
   * **[!UICONTROL Daily]**: o fluxo de trabalho é executado em um horário específico, uma vez por dia.
   * **[!UICONTROL Weekly]**: o fluxo de trabalho é executado em um horário especificado, uma ou várias vezes por semana.
   * **[!UICONTROL Monthly]**: o fluxo de trabalho é executado em um horário especificado, uma ou várias vezes por mês. Você pode selecionar meses quando precisar que o fluxo de trabalho seja executado. Você também pode configurar as execuções em um determinado dia da semana do mês, como a segunda terça-feira do mês.
   * **[!UICONTROL Yearly]**: o fluxo de trabalho é executado em um momento especificado, uma ou várias vezes por ano.

1. Defina os detalhes da execução de acordo com a frequência selecionada. Os campos de detalhes podem variar dependendo da frequência usada (tempo, frequência de repetição, dias especificados etc.).

   >[!NOTE]
   >
   >O campo **[!UICONTROL Repetition frequency]** permite que você espace os horários em que o fluxo de trabalho é acionado. Por exemplo, se você selecionar um período de execução diária e a frequência de repetição for definida como **2** (dias), o fluxo de trabalho será acionado a cada dois dias. Ele não pode ser inferior a 10 minutos. Se a frequência de repetição for definida como **0** (também o valor padrão), essa opção não será considerada, e o fluxo de trabalho será executado de acordo com a frequência de execução especificada.

1. Especifique quando a execução expirará:

   * **[!UICONTROL Never]**: o fluxo de trabalho será executado de acordo com a frequência especificada, sem limites para o intervalo de tempo ou o número de iterações.
   * **[!UICONTROL After a certain number of iterations]**: o fluxo de trabalho será executado de acordo com a frequência especificada, até que o limite **X** seja atingido. Portanto, o **[!UICONTROL Number of iterations]** precisará ser especificado.
   * **[!UICONTROL On a specific date]**: o fluxo de trabalho será executado de acordo com a frequência especificada, até uma data específica. Portanto, o prazo de execução precisará ser especificado.

1. Verifique a programação das próximas dez execuções do seu fluxo de trabalho clicando em **[!UICONTROL Preview next executions]**.

1. Na guia **[!UICONTROL Execution options]**, configure o fuso horário para seu scheduler no campo **[!UICONTROL Time zone]**.

   Para saber mais sobre como enviar um delivery dependendo do fuso horário do recipient, consulte esta [seção](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md) ou este [exemplo](../../automating/using/recurring-push-notifications.md) de um fluxo de trabalho recorrente.

1. Confirme a configuração da sua atividade e salve o fluxo de trabalho.

## Exemplo {#example}

No exemplo a seguir, a atividade é configurada para iniciar o fluxo de trabalho todas as segundas-feiras, às 7h, por tempo indeterminado.

![](assets/wkf_scheduler_example.png)

