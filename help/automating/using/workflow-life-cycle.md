---
title: Ciclo de vida do fluxo de trabalho
description: Saiba mais sobre o ciclo de vida do workflow
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Beginner
exl-id: ba968add-25a3-4962-9e90-f0a06d9b74a8
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 3%

---

# Ciclo de vida do fluxo de trabalho {#life-cycle}

O ciclo de vida de um fluxo de trabalho inclui três etapas principais e cada etapa está vinculada a um status e a uma cor:

* **Edição**  (cinza)

   Esta é a fase inicial de design de um workflow (consulte [Criação de um workflow](../../automating/using/building-a-workflow.md#creating-a-workflow)). O workflow ainda não foi manipulado pelo servidor e pode ser modificado sem riscos.

* **Em andamento**  (azul)

   Quando a fase inicial de design for concluída, o workflow poderá ser iniciado e será manipulado pelo servidor.

* **Finished**  (verde)

   Um workflow é concluído quando não há mais nenhuma tarefa em andamento ou quando um operador tiver interrompido explicitamente a instância.

Depois de iniciado, um workflow também pode ter dois outros status:

* **Aviso**  (amarelo)

   O fluxo de trabalho não pôde ser concluído ou foi pausado usando os botões ![](assets/pause_darkgrey-24px.png) ou ![](assets/check_pause_darkgrey-24px.png).

* **Errado**  (vermelho)

   Ocorreu um erro ao executar um fluxo de trabalho. O fluxo de trabalho foi interrompido e o usuário deve executar uma ação . Para saber mais sobre esse erro, use o botão ![](assets/printpreview_darkgrey-24px.png) para acessar o log do workflow (consulte [Monitoring](../../automating/using/monitoring-workflow-execution.md)).

A lista de atividades de marketing permite exibir todos os workflows, bem como seus status. Para obter mais informações, consulte [Gerenciamento de atividades de marketing](../../start/using/marketing-activities.md#about-marketing-activities).

![](assets/wkf_execution_3.png)
