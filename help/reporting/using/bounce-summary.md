---
title: Resumo da rejeição
description: Com o relatório resumido de rejeição pronto para uso, saiba mais sobre o status de suas campanhas enviadas e os erros que elas podem ter encontrado.
page-status-flag: never-activated
uuid: 90087311-4236-4df9-ae7d-4a15c00c70ab
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: reporting
content-type: reference
topic-tags: list-of-reports
discoiquuid: 5ae561b4-03cf-4541-87ff-47f1027d53b8
context-tags: bounceReport,main;campaignCirculationReport,main;programCirculationReport,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 8%

---


# Resumo da rejeição{#bounce-summary}

Esse relatório detalha os erros gerais de hardware e software encontrados durante os deliveries, bem como o processamento automático de rejeições.

![](assets/campaign_reports_bounces.png)

Cada tabela é representada por números de resumo e gráficos. Você pode alterar a forma como os detalhes são exibidos em suas respectivas configurações de visualização.

**A repartição** Flop 5 lista os cinco delivery com o maior número de quarentenas:

A tabela de motivos **de** rejeição contém os dados disponíveis para os tipos de erros que causaram saltos para cada delivery:

* **[!UICONTROL User unknown]**: O tipo de erro gerado quando um delivery é enviado para um endereço de email inválido.
* **[!UICONTROL Invalid domain]**: O tipo de erro gerado quando um delivery é enviado para um endereço de email cujo domínio está errado ou não existe mais.
* **[!UICONTROL Unreachable]**: O tipo de erro encontrado na cadeia de caracteres de delivery de mensagem, como domínio temporariamente inacessível.
* **[!UICONTROL Account disabled]**: O tipo de erro gerado quando um delivery é enviado para um endereço de email que não existe mais.
* **[!UICONTROL Mailbox full]**: O tipo de erro gerado quando a caixa de entrada do recipient está cheia. Há cinco tentativas de entregar a mensagem antes que esse erro seja gerado.
* **[!UICONTROL Not connected]**: O tipo de erro gerado quando o telefone móvel do recipient está desligado ou não está conectado a uma rede no momento em que a mensagem é enviada.

   >[!NOTE]
   >
   >Esse tipo de erro diz respeito apenas a delivery em canais móveis.

* **[!UICONTROL Refused]**: O tipo de erro gerado quando um endereço é recusado pelo ISP (Internet provedor de serviço). Por exemplo, quando uma regra de segurança é aplicada por software antisspam.

A tabela de repartição **de** domínio exibe os problemas gerais encontrados durante os delivery de acordo com o domínio do recipient.
