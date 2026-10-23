---
title: Teste
description: A atividade Test permite uma transição com base em um resultado de teste.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: jstest,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 62a064f7-6d0b-49ca-9834-eccb5bf42496
TQID: 'https://experienceleague.adobe.com/oyXhQ4Fgx2-cooFelMxsoFiP1qx48-ZQ1eoAudNivF8'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '190'
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
* [Chamar um fluxo de trabalho com parâmetros externos](../../automating/using/calling-a-workflow-with-external-parameters.md)

## Configuração {#configuration}

1. Arraste e solte uma atividade **[!UICONTROL Test]** no fluxo de trabalho.
1. Selecione e abra a atividade usando o botão ![](assets/edit_darkgrey-24px.png) das ações rápidas exibidas.
1. Defina os atributos de cada condição:

   Ao editar o campo **[!UICONTROL Condition]**, dois botões ajudam a chamar as variáveis de eventos e editar expressões que combinam variáveis e funções:

   * ![](assets/extsignal_picker.png): selecione a variável de eventos entre todas as variáveis disponíveis no fluxo de trabalho (consulte [esta página](../../automating/using/customizing-workflow-external-parameters.md)).

     Por exemplo, você pode verificar o número de arquivos baixados após uma atividade [Transferência de arquivos](../../automating/using/transfer-file.md) usando a variável **[!UICONTROL filesCount]**.

     ![](assets/wkf_test_activity_variables.png)

   * ![](assets/extsignal_expression_editor.png): edite as expressões que combinam variáveis e funções. Para saber mais sobre o editor de expressão, consulte [esta seção](../../automating/using/advanced-expression-editing.md).

     ![](assets/wkf_test_activity_variables_expression.png)
