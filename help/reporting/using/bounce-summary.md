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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: bee7ea0f1728da2a96c1f225b91b13a7903be660

---


# Resumo da rejeição{#bounce-summary}

Este relatório detalha os erros gerais de hardware e software encontrados durante as entregas, bem como o processamento automático de rejeições.

![](assets/campaign_reports_bounces.png)

Cada tabela é representada por números de resumo e gráficos. Você pode alterar a forma como os detalhes são exibidos em suas respectivas configurações de visualização.

**A repartição** Flop 5 lista as cinco distribuições com o maior número de quarentena:

A tabela de motivos **de** rejeição contém os dados disponíveis para os tipos de erros que causaram rejeições para cada entrega:

* **[!UICONTROL User unknown]**: O tipo de erro gerado quando uma entrega é enviada para um endereço de email inválido.
* **[!UICONTROL Invalid domain]**: O tipo de erro gerado quando uma entrega é enviada para um endereço de email cujo domínio está errado ou não existe mais.
* **[!UICONTROL Unreachable]**: O tipo de erro encontrado na cadeia de entrega de mensagens, como domínio temporariamente inacessível.
* **[!UICONTROL Account disabled]**: O tipo de erro gerado quando uma entrega é enviada para um endereço de email que não existe mais.
* **[!UICONTROL Mailbox full]**: O tipo de erro gerado quando a caixa de entrada do destinatário está cheia. Há cinco tentativas de entregar a mensagem antes que esse erro seja gerado.
* **[!UICONTROL Not connected]**: O tipo de erro gerado quando o telefone celular do destinatário está desligado ou não está conectado a uma rede no momento em que a mensagem é enviada.

   >[!NOTE]
   >
   >Esse tipo de erro só diz respeito às entregas em canais móveis.

* **[!UICONTROL Refused]**: O tipo de erro gerado quando um endereço é recusado pelo provedor de serviços de Internet (ISP). Por exemplo, quando uma regra de segurança é aplicada por software antisspam.

A tabela de repartição **de** domínio exibe os problemas gerais encontrados durante as entregas de acordo com o domínio do destinatário.
