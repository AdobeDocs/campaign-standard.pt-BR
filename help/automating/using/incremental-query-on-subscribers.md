---
solution: Campaign Standard
product: campaign
title: Query incremental para assinantes de um serviço
description: O exemplo a seguir apresenta como configurar uma atividade de Query incremental para filtrar assinantes de um serviço.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: incremental,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 67%

---


# Query incremental para assinantes de um serviço {#example--incremental-query-on-subscribers-to-a-service}

O exemplo a seguir mostra a configuração de uma atividade **[!UICONTROL Incremental query]** que filtra os perfis no banco de dados do Adobe Campaign que estão inscritos no serviço **Running Newsletter** para enviar um email de boas-vindas contendo um código promocional.

O workflow é composto pelos seguintes elementos:

![](assets/incremental_query_example1.png)

* A [Scheduler](../../automating/using/scheduler.md) activity, to execute the workflow every Monday at 6 am.

   ![](assets/incremental_query_example2.png)

* An [Incremental query](../../automating/using/incremental-query.md) activity, which targets all of the current subscribers during the first execution, then only the new subscribers of that week during the following executions.

   ![](assets/incremental_query_example3.png)

* Uma atividade [de delivery](../../automating/using/email-delivery.md) por email. O workflow é executado uma vez por semana, mas você pode agregar os emails enviados e os resultados por mês, por exemplo, para gerar relatórios durante um período de um mês inteiro e não apenas uma única semana.

   Para fazer isso, escolha criar um **[!UICONTROL Recurring email]** aqui, reagrupando os emails e os resultados **[!UICONTROL By month]**.

   Defina o conteúdo do seu email e insira o código promocional de boas-vindas. Para obter mais informações, consulte [Definição de seções de conteúdo](../../designing/using/personalization.md) de email.

Em seguida, inicie a execução do workflow. Todas as semanas, os novos assinantes receberão o email de boas-vindas com o código promocional.
