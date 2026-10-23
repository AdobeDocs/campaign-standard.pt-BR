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
TQID: 'https://experienceleague.adobe.com/25Ci4GFEJHIO3Ed2BTBF2qUmD4LKh3jwUC56K8JZgzA'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: c309ee4e-82e4-4f7e-b608-ef345678c34e
    internal-label: Dynamic reporting
subfeature_v2:
  - id: b3a4149f-2b3a-44d1-894e-e3ac4c77fb47
    internal-label: Reporting interface
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 3%
---
# Detalhamento por domínios{#breakdown-by-domains}

Este relatório contém os dados de desempenho de cada domínio representado no público-alvo de uma entrega de email. Se for um relatório de campanha ou de programa, os dados de desempenho estão disponíveis para vários públicos-alvo. Esses dados permitem analisar o comportamento de cada domínio em reação a eventos específicos. Por exemplo, exibição de link, URL de inclui na lista de bloqueios etc.

![](assets/delivery_reports_6.png)

A tabela **Estatísticas de transmissão** contém os dados disponíveis para possíveis erros encontrados com cada domínio, como:

* **Processados/enviados**: o número de emails enviados.
* **Entregues**: o número de emails entregues.
* **Rejeições + Erros**: o número de mensagens que não puderam ser entregues.
* **Rejeição permanente**: o número total de erros permanentes, como um endereço de email incorreto.
* **Rejeição temporária**: o número total de erros temporários, como uma caixa de entrada cheia.

A segunda tabela, **Estatísticas de rastreamento**, contém os dados disponíveis para a reatividade do destinatário para entrega, como:

* **Entregues**: o número de emails entregues
* **Aberto**: o número de vezes que uma mensagem foi aberta em uma entrega.
* **Clique**: o número de vezes que o conteúdo foi clicado em uma entrega.
* **Cancelar assinatura**: o número de cliques no link de assinatura.
* **Mirror Page**: o número de cliques no link da mirror page.
* **Na inclui na lista de bloqueios**: o número de destinatários que declararam um email como spam ou lixo eletrônico. [Saiba mais](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)
