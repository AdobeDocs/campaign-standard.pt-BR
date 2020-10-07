---
title: Delivery de aniversário
description: Esse exemplo é um workflow de aniversário. Todos os dias, um email é enviado a perfis cujo aniversário é nesse dia.
page-status-flag: never-activated
uuid: 7de53431-84ae-4d21-8361-2775ad314ed2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: 5f288cf6-f8ff-4ac9-9c1a-8010260554bb
context-tags: delivery,workflow,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 69%

---


# Delivery de aniversário {#birthday-delivery}

![](assets/wkf_delivery_example_1.png)

Esse exemplo é um workflow de aniversário. Todos os dias, um email é enviado a perfis cujo aniversário é nesse dia.

Para criar o fluxo de trabalho, siga estas etapas:

* The [Scheduler](../../automating/using/scheduler.md) allows you to start the workflow every day at 8am.

   ![](assets/wkf_delivery_example_2.png)

* The [Query](../../automating/using/query.md) activity allows you to calculate the profiles who have provided an email and whose birthday it is on the current day, every time the workflow is executed. O cálculo do aniversário é executado usando um filtro predefinido, disponível na paleta da ferramenta de edição de queries.

   ![](assets/wkf_delivery_example_3.png)

* O delivery [](../../automating/using/email-delivery.md) Email é recorrente. Os envios são agregados por mês. Assim, todos os emails enviados em um mês são agregados em uma única visualização. Portanto, em um ano, 365 deliveries são executados, mas são agrupados em 12 visualizações (também chamadas de **execuções recorrentes**) na interface do Adobe Campaign. O histórico e os detalhes do relatório são exibidos todos os meses e não para cada envio.

   ![](assets/wkf_delivery_example_4.png)
