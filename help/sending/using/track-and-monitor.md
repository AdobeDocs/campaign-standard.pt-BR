---
solution: Campaign Standard
product: campaign
title: Rastrear e monitorar mensagens
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: Saiba como o Adobe Campaign permite acompanhar as mensagens enviadas e descobrir como os recipients reagem ao seu delivery
feature: Deliverability
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '436'
ht-degree: 46%

---


# Rastrear e monitorar {#track-and-monitor}

Você clicou no botão Enviar? Vamos ver o que acontece. Depois que o delivery é enviado, o Adobe Campaign permite acompanhar as mensagens enviadas e descobrir como os recipients reagem ao seu delivery. Isso o ajudará a melhorar o envio futuro e a otimizar as próximas campanhas.

## Monitoramento de deliveries {#monitoring-deliveries}

Para controlar suas campanhas, você deve garantir que a mensagem tenha sido entregue aos recipients.

**Dicas**

* Você pode controlar o status das mensagens nos logs do delivery.

* Para acompanhar os sucessos ou as falhas do delivery, o Adobe Campaign fornece um sistema de alerta por email que envia notificações para informar os usuários sobre atividades importantes do sistema.

* No painel de mensagens, é possível acessar vários relatórios para essa mensagem específica.

Para obter mais informações, consulte [Monitorando um delivery](../../sending/using/monitoring-a-delivery.md).

## Rastreamento {#tracking-deliveries}

Para conhecer melhor o comportamento dos perfis segmentados, você pode acompanhar como eles reagem a um delivery: recepção, abertura, cliques em links, unsubscriptions, etc. Consulte a guia **Tracking logs** do delivery.

**Dica**: o rastreamento de mensagens é habilitado por padrão. Para configurar URLs, selecione a opção Exibir URLs na seção inferior do assistente do delivery. Para cada URL da mensagem, você pode escolher se deseja ativar o rastreamento.

Para obter mais informações, consulte a seção [Tracking messages](../../sending/using/tracking-messages.md) e a descrição [Tracking indicators](../../reporting/using/tracking-indicators.md).

## Relatórios dinâmicos {#dyn-reports}

Relatórios dinâmicos permitem que você crie relatórios totalmente personalizáveis e em tempo real para monitorar suas campanhas. Dimension, métricas e visualizações permitem medir o impacto e o sucesso de suas campanhas nos recipients.

**Dica**  - Relatórios integrados estão disponíveis para você monitorar suas campanhas, mas esses relatórios também podem ser personalizados arrastando e soltando quaisquer métricas ou dimensões em seu relatório.

Para obter mais informações, consulte o [Guia de relatórios](../../reporting/using/about-dynamic-reports.md).

## Hot clicks

O relatório Hot clicks apresenta o conteúdo da mensagem (HTML e/ou texto) com a porcentagem de cliques em cada link. Ao exibir a porcentagem de cliques em cada conteúdo dinâmico, você pode avaliar qual conteúdo agrada mais aos destinatários.

Para obter mais informações, consulte o [Relatório de cliques ativos](../../reporting/using/hot-clicks.md).

## Dicas de desempenho de delivery {#performance-tips}

* Não mantenha os deliveries em estado de falha na instância, pois tabelas temporárias serão mantidas e o desempenho será afetado.

* Remova as remessas que não são mais necessárias e os destinatários inativos do banco de dados para manter a qualidade do endereço.

* Não tente programar deliveries grandes juntos. Observe que pode levar de 5 a 10 minutos para que a carga seja uniformemente espalhada sobre o sistema.

**Tópicos relacionados:**

* [Receber alertas quando ocorrerem falhas](../../sending/using/receiving-alerts-when-failures-happen.md)
* [Relatórios](../../reporting/using/about-dynamic-reports.md)
