---
solution: Campaign Standard
product: campaign
title: Segmentação por faixa etária
description: Esta página apresenta uma segmentação de perfis de banco de dados de acordo com sua faixa etária. O objetivo do fluxo de trabalho é enviar um email específico para cada faixa etária.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: segmentation,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 66%

---


# Segmentação por faixa etária {#segmentation-age-groups}

O exemplo a seguir mostra uma segmentação de perfis de banco de dados de acordo com a faixa etária.

O objetivo do fluxo de trabalho é enviar um email específico para cada faixa etária. Considerando que esse fluxo de trabalho faz parte de uma campanha de teste, cada segmento só pode conter um máximo de 100 perfis selecionados aleatoriamente para que seja possível usar públicos-alvo limitados e representativos ao mesmo tempo.

![](assets/wkf_segment_example_4.png)

O fluxo de trabalho é composto dos seguintes elementos:

* Uma [atividade de Scheduler](../../automating/using/segmentation.md) para especificar a data de execução do fluxo de trabalho.
* Uma atividade [Query](../../automating/using/query.md) para públicos alvos de pessoas cujo aniversário e endereço de email foram inseridos.
* Uma atividade [Segmentação](../../automating/using/segmentation.md) para criar três segmentos divididos em diferentes transições de saída: Com 18-25 anos, 26-32 anos e perfis com mais de 32 anos. Os segmentos são definidos de acordo com os seguintes parâmetros:

   ![](assets/wkf_segment_example_3.png)

   * Um filtro na idade para definir a faixa etária do segmento

      ![](assets/wkf_segment_new_segment.png)

   * Um limite do tipo **[!UICONTROL Random sampling]** vinculado a um limite 100 para **[!UICONTROL Maximum size]**

      ![](assets/wkf_segment_example_1.png)

* Uma atividade [delivery de email](../../automating/using/email-delivery.md) por segmento.
