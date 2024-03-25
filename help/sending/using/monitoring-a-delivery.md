---
title: Monitoramento de uma entrega no Adobe Campaign Standard
description: Saiba como monitorar uma entrega no Adobe Campaign Standard.
audience: sending
content-type: reference
topic-tags: monitoring-messages
context-tags: delivery,main
feature: Performance Monitoring
role: User
level: Beginner
exl-id: ddc92077-df73-411d-a161-3263581e6945
source-git-commit: ed60bde4785da9a8cc5a6cc0efcdb24e2c1f65e3
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 79%

---

# Monitoramento de uma entrega{#monitoring-a-delivery}

Há várias maneiras de monitorar um delivery e medir seu impacto. Como administrador funcional, você pode acessar logs de mensagens e logs do delivery.

>[!IMPORTANT]
>
>Somente funcional [administradores](../../administration/using/users-management.md#functional-administrators), com **[!UICONTROL Administration]** função e acesso a **Todos** as unidades podem acessar logs de envio, logs de mensagem, logs de rastreamento, logs de exclusão ou de subscrição. Um usuário não administrador pode direcionar esses logs, mas começando por uma tabela vinculada (perfis, delivery).

* **Logs de mensagem**: esses logs podem ser acessados diretamente do painel de mensagens. Eles mostram os detalhes do envio, o target que foi excluído e o motivo, bem como as informações de rastreamento, como aberturas e cliques.

  Para exibir os logs de mensagem, clique no ícone na parte inferior direita do bloco **[!UICONTROL Deployment]**.

  Várias guias contêm informações (se houver) relacionadas a **[!UICONTROL Sending logs]**, **[!UICONTROL Exclusion logs]**, **[!UICONTROL Exclusion causes]**, **[!UICONTROL Tracking logs]** e **[!UICONTROL Tracked URLs]**. Consulte [Logs da entrega](#delivery-logs).

  ![](assets/sending_delivery1.png)

  O log contém todas as mensagens relacionadas com a entrega e com as provas. Os ícones especiais permitem identificar erros ou avisos. Para saber mais, consulte [Aprovação de mensagens](../../sending/using/previewing-messages.md).

  Você pode exportar o log clicando no botão **[!UICONTROL Export list]**.

  ![](assets/sending_delivery2.png)

* **Logs de trabalho**: uma lista dos processos em lote acionados pelo delivery pode ser acessada no painel de mensagens selecionando **[!UICONTROL Job history]** do **[!UICONTROL Summary]** lista suspensa.

  Selecione qualquer trabalho na lista para ver os detalhes do **[!UICONTROL Batch job]**.

  ![](assets/sending_delivery8.png)

* **Alertas de entrega**: para rastrear os sucessos ou as falhas da entrega, o Adobe Campaign tem um sistema de alerta por email que envia notificações para informar os usuários sobre atividades importantes do sistema.
* **Relatórios**: no painel de mensagens, você pode acessar vários relatórios para a mensagem específica. O menu **[!UICONTROL Reports]** permite acessar uma lista completa de relatórios incorporados ou personalizados que você pode usar para destacar métricas específicas relacionadas à mensagem ou campanha.
* Um administrador também pode exportar os logs em um arquivo que pode ser processado nos próprios relatórios ou nas ferramentas de BI. Para saber mais, consulte [Exportação de logs](../../automating/using/exporting-logs.md).

**Tópicos relacionados:**

* [Recebimento de alertas quando ocorrerem falhas](../../sending/using/receiving-alerts-when-failures-happen.md)
* [Relatórios](../../reporting/using/about-dynamic-reports.md)

## Logs de entrega {#delivery-logs}

### Logs de envio {#sending-logs}

A guia **[!UICONTROL Sending logs]** tem um histórico de todas as ocorrências da entrega. A lista de mensagens enviadas com os status é armazenada aqui. Assim, você pode exibir o status da entrega para cada destinatário.

Para cada perfil com status **[!UICONTROL Sent]**, a coluna **[!UICONTROL Date]** mostra quando a mensagem foi enviada.

![](assets/sending_delivery3.png)

Para acessar os detalhes de um log de envio específico, clique no ícone de lápis à direita da linha correspondente.

![](assets/sending_access-sending-log.png)

Todos os detalhes do log de envio são somente leitura. Você também pode pré-visualizar a mirror page.

![](assets/sending_sending-log.png)

>[!NOTE]
>
>Para exibir a renderização da mirror page na interface do usuário do Campaign, o URL do servidor da mirror page deve estar protegido. Nesse caso, use https:// em vez de http:// para definir esse URL ao [configurar sua marca](../../administration/using/branding.md#configuring-and-using-brands).

### Logs de exclusão {#exclusion-logs}

A guia **[!UICONTROL Exclusion logs]** lista todas as mensagens que foram excluídas do público-alvo enviado e especifica o motivo da falha de envio.

![](assets/sending_delivery4.png)

### Causas da exclusão {#exclusion-causes}

A guia **[!UICONTROL Exclusion causes]** exibe o volume (em número) das mensagens que foram excluídas do público-alvo enviado.

![](assets/sending_delivery5.png)
