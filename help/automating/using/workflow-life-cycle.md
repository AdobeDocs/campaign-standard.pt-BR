---
solution: Campaign Standard
product: campaign
title: Ciclo de vida do workflow
description: Saiba mais sobre o ciclo de vida do fluxo de trabalho
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 3%

---


# Ciclo de vida do workflow {#life-cycle}

O ciclo de vida de um fluxo de trabalho inclui três etapas principais e cada etapa está vinculada a um status e a uma cor:

* **Edição**  (cinza)

   Esta é a fase de design inicial de um fluxo de trabalho (consulte [Criar um fluxo de trabalho](../../automating/using/building-a-workflow.md#creating-a-workflow)). O fluxo de trabalho ainda não é manipulado pelo servidor e pode ser modificado sem nenhum risco.

* **Em andamento**  (azul)

   Quando a fase de design inicial estiver concluída, o fluxo de trabalho poderá ser iniciado e será manipulado pelo servidor.

* **Concluído** (verde)

   Um fluxo de trabalho é concluído quando não há mais tarefas em andamento ou quando um operador tiver parado explicitamente a instância.

Depois de iniciado, um fluxo de trabalho também pode ter dois outros status:

* **Aviso** (amarelo)

   O fluxo de trabalho não pôde ser concluído ou foi pausado usando os botões ![](assets/pause_darkgrey-24px.png) ou ![](assets/check_pause_darkgrey-24px.png).

* **Errôneo**  (vermelho)

   Ocorreu um erro quando um fluxo de trabalho foi executado. O fluxo de trabalho foi interrompido e o usuário deve executar uma ação. Para saber mais sobre esse erro, use o botão ![](assets/printpreview_darkgrey-24px.png) para acessar o log do fluxo de trabalho (consulte [Monitoramento](../../automating/using/monitoring-workflow-execution.md)).

A lista de atividades de marketing permite exibir todos os workflows, bem como seus status. Para obter mais informações, consulte [Gerenciamento de atividades de marketing](../../start/using/marketing-activities.md#about-marketing-activities).

![](assets/wkf_execution_3.png)
