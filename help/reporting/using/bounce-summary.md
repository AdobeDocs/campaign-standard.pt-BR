---
solution: Campaign Standard
product: campaign
title: Resumo da rejeição
description: Com o relatório pronto para uso do resumo de rejeição, saiba mais sobre o status das campanhas enviadas e os erros que elas podem ter encontrado.
audience: reporting
content-type: reference
topic-tags: list-of-reports
context-tags: bounceReport,main;campaignCirculationReport,main;programCirculationReport,main
feature: Reporting
role: Leader
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 1%

---


# Resumo da rejeição{#bounce-summary}

Esse relatório detalha os erros gerais de hardware e software encontrados durante os deliveries, bem como o processamento automático de rejeições (consulte [Entendendo as falhas de delivery](../../sending/using/understanding-delivery-failures.md)).

![](assets/campaign_reports_bounces.png)

Cada tabela é representada por números de resumo e gráficos. Você pode alterar como os detalhes são mostrados em suas respectivas configurações de visualização.

**A** repartição Flop 5 lista os cinco deliveries com o maior número de quarentenas:

A tabela **Bounce reasons** contém os dados disponíveis para os tipos de erros que causaram devoluções para cada delivery:

* **[!UICONTROL User unknown]**: O tipo de erro gerado quando um delivery é enviado a um endereço de email inválido.
* **[!UICONTROL Invalid domain]**: O tipo de erro gerado quando um delivery é enviado a um endereço de email cujo domínio está errado ou não existe mais.
* **[!UICONTROL Unreachable]**: O tipo de erro encontrado na cadeia de caracteres de delivery de mensagem, como domínio temporariamente inacessível.
* **[!UICONTROL Account disabled]**: O tipo de erro gerado quando um delivery é enviado para um endereço de email que não existe mais.
* **[!UICONTROL Mailbox full]**: O tipo de erro gerado quando a caixa de entrada do recipient está cheia. Há cinco tentativas de entregar a mensagem antes que esse erro seja gerado.
* **[!UICONTROL Not connected]**: O tipo de erro gerado quando o celular do recipient está desligado ou não está conectado a uma rede no momento em que a mensagem é enviada.

   >[!NOTE]
   >
   >Esse tipo de erro só afeta deliveries em canais móveis.

* **[!UICONTROL Refused]**: O tipo de erro gerado quando um endereço é recusado pelo provedor de serviços de Internet (ISP). Por exemplo, quando uma regra de segurança é aplicada por um software antisspam.

A tabela **Domain repartição** exibe os problemas gerais encontrados durante os deliveries de acordo com o domínio do recipient.
