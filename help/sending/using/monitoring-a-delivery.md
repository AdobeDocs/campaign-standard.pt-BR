---
title: Monitoramento de uma entrega
seo-title: Monitoramento de uma entrega
description: Monitoramento de uma entrega
seo-description: Descobrir como monitorar uma entrega.
page-status-flag: nunca ativado
uuid: 7772 c 607-debd -40 fd -8322-4 d 49119979 b 4
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: enviando
content-type: reference
topic-tags: monitoramento-mensagens
discoiquuid: eb 9 fa 216-4568-423 a -9396-8 f 7 b 82181 ae 9
context-tags: entrega, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: cb6396228e42f99f7e184a82e6c894b09a164cd9

---


# Monitoring a delivery{#monitoring-a-delivery}

Há várias maneiras de monitorar uma entrega e medir seu impacto:

* **Logs de mensagens**: Esses logs podem ser acessados diretamente do painel de mensagens. Elas mostram os detalhes do envio, que o direcionamento foi excluído e por que, assim como as informações de rastreamento, como abrir e clicar.

   To view the message logs, click the icon at the bottom right of the **[!UICONTROL Deployment]** block.

   Several tabs contain information (if it exists) regarding the **[!UICONTROL Sending logs]**, **[!UICONTROL Exclusion logs]**, **[!UICONTROL Exclusion causes]**, **[!UICONTROL Tracking logs]** and **[!UICONTROL Tracked URLs]**. See [Delivery logs](../../sending/using/monitoring-a-delivery.md#delivery-logs).

   ![](assets/sending_delivery1.png)

   O log contém todas as mensagens relacionadas à entrega e aos testes. Os ícones específicos permitem identificar erros ou avisos. For more on this, see [Approving messages](../../sending/using/previewing-messages.md).

   You can export the log by clicking the **[!UICONTROL Export list]** button.

   ![](assets/sending_delivery2.png)

* **Alertas de entrega**: Para acompanhar sucessos ou falhas de entrega, o Adobe Campaign fornece um sistema de alertas por email que envia notificações para informar os usuários sobre atividades importantes do sistema.
* **Relatórios**: No painel de mensagens, você pode acessar vários relatórios para esta mensagem específica. You also have a **[!UICONTROL Reports]** menu that allows you to access a complete list of built-in or custom reports that you can use to outline specific metrics related to your message or campaign.
* Um administrador também pode exportar logs em um arquivo separado que pode ser processado em seu próprio relatório ou em ferramentas BI. For more on this, see [Exporting logs](../../automating/using/exporting-logs.md).

**Tópicos relacionados:**

* [Recebimento de alertas quando ocorrerem falhas](../../sending/using/receiving-alerts-when-failures-happen.md)
* [Relatórios](../../reporting/using/about-dynamic-reports.md)

## Delivery logs {#delivery-logs}

### Sending logs {#sending-logs}

The **[!UICONTROL Sending logs]** tab offers a history of every occurrence of this delivery. A lista de mensagens enviadas e seus status é armazenada aqui. Permite exibir o status de entrega de cada destinatário.

For each profile with a **[!UICONTROL Sent]** status, the **[!UICONTROL Date]** column shows when the message was sent.

![](assets/sending_delivery3.png)

### Exclusion logs {#exclusion-logs}

The **[!UICONTROL Exclusion logs]** tab lists all the messages that have been excluded from the target sent and specifies the reason for the send failure.

![](assets/sending_delivery4.png)

### Exclusion causes {#exclusion-causes}

**[!UICONTROL Exclusion causes]** A guia exibe o volume (em número de mensagens) das mensagens que foram excluídas do destino de destino.

![](assets/sending_delivery5.png)

