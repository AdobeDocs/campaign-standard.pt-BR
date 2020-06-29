---
title: delivery de aniversário
description: Este exemplo é um fluxo de trabalho de aniversário. Todos os dias, um e-mail é enviado a perfis cujo aniversário é nesse dia.
page-status-flag: never-activated
uuid: 7de53431-84ae-4d21-8361-2775ad314ed2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: 5f288cf6-f8ff-4ac9-9c1a-8010260554bb
context-tags: delivery,workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 0%

---


# delivery de aniversário {#birthday-delivery}

![](assets/wkf_delivery_example_1.png)

Este exemplo é um fluxo de trabalho de aniversário. Todos os dias, um e-mail é enviado a perfis cujo aniversário é nesse dia.

Para criar o fluxo de trabalho, siga estas etapas:

* O [Scheduler](../../automating/using/scheduler.md) permite que você start o fluxo de trabalho todos os dias às 8h00.

   ![](assets/wkf_delivery_example_2.png)

* A atividade de [Query](../../automating/using/query.md) permite calcular os perfis que forneceram um email e cujo aniversário é no dia atual, sempre que o fluxo de trabalho é executado. O cálculo de aniversário é executado usando um filtro predefinido disponível na paleta na ferramenta de edição de query.

   ![](assets/wkf_delivery_example_3.png)

* O delivery [](../../automating/using/email-delivery.md) Email é recorrente. Os envios são agregados por mês. Assim, todos os emails enviados em um mês são agregados em uma única visualização. Em um ano, 365 delivery são, portanto, executados, mas são agrupados em 12 visualizações (também chamadas de execuções **** recorrentes) na interface do Adobe Campaign. Os detalhes do histórico e do relatório são exibidos todos os meses e não para cada envio.

   ![](assets/wkf_delivery_example_4.png)
