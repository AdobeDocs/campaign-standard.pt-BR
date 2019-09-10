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
source-git-commit: bb65cbf808a95e8b42b2a682b7c0a9cc6225d920

---


# Dados de definição de metas{#targeting-data}

## Seleção de dados {#selecting-data}

É possível selecionar dados usando as seguintes atividades:

* A **[!UICONTROL Query]** atividade permite filtrar e extrair uma população de elementos do banco de dados do Adobe Campaign. Consulte a [seção Consulta](../../automating/using/query.md) .
* A **[!UICONTROL Incremental query]** atividade permite filtrar e extrair uma população de elementos do banco de dados do Adobe Campaign. Cada vez que essa atividade é executada, os resultados das execuções anteriores são excluídos. Isso permite direcionar somente os novos elementos Ver o. [Seção de consulta](../../automating/using/incremental-query.md) incremental.
* A **[!UICONTROL Read audience]** atividade permite recuperar um público existente e refiná-lo aplicando condições de filtragem adicionais. Consulte [a](../../automating/using/read-audience.md) seção Ler público-alvo.

## Segmentação de dados {#segmenting-data}

O Adobe Campaign permite que você processe conjuntos em dados de entrada. Dessa forma, você pode combinar várias populações, excluir parte dele ou manter dados comuns a vários alvos.

* A **[!UICONTROL Union]** atividade permite que você recupere o resultado de várias atividades em um único destino. Consulte a seção [União](../../automating/using/union.md) .
* A **[!UICONTROL Intersection]** atividade permite manter apenas os elementos comuns às diferentes populações de entrada na atividade. Consulte a seção [Interseção](../../automating/using/intersection.md) .
* A **[!UICONTROL Exclusion]** atividade permite excluir elementos de uma população de acordo com alguns critérios. Consulte a [seção Exclusão](../../automating/using/exclusion.md) .
* A **[!UICONTROL Segmentation]** atividade permite criar um ou vários segmentos a partir de uma população calculada pelas atividades realizadas anteriormente no fluxo de trabalho. No fim da atividade, eles podem ser processados em uma única transição ou transições diferentes. Consulte a [seção Segmentação](../../automating/using/segmentation.md) .

## Enriquecer dados {#enriching-data}

Os dados identificados e coletados podem ser aprimorados, agregados e manipulados para otimizar a construção de metas. É possível simplificar e otimizar os processos de definição de metas, incluindo dados que não são modelados na mart de dados.

A **[!UICONTROL Additional data]** guia **[!UICONTROL Query]** e **[!UICONTROL Incremental query]** as atividades permitem aprimorar os dados direcionados pela consulta e transferir esses dados para as seguintes atividades do fluxo de trabalho, onde pode ser usado. Em particular, você pode adicionar:

* Dados simples
* Agregados
* Coleções

**Tópicos relacionados**

* [Caso de uso: Criar uma entrega de email uma vez a semana](../../automating/using/workflow-weekly-offer.md)
* [Caso de uso: Criação de uma entrega segmentada na localização](../../automating/using/workflow-segmentation-location.md)
* [Caso de uso: Criação de entregas com um complemento](../../automating/using/workflow-created-query-with-complement.md)
* [Caso de uso: Fluxo de trabalho de redefinição de metas enviando uma nova entrega para não-openers](../../automating/using/workflow-cross-channel-retargeting.md)
