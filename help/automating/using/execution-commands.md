---
title: Comandos de execução
description: Saiba como usar comandos de execução de workflows.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Beginner
exl-id: fddd88b1-603a-465b-b5e7-624632c0d5cd
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 4%

---

# Comandos de execução {#execution-commands}

Os ícones na barra de ações permitem iniciar, rastrear e modificar a execução de um fluxo de trabalho. Consulte [Barra de ação](../../automating/using/workflow-interface.md#action-bar).

![](assets/wkf_execution_2.png)

As opções disponíveis são as seguintes:

**Start**

O ![](assets/play_darkgrey-24px.png) O botão inicia a execução de um fluxo de trabalho, que **Em andamento** Status (azul). Se o workflow tiver sido pausado, ele será retomado, caso contrário, será iniciado e as atividades iniciais serão ativadas.

>[!NOTE]
>
>Iniciar é um processo assíncrono: a solicitação é salva e será processada o mais rápido possível pelo mecanismo de execução do workflow.

**Pause**

O ![](assets/pause_darkgrey-24px.png) O botão pausa a execução. O fluxo de trabalho assume o **Aviso** status (amarelo). Nenhuma nova atividade será ativada até que seja retomada, mas as operações em andamento não serão suspensas.

**Stop**

O ![](assets/stop_darkgrey-24px.png) O botão interrompe um fluxo de trabalho que está sendo executado, o que assumirá a função **Concluído** (verde). As operações em andamento são interrompidas se possível e as importações ou consultas SQL em andamento são imediatamente canceladas. Não é possível retomar do workflow a partir do mesmo local em que ele foi interrompido.

**Restart**

O ![](assets/pauseplay_darkgrey-24px.png) envolve parar e reiniciar um workflow. Na maioria dos casos, isso permite reiniciar mais rápido. Também pode ser útil automatizar a reinicialização quando a interrupção levar um determinado período, porque a variável ![](assets/play_darkgrey-24px.png) só estará disponível quando a parada estiver ativa.

Quando uma ou várias atividades em um workflow são selecionadas, há outras ações que você pode realizar, como:

**Execução imediata**

O ![](assets/pending_darkgrey-24px.png) inicia qualquer atividade pendente selecionada assim que possível.

**Execução normal**

O ![](assets/check_darkgrey-24px.png) reativa qualquer atividade pausada ou desativada.

**Execução suspensa**

O ![](assets/check_pause_darkgrey-24px.png) O botão pausa o workflow na atividade selecionada: essa tarefa, bem como todas as que a seguem (na mesma ramificação) não são executadas.

**Sem execução**

O ![](assets/checkdisable.png) desativa qualquer atividade selecionada.

>[!NOTE]
>
>As ações rápidas permitem que você acesse ações diferentes relacionadas a uma atividade específica e sejam exibidas quando uma atividade é selecionada.
