---
title: Entrega de aniversário
description: Esse exemplo é um workflow de aniversário. Todos os dias, um email é enviado a perfis cujo aniversário é nesse dia.
audience: automating
content-type: reference
topic-tags: channel-activities
context-tags: delivery,workflow,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 535ddbce-d8ba-4578-9e37-10604291c95d
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 52%

---

# Entrega de aniversário {#birthday-delivery}

![](assets/wkf_delivery_example_1.png)

Esse exemplo é um workflow de aniversário. Todos os dias, um email é enviado a perfis cujo aniversário é nesse dia.

Para criar o workflow, siga estas etapas:

* A variável [Scheduler](../../automating/using/scheduler.md) permite iniciar o workflow todos os dias às 8h.

  ![](assets/wkf_delivery_example_2.png)

* A variável [Query](../../automating/using/query.md) A atividade permite calcular os perfis que forneceram um email e cujo aniversário é no dia atual, todas as vezes que o workflow for executado. O cálculo do aniversário é executado usando um filtro predefinido, disponível na paleta da ferramenta de edição de queries.

  ![](assets/wkf_delivery_example_3.png)

* A variável [Entrega de email](../../automating/using/email-delivery.md) é recorrente. Os envios são agregados por mês. Assim, todos os emails enviados em um mês são agregados em uma única visualização. Portanto, em um ano, 365 entregas são executadas, mas são agrupadas em 12 visualizações (também chamadas de **execuções recorrentes**) na interface do Adobe Campaign. O histórico e os detalhes do relatório são exibidos todos os meses e não para cada envio.

  ![](assets/wkf_delivery_example_4.png)
