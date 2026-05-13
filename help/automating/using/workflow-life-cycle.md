---
title: Ciclo de vida do fluxo de trabalho
description: Saiba mais sobre o ciclo de vida do workflow
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Beginner
exl-id: ba968add-25a3-4962-9e90-f0a06d9b74a8
TQID: https://experienceleague.adobe.com/nWv8hOZa2JQgiO2CEnffriIqb6czIA7Gh0AwWCTwRAA
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 200
ht-degree: 3%

---

# Ciclo de vida do fluxo de trabalho {#life-cycle}

O ciclo de vida de um fluxo de trabalho inclui três etapas principais e cada etapa está vinculada a um status e uma cor:

* **Editando** (cinza)

  Esta é a fase inicial de design de um fluxo de trabalho (consulte [Criação de um fluxo de trabalho](../../automating/using/building-a-workflow.md#creating-a-workflow)). O workflow ainda não é manipulado pelo servidor e pode ser modificado sem nenhum risco.

* **Em andamento** (azul)

  Quando a fase inicial de design for concluída, o workflow poderá ser iniciado e será manipulado pelo servidor.

* **Concluído** (verde)

  Um workflow é concluído quando não há mais nenhuma tarefa em andamento ou quando um operador interrompeu explicitamente a instância.

Depois de iniciado, um workflow também pode ter dois outros status:

* **Aviso** (amarelo)

  O fluxo de trabalho não pôde ser concluído ou foi pausado usando os botões ![](assets/pause_darkgrey-24px.png) ou ![](assets/check_pause_darkgrey-24px.png).

* **Erro** (vermelho)

  Ocorreu um erro quando um fluxo de trabalho foi executado. O workflow foi interrompido e o usuário deve realizar uma ação. Para saber mais sobre este erro, use o botão ![](assets/printpreview_darkgrey-24px.png) para acessar o log de fluxo de trabalho (consulte [Monitoramento](../../automating/using/monitoring-workflow-execution.md)).

A lista de atividades de marketing permite exibir todos os workflows, bem como seus status. Para obter mais informações, consulte [Gerenciamento de atividades de marketing](../../start/using/marketing-activities.md#about-marketing-activities).

![](assets/wkf_execution_3.png)
