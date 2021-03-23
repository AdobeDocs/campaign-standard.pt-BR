---
solution: Campaign Standard
product: campaign
title: Monitoramento da capacidade de entrega no Adobe Campaign Standard
description: Use as ferramentas oferecidas pelo Adobe Campaign Standard para monitorar a capacidade de entrega da sua plataforma.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Avaliação do delivery
role: Profissional
level: Intermediário
translation-type: tm+mt
source-git-commit: fb9a6218bb754f803affde1fdf6c6fc01570126f
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 59%

---


# Monitoramento da capacidade de entrega{#monitor-deliverability}

Abaixo você encontrará detalhes sobre o relatório **[!UICONTROL Delivery throughput]**, bem como as diferentes ferramentas de monitoramento oferecidas pelo Adobe Campaign. Estas são algumas diretrizes adicionais sobre o monitoramento da capacidade de entrega:
* Verifique regularmente a taxa de transferência do delivery de toda a plataforma para verificar se ela é consistente com a configuração original.
* Verifique se as tentativas estão configuradas corretamente (30 minutos para o período de nova tentativa e mais de 20 tentativas) nos templates do delivery.
* Verifique regularmente se a caixa de rejeição está acessível e se a conta não está prestes a expirar.
* Verifique a taxa de transferência de cada delivery para garantir que ela seja consistente com a validade do conteúdo do delivery (por exemplo, &quot;vendas rápidas&quot; devem ser entregues em minutos, não em dias).
* Verifique se o número de erros e as novas quarentenas estão consistentes com outros deliveries.
* Consulte detalhadamente os logs do delivery para verificar o tipo de erro destacado (lista de bloqueios, problemas de DNS, regras anti-spam, etc…).

## Taxa de transferência da entrega {#delivery-throughput}

Este relatório contém informações sobre a taxa de transferência de delivery da plataforma inteira por um determinado período para medir a velocidade em que as mensagens são entregues.

Para obter mais informações, consulte [Taxa de transferência de delivery](../../reporting/using/delivery-throughput.md).

![](assets/delivery_reports_1.png)

Você pode configurar os valores exibidos alterando a escala de tempo.

Outros relatórios estão disponíveis, como **[!UICONTROL Delivery summary]** ou **[!UICONTROL Non-deliverables and bounces]**. Para obter mais informações, consulte [Relatórios dinâmicos](../../reporting/using/about-dynamic-reports.md).

## Monitoramento de deliveries {#monitoring-deliveries}

O painel de mensagens oferece acesso aos logs do delivery: **[!UICONTROL Sending logs]**, **[!UICONTROL Exclusion logs]**, **[!UICONTROL Exclusion causes]**, **[!UICONTROL Tracking logs]** e **[!UICONTROL Tracked URLs]**. Eles mostram os detalhes do envio, o target que foi excluído e o motivo, bem como as informações de rastreamento, como aberturas e cliques.

Para obter mais informações, consulte [Monitoramento de um delivery](../../sending/using/monitoring-a-delivery.md)

![](assets/sending_delivery1.png)

## Recebendo alertas {#receiving-alerts}

O recurso **[!UICONTROL Delivery alerting]** é um sistema de gerenciamento de alertas que permite que um grupo de usuários receba automaticamente notificações contendo informações sobre a execução de seus deliveries.

Para obter mais informações, consulte [Recebendo alertas quando ocorrerem falhas](../../sending/using/receiving-alerts-when-failures-happen.md).

<!--## External tools (#external-tools)

### Signal Spam {#signal-spam}

Signal Spam is a French service which offers anonymized feedback loop reporting for French ISPs (Orange, SFR).

This service allows you to follow the reputation of the French ISPs and track customers' activity evolution.

Signal Spam also provides direct complaints that end users log through a dedicated interface. Those complaints are then quarantined from the email address database.

### 250ok {#solution-250ok}

250ok is a monitoring solution which provides IP and domain denylists, as well as reputation indicators.

The information provided is real-time, which allows for a pro-active assistance. 250ok a complementary solution to the Adobe deliverability internal tools.-->
