---
title: '" Caso de uso de fluxo de trabalho: Segmentação no local "'
seo-title: '" Caso de uso de fluxo de trabalho: Segmentação no local "'
description: '" Caso de uso de fluxo de trabalho: Segmentação no local "'
seo-description: '" Caso de uso de fluxo de trabalho: Segmentação no local "'
page-status-flag: nunca ativado
uuid: 396 a 3 de 1-6 ffa -4385-ac 9 f -15 fdeae 5 a 366
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizando
content-type: reference
topic-tags: execução-atividades
discoiquuid: 377821 e 6-69 f 8-41 cc-a 1 ad -8 a 2 f 5 ed 4 d 409
context-tags: 'fluxo de trabalho, caso de uso, consulta, segmentação, entrega '
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e77c8a65834009f2f7157d9535ae8e12e59244ff

---


# Caso de uso de fluxo de trabalho: Segmentação no local {#segmentation-on-location}

Você pode enviar um email de direcionamento para clientes com ofertas em suas lojas locais.

1. Em **[!UICONTROL Marketing Activities]**, clique **[!UICONTROL Create]** em e selecione **[!UICONTROL Workflow]**.
1. Selecione **[!UICONTROL New Workflow]** como tipo de fluxo de trabalho e clique **[!UICONTROL Next]** em.
1. Insira as propriedades do fluxo de trabalho e clique **[!UICONTROL Create]** em.

## Seleção de destinatários que podem ser acessados por email{#selecting-recipients-contactable-via-email}

1. Em **[!UICONTROL Activities]** &gt; **[!UICONTROL Targeting]**, arraste e solte a **[!UICONTROL Query activity]**![](assets/query.png).
1. Clique duas vezes na atividade.
1. Em **[!UICONTROL Shortcuts]**, arraste e solte **[!UICONTROL Profiles]** e selecione o campo **[!UICONTROL email]** com o operador **[!UICONTROL is not empty]**.
1. Em **[!UICONTROL Shortcuts]**, arraste e solte **[!UICONTROL Profiles]** e selecione o campo **[!UICONTROL no longer contact by email]** com o valor **[!UICONTROL no]**.
1. Clique **[!UICONTROL Confirm]** duas vezes.

## Criação de uma atividade de segmentação{#creating-a-segmentation-activity}

1. Arraste e solte uma **[!UICONTROL Segmentation]** atividade e clique duas vezes nele.
1. Clique no segmento em seguida, abra a transição para definir como meta as pessoas na primeira cidade. Aqui Boston.
1. Arraste e solte **[!UICONTROL Location]** e selecione **[!UICONTROL City]** com o operador **[!UICONTROL equals to]** e o valor **[!UICONTROL Boston]**.
Observação: Para atingir todas as pessoas que entraram em boston, não se preocupe com a opção desmarcar a opção distinção entre maiúsculas e minúsculas.
1. Click **[!UICONTROL Confirm]**.
1. Em **[!UICONTROL List of outbound segments]**, clique **[!UICONTROL Add an element]** e clique ![](assets/edit_darkgrey-24px.png) em para criar um segmento direcionado às pessoas na segunda cidade. Aqui Chicago.
1. Arraste e solte **[!UICONTROL Location]** , e selecione **[!UICONTROL City]** com o operador **[!UICONTROL equals to]** e digite **[!UICONTROL Chicago]** o valor.
1. Para atingir todas as pessoas que entraram em chicago, não se preocupe com a opção desmarcar a opção distinção entre maiúsculas e minúsculas.
1. Click **[!UICONTROL Confirm]**.

## Criação de uma entrega por email{#creating-an-email-delivery}

1. Em **[!UICONTROL Activities]** &gt; **[!UICONTROL Channels]**, arraste e solte um **[!UICONTROL Email Delivery]** após cada segmento.
1. Clique na atividade e selecione ![](assets/edit_darkgrey-24px.png) editar.
1. Selecione **[!UICONTROL Simple email]** e clique **[!UICONTROL Next]** em.
1. Selecione um modelo de e-mail e clique **[!UICONTROL Next]** em.
1. Insira as propriedades e clique **[!UICONTROL Next]** em.
1. Para criar o layout de seu email, clique **[!UICONTROL Email Designer]** em.
1. Inserir elementos ou selecionar um modelo existente.
1. Personalize seu email com ofertas específicas para cada localização.

Para obter mais informações, consulte [Criar um email](../../designing/using/about-email-content-design.md#designing-an-email-content-from-scratch).

1. Clique **[!UICONTROL Preview]** em para verificar o layout.
1. Click **[!UICONTROL Save]**.

**Tópicos relacionados:**

* [Atividade de consulta](../../automating/using/query.md)
* [Atividade de segmentação](../../automating/using/segmentation.md)
* [Entrega por email](../../automating/using/email-delivery.md)
