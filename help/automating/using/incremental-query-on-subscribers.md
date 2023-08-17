---
title: Query incremental para assinantes de um serviço
description: O exemplo a seguir apresenta como configurar uma atividade Query incremental para filtrar assinantes de um serviço.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: incremental,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: c80ed1f6-ad8a-4448-a6df-b9881327228a
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 67%

---

# Query incremental para assinantes de um serviço {#example--incremental-query-on-subscribers-to-a-service}

O exemplo a seguir mostra a configuração de uma atividade **[!UICONTROL Incremental query]** que filtra os perfis no banco de dados do Adobe Campaign que estão inscritos no serviço **Running Newsletter** para enviar um email de boas-vindas contendo um código promocional.

O workflow é composto pelos seguintes elementos:

![](assets/incremental_query_example1.png)

* A [Scheduler](../../automating/using/scheduler.md) atividade, para executar o workflow todas as segundas-feiras às 6 horas.

  ![](assets/incremental_query_example2.png)

* Um [Query incremental](../../automating/using/incremental-query.md) atividade direcionada a todos os assinantes atuais durante a primeira execução e depois somente os novos assinantes daquela semana durante as execuções a seguir.

  ![](assets/incremental_query_example3.png)

* Um [Entrega de email](../../automating/using/email-delivery.md) atividade. O workflow é executado uma vez por semana, mas você pode agregar os emails enviados e os resultados por mês, por exemplo, para gerar relatórios durante um período de um mês inteiro e não apenas uma única semana.

  Para fazer isso, escolha criar um **[!UICONTROL Recurring email]** aqui, reagrupando os emails e os resultados **[!UICONTROL By month]**.

  Defina o conteúdo do seu email e insira o código promocional de boas-vindas. Para obter mais informações, consulte [Definição do conteúdo do email](../../designing/using/personalization.md) seções.

Em seguida, inicie a execução do workflow. Todas as semanas, os novos assinantes receberão o email de boas-vindas com o código promocional.
