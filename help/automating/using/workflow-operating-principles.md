---
title: Princípios operacionais do fluxo de trabalho
description: Saiba mais sobre os principais aspectos dos fluxos de trabalho.
page-status-flag: nunca ativado
uuid: 85755e85-617b-4a9b-bb30-96ba8333f4f0
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: automatização
content-type: referência
topic-tags: sobre fluxos de trabalho e gerenciamento de dados
discoiquuid: 3a13785d-1ef7-4043-9927-2d495b83709f
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Princípios operacionais do fluxo de trabalho{#workflow-operating-principles}

Um fluxo de trabalho é uma **sequência de atividades** configuráveis. Cada atividade tem uma função específica no processo. O resultado de cada atividade é encaminhado para a seguinte atividade por uma **transição**, representada por uma seta.

O tipo de dados trocados entre uma atividade e outra pode afetar a forma como as seguintes atividades são configuradas. Por exemplo, se um público for estabelecido antes da atividade de entrega de email, ele poderá servir como o destino do email em questão.

É possível abrir atividades para verificar ou editar parâmetros antes ou depois de executar o fluxo de trabalho.

Você pode abrir transições para verificar se os dados enviados estão corretos durante ou após a execução do fluxo de trabalho. Para acessar a exibição detalhada das transições, é necessário verificar a opção **[!UICONTROL Keep interim results]** na seção **[!UICONTROL Execution]** das propriedades do fluxo de trabalho.

![](assets/workflow_overview.png)

