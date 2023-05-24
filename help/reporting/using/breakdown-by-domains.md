---
title: Detalhamento por domínios
description: Com o relatório Detalhamento por domínios pronto para uso, saiba mais sobre os dados de desempenho de seus deliveries dependendo do domínio de cada cliente.
audience: reporting
content-type: reference
topic-tags: list-of-reports
context-tags: deliveryDomainBreakdownReport,main;campaignDomainBreakdownReport,main;programDomainBreakdownReport,main
feature: Reporting
role: Leader
level: Intermediate
exl-id: 513d74ae-10c0-4d41-a7d1-8ed655e1a2d1
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 3%

---

# Detalhamento por domínios{#breakdown-by-domains}

Este relatório contém os dados de desempenho de cada domínio representado no público-alvo de uma entrega de email. Se for um relatório de campanha ou de programa, os dados de desempenho estão disponíveis para vários públicos-alvo. Esses dados permitem analisar o comportamento de cada domínio em reação a eventos específicos. Por exemplo, exibição de link, URL de inclui na lista de bloqueios etc.

![](assets/delivery_reports_6.png)

A tabela **Estatísticas de transmissão** contém os dados disponíveis para possíveis erros encontrados com cada domínio, como:

* **Processado/enviado**: o número de emails enviados.
* **Entregue**: o número de emails entregues.
* **Devoluções + Erros**: o número de mensagens que não puderam ser entregues.
* **Rejeição permanente**: o número total de erros permanentes, como um endereço de email incorreto.
* **Rejeição leve**: o número total de erros temporários, como uma caixa de entrada cheia.

A segunda tabela, **Estatísticas de rastreamento**, contém os dados disponíveis para a reatividade do recipient ao delivery, como:

* **Entregue**: o número de emails entregues
* **Abertura**: o número de vezes que uma mensagem foi aberta em um delivery.
* **Clique em**: O número de vezes que o conteúdo foi clicado em um delivery.
* **Assinatura cancelada**: O número de cliques no link de subscrição.
* **Mirror Page**: o número de cliques no link da mirror page.
* **Na inclui na lista de bloqueios**: o número de recipients que declararam um email como spam ou lixo eletrônico. [Saiba mais](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)
