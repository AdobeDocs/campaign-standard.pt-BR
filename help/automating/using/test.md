---
solution: Campaign Standard
product: campaign
title: Teste
description: A atividade Test permite uma transição com base em um resultado de teste.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: jstest,main
feature: Fluxos de trabalho
role: Arquiteto de dados
level: Intermediário
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '194'
ht-degree: 80%

---


# Teste{#test}

## Descrição {#description}

![](assets/test.png)

A atividade **[!UICONTROL Test]** permite uma transição com base em um resultado de teste.

## Contexto de uso {#context-of-use}

Uma atividade **Test** ativa a primeira transição que satisfaz a condição associada a ela.

Se nenhuma condição for satisfeita e a opção **Use default transition** estiver ativada, a transição padrão será ativada.

![](assets/wkf_test_activity_example.png)

As condições podem ser baseadas em **funções** ou **variáveis**, por exemplo, as variáveis de eventos que foram declaradas na atividade **[!UICONTROL External signal]** do fluxo de trabalho.

**Tópicos relacionados:**

* [Lista de funções](../../automating/using/list-of-functions.md)
* [Chamada de um fluxo de trabalho com parâmetros externos](../../automating/using/calling-a-workflow-with-external-parameters.md)

## Configuração {#configuration}

1. Arraste e solte uma atividade **[!UICONTROL Test]** no fluxo de trabalho.
1. Selecione e abra a atividade usando o botão ![](assets/edit_darkgrey-24px.png) das ações rápidas exibidas.
1. Defina os atributos de cada condição:

   Ao editar o campo **[!UICONTROL Condition]**, dois botões ajudam a chamar as variáveis de eventos e editar expressões que combinam variáveis e funções:

   * ![](assets/extsignal_picker.png): selecione a variável events entre todas as variáveis disponíveis no workflow (consulte  [esta página](../../automating/using/customizing-workflow-external-parameters.md)).

      Por exemplo, você pode verificar o número de arquivos baixados após uma atividade [File transfer](../../automating/using/transfer-file.md) usando a variável **[!UICONTROL filesCount]**.

      ![](assets/wkf_test_activity_variables.png)

   * ![](assets/extsignal_expression_editor.png): edite as expressões que combinam variáveis e funções. Para saber mais sobre o editor de expressão, consulte [esta seção](../../automating/using/advanced-expression-editing.md).

      ![](assets/wkf_test_activity_variables_expression.png)
