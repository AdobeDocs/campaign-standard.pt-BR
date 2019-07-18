---
title: União
seo-title: União
description: União
seo-description: A atividade da União permite que você reúna o resultado de várias atividades em um único destino.
page-status-flag: nunca ativado
uuid: fafc 3 ce 9-2212-4403-8754-cfbb 28 ba 6 e 26
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizando
content-type: reference
topic-tags: atividades de definição de metas
discoiquuid: 99 a 8 c 3 a 5-7 d 90-4 dbb-aa 37-1 d 0 a 84719 cf 6
context-tags: union, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Union{#union}

## Description {#description}

![](assets/union.png)

The **[!UICONTROL Union]** activity allows you to regroup the result of multiple activities into a single target.

>[!NOTE]
>
>Os conjuntos não precisam necessariamente ser homogêneo.

## Context of use {#context-of-use}

**[!UICONTROL Union]** A atividade é usada para combinar as populações das transições de entrada ao realizar uma segmentação, definir um público-alvo ou ao preparar o direcionamento da mensagem como exemplo.

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Union]** activity into your workflow.
1. Conecte-o a outras atividades que vêm antes dele, como consultas.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Select the **[!UICONTROL Reconciliation type]** to define how duplicates are from the confrontation between inbound populations are handled:

   * **[!UICONTROL Keys only]**: esse é o modo padrão. A atividade mantém apenas um elemento quando os elementos das diferentes transições de entrada têm a mesma chave. Essa opção só pode ser usada se as populações de entrada forem homogêneas.
   * **[!UICONTROL All shared columns]**: Os dados são conciliados com base em todas as colunas em comum com as transições de entrada. Portanto, é necessário selecionar o conjunto principal que será mantido no caso de uma duplicata. Essa opção pode ser usada se as dimensões de definição de metas de população de entrada forem diferentes.
   * **[!UICONTROL A selection of columns]**: selecione esta opção para definir a lista de colunas nas quais a reconciliação de dados será aplicada. Primeiro, você deve selecionar o conjunto principal (que contém os dados de origem), em seguida, as colunas a serem usadas para a junção.

1. Check the **[!UICONTROL Use common additional data only]** box if you would like to keep only the additional data that is in all inbound transitions.
1. If you would like to limit the size of the final population, check the **[!UICONTROL Limit size of generated population]** box. The size can be specified in the **[!UICONTROL Maximum number of records]** field.
1. If needed, manage the activity's [Transitions](../../automating/using/executing-a-workflow.md#managing-an-activity-s-outbound-transitions) to access the advanced options for the calculated population.
1. Confirme a configuração da atividade e salve seu fluxo de trabalho.

## Example {#example}

O exemplo a seguir mostra o resultado de duas atividades de consulta que visam recuperar perfis do banco de dados do Adobe Campaign que estão entre 18 e 27 anos e aqueles que têm entre 34 e 40 anos. O resultado contém todos os perfis das duas consultas ou o número máximo de registros, se aplicável, conforme especificado durante a configuração.

![](assets/wkf_union_example.png)