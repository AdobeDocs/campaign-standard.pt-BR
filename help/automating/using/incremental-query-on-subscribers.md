---
title: Consulta incremental para assinantes de um serviço
description: O exemplo a seguir apresenta como configurar uma atividade Query incremental para filtrar assinantes de um serviço.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: incremental,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: c80ed1f6-ad8a-4448-a6df-b9881327228a
TQID: 'https://experienceleague.adobe.com/MHB1ETCecN9gQq51bSii-keTyFaYof0JtAyckFSCKQE'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 61%
---
# Consulta incremental para assinantes de um serviço {#example--incremental-query-on-subscribers-to-a-service}

O exemplo a seguir mostra a configuração de uma atividade **[!UICONTROL Incremental query]** que filtra os perfis no banco de dados do Adobe Campaign que estão inscritos no serviço **Running Newsletter** para enviar um email de boas-vindas contendo um código promocional.

O fluxo de trabalho é composto pelos seguintes elementos:

![](assets/incremental_query_example1.png)

* Uma atividade [Scheduler](../../automating/using/scheduler.md), para executar o fluxo de trabalho todas as segundas-feiras às 6 horas.

  ![](assets/incremental_query_example2.png)

* Uma atividade [Query incremental](../../automating/using/incremental-query.md), que segmenta todos os assinantes atuais durante a primeira execução e depois somente os novos assinantes daquela semana durante as execuções a seguir.

  ![](assets/incremental_query_example3.png)

* Uma atividade de [Entrega de email](../../automating/using/email-delivery.md). O fluxo de trabalho é executado uma vez por semana, mas você pode agregar os emails enviados e os resultados por mês, por exemplo, para gerar relatórios durante um período de um mês inteiro e não apenas uma única semana.

  Para fazer isso, escolha criar um **[!UICONTROL Recurring email]** aqui, reagrupando os emails e os resultados **[!UICONTROL By month]**.

  Defina o conteúdo do seu email e insira o código promocional de boas-vindas. Para obter mais informações, consulte as [seções Definição do conteúdo do email](../../designing/using/personalization.md).

Em seguida, inicie a execução do fluxo de trabalho. Todas as semanas, os novos assinantes receberão o email de boas-vindas com o código promocional.
