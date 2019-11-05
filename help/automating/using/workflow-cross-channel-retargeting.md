---
title: '"Caso de uso do fluxo de trabalho: Redefinição de metas para não-iniciantes"'
description: '"Caso de uso do fluxo de trabalho: Redefinição de metas para não-iniciantes"'
page-status-flag: nunca ativado
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: automatização
content-type: referência
topic-tags: atividades de execução
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: 'workflow,use-case,query,wait,delivery '
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Caso de uso do fluxo de trabalho: Fluxo de trabalho de redefinição de metas enviando uma nova entrega para não iniciantes{#retargeting-delivery-to-non-openers}

Você pode enviar um email para os clientes e, em seguida, um sms para aqueles que não abriram o email.

1. Em **[!UICONTROL Marketing Activities]**, clique **[!UICONTROL Create]** e selecione **[!UICONTROL Workflow]**.
1. Selecione **[!UICONTROL New Workflow]** como tipo de fluxo de trabalho e clique em **[!UICONTROL Next]**.
1. Insira as propriedades do fluxo de trabalho e clique em **[!UICONTROL Create]**.

## Criando uma atividade de consulta{#creating-a-query-activity}

1. Em **[!UICONTROL Activities]** &gt; **[!UICONTROL Targeting]**, arraste e solte um **[!UICONTROL Query activity]**![](assets/query.png).
1. Clique duas vezes na atividade.
1. Em **[!UICONTROL Shortcuts]**, arraste e solte **[!UICONTROL Profiles]** e selecione **[!UICONTROL email]** com o operador **[!UICONTROL is not empty]**.
1. Em **[!UICONTROL Shortcuts]**, arraste e solte **[!UICONTROL Profiles]** e selecione **[!UICONTROL no longer contact by email]** com o valor **[!UICONTROL no ]**.
1. Click **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## Criação de um delivery de email{#creating-an-email-delivery}

1. Arraste e solte um **[!UICONTROL Email delivery]** depois de cada segmento.
1. Clique na atividade e selecione ![](assets/edit_darkgrey-24px.png) para editar.
1. Selecione **[!UICONTROL Simple email]** e clique em **[!UICONTROL Next]**.
1. Selecione **[!UICONTROL Add an outbound transition without the population]** e clique em **[!UICONTROL Next]**.
1. Selecione um modelo de email e clique em **[!UICONTROL Next]**.
1. Insira as propriedades do email e clique em **[!UICONTROL Next]**.
1. Para criar o layout do seu email, clique em **[!UICONTROL Using the Email Designer]**.
1. Insira elementos ou selecione um modelo existente.
1. Personalize seu email com ofertas específicas para cada local.Para obter mais informações, consulte [criar um email](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).
1. Clique **[!UICONTROL Preview]** para verificar seu layout.
1. Click **[!UICONTROL Save]**.

## Direcionando não-iniciantes em uma atividade de consulta{#targeting-non-openers-in-a-query-activity}

1. Em **[!UICONTROL Activities]** &gt; **[!UICONTROL Execution]**, arraste e solte um **[!UICONTROL Wait activity]**![](assets/wait.png).
1. Em **[!UICONTROL Duration]**, clique em ![](assets/duration-icon.png) e selecione um dia.
1. Em **[!UICONTROL Activities]** &gt; **[!UICONTROL Targeting]**, arraste e solte um **[!UICONTROL Query activity]**![](assets/query.png).
1. Clique duas vezes na atividade.
1. Em **[!UICONTROL Shortcuts]**, arraste e solte **[!UICONTROL Tracking Logs]** e com o operador **[!UICONTROL exists]**.
1. Em **[!UICONTROL Shortcuts]**&gt; **[!UICONTROL Delivery]**, arraste e solte **[!UICONTROL delivery]** com o operador **[!UICONTROL is equal to]** e selecione a entrega como valor.
1. Em **[!UICONTROL Shortcuts]**&gt; **[!UICONTROL Delivery]**, arraste e solte **[!UICONTROL type]** e marque **[!UICONTROL Open]** como valor.
1. Selecione o operador entre as regras como **[!UICONTROL except]**.
1. Click **[!UICONTROL Confirm]**.

## Creating a sms delivery{#creating-a-sms-delivery}

1. Arraste e solte uma entrega sms após cada segmento.
1. Clique na atividade e selecione ![](assets/edit_darkgrey-24px.png) para editar.
1. Selecione **[!UICONTROL Simple sms]** e clique em **[!UICONTROL Next]**.
1. Selecione um modelo sms e clique em **[!UICONTROL Next]**.
1. Insira as propriedades do sms e clique em **[!UICONTROL Next]**.
1. Para criar o layout do seu sms, clique em **[!UICONTROL Email Designer]**.
1. Insira elementos ou selecione um modelo existente.
1. Personalize seus sms com ofertas específicas para cada local.
Para obter mais informações, consulte a [criação de um sms](../../channels/using/creating-an-sms-message.md).
1. Clique **[!UICONTROL Preview]** para verificar seu layout.
1. Click **[!UICONTROL Save]**.

![](assets/wf-retargeting-non-openers.png)

**Tópicos relacionados:**

* [Consulta](../../automating/using/query.md)
* [Entrega por SMS](../../automating/using/sms-delivery.md)
* [Entrega por email](../../automating/using/email-delivery.md)
* [Canal de email](../../channels/using/creating-an-email.md)
