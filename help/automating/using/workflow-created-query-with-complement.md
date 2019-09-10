---
title: '" Caso de uso de fluxo de trabalho: Criação de entregas com um complemento "'
seo-title: '" Caso de uso de fluxo de trabalho: Criação de entregas com um complemento "'
description: '" Caso de uso de fluxo de trabalho: Criação de entregas com um complemento "'
seo-description: '" Caso de uso de fluxo de trabalho: Criação de entregas com um complemento "'
page-status-flag: nunca ativado
uuid: 396 a 3 de 1-6 ffa -4385-ac 9 f -15 fdeae 5 a 366
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizando
content-type: reference
topic-tags: execução-atividades
discoiquuid: 377821 e 6-69 f 8-41 cc-a 1 ad -8 a 2 f 5 ed 4 d 409
context-tags: fluxo de trabalho, caso de uso, segmentação
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 035726bbd3112058b9a89525a861521bc3b9867e

---


# Caso de uso de fluxo de trabalho: Criação de entregas com um complemento {#deliveries-with-complement}

Você pode enviar um email para os clientes: um para clientes criados há menos de um ano, um para os clientes criados mais de um ano atrás.

1. Em **[!UICONTROL Marketing Activities]**, clique **[!UICONTROL Create]** em e selecione **[!UICONTROL Workflow]**.
1. Selecione **[!UICONTROL New Workflow]** como tipo de fluxo de trabalho e clique **[!UICONTROL Next]** em.
1. Insira as propriedades do fluxo de trabalho e clique **[!UICONTROL Create]** em.

## Criar uma atividade de consulta {#create-a-query-activity}

1. Em **[!UICONTROL Activities]** &gt; **[!UICONTROL Targeting]**, arraste e solte a **[!UICONTROL Query activity]**![](assets/query.png).
1. Clique duas vezes na atividade.
1. Em **[!UICONTROL Shortcuts]**, arraste e solte **[!UICONTROL Profiles]** e selecione **[!UICONTROL email]** com o operador **[!UICONTROL is not empty]**.
1. Em **[!UICONTROL Shortcuts]**, arraste e solte **[!UICONTROL Profiles]** e selecione **[!UICONTROL no longer contact by email]** com o valor **[!UICONTROL no]**.
1. Click **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## Criar uma atividade de segmentação {#create-a-segmentation-activity}

1. Em **[!UICONTROL Activities]** &gt; **[!UICONTROL Targeting]**, arraste e solte **[!UICONTROL Segmentation]** uma atividade e clique duas vezes nele.
1. Passe o mouse sobre o segmento em seguida, clique ![](assets/edit_darkgrey-24px.png) em para direcionar os clientes adicionados deste ano no banco de dados.
1. Arraste e solte **[!UICONTROL Profiles]** e selecione **[!UICONTROL Created]** com o tipo **[!UICONTROL Relative]** de filtro.
1. Altere o **[!UICONTROL Level of precision]** para **[!UICONTROL Year]** e selecione **[!UICONTROL This year]**.
1. Clique **[!UICONTROL Confirm]** duas vezes.
1. Em **[!UICONTROL Advanced Options]**, marque **[!UICONTROL Generate complement]** para criar um segmento direcionado aos destinatários restantes.
1. Click **[!UICONTROL Confirm]**.
1. Click **[!UICONTROL Save]**.

![](assets/wf-complement-segmentation.png)

>[!NOTE]
>
>Para observar a estrutura da regra, clique **[!UICONTROL Advanced Mode]** em.

## Criação de uma entrega por email {#create-an-email-delivery}

1. Em **[!UICONTROL Activities]** &gt; **[!UICONTROL Channels]**, arraste e solte uma entrega de email após cada segmento.
1. Clique na atividade e selecione ![](assets/edit_darkgrey-24px.png) editar.
1. Selecione **[!UICONTROL Single send email]** e clique **[!UICONTROL Next]** em.
1. Selecione um modelo de e-mail e clique **[!UICONTROL Next]** em.
1. Insira as propriedades e clique **[!UICONTROL Next]** em.
1. Para criar o layout de seu email, clique **[!UICONTROL Email Designer]** em.
1. Inserir elementos ou selecionar um modelo existente.
1. Personalize seu email com ofertas específicas para cada entrega.
1. Clique **[!UICONTROL Preview]** em para verificar o layout.
1. Click **[!UICONTROL Save]**.

Para obter mais informações, consulte [Criar um email](../../designing/using/about-email-content-design.md#designing-an-email-content-from-scratch).

![](assets/wf-deliveries-with-a-complement.png)

**Tópicos relacionados:**

* [Consulta](../../automating/using/query.md)
* [Atividade de segmentação](../../automating/using/segmentation.md)
* [Entrega por email](../../automating/using/email-delivery.md)
