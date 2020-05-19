---
title: União
description: A atividade da União permite que você reagrupe o resultado de várias atividades em um único público alvo.
page-status-flag: never-activated
uuid: fafc3ce9-2212-4403-8754-cfbb28ba6e26
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 99a8c3a5-7d90-4dbb-aa37-1d0a84719cf6
context-tags: union,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 21faea89b3b38f3e667ed6c4de0be6d07f0b7197
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 1%

---


# União{#union}

## Descrição {#description}

![](assets/union.png)

A **[!UICONTROL Union]** atividade permite que você reagrupe o resultado de várias atividades em um único público alvo.

>[!NOTE]
>
>Os conjuntos não precisam necessariamente de ser homogêneos.

## Contexto de utilização {#context-of-use}

A **[!UICONTROL Union]** atividade é usada para combinar as populações das transições de entrada ao executar uma segmentação, definir uma audiência ou ao preparar o público alvo de mensagens, por exemplo.

## Configuração {#configuration}

1. Arraste e solte uma **[!UICONTROL Union]** atividade no seu fluxo de trabalho.
1. Conecte-o às outras atividades anteriores, como query.
1. Selecione a atividade e abra-a usando o ![](assets/edit_darkgrey-24px.png) botão das ações rápidas que aparecem.
1. Selecione a opção **[!UICONTROL Reconciliation type]** para definir como os duplicados são tratados a partir do confronto entre as populações de entrada:

   * **[!UICONTROL Keys only]**: este é o modo padrão. A atividade só mantém um elemento quando elementos de transições de entrada diferentes têm a mesma chave. Esta opção só pode ser utilizada se as populações de entrada forem homogêneas.
   * **[!UICONTROL All shared columns]**: Os dados são reconciliados com base em todas as colunas em comum com as transições de entrada. Portanto, é necessário selecionar o conjunto principal que será mantido no caso de um duplicado. Essa opção pode ser usada se os targeting dimension de preenchimento de entrada forem diferentes.
   * **[!UICONTROL A selection of columns]**: selecione essa opção para definir a lista de colunas nas quais a reconciliação de dados será aplicada. Primeiro, selecione o conjunto principal (que contém os dados de origem) e, em seguida, as colunas a serem usadas para a junção.

1. Marque a **[!UICONTROL Use common additional data only]** caixa se desejar manter somente os dados adicionais que estão em todas as transições de entrada.
1. If you would like to limit the size of the final population, check the **[!UICONTROL Limit size of generated population]** box. O tamanho pode ser especificado no **[!UICONTROL Maximum number of records]** campo.
1. Se necessário, gerencie as [Transições](../../automating/using/activity-properties.md) de atividade para acessar as opções avançadas para a população calculada.
1. Confirme a configuração da atividade e salve o fluxo de trabalho.

## Exemplo {#example}

O exemplo a seguir mostra o resultado de duas atividades query que visam reagrupar perfis do banco de dados Adobe Campaign com idade entre 18 e 27 anos e aqueles com idade entre 34 e 40 anos. O resultado contém todos os perfis dos dois query ou o número máximo de registros, se aplicável, conforme especificado durante a configuração.

![](assets/wkf_union_example.png)