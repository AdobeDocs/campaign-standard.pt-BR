---
title: Teste
description: A atividade Test permite uma transição com base no resultado do teste.
page-status-flag: nunca ativado
uuid: 1562ec7a-253a-4f4f-b66a-c2948b5775a
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: automatização
content-type: referência
topic-tags: atividades de execução
discoiquuid: 2650bf1f-0bce-4049-a226-2369f666b95
context-tags: jstest,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Teste{#test}

## Descrição {#description}

![](assets/test.png)

The **[!UICONTROL Test]** activity enables a transition based on a test result.

## Contexto de utilização {#context-of-use}

A **Test** activity activates the first transition that satisfies the condition associated to it.

If no condition is satisfied and if the **Use default transition** option is activated, a default transition will be activated.

![](assets/wkf_test_activity_example.png)

As condições podem ser baseadas em **funções** ou em **variáveis**, por exemplo, variáveis de eventos que foram declaradas na atividade do fluxo de trabalho **[!UICONTROL External signal]** .

**Tópicos relacionados:**

* [Lista de funções](../../automating/using/list-of-functions.md)
* [Chamada de um fluxo de trabalho com parâmetros externos](../../automating/using/calling-a-workflow-with-external-parameters.md)

## Configuração {#configuration}

1. Arraste e solte uma **[!UICONTROL Test]** atividade no fluxo de trabalho.
1. Selecione a atividade e abra-a usando o ![](assets/edit_darkgrey-24px.png) botão das ações rápidas que aparecem.
1. Defina os atributos de cada condição:

   Ao editar o **[!UICONTROL Condition]** campo, dois botões fornecem ajuda para chamar variáveis de eventos e editar expressões que combinam variáveis e funções:

   * ![](assets/extsignal_picker.png): selecione a variável de eventos entre todas as variáveis disponíveis no fluxo de trabalho (consulte [Personalizar um fluxo de trabalho com parâmetros](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-a-workflow-with-external-parameters)externos)

      ![](assets/wkf_test_activity_variables.png)

   * ![](assets/extsignal_expression_editor.png): editar expressões que combinam variáveis e funções. For more on the Expression editor, refer to [this section](../../automating/using/advanced-expression-editing.md).

      ![](assets/wkf_test_activity_variables_expression.png)

