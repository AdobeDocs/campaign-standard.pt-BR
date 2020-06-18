---
title: Monitoramento da entrega no Adobe Campaign Standard
description: Use as ferramentas oferecidas pelo Adobe Campaign Standard para monitorar a capacidade de entrega da sua plataforma.
page-status-flag: never-activated
uuid: 286fceee-65a9-4cb9-b205-9ce5d024675c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 9c7fd670-bba9-4f3c-8cb1-87397a1acd27
context-tags: delivery,schedule,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c89973e2c733d9c0b1c4434e77ef51103ccde0fa
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 50%

---


# Monitoramento da capacidade de entrega{#monitor-deliverability}

Abaixo, você encontrará detalhes sobre o **[!UICONTROL Delivery throughput]** relatório, bem como sobre as diferentes ferramentas de monitoramento oferecidas pelo Adobe Campaign. Estas são algumas diretrizes adicionais sobre o monitoramento da capacidade de entrega:
* Verifique regularmente a taxa de transferência do delivery de toda a plataforma para verificar se ela é consistente com a configuração original.
* Verifique se as tentativas estão configuradas corretamente (30 minutos para o período de nova tentativa e mais de 20 tentativas) nos templates do delivery.
* Verifique regularmente se a caixa de rejeição está acessível e se a conta não está prestes a expirar.
* Verifique a taxa de transferência de cada delivery para garantir que ela seja consistente com a validade do conteúdo do delivery (por exemplo, &quot;vendas rápidas&quot; devem ser entregues em minutos, não em dias).
* Ao usar as ondas, verifique se cada onda tem tempo suficiente para terminar antes que a próxima seja acionada.
* Verifique se o número de erros e as novas quarentenas estão consistentes com outros deliveries.
* Consulte os logs do delivery cuidadosamente em detalhes para verificar o tipo de erros que são destacados (listas de blocos, problemas de DNS, regras antisspam, etc.).

## Taxa de transferência da entrega {#delivery-throughput}

Este relatório contém informações sobre a throughput do delivery de toda a plataforma durante um determinado período para medir a velocidade na qual as mensagens são entregues.

For more on this, see [Delivery throughput](../../reporting/using/delivery-throughput.md).

![](assets/delivery_reports_1.png)

Você pode configurar os valores exibidos alterando a escala de tempo.

Outros relatórios estão disponíveis, como **[!UICONTROL Delivery summary]** ou **[!UICONTROL Non-deliverables and bounces]**. Para obter mais informações, consulte Relatórios [](../../reporting/using/about-dynamic-reports.md)dinâmicos.

## Monitoramento de deliveries {#monitoring-deliveries}

O painel de mensagem fornece acesso aos logs do delivery: **[!UICONTROL Sending logs]**, **[!UICONTROL Exclusion logs]**, **[!UICONTROL Exclusion causes]**, **[!UICONTROL Tracking logs]** e **[!UICONTROL Tracked URLs]**. Eles mostram os detalhes do envio, qual público alvo foi excluído e por que, bem como as informações de rastreamento, como abrir e clicar.

Para obter mais informações, consulte [Monitoramento de um delivery](../../sending/using/monitoring-a-delivery.md)

![](assets/sending_delivery1.png)

## Recebendo alertas {#receiving-alerts}

O **[!UICONTROL Delivery alerting]** recurso é um sistema de gerenciamento de alertas que permite que um grupo de usuários receba automaticamente notificações contendo informações sobre a execução de seus delivery.

Para obter mais informações, consulte [Recebendo alertas quando ocorrerem](../../sending/using/receiving-alerts-when-failures-happen.md)falhas.

## Signal Spam {#signal-spam}

O Signal Spam é um serviço francês que oferece relatórios de ciclo de feedback anônimo para ISPs franceses (Orange, SFR).

Esse serviço permite que você acompanhe a reputação dos ISPs franceses e rastreie a evolução da atividade dos clientes.

O Signal Spam também fornece reclamações diretas que os usuários finais registram por meio de uma interface dedicada. Essas reclamações são colocadas em quarentena a partir do banco de dados de endereços de email.

## 250ok {#solution-250ok}

250ok é uma solução de monitoramento que fornece listas de blocos de domínio e IP, bem como indicadores de reputação.

As informações fornecidas são em tempo real, o que permite uma assistência proativa. 250ok uma solução complementar para as ferramentas internas de entrega da Adobe.
