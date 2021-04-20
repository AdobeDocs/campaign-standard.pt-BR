---
solution: Campaign Standard
product: campaign
title: Orientações de monitoramento
description: Esta seção apresenta as diretrizes gerais para monitoramento do Campaign Standard.
audience: production
content-type: reference
topic-tags: introduction
index: y
feature: Access Management
role: Administrator
level: Experienced
translation-type: tm+mt
source-git-commit: 7979d8fd88b93a1cdd7b5a11bb66e894ab12f1c2
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 14%

---


# Orientações de monitoramento {#monitoring-guidelines}

<table>
<tr><td><img src="assets/do-not-localize/icon_system.svg" width="60px"><p><a href="#monitoring-system">Monitoramento do sistema</a></p></td>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#moniroting-workflows">Monitoramento de workflows</a></p></td>
<td><img src="assets/do-not-localize/icon_send.svg" width="60px"><p><a href="#monitoring-deliveries">Monitoramento de deliveries</a></p></td></tr>
</table>

O Campaign Standard fornece várias maneiras de monitorar as instâncias para garantir que o sistema esteja íntegro e, eventualmente, solucionar problemas que podem ocorrer ao configurar workflows, enviar deliveries etc.

## Monitoramento do sistema {#monitoring-system}

<img src="assets/do-not-localize/icon_system.svg" width="60px">

**Notificações do sistema**

A interface do Campaign Standard fornece um painel de notificação que permite que você seja informado sobre o que está acontecendo no sistema: status de eventos, atualizações do sistema, ação necessária, etc. [Leia mais](../../start/using/interface-description.md#top-bar)


**Workflows técnicos**

Eles são operações ou trabalhos programados para serem executados regularmente no servidor. Para garantir que sua instância esteja funcionando corretamente, é necessário garantir que esteja sempre ativa e em execução. [Leia mais](../../administration/using/technical-workflows.md)

**Painel de controle do Campaign**

O Painel de controle do Campaign permite gerenciar várias configurações da sua instância: Permissões de URL, verifique os detalhes da instância, como as versões de criação dos servidores, monitore o uso de perfis ativos etc. Ela também permite monitorar o espaço disponível nos servidores SFTP conectados à sua instância. [Leia mais](https://docs.adobe.com/content/help/pt-BR/control-panel/using/control-panel-home.translate.html).

>[!NOTE]
>
>O Painel de controle do Campaign é acessível a todos os usuários administradores. As etapas para conceder acesso de Administrador a um usuário estão detalhadas em [this page](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/managing-permissions.html?lang=en#discover-control-panel).

**Objetos técnicos**

O menu **[!UICONTROL Diagnosis]** é uma ferramenta essencial para monitorar e analisar os diferentes objetos técnicos gerados pelo aplicativo: esquemas de dados, páginas da Web, trabalhos em lote etc. [Leia mais](../../developing/using/monitoring-data-model-changes.md)

**Auditorias à exportação**

As auditorias de exportação permitem monitorar as exportações realizadas em suas instâncias: arquivos carregados de workflows, exportações de lista e arquivos baixados de mensagens de mala direta.
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

O monitoramento de logs do fluxo de trabalho é uma etapa essencial para analisar seus fluxos de trabalho e garantir que eles estejam em execução corretamente.
[Leia mais](../../automating/using/monitoring-workflow-execution.md#workflow-log-and-tasks)

**Notificações**

O Campaign Standard permite enviar notificações para supervisores a fim de monitorar a execução dos workflows e ver se há algum erro que exija sua atenção.
[Leia mais](../../automating/using/monitoring-workflow-execution.md#error-management)

## Monitoramento de deliveries {#monitoring-deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">

**Avaliação do delivery**

O Campaign Standard oferece várias ferramentas de deliverability para ajudar você a melhorar o número de mensagens entregues com êxito: relatórios de taxa de transferência de delivery, otimização de tempo de envio, pré-visualização de mensagens, renderização de email, gerenciamento de quarentena etc.
[Leia mais](../../sending/using/about-deliverability.md)

**Deliveries**

Depois que as mensagens são enviadas, os logs detalhados permitem monitorar os deliveries e medir o sucesso da campanha, bem como rastrear o comportamento dos recipients das mensagens.
[Leia mais](../../sending/using/monitoring-a-delivery.md)

**Alerta de delivery**

Com o recurso de Alerta de delivery, é possível configurar alertas que serão enviados automaticamente para um grupo de usuários em relação à execução dos deliveries: falha no envio ou preparação, taxa de devoluções incorretas, baixa taxa de transferência etc.
[Leia mais](../../sending/using/receiving-alerts-when-failures-happen.md)

**Relatórios dinâmicos**

Os Relatórios dinâmicos fornecem vários relatórios para ajudar você a ser informado sobre o desempenho de seus deliveries: devoluções, deliveries mais vistos por recipients, taxa de transferência dos deliveries etc.
[Leia mais](../../reporting/using/about-dynamic-reports.md)
