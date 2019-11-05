---
title: Detalhamento por domínios
description: Com o relatório detalhado por domínios pronto para uso, saiba mais sobre os dados de desempenho de suas entregas, dependendo do domínio de cada cliente.
page-status-flag: nunca ativado
uuid: 75a64c81-325b-422f-b6ef-deb06eec7f7b
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: relatório
content-type: referência
topic-tags: lista de relatórios
discoiquuid: 2ce174f9-5d7d-48b9-9235-6bf3e238ff37
context-tags: deliveryDomainBreakdownReport,main;campaignDomainBreakdownReport,main;programDomainBreakdownReport,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Detalhamento por domínios{#breakdown-by-domains}

Este relatório contém os dados de desempenho de cada domínio representado no público-alvo para uma entrega de email. Se for um relatório de campanha ou programa, os dados de desempenho estarão disponíveis para vários públicos-alvo. Esses dados permitem analisar o comportamento de cada domínio em reação a eventos específicos. Por exemplo, exibição de link, lista negra de URL etc.

![](assets/delivery_reports_6.png)

A tabela Estatísticas **de** transmissão contém os dados disponíveis para possíveis erros encontrados em cada domínio, como:

* **Processado/enviado**: O número de emails enviados.
* **Entregue**: O número de emails entregues.
* **Rejeições + Erros**: O número de mensagens que não puderam ser entregues.
* **Rejeição** forçada: O número total de erros permanentes, como um endereço de email incorreto.
* **Rejeição** suave: O número total de erros temporários, como uma caixa de entrada completa.

A segunda tabela, Estatísticas **de** rastreamento, contém os dados disponíveis para a reatividade do destinatário na entrega, como:

* **Entregue**: O número de emails entregues
* **Abrir**: O número de vezes que uma mensagem foi aberta em uma entrega.
* **Clique**: O número de vezes que o conteúdo foi clicado em uma entrega.
* **Inscrito**: O número de cliques no link de assinatura.
* **Página** de espelho: O número de cliques no link da página espelhada.
* **Lista negra**: O número de destinatários que declararam um email como spam ou lixo eletrônico (consulte [Gerenciamento de listas negras no Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)).

