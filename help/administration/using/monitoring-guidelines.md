---
solution: Campaign Standard
product: campaign
title: Orientações de monitoramento
description: A presente seção apresenta orientações gerais para a monitorização do Campaign Standard.
audience: production
content-type: reference
topic-tags: introduction
index: y
translation-type: tm+mt
source-git-commit: 4b87ebc2585b87f918bbd688c5858394d8d4a742
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 9%

---


# Orientações de monitoramento {#monitoring-guidelines}

<table>
<tr><td><img src="assets/do-not-localize/icon_system.svg" width="60px"><p><a href="#monitoring-system">Monitoramento do sistema</a></p></td>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#moniroting-workflows">Monitoramento de workflows</a></p></td>
<td><img src="assets/do-not-localize/icon_send.svg" width="60px"><p><a href="#monitoring-deliveries">Monitoramento de deliveries</a></p></td></tr>
</table>

O Campaign Standard fornece várias maneiras de monitorar suas instâncias para garantir que seu sistema esteja saudável e, eventualmente, solucionar problemas que podem ocorrer ao configurar workflows, enviar delivery etc.

## Monitoramento do sistema {#monitoring-system}

<img src="assets/do-not-localize/icon_system.svg" width="60px">

**Notificações do sistemaA interface do Campaign Standard fornece um painel de notificação que permite que você seja mantido informado sobre o que está acontecendo no sistema:**
 status de eventos, atualizações do sistema, ação necessária etc. [Leia mais](../../start/using/interface-description.md#top-bar)


**Fluxos de**
trabalho técnicosOs workflows técnicos são operações ou trabalhos programados para serem executados regularmente no servidor. Para garantir que sua instância esteja saudável e funcionando corretamente, é necessário certificar-se de que elas estejam sempre funcionando. [Leia mais](../../administration/using/technical-workflows.md)

**Painel**
de controleO Painel de controle do Campaign permite gerenciar várias configurações da sua instância: Permissões de URL, verifique os detalhes da instância, como as versões de compilação dos servidores, monitore o uso de perfis ativos etc. Também permite monitorar o espaço disponível nos servidores SFTP conectados à sua instância. [Leia mais](https://docs.adobe.com/content/help/pt-BR/control-panel/using/control-panel-home.translate.html).

>[!NOTE]
>
>Observe que o Painel de controle do Campaign é acessível somente para usuários administradores e está disponível para todos os clientes que usam os Serviços gerenciados da Adobe.

**Objetos técnicos**
O  **[!UICONTROL Diagnosis]** menu é uma ferramenta essencial para monitorar e analisar os diferentes objetos técnicos gerados pelo aplicativo: schemas de dados, páginas da Web, trabalhos em lote etc. [Leia mais](../../developing/using/monitoring-data-model-changes.md)

**Exportar**
auditoriasAs auditorias de exportação permitem que você monitore as exportações realizadas em suas instâncias: arquivos carregados de workflows, exportações de listas e arquivos baixados de mensagens de mala direta.
[Leia mais](../../administration/using/auditing-export-logs.md)

****
LicençasCom o  **[!UICONTROL Licenses]** menu, monitore as informações sobre suas instâncias: licenças instaladas, versões de criação e aceitações de termos e contratos.
[Leia mais](../../administration/using/licenses.md)

## Monitoramento de workflows {#monitoring-workflows}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

**Práticas recomendadas e**
solução de problemasSeguir as práticas recomendadas e as diretrizes de solução de problemas ao usar workflows pode ajudar a melhorar o desempenho.
[Leia mais](../../automating/using/best-practices-workflows.md)

**Logs e**
tarefasO monitoramento de logs de fluxo de trabalho é uma etapa essencial para analisar seus workflows e garantir que eles estejam sendo executados corretamente.
[Leia mais](../../automating/using/monitoring-workflow-execution.md#workflow-log-and-tasks)

****
Notificações O Campaign Standard permite que você envie notificações aos supervisores para monitorar a execução de seus workflows e verificar se há algum erro que exija sua atenção.
[Leia mais](../../automating/using/monitoring-workflow-execution.md#error-management)

## Monitoramento de deliveries {#monitoring-deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">

****
DisponibilidadeO Campaign Standard fornece várias ferramentas de entrega para ajudá-lo a melhorar o número de mensagens entregues com êxito: Relatórios de throughput do delivery, otimização do tempo de envio, pré-visualização de mensagens, renderização de email, gerenciamento de quarentenas etc.
[Leia mais](../../sending/using/about-deliverability.md)

****
EntregasDepois que suas mensagens são enviadas, os registros detalhados permitem que você monitore os delivery e meça o sucesso de sua campanha, bem como rastreie o comportamento dos recipient de mensagens.
[Leia mais](../../sending/using/monitoring-a-delivery.md)

**Alertas do deliveryCom o recurso de alerta do Delivery, você pode configurar alertas que serão enviados automaticamente para um grupo de usuários em relação à execução dos delivery:**
 falha no envio ou preparação, taxa de rejeição ruim, baixa throughput etc.
[Leia mais](../../sending/using/receiving-alerts-when-failures-happen.md)

**Relatório dinâmico**
O relatórios dinâmico fornece vários relatórios para ajudar você a ser mantido informado sobre o desempenho de seus delivery: rejeições, delivery mais vistos por recipient, throughput de delivery etc.
[Leia mais](../../reporting/using/about-dynamic-reports.md)
