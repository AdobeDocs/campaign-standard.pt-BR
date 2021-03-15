---
solution: Campaign Standard
product: campaign
title: Ciclo de vida do workflow
description: Saiba mais sobre o ciclo de vida do workflow
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
source-wordcount: '204'
ht-degree: 3%

---


# Ciclo de vida do workflow {#life-cycle}

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
