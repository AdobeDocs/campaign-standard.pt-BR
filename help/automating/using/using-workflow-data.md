---
title: Uso de dados de fluxo de trabalho
description: Saiba mais sobre as diferentes possibilidades de consumir os dados importados ou direcionados.
page-status-flag: nunca ativado
uuid: 3dd66aeb-3a26-4214-b6a0-242c2b7fbc49
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: automatização
content-type: referência
topic-tags: fluxo de trabalho geral-operação
discoiquuid: 90b250f1-f32d-4256-83ea-4c0627628610
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Uso de dados de fluxo de trabalho{#using-workflow-data}

Depois que os dados forem identificados e preparados, eles poderão ser usados nos seguintes contextos:

* A **[!UICONTROL Update data]** atividade permite executar uma atualização em massa nos campos no banco de dados.
* A **[!UICONTROL Save audience]** atividade permite que você atualize um público existente ou crie um novo público-alvo a partir da população computada upstream em um fluxo de trabalho. Os públicos-alvo criados ou atualizados a partir desta atividade são públicos-alvo da **Lista** ou **Arquivo** . Essa atividade também permite exportar perfis como públicos/segmentos da Adobe Experience Cloud.
* A **[!UICONTROL Subscription Services]** atividade permite que você pegue perfis em massa e assine-os em um serviço ou cancele sua assinatura de um serviço.
* A **[!UICONTROL Extract file]** atividade permite exportar dados do Adobe Campaign na forma de um arquivo externo.

Depois de definir uma meta de perfil, você pode usar várias atividades para criar e enviar entregas:

* A **[!UICONTROL Email delivery]** atividade permite configurar o envio de um email em um fluxo de trabalho. Pode ser um **único email de envio** e enviado apenas uma vez, ou um email **recorrente** .
* A **[!UICONTROL SMS delivery]** atividade permite configurar o envio de um SMS em um fluxo de trabalho. Isto pode ser um **único SMS enviado** e enviado apenas uma vez, ou pode ser um SMS **recorrente** .
* A **[!UICONTROL Mobile app delivery]** atividade permite configurar o envio de uma notificação por push em um fluxo de trabalho. Esta pode ser uma **única notificação de envio** e enviada apenas uma vez, ou pode ser uma notificação **recorrente** .

