---
title: Criar uma entrega semanal
description: Este caso de uso mostra como criar um delivery semanal.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: workflow,use-case,query,delivery,scheduler
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 32d9d174-8438-48d7-b876-33a0c35d9549
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 76%

---

# Criação de um delivery de email todas as terças-feiras{#creating-email-every-tuesday}

Você pode enviar um email todas as terças-feiras a todos os clientes com ofertas especiais.

1. Em **[!UICONTROL Marketing Activities]**, clique em **[!UICONTROL Create]** e selecione **[!UICONTROL Workflow]**.
1. Selecione **[!UICONTROL New Workflow]** como tipo de fluxo de trabalho e clique em **[!UICONTROL Next]**.
1. Insira as propriedades do fluxo de trabalho e clique em **[!UICONTROL Create]**.

## Criação de uma atividade do Scheduler{#creating-a-scheduler-activity}

1. Entrada **[!UICONTROL Activities]** > **[!UICONTROL Execution]**, arraste e solte uma [Scheduler](../../automating/using/scheduler.md) atividade.
1. Clique duas vezes na atividade.
1. Configure a execução da entrega.
1. Em **[!UICONTROL Execution frequency]**, selecione **[!UICONTROL Weekly]**.
1. Selecione uma **[!UICONTROL Time]** e uma **[!UICONTROL Repetition frequency]** para suas entregas.
1. Em **[!UICONTROL Days of the week]**, selecione **[!UICONTROL Tuesday]**.
1. Especifique um parâmetro **[!UICONTROL Start]** e **[!UICONTROL Expiration]** para o fluxo de trabalho.
1. Confirme sua atividade e salve o fluxo de trabalho.

![](assets/scheduler_properties.png)

>[!NOTE]
>
>Para iniciar o fluxo de trabalho em um **[!UICONTROL Time Zone]** específico, na guia **[!UICONTROL Execution options]**, configure o fuso horário para o scheduler no campo Time zone. Por padrão, o fuso horário selecionado é o definido nas propriedades do fluxo de trabalho (consulte [Criação de um fluxo de trabalho](../../automating/using/building-a-workflow.md)).

## Criação de uma atividade Query{#creating-a-query-activity}

1. Entrada **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, para selecionar recipients, arraste e solte uma [Query](../../automating/using/query.md) atividade e clique duas vezes nela.
1. Em **[!UICONTROL Shortcuts]** > **[!UICONTROL Profile]**, arraste e solte **[!UICONTROL Email]**.
1. Selecione **[!UICONTROL is not empty]** como operador.
1. Em **[!UICONTROL Shortcuts]** > **[!UICONTROL General]**, adicione perfis e selecione **[!UICONTROL no longer contact by email]** com o valor **[!UICONTROL No]**.
1. Clique em **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## Criação de um delivery de email{#creating-an-email-delivery}

1. Entrada **[!UICONTROL Activities]** > **[!UICONTROL Channels]**, arraste e solte um [Entrega de email](../../automating/using/email-delivery.md) atividade.
1. Clique na atividade e selecione ![](assets/edit_darkgrey-24px.png) para editar.
1. Selecione **[!UICONTROL Recurring email]** e clique em **[!UICONTROL Next]**.
1. Selecione um template de email e clique em **[!UICONTROL Next]**.
1. Insira as propriedades do email e clique em **[!UICONTROL Next]**.
1. Para criar o layout do email, clique em **[!UICONTROL Use Email Designer]**.
1. Insira elementos ou selecione um template.
1. Personalize o email usando campos e links.
1. Clique em **[!UICONTROL Save]**.

Para obter mais informações, consulte [Design de email](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).

**Tópicos relacionados:**

* [Canal de email](../../channels/using/creating-an-email.md)
