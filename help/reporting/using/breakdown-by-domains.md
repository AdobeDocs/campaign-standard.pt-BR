---
title: Detalhamento por domínios
seo-title: Detalhamento por domínios
description: Detalhamento por domínios
seo-description: Com o Detalhamento por domínios out-of-the-box, saiba mais sobre os dados de desempenho de suas entregas, dependendo de cada domínio do cliente.
page-status-flag: nunca ativado
uuid: 75 a 64 c 81-325 b -422 f-b 6 ef-deb 06 eec 7 f 7 b
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: relatórios
content-type: reference
topic-tags: lista de relatórios
discoiquuid: 2 ce 174 f 9-5 d 7 d -48 b 9-9b35-6 bf 3 e 238 ff 37
context-tags: Deliverydomainbreakdownreport, principal; Campaigndomainbreakdownreport, main; Programdomainbreakdownreport, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 77b0933bcd004cedc6a58f80717a4284b284e0cd

---


# Breakdown by domains{#breakdown-by-domains}

Este relatório contém os dados de desempenho de cada domínio representado no público-alvo para uma entrega de email. Se for um relatório de campanha ou programa, os dados de desempenho estarão disponíveis para vários públicos-alvo. Esses dados permitem analisar o comportamento de cada domínio em reação a eventos específicos. Por exemplo, exibição de link, lista de negação de URL etc.

![](assets/delivery_reports_6.png)

The table **Broadcast statistics** contains the available data for possible errors encountered with each domain, such as:

* **Processado/enviado**: O número de e-mails enviados.
* **Entregue**: O número de emails entregues.
* **Rejeições + erros**: O número de mensagens que não puderam ser entregues.
* **Rejeição Hard**: O número total de erros permanentes, como um endereço de email errado.
* **Rejeição suave**: O número total de erros temporários, como uma caixa de entrada completa.

The second table, **Tracking statistics**, contains the available data for recipient reactivity to delivery, such as:

* **Entregue**: O número de emails entregues
* **Abrir**: O número de vezes que uma mensagem foi aberta em uma entrega.
* **Clique** em: O número de vezes que o conteúdo foi clicado em uma entrega.
* **Cancelar inscrição**: O número de cliques no link de assinatura.
* **Página espelhada**: O número de cliques no link da página espelhada.
* **Lista negra**: O número de destinatários que declararam um email como spam ou lixo (consulte [Gerenciamento de lista negra no Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)).

