---
title: Direcionamento de dados
description: Saiba mais sobre as diferentes maneiras de direcionar e selecionar os dados necessários.
page-status-flag: nunca ativado
uuid: 0645d6e5-6a7e-4917-874a-7e7725f06abd
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: automatização
content-type: referência
topic-tags: fluxo de trabalho geral-operação
discoiquuid: 382ea74e-1662-4c64-96d7-676040586913
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Direcionamento de dados{#targeting-data}

## Seleção de dados {#selecting-data}

Você pode selecionar dados usando as seguintes atividades:

* A **[!UICONTROL Query]** atividade permite filtrar e extrair um preenchimento de elementos do banco de dados do Adobe Campaign. Consulte a seção [Consulta](../../automating/using/query.md) .
* A **[!UICONTROL Incremental query]** atividade permite filtrar e extrair um preenchimento de elementos do banco de dados do Adobe Campaign. Cada vez que essa atividade é executada, os resultados das execuções anteriores são excluídos. Isso permite que você direcione somente novos elementos. Consulte o. [Seção de consulta](../../automating/using/incremental-query.md) incremental.
* A **[!UICONTROL Read audience]** atividade permite recuperar um público-alvo existente e refiná-lo aplicando condições de filtragem adicionais.Consulte a seção [Ler público-alvo](../../automating/using/read-audience.md) .

## Segmentação de dados {#segmenting-data}

O Adobe Campaign permite que você processe conjuntos em dados de entrada. Assim, é possível combinar várias populações, excluir parte dela ou apenas manter os dados comuns a várias metas.

* A **[!UICONTROL Union]** atividade permite que você reagrupe o resultado de várias atividades em um único destino. Ver a seção [União](../../automating/using/union.md) .
* A **[!UICONTROL Intersection]** atividade permite manter somente os elementos comuns às diferentes populações de entrada na atividade. Consulte a seção [Interseção](../../automating/using/intersection.md) .
* A **[!UICONTROL Exclusion]** atividade permite excluir elementos de uma população de acordo com determinados critérios. Consulte a seção [Exclusão](../../automating/using/exclusion.md) .
* A **[!UICONTROL Segmentation]** atividade permite criar um ou vários segmentos a partir de uma população calculada por atividades colocadas anteriormente no fluxo de trabalho. No final da atividade, eles podem ser processados em uma única transição ou diferentes transições. Consulte a seção [Segmentação](../../automating/using/segmentation.md) .

## Enriquecimento de dados {#enriching-data}

Os dados identificados e coletados podem ser enriquecidos, agregados e manipulados para otimizar a construção de target. Você pode simplificar e otimizar os processos de definição de metas, incluindo dados que não são modelados no data mart.

A **[!UICONTROL Additional data]** guia das atividades **[!UICONTROL Query]** e **[!UICONTROL Incremental query]** permite que você aprimore os dados direcionados pela consulta e transfira esses dados para as seguintes atividades de fluxo de trabalho, onde eles podem ser utilizados. Em particular, você pode adicionar:

* Dados simples
* Agregados
* Coleções

**Tópicos relacionados**

* [Caso de uso: Criar uma entrega de email uma vez por semana](../../automating/using/workflow-weekly-offer.md)
* [Caso de uso: Criação de uma entrega segmentada no local](../../automating/using/workflow-segmentation-location.md)
* [Caso de uso: Criação de entregas com um complemento](../../automating/using/workflow-created-query-with-complement.md)
* [Caso de uso: Fluxo de trabalho de redefinição de metas enviando uma nova entrega para não iniciantes](../../automating/using/workflow-cross-channel-retargeting.md)
