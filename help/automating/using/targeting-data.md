---
title: Dados de definição de metas
seo-title: Dados de definição de metas
description: Dados de definição de metas
seo-description: Aprenda as diferentes maneiras de direcionar e selecionar os dados necessários.
page-status-flag: nunca ativado
uuid: 0645 d 6 e 5-6 a 7 e -4917-874 a -7 e 7725 f 06 abd
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizando
content-type: reference
topic-tags: fluxo de trabalho-geral-operação
discoiquuid: 382 ea 74 e -1662-4 c 64-96 d 7-676040586913
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Targeting data{#targeting-data}

## Selecting data {#selecting-data}

É possível selecionar dados usando as seguintes atividades:

* The **[!UICONTROL Query]** activity allows you to filter and extract a population of elements from the Adobe Campaign database. See the [Query](../../automating/using/query.md) section.
* The **[!UICONTROL Incremental query]** activity allows you to filter and extract a population of elements from the Adobe Campaign database. Cada vez que essa atividade é executada, os resultados das execuções anteriores são excluídos. Isso permite direcionar somente os novos elementos Ver o. [Seção de consulta](../../automating/using/incremental-query.md) incremental.
* The **[!UICONTROL Read audience]** activity allows you to retrieve an existing audience and to refine it by applying additional filtering conditions.See the [Read audience](../../automating/using/read-audience.md) section.

## Segmenting data {#segmenting-data}

O Adobe Campaign permite que você processe conjuntos em dados de entrada. Dessa forma, você pode combinar várias populações, excluir parte dele ou manter dados comuns a vários alvos.

* The **[!UICONTROL Union]** activity allows you to regroup the result of multiple activities into a single target. See the [Union](../../automating/using/union.md) section.
* The **[!UICONTROL Intersection]** activity allows you to keep only the elements common to the different inbound populations in the activity. See the [Intersection](../../automating/using/intersection.md) section.
* The **[!UICONTROL Exclusion]** activity allows you to exclude elements from one population according to certain criteria. See the [Exclusion](../../automating/using/exclusion.md) section.
* The **[!UICONTROL Segmentation]** activity lets you create one or several segments from a population calculated by activities placed earlier in the workflow. No fim da atividade, eles podem ser processados em uma única transição ou transições diferentes. See the [Segmentation](../../automating/using/segmentation.md) section.

## Enriching data {#enriching-data}

Os dados identificados e coletados podem ser aprimorados, agregados e manipulados para otimizar a construção de metas. É possível simplificar e otimizar os processos de definição de metas, incluindo dados que não são modelados na mart de dados.

The **[!UICONTROL Additional data]** tab of the **[!UICONTROL Query]** and **[!UICONTROL Incremental query]** activities allows you to enrich the data targeted by the query and transfer this data to the following workflow activities, where it can be utilized. Em particular, você pode adicionar:

* Dados simples
* Agregados
* Coleções

