---
title: Interseção
seo-title: Interseção
description: Interseção
seo-description: A atividade de Interseção permite manter somente os elementos comuns às diferentes populações de entrada na atividade.
page-status-flag: nunca ativado
uuid: a 60 f 9811-0158-44 b 3-94 2 b -392685 c 006 cc
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizando
content-type: reference
topic-tags: atividades de definição de metas
discoiquuid: 7 a 107 d 6 b-edc 3-44 c 3-bbb 7-ba 3 dec 8 e 43 f 9
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 36727e82d3aa73add6116fa2916752ff0e407d9d

---


# Intersection{#intersection}

## Description {#description}

![](assets/intersection.png)

The **[!UICONTROL Intersection]** activity allows you to keep only the elements common to the different inbound populations in the activity.

## Context of use {#context-of-use}

The **[!UICONTROL Intersection]** activity is generally used to carry out additional filtering on populations from inbound transitions.

## Configuration {#configuration}

1. Drag and drop an **[!UICONTROL Intersection]** activity into your workflow.
1. Conecte-o a outras atividades que vêm antes dele, como consultas.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Select the **[!UICONTROL Reconciliation type]**:

   * **[!UICONTROL Keys only]**: Modo padrão. A atividade mantém apenas um elemento quando os elementos das diferentes transições de entrada têm a mesma chave.
   * **[!UICONTROL All shared columns]**: Os dados são conciliados com base em colunas em comum com as transições de entrada. Portanto, é necessário selecionar o conjunto principal que servirá como base para comparação. Essa opção pode ser usada se as dimensões de definição de metas de população de entrada forem diferentes.
   * **[!UICONTROL A selection of columns]**: Selecione esta opção para definir a lista de colunas nas quais a reconciliação de dados será aplicada. Primeiro, você deve selecionar o conjunto principal (aquele que contém os dados de origem) e, em seguida, especificar os campos a serem usados para a participação.

1. Check the **[!UICONTROL Use common additional data only]** box if you would like to keep only the additional data that is in all inbound transitions.
1. If needed, manage the activity's [Transitions](../../automating/using/executing-a-workflow.md#managing-an-activity-s-outbound-transitions) to access the advanced options for the outbound population.
1. Confirme a configuração da atividade e salve seu fluxo de trabalho.

## Example {#example}

O exemplo a seguir mostra a interseção entre duas atividades de consulta. Ele está sendo usado aqui para analisar o banco de dados do Adobe Campaign e recuperar perfis que têm entre 18 a 27 anos e perfis cujo endereço de email foi fornecido respectivamente.

![](assets/wkf_intersection_example.png)

