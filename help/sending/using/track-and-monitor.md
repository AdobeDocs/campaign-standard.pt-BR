---
title: Rastrear e monitorar mensagens
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: Saiba como o Adobe Campaign permite acompanhar as mensagens enviadas e descobrir como seus destinatários reagem à sua entrega
feature: Deliverability
role: User
level: Intermediate
exl-id: dd3bd672-fb9d-4e82-bdf3-d319f372baaa
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 39%

---

# Rastrear e monitorar {#track-and-monitor}

Você clicou no botão Enviar? Vamos ver o que acontece. Depois que a entrega é enviada, o Adobe Campaign permite acompanhar as mensagens enviadas e descobrir como os destinatários reagem a sua entrega. Isso ajuda a melhorar o envio futuro e a otimizar as próximas campanhas.

## Monitoramento de entregas {#monitoring-deliveries}

Para controlar suas campanhas, você deve garantir que a mensagem tenha sido entregue aos destinatários.

**Dicas**

* Você pode controlar o status das mensagens nos logs do delivery.

* Para rastrear os sucessos ou as falhas do delivery, o Adobe Campaign fornece um sistema de alerta por email que envia notificações para informar os usuários sobre atividades importantes do sistema.

* No painel de mensagens, você pode acessar vários relatórios para a mensagem específica.

Para obter mais informações, consulte [Monitoramento de uma entrega](../../sending/using/monitoring-a-delivery.md).

## Rastreamento {#tracking-deliveries}

Para conhecer melhor o comportamento de perfis direcionados, você pode acompanhar como eles reagem a uma entrega: recebimento, abertura, cliques em links, assinaturas canceladas, etc. Consulte a guia **Logs de rastreamento** da entrega.

**Dica**: o rastreamento de mensagens é habilitado por padrão. Para configurar URLs, selecione a opção Exibir URLs na seção inferior do assistente da entrega. Para cada URL da mensagem, você pode escolher se deseja ativar o rastreamento.

Para obter mais informações, consulte a seção [Mensagens de rastreamento](../../sending/using/tracking-messages.md) e a descrição dos [Indicadores de rastreamento](../../reporting/using/tracking-indicators.md).

## Relatórios dinâmicos {#dyn-reports}

Os relatórios dinâmicos permitem criar relatórios totalmente personalizáveis e em tempo real para monitorar suas campanhas. Dimension, métricas e visualizações permitem medir o impacto e o sucesso de suas campanhas nos recipients.

**Dica** - Relatórios internos estão disponíveis para você monitorar suas campanhas, mas esses relatórios também podem ser personalizados arrastando e soltando métricas ou dimensões em seu relatório.

Para obter mais informações, consulte o [Guia de relatórios](../../reporting/using/about-dynamic-reports.md).

## Hot clicks

O relatório Hot clicks apresenta o conteúdo da mensagem (HTML e/ou texto) com a porcentagem de cliques em cada link. Ao exibir a porcentagem de cliques em cada conteúdo dinâmico, você pode avaliar qual conteúdo agrada mais aos destinatários.

Para obter mais informações, consulte o [Relatório de cliques ativos](../../reporting/using/hot-clicks.md).

## Dicas de desempenho de entrega {#performance-tips}

* Não mantenha as entregas em estado de falha na instância, pois tabelas temporárias serão mantidas e o desempenho será afetado.

* Remova as remessas que não são mais necessárias e os destinatários inativos do banco de dados para manter a qualidade do endereço.

* Não tente programar entregas grandes juntas. Observe que pode levar de 5 a 10 minutos para que a carga seja uniformemente espalhada sobre o sistema.

**Tópicos relacionados:**

* [Recebimento de alertas quando ocorrerem falhas](../../sending/using/receiving-alerts-when-failures-happen.md)
* [Relatórios](../../reporting/using/about-dynamic-reports.md)
