---
title: Redirecionamento de não-iniciadores
description: Este caso de uso mostra como redirecionar não-iniciantes.
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,query,wait,delivery
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 87e0611fae0560aca276caa3c4cf793e9c095d72
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 7%

---


# Fluxo de trabalho de redefinição de metas enviando um novo delivery para não iniciantes{#retargeting-delivery-to-non-openers}

Você pode enviar um e-mail para os clientes e, em seguida, um sms para aqueles que não abriram o e-mail.

1. Em **[!UICONTROL Marketing Activities]**, clique **[!UICONTROL Create]** e selecione **[!UICONTROL Workflow]**.
1. Selecione **[!UICONTROL New Workflow]** como tipo de fluxo de trabalho e clique em **[!UICONTROL Next]**.
1. Insira as propriedades do fluxo de trabalho e clique em **[!UICONTROL Create]**.

## Creating a query activity{#creating-a-query-activity}

1. Em **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, arraste e solte uma atividade de [Query](../../automating/using/query.md) .
1. Duplo clique na atividade.
1. Em **[!UICONTROL Shortcuts]**, arraste e solte **[!UICONTROL Profiles]** e selecione **[!UICONTROL email]** com o operador **[!UICONTROL is not empty]**.
1. Em **[!UICONTROL Shortcuts]**, arraste e solte **[!UICONTROL Profiles]** e selecione **[!UICONTROL no longer contact by email]** com o valor **[!UICONTROL no ]**.
1. Clique em **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## Criação de um delivery de email{#creating-an-email-delivery}

1. Arraste e solte um delivery [de](../../automating/using/email-delivery.md) email após cada segmento.
1. Clique na atividade e selecione ![](assets/edit_darkgrey-24px.png) para editar.
1. Selecione **[!UICONTROL Simple email]** e clique em **[!UICONTROL Next]**.
1. Selecione **[!UICONTROL Add an outbound transition without the population]** e clique em **[!UICONTROL Next]**.
1. Selecione um modelo de email e clique em **[!UICONTROL Next]**.
1. Insira as propriedades do email e clique em **[!UICONTROL Next]**.
1. Para criar o layout do seu email, clique em **[!UICONTROL Using the Email Designer]**.
1. Insira elementos ou selecione um modelo existente.
1. Personalize seu email com ofertas específicas para cada local.Para obter mais informações, consulte [criar um email](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).
1. Clique **[!UICONTROL Preview]** para verificar seu layout.
1. Clique em **[!UICONTROL Save]**.

## Direcionando não-iniciantes em uma atividade de query{#targeting-non-openers-in-a-query-activity}

1. Em **[!UICONTROL Activities]** > **[!UICONTROL Execution]**, arraste e solte uma atividade de [espera](../../automating/using/wait.md) .
1. Em **[!UICONTROL Duration]**, clique em ![](assets/duration-icon.png) e selecione um dia.
1. Em **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, arraste e solte um **[!UICONTROL Query activity]**.
1. Duplo clique na atividade.
1. Em **[!UICONTROL Shortcuts]**, arraste e solte **[!UICONTROL Tracking Logs]** e com o operador **[!UICONTROL exists]**.
1. Em **[!UICONTROL Shortcuts]**> **[!UICONTROL Delivery]**, arraste e solte **[!UICONTROL delivery]** com o operador **[!UICONTROL is equal to]** e selecione o delivery como valor.
1. Em **[!UICONTROL Shortcuts]**> **[!UICONTROL Delivery]**, arraste e solte **[!UICONTROL type]** e marque **[!UICONTROL Open]** como valor.
1. Selecione o operador entre as regras como **[!UICONTROL except]**.
1. Clique em **[!UICONTROL Confirm]**.

## Creating a sms delivery{#creating-a-sms-delivery}

1. Arraste e solte um delivery sms após cada segmento.
1. Clique na atividade e selecione ![](assets/edit_darkgrey-24px.png) para editar.
1. Selecione **[!UICONTROL Simple sms]** e clique em **[!UICONTROL Next]**.
1. Selecione um modelo sms e clique em **[!UICONTROL Next]**.
1. Insira as propriedades do sms e clique em **[!UICONTROL Next]**.
1. Para criar o layout do seu sms, clique em **[!UICONTROL Email Designer]**.
1. Insira elementos ou selecione um modelo existente.
1. Personalize seus sms com ofertas específicas para cada local.
Para obter mais informações, consulte a seção [Design e sms](../../channels/using/creating-an-sms-message.md) .
1. Clique **[!UICONTROL Preview]** para verificar seu layout.
1. Clique em **[!UICONTROL Save]**.

![](assets/wf-retargeting-non-openers.png)

**Tópicos relacionados:**

* [Canal de email](../../channels/using/creating-an-email.md)
