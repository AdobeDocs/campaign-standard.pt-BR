---
title: Rastrear e monitorar mensagens
seo-title: Rastrear e monitorar mensagens
page-status-flag: never-activated
uuid: a540efc7-105d-4c7f-a2ee-ade4d22b3445
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
discoiquuid: 0cbc4e92-482f-4dac-a1fb-b738e7127938
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 469d2a8b3f8026087929583affd2c294e2a954bb
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 49%

---


# Rastrear e monitorar {#track-and-monitor}

Você clicou no botão Enviar? Vamos ver o que acontece. Depois que o delivery é enviado, o Adobe Campaign permite acompanhar as mensagens enviadas e descobrir como os recipients reagem ao seu delivery. Isso o ajudará a melhorar o envio futuro e a otimizar as próximas campanhas.

## Monitorar deliveries {#monitoring-deliveries}

Para controlar suas campanhas, você deve garantir que a mensagem tenha sido entregue aos recipients.

**Dicas**

* É possível controlar o status das mensagens nos logs do delivery.

* Para acompanhar os sucessos ou falhas do delivery, a Adobe Campaign fornece um sistema de alerta por email que envia notificações para informar os usuários sobre atividades importantes do sistema.

* No painel de mensagens, você pode acessar vários relatórios para essa mensagem específica.

For more this, see [Monitoring a delivery](../../sending/using/monitoring-a-delivery.md).

## Rastreamento {#tracking-deliveries}

Para conhecer melhor o comportamento de seus perfis direcionados, você pode rastrear como eles reagem a um delivery: recepção, abertura, cliques em links, unsubscription etc. Consulte a guia **Logs de rastreamento** do delivery.

**Dica**: o rastreamento de mensagens é habilitado por padrão. Para configurar URLs, selecione a opção Exibir URLs na seção inferior do assistente do delivery. Para cada URL da mensagem, você pode escolher se deseja ativar o rastreamento.

For more on this, refer to the [Tracking messages](../../sending/using/tracking-messages.md) section and the [Tracking indicators](../../reporting/using/tracking-indicators.md) description.

## Relatórios dinâmicos {#dyn-reports}

Relatórios dinâmicos permitem criar relatórios totalmente personalizáveis e em tempo real para monitorar suas campanhas. Dimension, métricas e visualizações permitem medir o impacto e o sucesso de suas campanhas nos recipient.

**Dica** - Relatórios incorporados estão disponíveis para você monitorar suas campanhas, mas esses relatórios também podem ser personalizados arrastando e soltando quaisquer métricas ou dimensões em seu relatório.

For more on this, refer to the [Reporting guide](../../reporting/using/about-dynamic-reports.md).

## Hot clicks

O relatório de cliques ativos apresenta o conteúdo da mensagem (HTML e/ou texto) com a porcentagem de cliques em cada link. Ao exibir a porcentagem de cliques em cada conteúdo dinâmico, você pode avaliar qual conteúdo agrada mais aos destinatários.

Para saber mais sobre isso, consulte o relatório [de](../../reporting/using/hot-clicks.md)cliques ativos.

## Dicas de desempenho do delivery {#performance-tips}

* Não mantenha os deliveries em estado de falha na instância, pois tabelas temporárias serão mantidas e o desempenho será afetado.

* Remova as remessas que não são mais necessárias e os destinatários inativos do banco de dados para manter a qualidade do endereço.

* Não tente programar deliveries grandes juntos. Observe que pode levar de 5 a 10 minutos para que a carga seja uniformemente espalhada sobre o sistema.

**Tópicos relacionados:**

* [Receber alertas quando ocorrerem falhas](../../sending/using/receiving-alerts-when-failures-happen.md)
* [Relatórios](../../reporting/using/about-dynamic-reports.md)
