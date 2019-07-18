---
title: Programador
seo-title: Programador
description: Programador
seo-description: A atividade do Agendador permite programar quando um fluxo de trabalho ou uma atividade é iniciada.
page-status-flag: nunca ativado
uuid: f 5 e 50 a 11-8 dc 9-4 d 98-9531-024 c 0 fb 3 f 7 da
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizando
content-type: reference
topic-tags: execução-atividades
discoiquuid: 0 fb 16 cea -3941-404 f -899 c -33 f 81 ed 4 ed 5
context-tags: programação, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e3a627376a91eb394aea90b1d94c7958ad77fd40

---


# Scheduler{#scheduler}

## Description {#description}

![](assets/scheduler.png)

The **[!UICONTROL Scheduler]** activity allows you to schedule when a workflow or an activity is started.

## Context of use {#context-of-use}

**[!UICONTROL Scheduler]** A atividade deve ser considerada como um início programado. The activity positioning rules within the chart are the same as for the **[!UICONTROL Start]** activity. Essa atividade não deve ter uma transição de entrada.

When building your workflow, only use one **[!UICONTROL Scheduler]** activity per branch and remember to set a time zone. Ele será definido, caso contrário, será executado no fuso horário do servidor.

>[!CAUTION]
>
>The **[!UICONTROL Repetition frequency]** of the activity cannot be less than 10 minutes. Isso significa que um fluxo de trabalho não pode ser executado automaticamente mais de uma vez a cada 10 minutos.

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Scheduler]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Specify the **[!UICONTROL Execution frequency]**:

   * **[!UICONTROL Once]**: o fluxo de trabalho é executado em um único momento.
   * **[!UICONTROL Several times a day]**: o fluxo de trabalho é executado regularmente várias vezes por dia. Você pode configurar execuções em horários específicos ou periodicamente.
   * **[!UICONTROL Daily]**: o fluxo de trabalho é executado em um horário específico, uma vez por dia.
   * **[!UICONTROL Weekly]**: o fluxo de trabalho é executado em um momento especificado, em um ou vários dias de uma semana.
   * **[!UICONTROL Monthly]**: o fluxo de trabalho é executado em um momento especificado, uma vez ou várias vezes por mês. Você pode selecionar meses, quando precisar executar o fluxo de trabalho. Também é possível configurar execuções no dia da semana especificado do mês, como o segundo terça-feira do mês.
   * **[!UICONTROL Yearly]**: o fluxo de trabalho é executado em um momento especificado, uma vez ou várias vezes por ano.

1. Defina os detalhes da execução de acordo com a frequência selecionada. Os campos de detalhes podem variar dependendo da frequência usada (tempo, frequência de repetição, dias especificados etc.).

   >[!NOTE]
   >
   >The **[!UICONTROL Repetition frequency]** field allows you to space out the times when the workflow is triggered. For example, if you select a daily execution period and the repetition frequency is set at **2** (days), the workflow will be triggered every two days. Não pode ser menor que 10 minutos. If the repetition frequency is set at **0** (also the default value), this option is not taken into account and the workflow will run according to the execution frequency specified.

1. Especifique quando a execução expirará:

   * **[!UICONTROL Never]**: o fluxo de trabalho será executado, de acordo com a frequência especificada, sem limites para o período ou o número de iterações.
   * **[!UICONTROL After a certain number of iterations]**: o fluxo de trabalho será executado de acordo com a frequência especificada, até que o limite de **X** seja atingido. The **[!UICONTROL Number of iterations]** will therefore need to be specified.
   * **[!UICONTROL On a specific date]**: o fluxo de trabalho será executado de acordo com a frequência especificada, até uma data específica. O prazo da execução precisará ser especificado.

1. Check the schedule of the next ten executions of your workflow by clicking **[!UICONTROL Preview next executions]**.

1. In the **[!UICONTROL Execution options]** tab, set up the time zone for your scheduler in the **[!UICONTROL Time zone]** field. Isso permite iniciar o fluxo de trabalho em um fuso horário específico, caso contrário, o fluxo de trabalho será executado no fuso horário do servidor por padrão.

   For more information on sending delivery depending on the recipient's time zone, refer to this [section](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md) or this [example](../../automating/using/push-notification-delivery.md#sending-a-recurring-push-notification-with-a-workflow) of a recurring workflow.

1. Confirme a configuração da atividade e salve seu fluxo de trabalho.

## Example {#example}

No exemplo a seguir, a atividade está configurada para que inicie o fluxo de trabalho semanalmente, a cada segunda segunda-feira, às 7 h, para uma duração indeterminada.

![](assets/wkf_scheduler_example.png)

