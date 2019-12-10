---
title: Monitoramento da entrega no Adobe Campaign Standard
description: Use as ferramentas oferecidas pelo Adobe Campaign Standard para monitorar a entrega da plataforma.
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
source-git-commit: 1d5bb21ab16df87e268b9eabe92965be1b052556

---


# Monitoramento da entrega{#monitor-deliverability}

Abaixo você encontrará detalhes sobre o **[!UICONTROL Delivery throughput]** relatório, bem como as diferentes ferramentas de monitoramento oferecidas pelo Adobe Campaign. Estas são algumas diretrizes adicionais sobre o monitoramento de entrega:
* Verifique regularmente a taxa de transferência de entrega para toda a plataforma para verificar se ela é consistente com a configuração original.
* Verifique se as tentativas estão configuradas corretamente (30 minutos para o período de tentativas e mais de 20 tentativas) nos modelos de entrega.
* Verifique regularmente se a caixa de correio de rejeição está acessível e se a conta não está prestes a expirar.
* Verifique cada throughput de entrega para certificar-se de que ele é consistente com a validade do conteúdo de entrega (por exemplo, "vendas flash" devem ser entregues em minutos, não em dias).
* Ao usar ondas, verifique se cada onda tem tempo suficiente para terminar antes que a próxima seja acionada.
* Verifique se o número de erros e as novas quarentena estão de acordo com outras entregas.
* Consulte cuidadosamente os registros de entrega para verificar o tipo de erros destacados (lista em cinza ou preto, problemas de DNS, regras antisspam etc.).

## Taxa de transferência da entrega {#delivery-throughput}

Este relatório contém informações sobre a taxa de transferência de entrega de toda a plataforma durante um determinado período para medir a velocidade de entrega das mensagens.

Para saber mais sobre isso, consulte [Taxa de transferência](../../reporting/using/delivery-throughput.md).

![](assets/delivery_reports_1.png)

Você pode configurar os valores exibidos alterando a escala de tempo.

Outros relatórios estão disponíveis, como **[!UICONTROL Delivery summary]** ou **[!UICONTROL Non-deliverables and bounces]**. Para obter mais informações, consulte Relatórios [](../../reporting/using/about-dynamic-reports.md)dinâmicos.

## Monitoramento das entregas {#monitoring-deliveries}

O painel de mensagens fornece acesso aos registros de entrega: **[!UICONTROL Sending logs]**, **[!UICONTROL Exclusion logs]**, **[!UICONTROL Exclusion causes]**, **[!UICONTROL Tracking logs]** e **[!UICONTROL Tracked URLs]**. Eles mostram os detalhes do envio, qual destino foi excluído e por que, bem como as informações de rastreamento, como abrir e clicar.

Para obter mais informações, consulte [Monitoramento de uma entrega](../../sending/using/monitoring-a-delivery.md).

![](assets/sending_delivery1.png)

## Recebendo alertas {#receiving-alerts}

O **[!UICONTROL Delivery alerting]** recurso é um sistema de gerenciamento de alertas que permite que um grupo de usuários receba automaticamente notificações contendo informações sobre a execução de suas entregas.

Para obter mais informações, consulte [Recebendo alertas quando ocorrerem](../../sending/using/receiving-alerts-when-failures-happen.md)falhas.

## Spam de sinal {#signal-spam}

Signal Spam é um serviço francês que oferece relatórios anônimos de feedback para ISPs franceses (Orange, SFR).

Esse serviço permite que você acompanhe a reputação dos ISPs franceses e rastreie a evolução da atividade dos clientes.

O Signal Spam também fornece reclamações diretas que os usuários finais registram por meio de uma interface dedicada. Essas reclamações são colocadas em quarentena a partir do banco de dados de endereços de email.

## 250 ok {#solution-250ok}

250ok é uma solução de monitoramento que fornece IP, lista negra de domínios e indicadores de reputação.

As informações fornecidas são em tempo real, o que permite uma assistência pró-ativa. 250ok uma solução complementar para as ferramentas internas de entrega da Adobe.
