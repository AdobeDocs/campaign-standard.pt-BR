---
title: '"Caso de uso do fluxo de trabalho: Criando uma entrega semanal"'
seo-title: '"Caso de uso do fluxo de trabalho: Criando uma entrega semanal"'
description: '"Caso de uso do fluxo de trabalho: Criando uma entrega semanal"'
seo-description: '"Caso de uso do fluxo de trabalho: Criando uma entrega semanal"'
page-status-flag: nunca ativado
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: automatização
content-type: referência
topic-tags: 'atividades de execução '
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: fluxo de trabalho,use-case,consulta,entrega,agendador
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4a38b1f3d7d6dbf12fa71c819147bf2d91acb0c4

---


# Caso de uso de fluxo de trabalho: Criar uma entrega por email todas as terças-feiras{#creating-email-every-tuesday}

Você pode enviar um e-mail todas as terças-feiras a todos os clientes para Ofertas especiais.

1. Em **[!UICONTROL Marketing Activities]**, clique **[!UICONTROL Create]** e selecione **[!UICONTROL Workflow]**.
1. Selecione **[!UICONTROL New Workflow]** como tipo de fluxo de trabalho e clique em **[!UICONTROL Next]**.
1. Insira as propriedades do fluxo de trabalho e clique em **[!UICONTROL Create]**.

## Criando uma atividade do Agendador{#creating-a-scheduler-activity}

1. Em **[!UICONTROL Activities]** &gt; **[!UICONTROL Execution]**, arraste e solte um **[!UICONTROL Scheduler activity]**.
1. Clique duas vezes na atividade.
1. Configure a execução da entrega.
1. Em **[!UICONTROL Execution frequency]**, selecione **[!UICONTROL Weekly]**.
1. Selecione um **[!UICONTROL Time]** e um **[!UICONTROL Repetition frequency]** para suas entregas.
1. Em **[!UICONTROL Days of the week]**, selecione **[!UICONTROL Tuesday]**.
1. Especifique um **[!UICONTROL Start]** e um **[!UICONTROL Expiration]** parâmetro para seu fluxo de trabalho.
1. Confirme sua atividade e salve seu fluxo de trabalho.

![](assets/scheduler_properties.png)

>[!NOTE]
>
>Para iniciar seu fluxo de trabalho em um determinado **[!UICONTROL Time Zone]**, na guia **[!UICONTROL Execution options]**, configure o fuso horário para seu programador no campo Fuso horário.

## Criando uma atividade de consulta{#creating-a-query-activity}

1. Em **[!UICONTROL Activities]** &gt; **[!UICONTROL Targeting]**, para selecionar destinatários, arraste e solte uma **[!UICONTROL query]** atividade e clique duas vezes nela.
1. Em **[!UICONTROL Shortcuts]** &gt; **[!UICONTROL Profile]**, arraste e solte **[!UICONTROL Email]**.
1. Selecione **[!UICONTROL is not empty]** como operador.
1. Em **[!UICONTROL Shortcuts]** &gt; **[!UICONTROL General]**, adicione perfis e selecione **[!UICONTROL no longer contact by email]** com o valor **[!UICONTROL No]**.
1. Click **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## Criação de uma entrega por email{#creating-an-email-delivery}

1. Em **[!UICONTROL Activities]** &gt; **[!UICONTROL Channels]**, arraste e solte um **[!UICONTROL Email delivery]**.
1. Clique na atividade e selecione ![](assets/edit_darkgrey-24px.png) para editar.
1. Selecione **[!UICONTROL Recurring email]** e clique em **[!UICONTROL Next]**.
1. Selecione um modelo de email e clique em **[!UICONTROL Next]**.
1. Insira as propriedades do email e clique em **[!UICONTROL Next]**.
1. Para criar o layout do seu email, clique em **[!UICONTROL Use Email Designer]**.
1. Insira elementos ou selecione um modelo existente.
1. Personalize seu email usando campos e links.
1. Click **[!UICONTROL Save]**.

Para obter mais informações, consulte a [criação de um email](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).

**Tópicos relacionados:**

* [Atividade de consulta](../..//automating/using/query.md)
* [Atividade do agendador](../..//automating/using/scheduler.md)
* [Entrega por email](../..//automating/using/email-delivery.md)
* [Canal de email](../..//channels/using/creating-an-email.md)
