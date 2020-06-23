---
title: Ciclo de vida do workflow
description: Saiba mais sobre o ciclo de vida do fluxo de trabalho
page-status-flag: never-activated
uuid: ff02b74e-53e8-49c6-bf8e-0c729eaa7d25
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 906c85ea-83b7-4268-86da-cd353f1dc591
context-tags: workflow,overview;workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b4d0aa1a9f116f022890d5eccd87730a7a513103
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 3%

---


# Ciclo de vida do workflow {#life-cycle}

O ciclo de vida de um fluxo de trabalho inclui três etapas principais e cada etapa está vinculada a um status e a uma cor:

* **Edição** (cinza)

   Esta é a fase de design inicial de um fluxo de trabalho (consulte [Criação de um fluxo de trabalho](../../automating/using/building-a-workflow.md#creating-a-workflow)). O fluxo de trabalho ainda não é manipulado pelo servidor e pode ser modificado sem nenhum risco.

* **Em andamento** (azul)

   Quando a fase de design inicial estiver concluída, o fluxo de trabalho poderá ser iniciado e será manipulado pelo servidor.

* **Concluído** (verde)

   Um fluxo de trabalho é concluído quando não há mais tarefas em andamento ou quando um operador tiver parado explicitamente a instância.

Depois de iniciado, um fluxo de trabalho também pode ter dois outros status:

* **Aviso** (amarelo)

   O fluxo de trabalho não pôde ser concluído ou foi pausado usando os ![](assets/pause_darkgrey-24px.png) botões ou ![](assets/check_pause_darkgrey-24px.png) .

* **Errado** (vermelho)

   Ocorreu um erro quando um fluxo de trabalho foi executado. O fluxo de trabalho foi interrompido e o usuário deve executar uma ação. Para saber mais sobre esse erro, use o ![](assets/printpreview_darkgrey-24px.png) botão para acessar o log do fluxo de trabalho (consulte [Monitoramento](../../automating/using/monitoring-workflow-execution.md)).

A lista de atividades de marketing permite exibir todos os workflows, bem como seus status. Para obter mais informações, consulte [Gerenciamento de atividades](../../start/using/marketing-activities.md#about-marketing-activities)de marketing.

![](assets/wkf_execution_3.png)
