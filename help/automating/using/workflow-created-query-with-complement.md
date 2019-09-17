---
title: '"Caso de uso do fluxo de trabalho: Criar entregas com um complemento"'
seo-title: '"Caso de uso do fluxo de trabalho: Criar entregas com um complemento"'
description: '"Caso de uso do fluxo de trabalho: Criar entregas com um complemento"'
seo-description: '"Caso de uso do fluxo de trabalho: Criar entregas com um complemento"'
page-status-flag: nunca ativado
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: automatização
content-type: referência
topic-tags: atividades de execução
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: fluxo de trabalho,caso de uso,segmentação
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f7e56dcb4c2bbdc802c9d271d4a44d9a72b239ed

---


# Caso de uso do fluxo de trabalho: Criação de entregas com um complemento {#deliveries-with-complement}

Você pode enviar um email para os clientes: um para clientes criados há menos de um ano, um para clientes criados há mais de um ano.

1. Em **[!UICONTROL Marketing Activities]**, clique **[!UICONTROL Create]** e selecione **[!UICONTROL Workflow]**.
1. Selecione **[!UICONTROL New Workflow]** como tipo de fluxo de trabalho e clique em **[!UICONTROL Next]**.
1. Insira as propriedades do fluxo de trabalho e clique em **[!UICONTROL Create]**.

## Criar uma atividade de consulta {#create-a-query-activity}

1. Em **[!UICONTROL Activities]** &gt; **[!UICONTROL Targeting]**, arraste e solte um **[!UICONTROL Query activity]**![](assets/query.png).
1. Clique duas vezes na atividade.
1. Em **[!UICONTROL Shortcuts]**, arraste e solte **[!UICONTROL Profiles]** e selecione **[!UICONTROL email]** com o operador **[!UICONTROL is not empty]**.
1. Em **[!UICONTROL Shortcuts]**, arraste e solte **[!UICONTROL Profiles]** e selecione **[!UICONTROL no longer contact by email]** com o valor **[!UICONTROL no]**.
1. Click **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## Criar uma atividade de segmentação {#create-a-segmentation-activity}

1. Em **[!UICONTROL Activities]** &gt; **[!UICONTROL Targeting]**, arraste e solte uma **[!UICONTROL Segmentation]** atividade e clique duas vezes nela.
1. Passe o mouse sobre o segmento e clique em para direcionar clientes adicionados este ano ao banco de dados. ![](assets/edit_darkgrey-24px.png)
1. Arraste e solte **[!UICONTROL Profiles]** e selecione **[!UICONTROL Created]** com o tipo de filtro **[!UICONTROL Relative]**.
1. Altere **[!UICONTROL Level of precision]** para **[!UICONTROL Year]** e selecione **[!UICONTROL This year]**.
1. Clique **[!UICONTROL Confirm]** duas vezes.
1. Em **[!UICONTROL Advanced Options]**, marque **[!UICONTROL Generate complement]** para criar um segmento direcionado para os destinatários restantes.
1. Click **[!UICONTROL Confirm]**.
1. Click **[!UICONTROL Save]**.

![](assets/wf-complement-segmentation.png)

>[!NOTE]
>
>Para observar a estrutura da regra, clique em **[!UICONTROL Advanced Mode]**.

## Criação de uma entrega por email {#create-an-email-delivery}

1. Em **[!UICONTROL Activities]** &gt; **[!UICONTROL Channels]**, arraste e solte uma entrega de email após cada segmento.
1. Clique na atividade e selecione ![](assets/edit_darkgrey-24px.png) para editar.
1. Selecione **[!UICONTROL Single send email]** e clique em **[!UICONTROL Next]**.
1. Selecione um modelo de email e clique em **[!UICONTROL Next]**.
1. Insira as propriedades do email e clique em **[!UICONTROL Next]**.
1. Para criar o layout do seu email, clique em **[!UICONTROL Email Designer]**.
1. Insira elementos ou selecione um modelo existente.
1. Personalize seu email com ofertas específicas para cada entrega.
1. Clique **[!UICONTROL Preview]** para verificar seu layout.
1. Click **[!UICONTROL Save]**.

Para obter mais informações, consulte a [criação de um email](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).

![](assets/wf-deliveries-with-a-complement.png)

**Tópicos relacionados:**

* [Consulta](../../automating/using/query.md)
* [Atividade de segmentação](../../automating/using/segmentation.md)
* [Entrega por email](../../automating/using/email-delivery.md)
