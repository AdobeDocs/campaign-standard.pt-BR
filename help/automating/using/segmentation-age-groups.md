---
title: Segmentação de acordo com grupos etários
description: Esta página apresenta uma segmentação de perfis de banco de dados de acordo com sua faixa etária. O objetivo do fluxo de trabalho é enviar um email específico para cada faixa etária.
page-status-flag: never-activated
uuid: 77796f18-cad5-4e7a-9d7b-4ed0dd8943bf
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 0ccd9d02-772e-406b-874a-5381dd0c8709
context-tags: segmentation,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 0%

---


# Segmentação de acordo com grupos etários {#segmentation-age-groups}

O exemplo a seguir mostra uma segmentação de perfis de banco de dados de acordo com sua faixa etária.

O objetivo do fluxo de trabalho é enviar um email específico para cada faixa etária. Considerando o fato de que esse fluxo de trabalho é parte de uma campanha de teste, cada segmento só pode conter um máximo de 100 perfis selecionados aleatoriamente para usar audiências limitadas e representativas ao mesmo tempo.

![](assets/wkf_segment_example_4.png)

O fluxo de trabalho é composto dos seguintes elementos:

* Uma atividade [de](../../automating/using/segmentation.md) Scheduler para especificar a data de execução do fluxo de trabalho.
* Uma atividade de [Query](../../automating/using/query.md) para perfis públicos alvos de pessoas cujo endereço de aniversário e e-mail foram inseridos.
* Uma atividade de [segmentação](../../automating/using/segmentation.md) para criar três segmentos divididos em diferentes transições de saída: Com 18-25 anos, 26-32 anos e perfis com mais de 32 anos. Os segmentos são definidos de acordo com os seguintes parâmetros:

   ![](assets/wkf_segment_example_3.png)

   * Um filtro na página para definir a faixa etária do segmento

      ![](assets/wkf_segment_new_segment.png)

   * Um limite **[!UICONTROL Random sampling]** de tipo vinculado a um **[!UICONTROL Maximum size]** limite de 100

      ![](assets/wkf_segment_example_1.png)

* Uma atividade [de delivery](../../automating/using/email-delivery.md) por segmento.
