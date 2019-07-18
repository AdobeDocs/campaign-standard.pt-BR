---
title: Sobre públicos-alvo
seo-title: Sobre públicos-alvo
description: Sobre públicos-alvo
seo-description: Saiba como criar públicos-alvo de uma consulta, uma lista ou um arquivo e importá-los da Adobe Experience Cloud.
page-status-flag: nunca ativado
uuid: b 3996642-96 ec -489 e-b 146-c 8 c 2 cb 52 aa 32
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: públicos-alvo
content-type: reference
topic-tags: gerenciamento-público-alvo
discoiquuid: 750 asu 8 d -67 a 5-4180-bfec -2 a 8 e 3098 c 812
context-tags: público-alvo, assistente; público-alvo, visão geral; entrega, público-alvo, voltar
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6a877d878f01fa1e541dc20b8b0941602113d15b

---


# About audiences{#about-audiences}

Um público é uma lista de perfis com base em regras e atributos.

O Adobe Campaign permite que você crie seus públicos manualmente usando consultas ou usando automaticamente fluxos de trabalho dedicados. Você também pode usar públicos-alvo compartilhados da Adobe Experience Cloud. All of the audiences are regrouped into a list that can be accessed via the **[!UICONTROL Audiences]** card on the Adobe Campaign home page or from the **[!UICONTROL Audiences]** link.

![](assets/audience_1.png)

Você pode manipular diferentes tipos de público-alvo no Adobe Campaign. O tipo de público-alvo corresponde à forma como foi criado:

* **[!UICONTROL Query]**: indica que o público foi criado a partir de uma [consulta](../../automating/using/editing-queries.md#about-query-editor) em dados do banco de dados do Adobe Campaign da lista de públicos-alvo. Os públicos-alvo definidos por uma consulta são recalculados em cada uso adicional.
* **[!UICONTROL List]**: indica que o público é uma lista fixa de perfis. These lists are created in a [workflow](../../automating/using/discovering-workflows.md), where the data dimension is known when saving the audience. For example, after targeting activities (especially **[!UICONTROL Query]** ) or after the reconciliation of data imported from a file.
* **[!UICONTROL File]**: indica que o público foi criado diretamente a partir de um [fluxo de trabalho de importação](../../automating/using/load-file.md) de arquivo e que a dimensão de dados era desconhecida ao salvar o público-alvo.
* **[!UICONTROL Experience Cloud]**: indica que o público foi importado da Adobe Experience Cloud. Essa opção só estará disponível se a funcionalidade de compartilhamento de público-alvo tiver sido configurada. For more information, see [Importing an audience from the Adobe Experience Cloud](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md#importing-an-audience).

![](assets/audience_type_selection.png)

