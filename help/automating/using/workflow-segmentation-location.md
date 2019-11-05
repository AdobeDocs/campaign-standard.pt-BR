---
title: '"Caso de uso do fluxo de trabalho: Segmentação no local"'
description: '"Caso de uso do fluxo de trabalho: Segmentação no local"'
page-status-flag: nunca ativado
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: automatização
content-type: referência
topic-tags: atividades de execução
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: 'fluxo de trabalho,use-case,consulta,segmentação,entrega '
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Caso de uso do fluxo de trabalho: Segmentação no local {#segmentation-on-location}

Você pode enviar um email de definição de metas para clientes com ofertas em suas lojas locais.

1. Em **[!UICONTROL Marketing Activities]**, clique **[!UICONTROL Create]** e selecione **[!UICONTROL Workflow]**.
1. Selecione **[!UICONTROL New Workflow]** como tipo de fluxo de trabalho e clique em **[!UICONTROL Next]**.
1. Insira as propriedades do fluxo de trabalho e clique em **[!UICONTROL Create]**.

## Selecionar destinatários contatáveis por email{#selecting-recipients-contactable-via-email}

1. Em **[!UICONTROL Activities]** &gt; **[!UICONTROL Targeting]**, arraste e solte um **[!UICONTROL Query activity]**![](assets/query.png).
1. Clique duas vezes na atividade.
1. Em **[!UICONTROL Shortcuts]**, arraste e solte **[!UICONTROL Profiles]** e selecione o campo **[!UICONTROL email]** com o operador **[!UICONTROL is not empty]**.
1. Em **[!UICONTROL Shortcuts]**, arraste e solte **[!UICONTROL Profiles]** e selecione o campo **[!UICONTROL no longer contact by email]** com o valor **[!UICONTROL no]**.
1. Clique **[!UICONTROL Confirm]** duas vezes.

![](assets/wf-complement-query.png)

## Criação de uma atividade de segmentação{#creating-a-segmentation-activity}

1. Arraste e solte uma **[!UICONTROL Segmentation]** atividade e clique duas vezes nela.
1. Clique no segmento e abra a transição para direcionar as pessoas na primeira cidade. Aqui Boston.
1. Arraste e solte **[!UICONTROL Location]** e selecione **[!UICONTROL City]** com o operador **[!UICONTROL equals to]** e o valor **[!UICONTROL Boston]**.
Observação: Para acessar todas as pessoas que entraram em Boston, desmarque a opção que faz distinção entre maiúsculas e minúsculas.
1. Click **[!UICONTROL Confirm]**.
1. Em **[!UICONTROL List of outbound segments]**, clique **[!UICONTROL Add an element]** e clique em ![](assets/edit_darkgrey-24px.png) para criar um segmento direcionando pessoas na segunda cidade. Aqui Chicago.
1. Arraste e solte **[!UICONTROL Location]** e selecione **[!UICONTROL City]** com o operador **[!UICONTROL equals to]** e insira **[!UICONTROL Chicago]** o valor.
1. Para acessar todas as pessoas que entraram em Chicago, desconsidere a opção que diferencia maiúsculas e minúsculas.
1. Click **[!UICONTROL Confirm]**.

## Criação de um delivery de email{#creating-an-email-delivery}

1. Em **[!UICONTROL Activities]** &gt; **[!UICONTROL Channels]**, arraste e solte um **[!UICONTROL Email Delivery]** depois de cada segmento.
1. Clique na atividade e selecione ![](assets/edit_darkgrey-24px.png) para editar.
1. Selecione **[!UICONTROL Simple email]** e clique em **[!UICONTROL Next]**.
1. Selecione um modelo de email e clique em **[!UICONTROL Next]**.
1. Insira as propriedades do email e clique em **[!UICONTROL Next]**.
1. Para criar o layout do seu email, clique em **[!UICONTROL Email Designer]**.
1. Insira elementos ou selecione um modelo existente.
1. Personalize seu email com ofertas específicas para cada local.

Para obter mais informações, consulte a [criação de um email](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).

1. Clique **[!UICONTROL Preview]** para verificar seu layout.
1. Click **[!UICONTROL Save]**.

![](assets/wf-segmentation-location.png)

**Tópicos relacionados:**

* [Atividade de consulta](../../automating/using/query.md)
* [Atividade de segmentação](../../automating/using/segmentation.md)
* [Entrega por email](../../automating/using/email-delivery.md)
