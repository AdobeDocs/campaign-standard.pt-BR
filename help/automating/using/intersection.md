---
title: Interseção
description: A atividade de Intersecção permite manter somente os elementos comuns às diferentes populações de entrada na atividade.
page-status-flag: never-activated
uuid: a60f9811-0158-44b3-952b-392685c006cc
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 7a107d6b-edc3-44c3-bbb7-ba3dec8e43f9
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 21faea89b3b38f3e667ed6c4de0be6d07f0b7197
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 1%

---


# Interseção{#intersection}

## Descrição {#description}

![](assets/intersection.png)

A **[!UICONTROL Intersection]** atividade permite manter somente os elementos comuns às diferentes populações de entrada na atividade.

## Contexto de utilização {#context-of-use}

A **[!UICONTROL Intersection]** atividade é geralmente usada para fazer filtragem adicional em populações de transições de entrada.

## Configuração {#configuration}

1. Arraste e solte uma **[!UICONTROL Intersection]** atividade no seu fluxo de trabalho.
1. Conecte-o às outras atividades anteriores, como query.
1. Selecione a atividade e abra-a usando o ![](assets/edit_darkgrey-24px.png) botão das ações rápidas que aparecem.
1. Selecione o **[!UICONTROL Reconciliation type]**:

   * **[!UICONTROL Keys only]**: Modo padrão. A atividade só mantém um elemento quando elementos de transições de entrada diferentes têm a mesma chave.
   * **[!UICONTROL All shared columns]**: Os dados são reconciliados com base em colunas em comum com as transições de entrada. Portanto, é necessário selecionar o conjunto principal que servirá de base para comparação. Essa opção pode ser usada se os targeting dimension de preenchimento de entrada forem diferentes.
   * **[!UICONTROL A selection of columns]**: Selecione essa opção para definir a lista de colunas nas quais a reconciliação de dados será aplicada. Primeiro, selecione o conjunto principal (aquele que contém os dados de origem) e especifique os campos a serem usados para a junção.

1. Marque a **[!UICONTROL Use common additional data only]** caixa se desejar manter somente os dados adicionais que estão em todas as transições de entrada.
1. Se necessário, gerencie as [Transições](../../automating/using/activity-properties.md) de atividade para acessar as opções avançadas para a população de saída.
1. Confirme a configuração da atividade e salve o fluxo de trabalho.

## Exemplo {#example}

O exemplo a seguir mostra a interseção entre duas atividades query. Ele está sendo usado aqui para investigar o banco de dados do Adobe Campaign e recuperar perfis com idade entre 18 e 27 anos e perfis cujo endereço de email foi fornecido, respectivamente.

![](assets/wkf_intersection_example.png)

