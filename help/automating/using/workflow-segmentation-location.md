---
title: Segmentação no local"
description: Este caso de uso mostra como executar a segmentação no local.
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,query,segmentation,delivery
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 83%

---


# Segmentação no local {#segmentation-on-location}

Você pode enviar um email de direcionamento para clientes com ofertas em suas lojas locais.

1. Em **[!UICONTROL Marketing Activities]**, clique em **[!UICONTROL Create]** e selecione **[!UICONTROL Workflow]**.
1. Selecione **[!UICONTROL New Workflow]** como tipo de fluxo de trabalho e clique em **[!UICONTROL Next]**.
1. Insira as propriedades do fluxo de trabalho e clique em **[!UICONTROL Create]**.

## Seleção dos recipients contatáveis por email{#selecting-recipients-contactable-via-email}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, drag and drop a [Query](../../automating/using/query.md) activity ![](assets/query.png).
1. Clique duas vezes na atividade.
1. Em **[!UICONTROL Shortcuts]**, arraste e solte **[!UICONTROL Profiles]** e selecione o campo **[!UICONTROL email]** com o operador **[!UICONTROL is not empty]**.
1. Em **[!UICONTROL Shortcuts]**, arraste e solte **[!UICONTROL Profiles]** e selecione o campo **[!UICONTROL no longer contact by email]** com o valor **[!UICONTROL no]**.
1. Clique em **[!UICONTROL Confirm]** duas vezes.

![](assets/wf-complement-query.png)

## Criação de uma atividade de Segmentação{#creating-a-segmentation-activity}

1. Drag and drop a [Segmentation](../../automating/using/segmentation.md) activity and double-click it.
1. Clique no segmento e abra a transição para segmentar as pessoas na primeira cidade. Neste caso, Boston.
1. Arraste e solte a **[!UICONTROL Location]** e selecione **[!UICONTROL City]** com o operador **[!UICONTROL equals to]** e o valor **[!UICONTROL Boston]**.
Observação: para acessar todas as pessoas que digitaram Boston, desmarque a opção que faz distinção entre maiúsculas e minúsculas.
1. Clique em **[!UICONTROL Confirm]**.
1. Em **[!UICONTROL List of outbound segments]**, clique em **[!UICONTROL Add an element]** e clique em ![](assets/edit_darkgrey-24px.png) para criar um segmento direcionado às pessoas na segunda cidade. Neste caso, Chicago.
1. Arraste e solte a **[!UICONTROL Location]**, selecione **[!UICONTROL City]** com o operador **[!UICONTROL equals to]** e insira **[!UICONTROL Chicago]** no valor.
1. Para acessar todas as pessoas que digitaram Chicago, desconsidere a opção que faz distinção entre maiúsculas e minúsculas.
1. Clique em **[!UICONTROL Confirm]**.

## Criação de um delivery de email{#creating-an-email-delivery}

1. Em **[!UICONTROL Activities]** > **[!UICONTROL Channels]**, arraste e solte uma atividade de delivery [de e-](../../automating/using/email-delivery.md) mail após cada segmento.
1. Clique na atividade e selecione ![](assets/edit_darkgrey-24px.png) para editar.
1. Selecione **[!UICONTROL Simple email]** e clique em **[!UICONTROL Next]**.
1. Selecione um template de email e clique em **[!UICONTROL Next]**.
1. Insira as propriedades do email e clique em **[!UICONTROL Next]**.
1. Para criar o layout do email, clique em **[!UICONTROL Email Designer]**.
1. Insira elementos ou selecione um template.
1. Personalize seu email com ofertas específicas para cada local.

   Para obter mais informações, consulte [Design de email](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).

1. Clique em **[!UICONTROL Preview]** para verificar o layout.
1. Clique em **[!UICONTROL Save]**.

![](assets/wf-segmentation-location.png)

