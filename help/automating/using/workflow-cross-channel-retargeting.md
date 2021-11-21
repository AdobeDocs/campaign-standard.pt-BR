---
title: Redirecionamento de não iniciadores
description: Este caso de uso mostra como redirecionar não abridores.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: workflow,use-case,query,wait,delivery
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: cba4e5c6-8acd-47a1-824e-14415e90d451
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 38%

---

# Workflow de redirecionamento enviando um novo delivery para não abridores{#retargeting-delivery-to-non-openers}

Você pode enviar um email para clientes e depois um sms para aqueles que não abriram o email.

1. Em **[!UICONTROL Marketing Activities]**, clique em **[!UICONTROL Create]** e selecione **[!UICONTROL Workflow]**.
1. Selecione **[!UICONTROL New Workflow]** como tipo de fluxo de trabalho e clique em **[!UICONTROL Next]**.
1. Insira as propriedades do fluxo de trabalho e clique em **[!UICONTROL Create]**.

## Criação de uma atividade de query{#creating-a-query-activity}

1. Em **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, arraste e solte uma atividade de [Query](../../automating/using/query.md).
1. Clique duas vezes na atividade.
1. Em **[!UICONTROL Shortcuts]**, arrastar e soltar **[!UICONTROL Profiles]** e selecione **[!UICONTROL email]** com o operador **[!UICONTROL is not empty]**.
1. Em **[!UICONTROL Shortcuts]**, arrastar e soltar **[!UICONTROL Profiles]** e selecione **[!UICONTROL no longer contact by email]** com o valor **[!UICONTROL no ]**.
1. Clique em **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## Criação de uma entrega de email{#creating-an-email-delivery}

1. Arraste e solte um [Delivery por email](../../automating/using/email-delivery.md) após cada segmento.
1. Clique na atividade e selecione ![](assets/edit_darkgrey-24px.png) para editar.
1. Selecione **[!UICONTROL Simple email]** e clique em **[!UICONTROL Next]**.
1. Selecione **[!UICONTROL Add an outbound transition without the population]** e clique em **[!UICONTROL Next]**.
1. Selecione um template de email e clique em **[!UICONTROL Next]**.
1. Insira as propriedades do email e clique em **[!UICONTROL Next]**.
1. Para criar o layout do email, clique em **[!UICONTROL Using the Email Designer]**.
1. Insira elementos ou selecione um template.
1. Personalize seu email com ofertas específicas para cada local.Para obter mais informações, consulte [criar um email](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).
1. Clique em **[!UICONTROL Preview]** para verificar o layout.
1. Clique em **[!UICONTROL Save]**.

## Direcionamento de não abridores em uma atividade de query{#targeting-non-openers-in-a-query-activity}

1. Em **[!UICONTROL Activities]** > **[!UICONTROL Execution]**, arraste e solte uma [Aguardar](../../automating/using/wait.md) atividade .
1. Em **[!UICONTROL Duration]**, clique em ![](assets/duration-icon.png) e selecione um dia.
1. Em **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, arraste e solte uma **[!UICONTROL Query activity]**.
1. Clique duas vezes na atividade.
1. Em **[!UICONTROL Shortcuts]**, arrastar e soltar **[!UICONTROL Tracking Logs]** e com o operador **[!UICONTROL exists]**.
1. Em **[!UICONTROL Shortcuts]**> **[!UICONTROL Delivery]**, arrastar e soltar **[!UICONTROL delivery]** com o operador **[!UICONTROL is equal to]** e selecione o delivery como valor.
1. Em **[!UICONTROL Shortcuts]**> **[!UICONTROL Delivery]**, arrastar e soltar **[!UICONTROL type]** e verificar **[!UICONTROL Open]** como valor.
1. Selecione o operador entre regras como **[!UICONTROL except]**.
1. Clique em **[!UICONTROL Confirm]**.

## Criação de um delivery de sms{#creating-a-sms-delivery}

1. Arraste e solte um delivery de sms após cada segmento.
1. Clique na atividade e selecione ![](assets/edit_darkgrey-24px.png) para editar.
1. Selecione **[!UICONTROL Simple sms]** e clique em **[!UICONTROL Next]**.
1. Selecione um modelo de sms e clique em **[!UICONTROL Next]**.
1. Insira as propriedades do sms e clique em **[!UICONTROL Next]**.
1. Para criar o layout do seu sms, clique em **[!UICONTROL Email Designer]**.
1. Insira elementos ou selecione um template.
1. Personalize seu sms com ofertas específicas para cada local.
Para obter mais informações, consulte [Criação de um sms](../../channels/using/creating-an-sms-message.md) seção.
1. Clique em **[!UICONTROL Preview]** para verificar o layout.
1. Clique em **[!UICONTROL Save]**.

![](assets/wf-retargeting-non-openers.png)

**Tópicos relacionados:**

* [Canal de email](../../channels/using/creating-an-email.md)
