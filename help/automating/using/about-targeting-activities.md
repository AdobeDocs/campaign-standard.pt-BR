---
title: Sobre atividades de direcionamento
description: As atividades de direcionamento podem ser acessadas no lado esquerdo da tela.
audience: automating
content-type: reference
topic-tags: targeting-activities
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 1cd471e3-5332-4119-b342-2c3c8503fdd1
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 40%

---

# Sobre atividades de direcionamento{#about-targeting-activities}

Na paleta, no lado esquerdo da tela, expanda a seção **[!UICONTROL Targeting]**.

Essas atividades são específicas para atividades de direcionamento, manipulação de dados de população e filtragem. Eles permitem construir um ou mais targets definindo conjuntos e dividindo ou combinando esses conjuntos usando operações de interseção, união ou exclusão.

![](assets/wkf_targeting_activities.png)

A seção **[!UICONTROL Targeting]** inclui as seguintes atividades:

* [Consulta](../../automating/using/query.md)
* [Consulta incremental](../../automating/using/incremental-query.md)
* [União](../../automating/using/union.md)
* [Intersecção](../../automating/using/intersection.md)
* [Exclusão](../../automating/using/exclusion.md)
* [Segmentação](../../automating/using/segmentation.md)
* [Ler público](../../automating/using/read-audience.md)
* [Salvar público](../../automating/using/save-audience.md)
* [Desduplicação](../../automating/using/deduplication.md)
* [Enriquecimento](../../automating/using/enrichment.md)

**[!UICONTROL Targeting]** atividades permite definir **códigos de segmento** para suas transições de saída. Em seguida, você poderá criar relatórios com base nesses códigos de segmento para medir a eficiência das suas campanhas de marketing. Para obter mais informações, consulte [esta seção](../../reporting/using/creating-a-report-workflow-segment.md).

## Seleção de dados {#selecting-data}

É possível selecionar dados usando as seguintes atividades:

* A atividade **[!UICONTROL Query]** permite filtrar e extrair uma população de elementos do banco de dados do Adobe Campaign. Consulte a [Query](../../automating/using/query.md) seção.
* A atividade **[!UICONTROL Incremental query]** permite filtrar e extrair uma população de elementos do banco de dados do Adobe Campaign. Todas as vezes que essa atividade é executada, os resultados das execuções anteriores são excluídos. Isso permite direcionar somente elementos novos Consulte o. [Query incremental](../../automating/using/incremental-query.md) seção.
* A variável **[!UICONTROL Read audience]** permite recuperar um público-alvo para refiná-lo aplicando condições de filtragem adicionais. Consulte a [Ler público](../../automating/using/read-audience.md) seção.

## Segmentação de dados {#segmenting-data}

O Adobe Campaign permite processar conjuntos em dados de entrada. Dessa forma, é possível combinar várias populações, excluir parte delas ou manter apenas dados comuns a vários targets.

* A variável **[!UICONTROL Union]** A atividade permite reagrupar o resultado de várias atividades em um único público-alvo. Consulte a seção [União](../../automating/using/union.md).
* A variável **[!UICONTROL Intersection]** A atividade de permite manter somente os elementos comuns aos diferentes preenchimentos de entrada na atividade. Consulte a seção [Interseção](../../automating/using/intersection.md).
* A variável **[!UICONTROL Exclusion]** A atividade permite excluir elementos de uma população de acordo com determinados critérios. Consulte a [Exclusão](../../automating/using/exclusion.md) seção.
* A atividade **[!UICONTROL Segmentation]** permite criar um ou vários segmentos com base em uma população calculada pelas atividades incluídas anteriormente no fluxo de trabalho. No final da atividade, eles podem ser processados em uma única transição ou em transições diferentes. Consulte a [Segmentação](../../automating/using/segmentation.md) seção.

## Enriquecimento de dados {#enriching-data}

Os dados identificados e coletados podem ser enriquecidos, agregados e manipulados para otimizar a construção de target. Você pode simplificar e otimizar os processos de segmentação ao incluir dados que não são modelados no data mart.

A variável **[!UICONTROL Additional data]** guia do **[!UICONTROL Query]** e **[!UICONTROL Incremental query]** activities permite enriquecer os dados direcionados pelo query e transferi-los para as seguintes atividades de workflow, onde podem ser utilizados. Você pode adicionar especificamente:

* Dados simples
* Agregados
* Coleções

**Tópicos relacionados:**

* [Caso de uso: personalização de um email com dados adicionais](../../automating/using/personalizing-email-with-additional-data.md)
