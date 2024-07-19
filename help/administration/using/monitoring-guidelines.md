---
title: Diretrizes de monitoramento
description: Esta página apresenta diretrizes gerais para monitoramento do Campaign Standard
audience: production
feature: Access Management
role: Admin
level: Experienced
exl-id: 5f25f2b2-ca41-4baf-ade2-42bbafb4790d
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 13%

---

# Diretrizes de monitoramento {#monitoring-guidelines}

<table>
<tr><td><img src="assets/do-not-localize/icon_system.svg" width="60px"><p><a href="#monitoring-system">Monitoramento do sistema</a></p></td>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#moniroting-workflows">Monitoramento de workflows</a></p></td>
<td><img src="assets/do-not-localize/icon_send.svg" width="60px"><p><a href="#monitoring-deliveries">Monitoramento de entregas</a></p></td></tr>
</table>

O Campaign Standard fornece várias maneiras de monitorar suas instâncias para garantir que seu sistema esteja íntegro e, eventualmente, solucionar problemas que podem ocorrer ao configurar workflows, enviar deliveries etc.

## Monitoramento do sistema {#monitoring-system}

<img src="assets/do-not-localize/icon_system.svg" width="60px">

**Notificações do sistema**

A interface do Campaign Standard fornece um painel de notificação que permite que você seja informado sobre o que está acontecendo no sistema: status de eventos, atualizações do sistema, ação necessária etc. [Leia mais](../../start/using/interface-description.md#top-bar)


**Workflows técnicos**

Os workflows técnicos são operações ou trabalhos agendados para serem executados regularmente no servidor. Para garantir que sua instância esteja íntegra e funcionando corretamente, é necessário garantir que elas estejam sempre ativas e em execução. [Leia mais](../../administration/using/technical-workflows.md)

**Painel de controle**

O Painel de controle do Campaign permite gerenciar várias configurações da sua instância: permissões de URL, verificar detalhes da instância como as versões de compilação dos servidores, monitorar o uso de perfis ativos etc. Também permite monitorar o espaço disponível nos servidores SFTP conectados à sua instância. [Leia mais](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=pt-BR).

>[!NOTE]
>
>O Painel de controle é acessível a todos os usuários administradores. As etapas para conceder acesso de Administrador a um usuário estão detalhadas [nesta página](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/managing-permissions.html?lang=pt-BR#discover-control-panel).

**Objetos técnicos**

O menu **[!UICONTROL Diagnosis]** é uma ferramenta essencial para monitorar e analisar os diferentes objetos técnicos gerados pelo aplicativo: esquemas de dados, páginas da Web, trabalhos em lote etc. [Leia mais](../../developing/using/monitoring-data-model-changes.md)

**Auditorias de exportação**

Auditorias de exportação permitem monitorar as exportações realizadas em suas instâncias: arquivos carregados de workflows, exportações de lista e arquivos baixados de mensagens de correspondência direta.
[Leia mais](../../administration/using/auditing-export-logs.md)

**Licenças**

Com o menu **[!UICONTROL Licenses]**, monitore as informações sobre suas instâncias: licenças instaladas, versões de compilação e aceitações do contrato de termos.
[Leia mais](../../administration/using/licenses.md)

## Monitoramento de workflows {#monitoring-workflows}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

**Práticas recomendadas e solução de problemas**

Seguir as práticas recomendadas e as diretrizes de solução de problemas ao usar workflows pode ajudar a melhorar o desempenho.
[Leia mais](../../automating/using/best-practices-workflows.md)

**Logs e tarefas**

O monitoramento de logs de fluxo de trabalho é uma etapa essencial para analisar seus fluxos de trabalho e verificar se eles estão sendo executados corretamente.
[Leia mais](../../automating/using/monitoring-workflow-execution.md#workflow-log-and-tasks)

**Notificações**

O Campaign Standard permite enviar notificações aos supervisores para monitorar a execução dos workflows e ver se há algum erro que exija sua atenção.
[Leia mais](../../automating/using/monitoring-workflow-execution.md#error-management)

## Monitoramento de entregas {#monitoring-deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">

**Avaliação da entrega**

O Campaign Standard fornece várias ferramentas de entrega para ajudar você a melhorar o número de mensagens entregues com êxito: relatórios de taxa de transferência de entrega, otimização de tempo de envio, pré-visualização de mensagens, renderização de email, gerenciamento de quarentena etc.
[Leia mais](../../sending/using/about-deliverability.md)

**Entregas**

Depois que as mensagens são enviadas, logs detalhados permitem monitorar as entregas e medir o sucesso da campanha, bem como rastrear o comportamento dos recipients das mensagens.
[Leia mais](../../sending/using/monitoring-a-delivery.md)

**Alerta de entrega**

Com o recurso de Alerta de delivery, você pode configurar alertas que serão enviados automaticamente para um grupo de usuários em relação à execução de deliveries: falha no envio ou na preparação, taxa de rejeições incorretas, baixa taxa de transferência etc.
[Leia mais](../../sending/using/receiving-alerts-when-failures-happen.md)

**Relatórios dinâmicos**

Os relatórios dinâmicos fornecem vários relatórios para ajudá-lo a ser informado sobre o desempenho de seus deliveries: rejeições, deliveries mais visualizados por recipients, taxa de transferência dos deliveries etc.
[Leia mais](../../reporting/using/about-dynamic-reports.md)
