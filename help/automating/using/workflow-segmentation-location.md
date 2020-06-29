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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 3%

---


# Segmentação no local {#segmentation-on-location}

Você pode enviar um email de definição de metas para clientes com ofertas em suas lojas locais.

1. Em **[!UICONTROL Marketing Activities]**, clique **[!UICONTROL Create]** e selecione **[!UICONTROL Workflow]**.
1. Selecione **[!UICONTROL New Workflow]** como tipo de fluxo de trabalho e clique em **[!UICONTROL Next]**.
1. Insira as propriedades do fluxo de trabalho e clique em **[!UICONTROL Create]**.

## Selecionar recipient contatáveis por email{#selecting-recipients-contactable-via-email}

1. Em **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, arraste e solte uma atividade de [Query](../../automating/using/query.md) ![](assets/query.png).
1. Duplo clique na atividade.
1. Em **[!UICONTROL Shortcuts]**, arraste e solte **[!UICONTROL Profiles]** e selecione o campo **[!UICONTROL email]** com o operador **[!UICONTROL is not empty]**.
1. Em **[!UICONTROL Shortcuts]**, arraste e solte **[!UICONTROL Profiles]** e selecione o campo **[!UICONTROL no longer contact by email]** com o valor **[!UICONTROL no]**.
1. Clique **[!UICONTROL Confirm]** duas vezes.

![](assets/wf-complement-query.png)

## Criação de uma atividade de segmentação{#creating-a-segmentation-activity}

1. Arraste e solte uma atividade de [segmentação](../../automating/using/segmentation.md) e clique com o duplo nele.
1. Clique no segmento e abra a transição para públicos alvos na primeira cidade. Aqui Boston.
1. Arraste e solte **[!UICONTROL Location]** e selecione **[!UICONTROL City]** com o operador **[!UICONTROL equals to]** e o valor **[!UICONTROL Boston]**.
Observação: Para acessar todas as pessoas que entraram em Boston, desmarque a opção que faz distinção entre maiúsculas e minúsculas.
1. Clique em **[!UICONTROL Confirm]**.
1. Em **[!UICONTROL List of outbound segments]**, clique **[!UICONTROL Add an element]** e clique em ![](assets/edit_darkgrey-24px.png) para criar um segmento direcionando pessoas na segunda cidade. Aqui Chicago.
1. Arraste e solte **[!UICONTROL Location]** e selecione **[!UICONTROL City]** com o operador **[!UICONTROL equals to]** e insira **[!UICONTROL Chicago]** o valor.
1. Para chegar a todas as pessoas que entraram em Chicago, desconsidere a opção que faz distinção entre maiúsculas e minúsculas.
1. Clique em **[!UICONTROL Confirm]**.

## Criação de um delivery de email{#creating-an-email-delivery}

1. Em **[!UICONTROL Activities]** > **[!UICONTROL Channels]**, arraste e solte uma atividade de delivery [de e-](../../automating/using/email-delivery.md) mail após cada segmento.
1. Clique na atividade e selecione ![](assets/edit_darkgrey-24px.png) para editar.
1. Selecione **[!UICONTROL Simple email]** e clique em **[!UICONTROL Next]**.
1. Selecione um modelo de email e clique em **[!UICONTROL Next]**.
1. Insira as propriedades do email e clique em **[!UICONTROL Next]**.
1. Para criar o layout do seu email, clique em **[!UICONTROL Email Designer]**.
1. Insira elementos ou selecione um modelo existente.
1. Personalize seu email com ofertas específicas para cada local.

   Para obter mais informações, consulte a [criação de um email](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).

1. Clique **[!UICONTROL Preview]** para verificar seu layout.
1. Clique em **[!UICONTROL Save]**.

![](assets/wf-segmentation-location.png)

