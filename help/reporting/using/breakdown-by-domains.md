---
solution: Campaign Standard
product: campaign
title: Detalhamento por domínios
description: Com o relatório Análise por domínios pronto para uso, saiba mais sobre os dados de desempenho de seus deliveries, dependendo do domínio de cada cliente.
audience: reporting
content-type: reference
topic-tags: list-of-reports
context-tags: deliveryDomainBreakdownReport,main;campaignDomainBreakdownReport,main;programDomainBreakdownReport,main
feature: Reporting
role: Leader
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 3%

---


# Detalhamento por domínios{#breakdown-by-domains}

Este relatório contém os dados de desempenho de cada domínio representado no público-alvo para um delivery de email. Se for um relatório de campanha ou programa, os dados de desempenho estarão disponíveis para vários públicos-alvo. Esses dados permitem analisar o comportamento de cada domínio em reação a eventos específicos. Por exemplo, exibição de link, URL lista de bloqueios etc.

![](assets/delivery_reports_6.png)

A tabela **Broadcast statistics** contém os dados disponíveis para possíveis erros encontrados em cada domínio, como:

* **Processado/enviado**: O número de emails enviados.
* **Entregue**: O número de emails entregues.
* **Rejeições + Erros**: O número de mensagens que não puderam ser entregues.
* **Rejeição** permanente: O número total de erros permanentes, como um endereço de email incorreto.
* **Rejeição** suave: O número total de erros temporários, como uma caixa de entrada completa.

A segunda tabela, **Tracking statistics**, contém os dados disponíveis para a reatividade do recipient no delivery, como:

* **Entregue**: O número de emails entregues
* **Abrir**: O número de vezes que uma mensagem foi aberta em um delivery.
* **Clique em**: O número de vezes que o conteúdo foi clicado em um delivery.
* **Inscrições canceladas**: O número de cliques no link de subscrição.
* **Mirror Page**: O número de cliques no link da mirror page.
* **Na** lista de bloqueios: O número de recipients que declararam um email como spam ou lixo eletrônico. [Saiba mais](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

