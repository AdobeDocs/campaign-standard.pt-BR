---
title: Resumo da rejeição
description: Com o relatório Pronto para uso do resumo de rejeição, saiba mais sobre o status das campanhas enviadas e os erros que elas podem ter encontrado.
audience: reporting
content-type: reference
topic-tags: list-of-reports
context-tags: bounceReport,main;campaignCirculationReport,main;programCirculationReport,main
feature: Reporting
role: Leader
level: Intermediate
exl-id: 03ea2f20-959c-497e-bd71-4e77132d712e
TQID: https://experienceleague.adobe.com/ggB-q-6kJyPF4GgJJzJGtsOqg6-7MeBhEfiGVY0M7sQ
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 282
ht-degree: 1%

---

# Resumo da rejeição{#bounce-summary}

Este relatório detalha os erros gerais de hardware e software encontrados durante os deliveries, bem como o processamento automático de rejeições (consulte [Noções básicas sobre falhas de delivery](../../sending/using/understanding-delivery-failures.md)).

![](assets/campaign_reports_bounces.png)

Cada tabela é representada por números de resumo e gráficos. É possível alterar como os detalhes são mostrados nas respectivas configurações de visualização.

A **repartição de Flop 5** lista as cinco entregas com o maior número de quarentenas:

A tabela **Motivos da rejeição** contém os dados disponíveis para os tipos de erros que causaram rejeições para cada entrega:

* **[!UICONTROL User unknown]**: O tipo de erro gerado quando uma entrega é enviada para um endereço de email inválido.
* **[!UICONTROL Invalid domain]**: O tipo de erro gerado quando uma entrega é enviada para um endereço de email cujo domínio está errado ou não existe mais.
* **[!UICONTROL Unreachable]**: O tipo de erro encontrado na cadeia de caracteres de entrega de mensagens, como domínio temporariamente inacessível.
* **[!UICONTROL Account disabled]**: O tipo de erro gerado quando uma entrega é enviada para um endereço de email que não existe mais.
* **[!UICONTROL Mailbox full]**: O tipo de erro gerado quando a caixa de entrada do destinatário está cheia. Há cinco tentativas de entregar a mensagem antes que esse erro seja gerado.
* **[!UICONTROL Not connected]**: O tipo de erro gerado quando o celular do destinatário está desligado ou não está conectado a uma rede no momento em que a mensagem é enviada.

  >[!NOTE]
  >
  >Esse tipo de erro só afeta deliveries em canais móveis.

* **[!UICONTROL Refused]**: O tipo de erro gerado quando um endereço é recusado pelo ISP (provedor de serviços de Internet). Por exemplo, quando uma regra de segurança tiver sido aplicada por um software antisspam.

A tabela **Repartição de domínio** exibe os problemas gerais encontrados durante as entregas de acordo com o domínio do destinatário.
