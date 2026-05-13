---
title: Entrega de aniversário
description: Esse exemplo é um fluxo de trabalho de aniversário. Todos os dias, um email é enviado a perfis cujo aniversário é nesse dia.
audience: automating
content-type: reference
topic-tags: channel-activities
context-tags: delivery,workflow,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 535ddbce-d8ba-4578-9e37-10604291c95d
TQID: https://experienceleague.adobe.com/LXiYfz5VXaY7j0pOHWUCGJzp5F4bCsSCmFzEqsQG18E
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 174
ht-degree: 52%

---

# Entrega de aniversário {#birthday-delivery}

![](assets/wkf_delivery_example_1.png)

Esse exemplo é um fluxo de trabalho de aniversário. Todos os dias, um email é enviado a perfis cujo aniversário é nesse dia.

Para criar o workflow, siga estas etapas:

* O [Scheduler](../../automating/using/scheduler.md) permite iniciar o fluxo de trabalho todos os dias às 8h.

  ![](assets/wkf_delivery_example_2.png)

* A atividade [Query](../../automating/using/query.md) permite calcular os perfis que forneceram um email e cujo aniversário é no dia atual, sempre que o fluxo de trabalho é executado. O cálculo do aniversário é executado usando um filtro predefinido, disponível na paleta da ferramenta de edição de consultas.

  ![](assets/wkf_delivery_example_3.png)

* A [Entrega de email](../../automating/using/email-delivery.md) é recorrente. Os envios são agregados por mês. Assim, todos os emails enviados em um mês são agregados em uma única visualização. Portanto, em um ano, 365 entregas são executadas, mas são agrupadas em 12 visualizações (também chamadas de **execuções recorrentes**) na interface do Adobe Campaign. O histórico e os detalhes do relatório são exibidos todos os meses e não para cada envio.

  ![](assets/wkf_delivery_example_4.png)
