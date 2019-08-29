---
title: '" Caso de uso de fluxo de trabalho: " Redefinição de metas "'
seo-title: '" Caso de uso de fluxo de trabalho: " Redefinição de metas "'
description: '" Caso de uso de fluxo de trabalho: " Redefinição de metas "'
seo-description: '" Caso de uso de fluxo de trabalho: " Redefinição de metas "'
page-status-flag: nunca ativado
uuid: 396 a 3 de 1-6 ffa -4385-ac 9 f -15 fdeae 5 a 366
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizando
content-type: reference
topic-tags: execução-atividades
discoiquuid: 377821 e 6-69 f 8-41 cc-a 1 ad -8 a 2 f 5 ed 4 d 409
context-tags: 'fluxo de trabalho, caso de uso, consulta, espera, entrega '
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f57775ec88925d43046fe4162f2753c189d50c62

---


# Caso de uso de fluxo de trabalho: Fluxo de trabalho de redefinição de metas enviando uma nova entrega para não-openers{#retargeting-delivery-to-non-openers}

Você pode enviar um email para os clientes e depois um sms para aqueles que não abriram o email.

1. Em **[!UICONTROL Marketing Activities]**, clique **[!UICONTROL Create]** em e selecione **[!UICONTROL Workflow]**.
1. Selecione **[!UICONTROL New Workflow]** como tipo de fluxo de trabalho e clique **[!UICONTROL Next]** em.
1. Insira as propriedades do fluxo de trabalho e clique **[!UICONTROL Create]** em.

## Criação de uma atividade de consulta{#creating-a-query-activity}

1. Em **[!UICONTROL Activities]** &gt; **[!UICONTROL Targeting]**, arraste e solte a **[!UICONTROL Query activity]**![](assets/query.png).
1. Clique duas vezes na atividade.
1. Em **[!UICONTROL Shortcuts]**, arraste e solte **[!UICONTROL Profiles]** e selecione **[!UICONTROL email]** com o operador **[!UICONTROL is not empty]**.
1. Em **[!UICONTROL Shortcuts]**, arraste e solte **[!UICONTROL Profiles]** e selecione **[!UICONTROL no longer contact by email]** com o valor **[!UICONTROL no ]**.
1. Click **[!UICONTROL Confirm]**.

## Criação de uma entrega por email{#creating-an-email-delivery}

1. Arraste e solte uma entrega[!UICONTROL Email delivery]de email**** após cada segmento.
1. Clique na atividade e selecione ![](assets/edit_darkgrey-24px.png) editar.
1. Selecione **[!UICONTROL Simple email]** e clique **[!UICONTROL Next]** em.
1. Selecione **[!UICONTROL Add an outbound transition without the population]** e clique **[!UICONTROL Next]** em.
1. Selecione um modelo de e-mail e clique **[!UICONTROL Next]** em.
1. Insira as propriedades e clique **[!UICONTROL Next]** em.
1. Renomeie a oferta **de email de email**.
1. Para criar o layout de seu email, clique **[!UICONTROL Using the Email Designer]** em.
1. Inserir elementos ou selecionar um modelo existente.
1. Personalize seu email com ofertas específicas para cada localização. Para obter mais informações, consulte [Criar um email](../../designing/using/about-email-content-design.md#designing-an-email-content-from-scratch).
1. Clique **[!UICONTROL Preview]** em para verificar o layout.
1. Click **[!UICONTROL Save]**.

## Direcionamento de não-openers em uma atividade de consulta{#targeting-non-openers-in-a-query-activity}

1. Em **[!UICONTROL Activities]** &gt; **[!UICONTROL Execution]**, arraste e solte a **[!UICONTROL Wait activity]**![](assets/wait.png).
1. Em **[!UICONTROL Duration]**, clique ![](assets/duration-icon.png) em e selecione um dia.
1. Em **[!UICONTROL Activities]** &gt; **[!UICONTROL Targeting]**, arraste e solte a **[!UICONTROL Query activity]**![](assets/query.png).
1. Clique duas vezes na atividade.
1. Em **[!UICONTROL Shortcuts]**, arraste e solte **[!UICONTROL Tracking Logs]** e com o operador **[!UICONTROL exists]**.
1. Em **[!UICONTROL Shortcuts]**&gt; **[!UICONTROL Delivery]**, arraste e solte **[!UICONTROL delivery]** com o operador **[!UICONTROL is equal to]** e selecione a entrega como valor.
1. Em **[!UICONTROL Shortcuts]**&gt; **[!UICONTROL Delivery]**, arraste e solte **[!UICONTROL type]** e verifique **[!UICONTROL Open]** como valor.
1. Selecione o operador entre as regras como **[!UICONTROL except]**.
1. Click **[!UICONTROL Confirm]**.

## Criação de uma entrega sms{#creating-a-sms-delivery}

1. Arraste e solte uma entrega sms após cada segmento.
1. Clique na atividade e selecione ![](assets/edit_darkgrey-24px.png) editar.
1. Selecione **[!UICONTROL Simple sms]** e clique **[!UICONTROL Next]** em.
1. Selecione um modelo de sms e clique **[!UICONTROL Next]** em.
1. Insira as propriedades sms e clique **[!UICONTROL Next]** em.
1. Para criar o layout de seu SMS, clique **[!UICONTROL Email Designer]** em.
1. Inserir elementos ou selecionar um modelo existente.
1. Personalize o sms com ofertas específicas para cada localização.
Para obter mais informações, consulte [Criar um sms](../../channels/using/creating-an-sms-message.md).
1. Clique **[!UICONTROL Preview]** em para verificar o layout.
1. Click **[!UICONTROL Save]**.

**Tópicos relacionados:**

* [Consulta](../../automating/using/query.md)
* [entrega SMS](../../automating/using/sms-delivery.md)
* [Entrega por email](../../automating/using/email-delivery.md)
* [Canal de email](../../channels/using/creating-an-email.md)
