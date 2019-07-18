---
title: Teste
seo-title: Teste
description: Teste
seo-description: A atividade Testar ativa uma transição com base em um resultado do teste.
page-status-flag: nunca ativado
uuid: 1562 ec 7 a -253 a -4 f 4 f-b 66 a-c 2948 b 57775 a
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizando
content-type: reference
topic-tags: execução-atividades
discoiquuid: 2650 bf 1 f -0 bce -4049-a 226-2369 f 6666 b 95
context-tags: jstest, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Test{#test}

## Description {#description}

![](assets/test.png)

**[!UICONTROL Test]** A atividade habilita uma transição com base em um resultado do teste.

## Context of use {#context-of-use}

A **Test** activity activates the first transition that satisfies the condition associated to it.

If no condition is satisfied and if the **Use default transition** option is activated, a default transition will be activated.

![](assets/wkf_test_activity_example.png)

Conditions can be based on **functions**, or on **variables**, for example events variables that have been declared into the workflow's **[!UICONTROL External signal]** activity.

**Tópicos relacionados:**

* [Lista de funções](../../automating/using/list-of-functions.md)
* [Chamada de um fluxo de trabalho com parâmetros externos](../../automating/using/calling-a-workflow-with-external-parameters.md)

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Test]** activity into the workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Defina os atributos de cada condição:

   When editing the **[!UICONTROL Condition]** field, two buttons provide help to call events variables and edit expressions combining variables and functions:

   * ![](assets/extsignal_picker.png): selecionar a variável de eventos entre todas as variáveis disponíveis no fluxo de trabalho (consulte [Personalizar um fluxo de trabalho com parâmetros externos](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-a-workflow-with-external-parameters))

      ![](assets/wkf_test_activity_variables.png)

   * ![](assets/extsignal_expression_editor.png): expressões de edição que combinam variáveis e funções. For more on the Expression editor, refer to [this section](../../automating/using/advanced-expression-editing.md).

      ![](assets/wkf_test_activity_variables_expression.png)

