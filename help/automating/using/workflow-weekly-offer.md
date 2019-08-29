---
title: '" Caso de uso de fluxo de trabalho: Criação de uma entrega semanal "'
seo-title: '" Caso de uso de fluxo de trabalho: Criação de uma entrega semanal "'
description: '" Caso de uso de fluxo de trabalho: Criação de uma entrega semanal "'
seo-description: '" Caso de uso de fluxo de trabalho: Criação de uma entrega semanal "'
page-status-flag: nunca ativado
uuid: 396 a 3 de 1-6 ffa -4385-ac 9 f -15 fdeae 5 a 366
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizando
content-type: reference
topic-tags: 'execução-atividades '
discoiquuid: 377821 e 6-69 f 8-41 cc-a 1 ad -8 a 2 f 5 ed 4 d 409
context-tags: fluxo de trabalho, caso de uso, consulta, entrega, programador
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f57775ec88925d43046fe4162f2753c189d50c62

---


# Caso de uso de subfluxo: Criar uma entrega de email a cada terça-feira{#creating-email-every-tuesday}

Você pode enviar um email toda terça-feira para todos os clientes para ofertas especiais.

1. Em **[!UICONTROL Marketing Activities]**, clique **[!UICONTROL Create]** em e selecione **[!UICONTROL Workflow]**.
1. Selecione **[!UICONTROL New Workflow]** como tipo de fluxo de trabalho e clique **[!UICONTROL Next]** em.
1. Insira as propriedades do fluxo de trabalho e clique **[!UICONTROL Create]** em.

## Criação de uma atividade programada{#creating-a-scheduler-activity}

1. Em **[!UICONTROL Activities]** &gt; **[!UICONTROL Execution]**, arraste e solte a **[!UICONTROL Scheduler activity]**![](assets/scheduler_icon.png).
1. Clique duas vezes na atividade.
1. Configure a execução da entrega.
1. Em **[!UICONTROL Execution frequency]**, selecione **[!UICONTROL Weekly]**.
1. Selecione a **[!UICONTROL Time]** e a **[!UICONTROL Repetition frequency]** para suas entregas.
1. Em **[!UICONTROL Days of the week]**, selecione **[!UICONTROL Tuesday]**.
1. Especifique um **[!UICONTROL Start]** parâmetro e um **[!UICONTROL Expiration]** parâmetro para o seu fluxo de trabalho.

![](assets/scheduler_properties.png)

>[!NOTE]
>
>Para iniciar o fluxo de trabalho em um determinado momento **[!UICONTROL Time Zone]** na **[!UICONTROL Execution options]** guia, configure o fuso horário do seu programador no campo Fuso horário.

1. Confirme sua atividade e salve seu fluxo de trabalho.

## Criação de uma atividade de consulta{#creating-a-query-activity}

1. Em **[!UICONTROL Activities]** &gt; **[!UICONTROL Targeting]**, para selecionar destinatários, arraste e solte **[!UICONTROL query]** uma atividade e clique duas vezes nele.
1. Em **[!UICONTROL Shortcuts]** &gt; **[!UICONTROL Profile]**, arraste **[!UICONTROL Email]** e solte.
1. Selecione **[!UICONTROL is not empty]** como um operador.
1. Em **[!UICONTROL Shortcuts]** &gt; **[!UICONTROL General]**, adicione perfis e selecione **[!UICONTROL no longer contact by email]** com o valor **[!UICONTROL No]**.
1. Click **[!UICONTROL Confirm]**.

## Criação de uma entrega por email{#creating-an-email-delivery}

1. Em **[!UICONTROL Activities]** &gt; **[!UICONTROL Channels]**, arraste e solte um **[!UICONTROL Email delivery]**.
1. Clique na atividade e selecione ![](assets/edit_darkgrey-24px.png) editar.
1. Selecione **[!UICONTROL Recurring email]** e clique **[!UICONTROL Next]** em.
1. Selecione um modelo de e-mail e clique **[!UICONTROL Next]** em.
1. Insira as propriedades e clique **[!UICONTROL Next]** em.
1. Para criar o layout de seu email, clique **[!UICONTROL Use Email Designer]** em.
1. Inserir elementos ou selecionar um modelo existente.
1. Personalize seu email usando campos e links.
1. Click **[!UICONTROL Save]**.

Para obter mais informações, consulte [Criar um email](../../designing/using/about-email-content-design.md#designing-an-email-content-from-scratch).

**Tópicos relacionados:**

* [Atividade de consulta](../..//automating/using/query.md)
* [Atividade do agendador](../..//automating/using/scheduler.md)
* [Entrega por email](../..//automating/using/email-delivery.md)
* [Canal de email](../..//channels/using/creating-an-email.md)
