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

* Uma atividade [Scheduler](../../automating/using/scheduler.md), para executar o fluxo de trabalho todas as segundas-feiras às 6 horas.

   ![](assets/incremental_query_example2.png)

* Uma atividade [Query incremental](../../automating/using/incremental-query.md), que público alvo todos os assinantes atuais durante a primeira execução, em seguida, somente os novos assinantes daquela semana durante as seguintes execuções.

   ![](assets/incremental_query_example3.png)

* Uma atividade [delivery de e-mail](../../automating/using/email-delivery.md). O workflow é executado uma vez por semana, mas você pode agregar os emails enviados e os resultados por mês, por exemplo, para gerar relatórios durante um período de um mês inteiro e não apenas uma única semana.

   Para fazer isso, escolha criar um **[!UICONTROL Recurring email]** aqui, reagrupando os emails e os resultados **[!UICONTROL By month]**.

   Defina o conteúdo do seu email e insira o código promocional de boas-vindas. Para obter mais informações, consulte as seções [Definição de conteúdo de email](../../designing/using/personalization.md).

Em seguida, inicie a execução do workflow. Todas as semanas, os novos assinantes receberão o email de boas-vindas com o código promocional.
