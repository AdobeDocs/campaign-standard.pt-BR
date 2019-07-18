---
title: Fork
seo-title: Fork
description: Fork
seo-description: A atividade Bidirecional permite que você crie transições de saída para iniciar várias atividades ao mesmo tempo.
page-status-flag: nunca ativado
uuid: e 4 eaf 69 b -84 ee -4 f 79-8 b 80-99284697 cd 2 c
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizando
content-type: reference
topic-tags: execução-atividades
discoiquuid: f 8 ffe 7 af-e 18 c -4599-8 fd 0-fcd 192565323
context-tags: fork, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e384a0cef325bc01eb5ea050b0f3d926aea9a88f

---


# Fork{#fork}

## Description {#description}

![](assets/fork.png)

The **[!UICONTROL Fork]** activity allows you to create outbound transitions to start several activities at the same time.

## Context of use {#context-of-use}

The **[!UICONTROL Fork]** activity allows you to carry out several different activities independently within the same workflow.

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Fork]** activity into your workflow.
1. Conecte-o a outras atividades que vêm antes dele, como consultas.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Especifique o número de transações de saída ao criar, excluir ou duplicá-las. Você também pode atribuir um nome e um rótulo a eles.
1. Confirme a configuração da atividade e salve seu fluxo de trabalho.

## Example {#example}

O exemplo a seguir mostra uma interseção de duas atividades de consulta que direcionam perfis do banco de dados do Adobe Campaign, nesse caso, mulheres que residem em Paris. A atividade de fork permite, portanto, usar várias atividades ao mesmo tempo: uma que salva o público-alvo para lembrar a população calculada e outra que faz com que os segmentos enviem dois emails diferentes com um conteúdo direcionado para cada segmento. O primeiro email é enviado para mulheres Parisian entre 18 e 40 e outro direcionamento feminino Parisian com mais de 40.

![](assets/wkf_fork_example.png)

