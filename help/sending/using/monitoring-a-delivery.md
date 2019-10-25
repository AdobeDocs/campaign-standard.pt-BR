---
title: Monitoramento de um delivery
seo-title: Monitoramento de um delivery
description: Monitoramento de um delivery
seo-description: Descubra como monitorar uma entrega.
page-status-flag: nunca ativado
uuid: 7772c607-debd-40fd-8322-4d49119979b4
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: envio
content-type: referência
topic-tags: mensagens de monitoramento
discoiquuid: eb9fa216-4568-423a-9396-8f7b82181ae9
context-tags: entrega,principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 51d80fc9c683e39b9d08ba7d36b76b71a9dd1e8c

---


# Monitoramento de um delivery{#monitoring-a-delivery}

Há várias maneiras de monitorar uma entrega e medir seu impacto:

* **Registros** de mensagens: Esses registros podem ser acessados diretamente do painel de mensagens. Eles mostram os detalhes do envio, qual destino foi excluído e por que, bem como as informações de rastreamento, como abrir e clicar.

   Para exibir os registros de mensagens, clique no ícone na parte inferior direita do **[!UICONTROL Deployment]** bloco.

   Várias guias contêm informações (se houver) relacionadas ao **[!UICONTROL Sending logs]**, **[!UICONTROL Exclusion logs]**, **[!UICONTROL Exclusion causes]** e **[!UICONTROL Tracking logs]** **[!UICONTROL Tracked URLs]**. Consulte Logs [de entrega](#delivery-logs).

   ![](assets/sending_delivery1.png)

   O log contém todas as mensagens relacionadas à entrega e às provas. Ícones específicos permitem identificar erros ou avisos. Para obter mais informações, consulte [Aprovação de mensagens](../../sending/using/previewing-messages.md).

   Você pode exportar o log clicando no **[!UICONTROL Export list]** botão.

   ![](assets/sending_delivery2.png)

* **Alertas** de entrega: Para rastrear sucessos ou falhas na entrega, o Adobe Campaign fornece um sistema de alerta por email que envia notificações para informar os usuários sobre atividades importantes do sistema.
* **Relatórios**: No painel de mensagens, você pode acessar vários relatórios para essa mensagem específica. Você também tem um **[!UICONTROL Reports]** menu que permite acessar uma lista completa de relatórios internos ou personalizados que podem ser usados para destacar métricas específicas relacionadas à sua mensagem ou campanha.
* Um administrador também pode exportar logs em um arquivo separado que pode ser processado nas suas próprias ferramentas de relatório ou BI. Para obter mais informações, consulte [Exportar logs](../../automating/using/exporting-logs.md).

**Tópicos relacionados:**

* [Recebendo alertas quando ocorrem falhas](../../sending/using/receiving-alerts-when-failures-happen.md)
* [Relatórios](../../reporting/using/about-dynamic-reports.md)

## Logs de entrega {#delivery-logs}

### Envio de logs {#sending-logs}

A **[!UICONTROL Sending logs]** guia oferece um histórico de todas as ocorrências desta entrega. A lista de mensagens enviadas e seus status são armazenados aqui. Permite que você visualize o status de entrega de cada destinatário.

Para cada perfil com um **[!UICONTROL Sent]** status, a **[!UICONTROL Date]** coluna mostra quando a mensagem foi enviada.

![](assets/sending_delivery3.png)

### Logs de exclusão {#exclusion-logs}

A **[!UICONTROL Exclusion logs]** guia lista todas as mensagens que foram excluídas do destino enviado e especifica o motivo da falha de envio.

![](assets/sending_delivery4.png)

### Causas de exclusão {#exclusion-causes}

A **[!UICONTROL Exclusion causes]** guia exibe o volume (em número de mensagens) das mensagens que foram excluídas do envio de destino.

![](assets/sending_delivery5.png)

