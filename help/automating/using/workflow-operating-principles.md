---
title: Princípios operacionais de fluxo de trabalho
seo-title: Princípios operacionais de fluxo de trabalho
description: Princípios operacionais de fluxo de trabalho
seo-description: Saiba mais sobre os principais aspectos dos fluxos de trabalho.
page-status-flag: nunca ativado
uuid: 85755 e 85-617 b -4 a 9 b-bb 30-96 ba 8333 f 4 f 0
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizando
content-type: reference
topic-tags: sobre fluxos de trabalho e gerenciamento de dados
discoiquuid: 3 a 13785 d -1 ef 7-4043-9927-2 d 495 b 83709 f
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Workflow operating principles{#workflow-operating-principles}

A workflow is a **sequence of configurable activities**. Cada atividade possui uma função específica no processo. The result of each activity is forwarded to the following activity by a **transition**, represented by an arrow.

O tipo de dados trocados entre uma atividade e outro pode afetar a maneira como as seguintes atividades são configuradas. Por exemplo, se uma população for estabelecida antes da atividade de entrega de email, ela poderá servir como a meta para o email em questão.

É possível abrir atividades para verificar ou editar parâmetros antes ou depois de executar o fluxo de trabalho.

É possível abrir transições para verificar se os dados enviados estão corretos durante ou depois de executar o fluxo de trabalho. To access the detail view of the transitions, you have to check the **[!UICONTROL Keep interim results]** option in the **[!UICONTROL Execution]** section of the workflow properties.

![](assets/workflow_overview.png)

