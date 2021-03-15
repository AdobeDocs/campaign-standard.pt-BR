---
solution: Campaign Standard
product: campaign
title: Comandos de execução
description: Saiba como usar comandos de execução de workflows.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Fluxos de trabalho
role: Arquiteto de dados
level: Iniciante
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '321'
ht-degree: 4%

---


# Comandos de execução {#execution-commands}

Os ícones na barra de ações permitem iniciar, rastrear e modificar a execução de um fluxo de trabalho. Consulte [Barra de ação](../../automating/using/workflow-interface.md#action-bar).

![](assets/wkf_execution_2.png)

As opções disponíveis são as seguintes:

**Start**

O botão ![](assets/play_darkgrey-24px.png) inicia a execução de um workflow, que assume o status **In progress** (azul). Se o workflow tiver sido pausado, ele será retomado, caso contrário, será iniciado e as atividades iniciais serão ativadas.

>[!NOTE]
>
>Iniciar é um processo assíncrono: a solicitação é salva e será processada o mais rápido possível pelo mecanismo de execução do workflow.

**Pause**

O botão ![](assets/pause_darkgrey-24px.png) pausa a execução. O workflow assume o status **Warning** (amarelo). Nenhuma nova atividade será ativada até que seja retomada, mas as operações em andamento não serão suspensas.

**Stop**

O botão ![](assets/stop_darkgrey-24px.png) interrompe um fluxo de trabalho que está sendo executado, que assumirá o status **Finished** (verde). As operações em andamento são interrompidas se possível e as importações ou consultas SQL em andamento são imediatamente canceladas. Não é possível retomar do workflow a partir do mesmo local em que ele foi interrompido.

**Restart**

O botão ![](assets/pauseplay_darkgrey-24px.png) envolve parar e reiniciar um workflow. Na maioria dos casos, isso permite reiniciar mais rápido. Também pode ser útil automatizar a reinicialização quando a interrupção levar um determinado período, porque o botão ![](assets/play_darkgrey-24px.png) só estará disponível quando a interrupção estiver efetiva.

Quando uma ou várias atividades em um workflow são selecionadas, há outras ações que você pode realizar, como:

**Execução imediata**

O botão ![](assets/pending_darkgrey-24px.png) inicia qualquer atividade pendente selecionada assim que possível.

**Execução normal**

O botão ![](assets/check_darkgrey-24px.png) reativa todas as atividades pausadas ou desativadas.

**Execução suspensa**

O botão ![](assets/check_pause_darkgrey-24px.png) pausa o workflow na atividade selecionada: essa tarefa, bem como todas as que a seguem (na mesma ramificação) não são executadas.

**Sem execução**

O botão ![](assets/checkdisable.png) desativa qualquer atividade selecionada.

>[!NOTE]
>
>As ações rápidas permitem que você acesse ações diferentes relacionadas a uma atividade específica e sejam exibidas quando uma atividade é selecionada.
