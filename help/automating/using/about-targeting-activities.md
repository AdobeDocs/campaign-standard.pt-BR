---
solution: Campaign Standard
product: campaign
title: Sobre as atividades de direcionamento
description: Atividades de definição de metas podem ser acessadas do lado esquerdo da tela.
audience: automating
content-type: reference
topic-tags: targeting-activities
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 52%

---


# Sobre as atividades de direcionamento{#about-targeting-activities}

Na paleta, no lado esquerdo da tela, expanda a seção **[!UICONTROL Targeting]**.

Essas atividades são específicas para segmentação, manipulação de dados de população e filtragem de atividades. Eles permitem que você crie um ou mais públicos alvos definindo conjuntos e dividindo ou combinando esses conjuntos usando operações de interseção, união ou exclusão.

![](assets/wkf_targeting_activities.png)

A seção **[!UICONTROL Targeting]** inclui as seguintes atividades:

* [Query](../../automating/using/query.md)
* [Query incremental](../../automating/using/incremental-query.md)
* [União](../../automating/using/union.md)
* [Interseção](../../automating/using/intersection.md)
* [Exclusão](../../automating/using/exclusion.md)
* [Segmentação](../../automating/using/segmentation.md)
* [Ler público-alvo](../../automating/using/read-audience.md)
* [Salvar público-alvo](../../automating/using/save-audience.md)
* [Desduplicação](../../automating/using/deduplication.md)
* [Enriquecimento](../../automating/using/enrichment.md)

**[!UICONTROL Targeting]** O atividade permite que você defina **códigos de segmento** para suas transições de saída. Em seguida, você poderá criar relatórios com base nesses códigos de segmento para medir a eficiência das suas campanhas de marketing. Para obter mais informações, consulte [esta seção](../../reporting/using/creating-a-report-workflow-segment.md).

## Seleção de dados {#selecting-data}

Você pode selecionar dados usando as seguintes atividades:

* A atividade **[!UICONTROL Query]** permite filtrar e extrair uma população de elementos do banco de dados do Adobe Campaign. Consulte a seção [Query](../../automating/using/query.md) .
* A atividade **[!UICONTROL Incremental query]** permite filtrar e extrair uma população de elementos do banco de dados do Adobe Campaign. Todas as vezes que essa atividade é executada, os resultados das execuções anteriores são excluídos. Isso permite que você público alvo somente os novos elementos. Consulte o [seção query incremental](../../automating/using/incremental-query.md) .
* The **[!UICONTROL Read audience]** activity allows you to retrieve an existing audience and to refine it by applying additional filtering conditions.See the [Read audience](../../automating/using/read-audience.md) section.

## Segmentação de dados {#segmenting-data}

A Adobe Campaign permite que você processe conjuntos em dados de entrada. Assim, é possível combinar várias populações, excluir parte dela ou manter apenas os dados comuns a vários públicos alvos.

* A atividade **[!UICONTROL Union]** permite reagrupar o resultado de várias atividades em um único público-alvo. Consulte a seção [União](../../automating/using/union.md) .
* A atividade **[!UICONTROL Intersection]** permite manter somente os elementos comuns aos diferentes preenchimentos de entrada na atividade. Consulte a seção [Intersecção](../../automating/using/intersection.md) .
* A atividade **[!UICONTROL Exclusion]** permite excluir elementos de uma população de acordo com determinados critérios. Consulte a seção [Exclusão](../../automating/using/exclusion.md) .
* A atividade **[!UICONTROL Segmentation]** permite criar um ou vários segmentos com base em uma população calculada pelas atividades incluídas anteriormente no fluxo de trabalho. No final da atividade, eles podem ser processados em uma única transição ou em transições diferentes. Consulte a seção [Segmentação](../../automating/using/segmentation.md) .

## Enriquecimento de dados {#enriching-data}

Os dados identificados e coletados podem ser enriquecidos, agregados e manipulados para otimizar a construção de target. Você pode simplificar e otimizar os processos de definição de metas, incluindo dados que não são modelados no data mart.

The **[!UICONTROL Additional data]** tab of the **[!UICONTROL Query]** and **[!UICONTROL Incremental query]** activities allows you to enrich the data targeted by the query and transfer this data to the following workflow activities, where it can be utilized. Você pode adicionar especificamente:

* Dados simples
* Agregados
* Coleções

**Tópicos relacionados:**

* [Caso de uso: Personalização de um email com dados adicionais](../../automating/using/personalizing-email-with-additional-data.md)
