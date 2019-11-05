---
title: União
description: A atividade da União permite que você reagrupe o resultado de várias atividades em um único alvo.
page-status-flag: nunca ativado
uuid: fafc3ce9-2212-4403-8754-cfbb28ba6e26
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: automatização
content-type: referência
topic-tags: atividades de definição de metas
discoiquuid: 99a8c3a5-7d90-4dbb-aa37-1d0a84719cf6
context-tags: sindicato,principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# União{#union}

## Descrição {#description}

![](assets/union.png)

A **[!UICONTROL Union]** atividade permite que você reagrupe o resultado de várias atividades em um único destino.

>[!NOTE]
>
>Os conjuntos não precisam necessariamente de ser homogêneos.

## Contexto de utilização {#context-of-use}

A **[!UICONTROL Union]** atividade é usada para combinar as populações das transições de entrada ao executar uma segmentação, definir um público-alvo ou ao preparar o destino da mensagem, por exemplo.

## Configuração {#configuration}

1. Arraste e solte uma **[!UICONTROL Union]** atividade em seu fluxo de trabalho.
1. Conecte-o às outras atividades que vêm antes dele, como consultas.
1. Selecione a atividade e abra-a usando o ![](assets/edit_darkgrey-24px.png) botão das ações rápidas que aparecem.
1. Selecione a opção **[!UICONTROL Reconciliation type]** para definir como as duplicatas são tratadas a partir do confronto entre as populações de entrada:

   * **[!UICONTROL Keys only]**: este é o modo padrão. A atividade só mantém um elemento quando os elementos de diferentes transições de entrada têm a mesma chave. Esta opção só pode ser utilizada se as populações de entrada forem homogêneas.
   * **[!UICONTROL All shared columns]**: Os dados são reconciliados com base em todas as colunas, em comum com as transições de entrada. Portanto, é necessário selecionar o conjunto principal que será mantido no caso de uma duplicata. Essa opção pode ser usada se as dimensões de direcionamento de preenchimento de entrada forem diferentes.
   * **[!UICONTROL A selection of columns]**: selecione essa opção para definir a lista de colunas na qual a reconciliação de dados será aplicada. Primeiro, você deve selecionar o conjunto principal (que contém os dados de origem) e depois as colunas a serem usadas para a junção.

1. Marque a **[!UICONTROL Use common additional data only]** caixa se desejar manter somente os dados adicionais que estão em todas as transições de entrada.
1. Se você deseja limitar o tamanho da população final, marque a **[!UICONTROL Limit size of generated population]** caixa. O tamanho pode ser especificado no **[!UICONTROL Maximum number of records]** campo.
1. Se necessário, gerencie as [Transições](../../automating/using/executing-a-workflow.md#managing-an-activity-s-outbound-transitions) da atividade para acessar as opções avançadas para a população calculada.
1. Confirme a configuração da atividade e salve o fluxo de trabalho.

## Exemplo {#example}

O exemplo a seguir mostra o resultado de duas atividades de consulta que visam reagrupar perfis do banco de dados do Adobe Campaign com idade entre 18 e 27 anos e aqueles com idade entre 34 e 40 anos. O resultado contém todos os perfis das duas consultas ou o número máximo de registros, se aplicável, conforme especificado durante a configuração.

![](assets/wkf_union_example.png)