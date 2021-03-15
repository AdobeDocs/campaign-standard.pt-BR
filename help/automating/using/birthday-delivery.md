---
solution: Campaign Standard
product: campaign
title: Delivery de aniversário
description: Esse exemplo é um workflow de aniversário. Todos os dias, um email é enviado a perfis cujo aniversário é nesse dia.
audience: automating
content-type: reference
topic-tags: channel-activities
context-tags: delivery,workflow,main
feature: Fluxos de trabalho
role: Arquiteto de dados
level: Intermediário
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 68%

---


# Delivery de aniversário {#birthday-delivery}

![](assets/wkf_delivery_example_1.png)

Esse exemplo é um workflow de aniversário. Todos os dias, um email é enviado a perfis cujo aniversário é nesse dia.

Para criar o workflow, siga estas etapas:

* O [Scheduler](../../automating/using/scheduler.md) permite iniciar o workflow todos os dias às 8h.

   ![](assets/wkf_delivery_example_2.png)

* A atividade [Query](../../automating/using/query.md) permite calcular os perfis que forneceram um email e cujo aniversário é no dia atual, sempre que o workflow é executado. O cálculo do aniversário é executado usando um filtro predefinido, disponível na paleta da ferramenta de edição de queries.

   ![](assets/wkf_delivery_example_3.png)

* O [Email delivery](../../automating/using/email-delivery.md) é recorrente. Os envios são agregados por mês. Assim, todos os emails enviados em um mês são agregados em uma única visualização. Portanto, em um ano, 365 deliveries são executados, mas são agrupados em 12 visualizações (também chamadas de **execuções recorrentes**) na interface do Adobe Campaign. O histórico e os detalhes do relatório são exibidos todos os meses e não para cada envio.

   ![](assets/wkf_delivery_example_4.png)
