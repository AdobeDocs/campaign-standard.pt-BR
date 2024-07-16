---
title: Monitoramento da capacidade de entrega no Adobe Campaign Standard
description: Use as ferramentas oferecidas pelo Adobe Campaign Standard para monitorar a capacidade de delivery da sua plataforma.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Deliverability
role: User
level: Intermediate
exl-id: 683341fb-fef5-4aa1-8606-9526d9ae6290
source-git-commit: 449187bba167f9ce00e644d44a124b36030ba001
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 25%

---

# Monitoramento da capacidade de entrega{#monitor-deliverability}

Abaixo você encontrará detalhes sobre o relatório **[!UICONTROL Delivery throughput]**, bem como as diferentes ferramentas de monitoramento oferecidas pelo Adobe Campaign. Estas são algumas diretrizes adicionais sobre o monitoramento da capacidade de entrega:

* Verifique regularmente a taxa de transferência do delivery de toda a plataforma para verificar se ela é consistente com a configuração original.
* Verifique se as tentativas estão configuradas corretamente (30 minutos para o período de nova tentativa e mais de 20 tentativas) nos templates do delivery.
* Verifique regularmente se a caixa de rejeição está acessível e se a conta não está prestes a expirar.
* Verifique a taxa de transferência de cada delivery para garantir que ela seja consistente com a validade do conteúdo do delivery (por exemplo, &quot;vendas rápidas&quot; devem ser entregues em minutos, não em dias).
* Verifique se o número de erros e as novas quarentenas estão consistentes com outros deliveries.
* Incluir na lista de bloqueios Consulte os logs do delivery detalhadamente para verificar o tipo de erro destacado (perguntas, problemas de DNS, regras antisspam etc.).

## Taxa de transferência de entrega {#delivery-throughput}

Este relatório contém informações sobre a taxa de transferência de delivery da plataforma inteira por um determinado período para medir a velocidade em que as mensagens são entregues.

Para obter mais informações, consulte [Taxa de transferência de entrega](../../reporting/using/delivery-throughput.md).

![](assets/delivery_reports_1.png)

Você pode configurar os valores exibidos alterando a escala de tempo.

Outros relatórios estão disponíveis, como **[!UICONTROL Delivery summary]** ou **[!UICONTROL Non-deliverables and bounces]**. Para obter mais informações, consulte [Relatórios dinâmicos](../../reporting/using/about-dynamic-reports.md).

## Monitoramento de entregas {#monitoring-deliveries}

O painel de mensagens fornece acesso aos logs de entrega: **[!UICONTROL Sending logs]**, **[!UICONTROL Exclusion logs]**, **[!UICONTROL Exclusion causes]**, **[!UICONTROL Tracking logs]** e **[!UICONTROL Tracked URLs]**. Eles mostram os detalhes do envio, o público-alvo que foi excluído e o motivo, e as informações de rastreamento, como aberturas e cliques.

Para obter mais informações, consulte [Monitoramento de uma entrega](../../sending/using/monitoring-a-delivery.md)

![](assets/sending_delivery1.png)

## Recebimento de alertas {#receiving-alerts}

O recurso **[!UICONTROL Delivery alerting]** é um sistema de gerenciamento de alertas que permite que um grupo de usuários receba automaticamente notificações contendo informações sobre a execução de suas entregas.

Para obter mais informações, consulte [Recebendo alertas quando ocorrerem falhas](../../sending/using/receiving-alerts-when-failures-happen.md).

<!--## External tools (#external-tools)

### Signal Spam {#signal-spam}

Signal Spam is a French service which offers anonymized feedback loop reporting for French ISPs (Orange, SFR).

This service allows you to follow the reputation of the French ISPs and track customers' activity evolution.

Signal Spam also provides direct complaints that end users log through a dedicated interface. Those complaints are then quarantined from the email address database.

### 250ok {#solution-250ok}

250ok is a monitoring solution which provides IP and domain denylists, as well as reputation indicators.

The information provided is real-time, which allows for a pro-active assistance. 250ok a complementary solution to the Adobe deliverability internal tools.-->
