---
title: '"Caso de uso do fluxo de trabalho: Criando uma entrega semanal"'
description: '"Caso de uso do fluxo de trabalho: Criando uma entrega semanal"'
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,query,delivery,scheduler
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: accc382ca1543d648e60d53cab338537fd9ea3ef

---


# Caso de uso de fluxo de trabalho: Criar uma entrega por email todas as terças-feiras{#creating-email-every-tuesday}

Você pode enviar um e-mail todas as terças-feiras a todos os clientes para Ofertas especiais.

1. Em **[!UICONTROL Marketing Activities]**, clique**[!UICONTROL Create]** e selecione **[!UICONTROL Workflow]**.
1. Selecione **[!UICONTROL New Workflow]**como tipo de fluxo de trabalho e clique em**[!UICONTROL Next]**.
1. Insira as propriedades do fluxo de trabalho e clique em **[!UICONTROL Create]**.

## Criando uma atividade do Agendador{#creating-a-scheduler-activity}

1. Em **[!UICONTROL Activities]**>**[!UICONTROL Execution]**, arraste e solte um **[!UICONTROL Scheduler activity]**.
1. Clique duas vezes na atividade.
1. Configure a execução da entrega.
1. Em **[!UICONTROL Execution frequency]**, selecione**[!UICONTROL Weekly]**.
1. Selecione um **[!UICONTROL Time]**e um**[!UICONTROL Repetition frequency]** para suas entregas.
1. Em **[!UICONTROL Days of the week]**, selecione**[!UICONTROL Tuesday]**.
1. Especifique um **[!UICONTROL Start]**e um**[!UICONTROL Expiration]** parâmetro para seu fluxo de trabalho.
1. Confirme sua atividade e salve seu fluxo de trabalho.

![](assets/scheduler_properties.png)

>[!NOTE]
>
>Para iniciar seu fluxo de trabalho em um determinado **[!UICONTROL Time Zone]**, na guia**[!UICONTROL Execution options]**, configure o fuso horário para seu programador no campo Fuso horário. Por padrão, o fuso horário selecionado é o definido nas propriedades do fluxo de trabalho (consulte [Criação de um fluxo de trabalho](../../automating/using/building-a-workflow.md)).

## Criando uma atividade de consulta{#creating-a-query-activity}

1. Em **[!UICONTROL Activities]**>**[!UICONTROL Targeting]**, para selecionar destinatários, arraste e solte uma **[!UICONTROL query]**atividade e clique duas vezes nela.
1. Em **[!UICONTROL Shortcuts]**>**[!UICONTROL Profile]**, arraste e solte **[!UICONTROL Email]**.
1. Selecione **[!UICONTROL is not empty]**como operador.
1. Em **[!UICONTROL Shortcuts]**>**[!UICONTROL General]**, adicione perfis e selecione **[!UICONTROL no longer contact by email]**com o valor**[!UICONTROL No]**.
1. Clique em **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## Creating an Email delivery{#creating-an-email-delivery}

1. Em **[!UICONTROL Activities]**>**[!UICONTROL Channels]**, arraste e solte um **[!UICONTROL Email delivery]**.
1. Clique na atividade e selecione ![](assets/edit_darkgrey-24px.png) para editar.
1. Selecione **[!UICONTROL Recurring email]**e clique em**[!UICONTROL Next]**.
1. Selecione um modelo de email e clique em **[!UICONTROL Next]**.
1. Insira as propriedades do email e clique em **[!UICONTROL Next]**.
1. Para criar o layout do seu email, clique em **[!UICONTROL Use Email Designer]**.
1. Insira elementos ou selecione um modelo existente.
1. Personalize seu email usando campos e links.
1. Clique em **[!UICONTROL Save]**.

Para obter mais informações, consulte a [criação de um email](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).

**Tópicos relacionados:**

* [Atividade de consulta](../..//automating/using/query.md)
* [Atividade do agendador](../..//automating/using/scheduler.md)
* [Entrega por email](../..//automating/using/email-delivery.md)
* [Canal de email](../..//channels/using/creating-an-email.md)
