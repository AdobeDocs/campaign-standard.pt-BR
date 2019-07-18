---
title: Resumo de rejeição
seo-title: Resumo de rejeição
description: Resumo de rejeição
seo-description: Com o resumo do Resumo da rejeição, saiba mais sobre o status de suas campanhas e erros que podem ser encontrados.
page-status-flag: nunca ativado
uuid: 90087311-4236-4 df 9-ae 7 d -4 a 15 c 00 c 70 ab
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: relatórios
content-type: reference
topic-tags: lista de relatórios
discoiquuid: 5 ae 561 b 4-03 cf -4541-87 ff -47 f 1027 d 53 b 8
context-tags: Bouncereport, principal; Campaigncirculationrelatório, principal; Programcirculationreport, Main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 77b0933bcd004cedc6a58f80717a4284b284e0cd

---


# Bounce summary{#bounce-summary}

Este relatório detalha os erros internos e internos gerais encontrados durante as entregas, bem como o processamento automático das rejeições.

![](assets/campaign_reports_bounces.png)

Cada tabela é representada por números de resumo e gráficos. É possível alterar como os detalhes são mostrados nas respectivas configurações de visualização.

**A distribuição** do Flop 5 lista as cinco entregas com o maior número de correias:

**A** tabela de motivos de Rejeição contém os dados disponíveis para os tipos de erros que resultaram em devoluções para cada entrega:

* **[!UICONTROL User unknown]**: O tipo de erro gerado quando uma entrega é enviada para um endereço de email inválido.
* **[!UICONTROL Invalid domain]**: O tipo de erro gerado quando uma entrega é enviada para um endereço de email cujo domínio está errado ou não existe mais.
* **[!UICONTROL Unreachable]**: O tipo de erro encontrado na string de entrega da mensagem. Por exemplo, o incidente de relâmpago SMTP, o domínio temporariamente inatingível, etc.
* **[!UICONTROL Account disabled]**: O tipo de erro gerado quando uma entrega é enviada para um endereço de email que não existe mais.
* **[!UICONTROL Mailbox full]**: O tipo de erro gerado quando a caixa de entrada do destinatário está cheia. Há cinco tentativas de entregar a mensagem antes que esse erro seja gerado.
* **[!UICONTROL Not connected]**: O tipo de erro gerado quando o telefone do destinatário está desligado ou não está conectado a uma rede no momento em que a mensagem é enviada.

   >[!NOTE]
   >
   >Esse tipo de erro diz respeito somente a entregas em canais móveis.

* **[!UICONTROL Refused]**: O tipo de erro gerado quando um endereço é recusado pelo provedor de serviços Internet (ISP). Por exemplo, quando uma regra de segurança é aplicada por um software anti-spam.

The **Domain repartition** table displays the overall problems encountered during the deliveries according to the recipient domain.
