---
title: Criar entregas com um complemento
description: Este caso de uso mostra como criar deliveries com um complemento.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: workflow,use-case,segmentation
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 5cd71e07-f955-4c15-bdfb-14b0daccec1a
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 41%

---

# Criar entregas com um complemento {#deliveries-with-complement}

Você pode enviar um email para os clientes: um para clientes criados há menos de um ano, um para clientes criados há mais de um ano.

1. Em **[!UICONTROL Marketing Activities]**, clique em **[!UICONTROL Create]** e selecione **[!UICONTROL Workflow]**.
1. Selecione **[!UICONTROL New Workflow]** como tipo de fluxo de trabalho e clique em **[!UICONTROL Next]**.
1. Insira as propriedades do fluxo de trabalho e clique em **[!UICONTROL Create]**.

## Criar uma atividade Query {#create-a-query-activity}

1. Em **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, arraste e solte uma atividade de [Query](../../automating/using/query.md).
1. Clique duas vezes na atividade.
1. Em **[!UICONTROL Shortcuts]**, arrastar e soltar **[!UICONTROL Profiles]** e selecione **[!UICONTROL email]** com o operador **[!UICONTROL is not empty]**.
1. Em **[!UICONTROL Shortcuts]**, arrastar e soltar **[!UICONTROL Profiles]** e selecione **[!UICONTROL no longer contact by email]** com o valor **[!UICONTROL no]**.
1. Clique em **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## Criar uma atividade de segmentação {#create-a-segmentation-activity}

1. Em **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, arraste e solte uma [Segmentação](../../automating/using/segmentation.md) e clique duas vezes nela.
1. Passe o mouse sobre o segmento e clique em ![](assets/edit_darkgrey-24px.png) para direcionar clientes adicionados este ano no banco de dados.
1. Arrastar e soltar **[!UICONTROL Profiles]** e selecione **[!UICONTROL Created]** com o tipo de filtro **[!UICONTROL Relative]**.
1. Altere o **[!UICONTROL Level of precision]** para **[!UICONTROL Year]** e selecione **[!UICONTROL This year]**.
1. Clique em **[!UICONTROL Confirm]** duas vezes.
1. Em **[!UICONTROL Advanced Options]**, verificar **[!UICONTROL Generate complement]** para criar um segmento direcionado aos recipients restantes.
1. Clique em **[!UICONTROL Confirm]**.
1. Clique em **[!UICONTROL Save]**.

![](assets/wf-complement-segmentation.png)

>[!NOTE]
>
>Para observar a estrutura da regra, clique em **[!UICONTROL Advanced Mode]**.

## Criação de um delivery de email {#create-an-email-delivery}

1. Em **[!UICONTROL Activities]** > **[!UICONTROL Channels]**, arraste e solte uma [Delivery por email](../../automating/using/email-delivery.md) atividade após cada segmento.
1. Clique na atividade e selecione ![](assets/edit_darkgrey-24px.png) para editar.
1. Selecione **[!UICONTROL Single send email]** e clique em **[!UICONTROL Next]**.
1. Selecione um template de email e clique em **[!UICONTROL Next]**.
1. Insira as propriedades do email e clique em **[!UICONTROL Next]**.
1. Para criar o layout do email, clique em **[!UICONTROL Email Designer]**.
1. Insira elementos ou selecione um template.
1. Personalize seu email com ofertas específicas para cada delivery.
1. Clique em **[!UICONTROL Preview]** para verificar o layout.
1. Clique em **[!UICONTROL Save]**.

Para obter mais informações, consulte [Design de email](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).

![](assets/wf-deliveries-with-a-complement.png)
