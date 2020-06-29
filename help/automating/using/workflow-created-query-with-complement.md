---
title: Criar entregas com um complemento
description: Este caso de uso mostra como criar delivery com um complemento.
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,segmentation
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 87e0611fae0560aca276caa3c4cf793e9c095d72
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 7%

---


# Criar entregas com um complemento {#deliveries-with-complement}

Você pode enviar um email para os clientes: um para clientes criados há menos de um ano, um para clientes criados há mais de um ano.

1. Em **[!UICONTROL Marketing Activities]**, clique **[!UICONTROL Create]** e selecione **[!UICONTROL Workflow]**.
1. Selecione **[!UICONTROL New Workflow]** como tipo de fluxo de trabalho e clique em **[!UICONTROL Next]**.
1. Insira as propriedades do fluxo de trabalho e clique em **[!UICONTROL Create]**.

## Criar uma atividade de Query {#create-a-query-activity}

1. Em **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, arraste e solte uma atividade de [Query](../../automating/using/query.md) .
1. Duplo clique na atividade.
1. Em **[!UICONTROL Shortcuts]**, arraste e solte **[!UICONTROL Profiles]** e selecione **[!UICONTROL email]** com o operador **[!UICONTROL is not empty]**.
1. Em **[!UICONTROL Shortcuts]**, arraste e solte **[!UICONTROL Profiles]** e selecione **[!UICONTROL no longer contact by email]** com o valor **[!UICONTROL no]**.
1. Clique em **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## Criar uma atividade de segmentação {#create-a-segmentation-activity}

1. Em **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, arraste e solte uma atividade de [Segmentação](../../automating/using/segmentation.md) e clique no duplo.
1. Passe o cursor do mouse sobre o segmento e clique em ![](assets/edit_darkgrey-24px.png) para clientes do público alvo adicionados este ano no banco de dados.
1. Arraste e solte **[!UICONTROL Profiles]** e selecione **[!UICONTROL Created]** com o tipo de filtro **[!UICONTROL Relative]**.
1. Altere **[!UICONTROL Level of precision]** para **[!UICONTROL Year]** e selecione **[!UICONTROL This year]**.
1. Clique **[!UICONTROL Confirm]** duas vezes.
1. Em **[!UICONTROL Advanced Options]**, marque **[!UICONTROL Generate complement]** para criar um segmento direcionando os recipient restantes.
1. Clique em **[!UICONTROL Confirm]**.
1. Clique em **[!UICONTROL Save]**.

![](assets/wf-complement-segmentation.png)

>[!NOTE]
>
>Para observar a estrutura da regra, clique em **[!UICONTROL Advanced Mode]**.

## Creating an Email delivery {#create-an-email-delivery}

1. Em **[!UICONTROL Activities]** > **[!UICONTROL Channels]**, arraste e solte uma atividade de delivery [de e-](../../automating/using/email-delivery.md) mail após cada segmento.
1. Clique na atividade e selecione ![](assets/edit_darkgrey-24px.png) para editar.
1. Selecione **[!UICONTROL Single send email]** e clique em **[!UICONTROL Next]**.
1. Selecione um modelo de email e clique em **[!UICONTROL Next]**.
1. Insira as propriedades do email e clique em **[!UICONTROL Next]**.
1. Para criar o layout do seu email, clique em **[!UICONTROL Email Designer]**.
1. Insira elementos ou selecione um modelo existente.
1. Personalize seu email com ofertas específicas para cada delivery.
1. Clique **[!UICONTROL Preview]** para verificar seu layout.
1. Clique em **[!UICONTROL Save]**.

Para obter mais informações, consulte a [criação de um email](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).

![](assets/wf-deliveries-with-a-complement.png)
