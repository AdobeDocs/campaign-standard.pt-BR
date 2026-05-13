---
title: Segmentação por faixa etária
description: Esta página apresenta uma segmentação de perfis de banco de dados de acordo com a faixa etária. O objetivo do fluxo de trabalho é enviar um email específico para cada faixa etária.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: segmentation,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: dab7ef86-4776-48f4-be9a-37de316e0dd9
TQID: https://experienceleague.adobe.com/LkH1qmElMwEn6JGmUaWj7Qpv7arSvLAZixbfJYTi2NQ
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 206
ht-degree: 58%

---

# Segmentação por faixa etária {#segmentation-age-groups}

O exemplo a seguir mostra uma segmentação de perfis de banco de dados de acordo com a faixa etária.

O objetivo do fluxo de trabalho é enviar um email específico para cada faixa etária. Considerando que esse fluxo de trabalho faz parte de uma campanha de teste, cada segmento só pode conter um máximo de 100 perfis selecionados aleatoriamente para que seja possível usar públicos-alvo limitados e representativos ao mesmo tempo.

![](assets/wkf_segment_example_4.png)

O fluxo de trabalho é composto dos seguintes elementos:

* Uma [Atividade Scheduler](../../automating/using/segmentation.md) para especificar a data de execução do fluxo de trabalho.
* Uma atividade [Query](../../automating/using/query.md) para direcionar perfis de pessoas cujas datas de nascimento e endereços de email foram inseridos.
* Uma atividade [Segmentação](../../automating/using/segmentation.md) para criar três segmentos divididos em transições de saída diferentes: 18-25 anos, 26-32 anos e perfis acima de 32 anos. Os segmentos são definidos de acordo com os seguintes parâmetros:

  ![](assets/wkf_segment_example_3.png)

   * Um filtro na idade para definir a faixa etária do segmento

     ![](assets/wkf_segment_new_segment.png)

   * Um limite do tipo **[!UICONTROL Random sampling]** vinculado a um limite 100 para **[!UICONTROL Maximum size]**

     ![](assets/wkf_segment_example_1.png)

* Uma atividade de [Entrega de email](../../automating/using/email-delivery.md) por segmento.
