---
title: Query incremental dos assinantes de um serviço
description: O exemplo a seguir apresenta como configurar uma atividade de Query incremental para filtrar assinantes de um serviço.
page-status-flag: never-activated
uuid: 73b42422-e815-43ef-84c0-97c4433ccc98
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 80961e73-42ec-463a-8496-cff69fab0475
context-tags: incremental,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 0%

---


# Query incremental dos assinantes de um serviço {#example--incremental-query-on-subscribers-to-a-service}

O exemplo a seguir mostra a configuração de uma **[!UICONTROL Incremental query]** atividade que filtros os perfis no banco de dados do Adobe Campaign que estão inscritos no serviço **Running Newsletter** para enviar um email de boas-vindas contendo um código promocional.

O fluxo de trabalho é composto pelos seguintes elementos:

![](assets/incremental_query_example1.png)

* Uma atividade de [Scheduler](../../automating/using/scheduler.md) , para executar o fluxo de trabalho todas as segundas-feiras às 6 horas.

   ![](assets/incremental_query_example2.png)

* Uma atividade de [Query incremental](../../automating/using/incremental-query.md) , que público alvo todos os assinantes atuais durante a primeira execução, então apenas os novos assinantes daquela semana durante as execuções a seguir.

   ![](assets/incremental_query_example3.png)

* Uma atividade [de delivery](../../automating/using/email-delivery.md) por email. O fluxo de trabalho é executado uma vez por semana, mas você pode agregação os emails enviados e os resultados por mês, por exemplo, para gerar relatórios durante um período de um mês inteiro e não apenas uma única semana.

   Para fazer isso, escolha criar um **[!UICONTROL Recurring email]** aqui que agrupe os emails e os resultados **[!UICONTROL By month]**.

   Defina o conteúdo de seu email e insira o código promocional de boas-vindas. Para obter mais informações, consulte [Definição de seções de conteúdo](../../designing/using/personalization.md) de email.

Em seguida, start a execução do fluxo de trabalho. Todas as semanas, os novos assinantes receberão o email de boas-vindas com o código promocional.
