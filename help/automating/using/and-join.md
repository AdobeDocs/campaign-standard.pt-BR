---
title: E ingressar e
seo-title: E ingressar e
description: E ingressar e
seo-description: A atividade de junção E permite sincronizar várias ramificações de execução de um fluxo de trabalho.
page-status-flag: nunca ativado
uuid: 9 b 54 fd 4 c -9915-400 f-a 494-74 e 52 c 329 b 8 a
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizando
content-type: reference
topic-tags: execução-atividades
discoiquuid: 4 b 55 efa 2-652 e -4493-bfa 7-eaee 59 b 383 ca
context-tags: integração, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e384a0cef325bc01eb5ea050b0f3d926aea9a88f

---


# AND-join{#and-join}

## Description {#description}

![](assets/and_join.png)

The **[!UICONTROL AND-join]** activity allows you to synchronize multiple execution branches of a workflow.

## Context of use {#context-of-use}

The **[!UICONTROL AND-join]** activity only triggers its outbound transition once all the inbound transitions are activated, in other words, once all of the preceding activities have finished.

## Configuration {#configuration}

1. Solte várias atividades, como consultas no seu fluxo de trabalho para formar pelo menos duas ramificações de execução diferentes.
1. Drag and drop an **[!UICONTROL AND-join]** activity into your workflow.
1. Conecte-o depois das duas ramificações diferentes que você gostaria de sincronizar.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Selecione o conjunto principal a ser mantido na transição de saída. Se você não selecionar um conjunto, uma população aleatória será enviada da atividade.
1. Confirme a configuração da atividade e salve seu fluxo de trabalho.

## Example {#example}

The following example shows two workflow branches before they are joined with the **[!UICONTROL AND-join]** activity. File extraction can only take place when the three inbound transitions of the **[!UICONTROL AND-join]** activity are enabled.

![](assets/wkf_and-join_example.png)

