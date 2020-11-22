---
solution: Campaign Standard
product: campaign
title: Comandos de execução
description: Saiba como usar comandos de execução de workflows.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 4%

---


# Comandos de execução {#execution-commands}

Os ícones na barra de ações permitem que você start, rastreie e modifique a execução de um fluxo de trabalho. Consulte Barra [de ação](../../automating/using/workflow-interface.md#action-bar).

![](assets/wkf_execution_2.png)

As opções disponíveis são as seguintes:

**Start**

O ![](assets/play_darkgrey-24px.png) botão start executando um fluxo de trabalho, que assume o status **Em andamento** (azul). Se o fluxo de trabalho foi pausado, ele será retomado, caso contrário, ele será iniciado e as atividades iniciais serão ativadas.

>[!NOTE]
>
>O início é um processo assíncrono: a solicitação é salva e será processada o mais rápido possível pelo mecanismo de execução do fluxo de trabalho.

**Pause**

O ![](assets/pause_darkgrey-24px.png) botão pausa a execução. O fluxo de trabalho assume o status **Aviso** (amarelo). Nenhuma nova atividade será ativada até que seja retomada, mas as operações em andamento não serão suspensas.

**Stop**

O ![](assets/stop_darkgrey-24px.png) botão para um fluxo de trabalho que está sendo executado, que assumirá o status **Concluído** (verde). As operações em andamento são interrompidas, se possível, e as importações ou query SQL em andamento são imediatamente cancelados. Não é possível retomar do fluxo de trabalho a partir do mesmo local em que ele foi interrompido.

**Restart**

O ![](assets/pauseplay_darkgrey-24px.png) botão envolve parar e reiniciar um fluxo de trabalho. Na maioria dos casos, isso permite reiniciar mais rapidamente. Também pode ser útil automatizar a reinicialização depois que a interrupção levar um determinado tempo, pois o ![](assets/play_darkgrey-24px.png) botão só estará disponível quando a interrupção for efetiva.

Quando uma ou várias atividades em um fluxo de trabalho são selecionadas, há outras ações que você pode realizar, como:

**Execução imediata**

O ![](assets/pending_darkgrey-24px.png) botão start qualquer atividade pendente selecionada o mais rápido possível.

**Execução normal**

O ![](assets/check_darkgrey-24px.png) botão reativa as atividades pausadas ou desativadas.

**Execução suspensa**

O ![](assets/check_pause_darkgrey-24px.png) botão pausa o fluxo de trabalho na atividade selecionada: esta tarefa, bem como todos os que a sucedem (na mesma ramificação) não são executados.

**Nenhuma execução**

O ![](assets/checkdisable.png) botão desativa qualquer atividade selecionada.

>[!NOTE]
>
>As ações rápidas permitem acessar ações diferentes relacionadas a uma atividade específica e aparecem quando uma atividade é selecionada.
