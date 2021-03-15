---
solution: Campaign Standard
product: campaign
title: Sobre as atividades de direcionamento
description: As atividades de direcionamento podem ser acessadas no lado esquerdo da tela.
audience: automating
content-type: reference
topic-tags: targeting-activities
feature: Fluxos de trabalho
role: Arquiteto de dados
level: Intermediário
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 52%

---


# Sobre as atividades de direcionamento{#about-targeting-activities}

Na paleta, no lado esquerdo da tela, expanda a seção **[!UICONTROL Targeting]**.

Essas atividades são específicas para direcionamento, manipulação de dados de população e atividades de filtragem. Eles permitem construir um ou mais targets definindo conjuntos e dividindo ou combinando esses conjuntos usando operações de interseção, união ou exclusão.

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

**[!UICONTROL Targeting]** As atividades do permitem definir os  **códigos** de segmento para as transições de saída. Em seguida, você poderá criar relatórios com base nesses códigos de segmento para medir a eficiência das suas campanhas de marketing. Para obter mais informações, consulte [esta seção](../../reporting/using/creating-a-report-workflow-segment.md).

## Seleção de dados {#selecting-data}

Você pode selecionar dados usando as seguintes atividades:

* A atividade **[!UICONTROL Query]** permite filtrar e extrair uma população de elementos do banco de dados do Adobe Campaign. Consulte a seção [Query](../../automating/using/query.md).
* A atividade **[!UICONTROL Incremental query]** permite filtrar e extrair uma população de elementos do banco de dados do Adobe Campaign. Todas as vezes que essa atividade é executada, os resultados das execuções anteriores são excluídos. Isso permite que você direcione somente novos elementos. Veja o. [Seção de ](../../automating/using/incremental-query.md) consulta incremental.
* A atividade **[!UICONTROL Read audience]** permite recuperar um público-alvo existente e refiná-lo aplicando condições de filtragem adicionais. Consulte a seção [Ler público](../../automating/using/read-audience.md).

## Segmentação de dados {#segmenting-data}

O Adobe Campaign permite processar conjuntos em dados de entrada. Assim, é possível combinar várias populações, excluir parte dela ou manter os dados comuns a vários targets.

* A atividade **[!UICONTROL Union]** permite reagrupar o resultado de várias atividades em um único público-alvo. Consulte a seção [Union](../../automating/using/union.md).
* A atividade **[!UICONTROL Intersection]** permite manter somente os elementos comuns aos diferentes preenchimentos de entrada na atividade. Consulte a seção [Interseção](../../automating/using/intersection.md).
* A atividade **[!UICONTROL Exclusion]** permite excluir elementos de uma população de acordo com determinados critérios. Consulte a seção [Exclusion](../../automating/using/exclusion.md) .
* A atividade **[!UICONTROL Segmentation]** permite criar um ou vários segmentos com base em uma população calculada pelas atividades incluídas anteriormente no fluxo de trabalho. No final da atividade, eles podem ser processados em uma única transição ou em transições diferentes. Consulte a seção [Segmentação](../../automating/using/segmentation.md) .

## Enriquecimento de dados {#enriching-data}

Os dados identificados e coletados podem ser enriquecidos, agregados e manipulados para otimizar a construção de target. Você pode simplificar e otimizar os processos de direcionamento, ao incluir dados que não são modelados no data mart.

A guia **[!UICONTROL Additional data]** das atividades **[!UICONTROL Query]** e **[!UICONTROL Incremental query]** permite enriquecer os dados direcionados pelo query e transferi-los para as seguintes atividades de workflow, onde podem ser utilizados. Você pode adicionar especificamente:

* Dados simples
* Agregados
* Coleções

**Tópicos relacionados:**

* [Caso de uso: Personalização de um email com dados adicionais](../../automating/using/personalizing-email-with-additional-data.md)
