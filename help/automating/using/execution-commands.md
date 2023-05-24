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
ht-degree: 5%

---

# Comandos de execução {#execution-commands}

Os ícones na barra de ações permitem iniciar, rastrear e modificar a execução de um fluxo de trabalho. Consulte [Barra de ação](../../automating/using/workflow-interface.md#action-bar).

![](assets/wkf_execution_2.png)

As opções disponíveis são as seguintes:

**Start**

A variável ![](assets/play_darkgrey-24px.png) inicia a execução de um workflow, que, em seguida, **Em andamento** Status (azul). Se o workflow tiver sido pausado, ele será retomado, caso contrário, será iniciado e as atividades iniciais serão ativadas.

>[!NOTE]
>
>Iniciar é um processo assíncrono: a solicitação é salva e será processada o mais rápido possível pelo mecanismo de execução do workflow.

**Pause**

A variável ![](assets/pause_darkgrey-24px.png) O botão pausa a execução. O fluxo de trabalho assume o **Aviso** Status (amarelo). Nenhuma nova atividade será ativada até que seja retomada, mas as operações em andamento não são suspensas.

**Stop**

A variável ![](assets/stop_darkgrey-24px.png) para um fluxo de trabalho que está sendo executado, que assumirá a função **Concluído** Status (verde). As operações em andamento são interrompidas, se possível, e as importações ou consultas SQL em andamento são canceladas imediatamente. Não é possível retomar do fluxo de trabalho a partir do mesmo local em que ele foi interrompido.

**Restart**

A variável ![](assets/pauseplay_darkgrey-24px.png) envolve parar e reiniciar um workflow. Na maioria dos casos, isso permite reiniciar mais rápido. Também pode ser útil para automatizar a reinicialização quando a interrupção leva um determinado tempo, pois a variável ![](assets/play_darkgrey-24px.png) O botão só estará disponível quando a interrupção for efetiva.

Quando uma ou várias atividades em um workflow são selecionadas, há outras ações que você pode executar, como:

**Execução imediata**

A variável ![](assets/pending_darkgrey-24px.png) O botão inicia todas as atividades pendentes selecionadas assim que possível.

**Execução normal**

A variável ![](assets/check_darkgrey-24px.png) O botão reativa qualquer atividade pausada ou desativada.

**Execução suspensa**

A variável ![](assets/check_pause_darkgrey-24px.png) button pauses the workflow at the seleted activity: essa tarefa, bem como todas as que a seguem (na mesma ramificação) não são executadas.

**Sem execução**

A variável ![](assets/checkdisable.png) O botão desativa todas as atividades selecionadas.

>[!NOTE]
>
>As ações rápidas permitem que você acesse ações diferentes referentes a uma atividade específica e sejam exibidas quando uma atividade for selecionada.
