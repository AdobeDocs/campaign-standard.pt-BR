---
title: Detalhamento por domínios
description: Com o relatório detalhado por domínios pronto para uso, saiba mais sobre os dados de desempenho de seus delivery, dependendo do domínio de cada cliente.
page-status-flag: never-activated
uuid: 75a64c81-325b-422f-b6ef-deb06eec7f7b
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: reporting
content-type: reference
topic-tags: list-of-reports
discoiquuid: 2ce174f9-5d7d-48b9-9235-6bf3e238ff37
context-tags: deliveryDomainBreakdownReport,main;campaignDomainBreakdownReport,main;programDomainBreakdownReport,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1b1fb4a0dc0f7881e24e10f8ac171feab2ac8cba
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 3%

---


# Detalhamento por domínios{#breakdown-by-domains}

Este relatório contém os dados de desempenho de cada domínio representado na audiência de um delivery de email. Se for um relatório de campanha ou programa, os dados de desempenho estarão disponíveis para várias audiências. Esses dados permitem analisar o comportamento de cada domínio em reação a eventos específicos. Por exemplo, exibição de link, URL na lista de bloqueios etc.

![](assets/delivery_reports_6.png)

A tabela Estatísticas **de** transmissão contém os dados disponíveis para possíveis erros encontrados em cada domínio, como:

* **Processado/enviado**: O número de emails enviados.
* **Entregue**: O número de emails entregues.
* **Rejeições + Erros**: O número de mensagens que não puderam ser entregues.
* **Rejeição** forçada: O número total de erros permanentes, como um endereço de email incorreto.
* **Rejeição** suave: O número total de erros temporários, como uma caixa de entrada completa.

A segunda tabela, Estatísticas **de** rastreamento, contém os dados disponíveis para a reatividade do recipient ao delivery, como:

* **Entregue**: O número de emails entregues
* **Abrir**: O número de vezes que uma mensagem foi aberta em um delivery.
* **Clique**: O número de vezes que o conteúdo foi clicado em um delivery.
* **Inscrito**: O número de cliques no link de subscrição.
* **mirror page**: O número de cliques no link do mirror page.
* **Na lista de bloqueios**: O número de recipient que declararam um email como spam ou lixo eletrônico. [Saiba mais](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

