---
title: Aguarde
seo-title: Aguarde
description: Aguarde
seo-description: A atividade de Espera suspende momentaneamente a execução de parte de um fluxo de trabalho.
page-status-flag: nunca ativado
uuid: 396 a 3 de 1-6 ffa -4385-ac 9 f -15 fdeae 5 a 366
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizando
content-type: reference
topic-tags: execução-atividades
discoiquuid: 377821 e 6-69 f 8-41 cc-a 1 ad -8 a 2 f 5 ed 4 d 409
context-tags: esperar, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e384a0cef325bc01eb5ea050b0f3d926aea9a88f

---


# Wait{#wait}

## Description {#description}

![](assets/wait.png)

The **[!UICONTROL Wait]** activity momentarily suspends executing a part of a workflow. Ele ativa sua transição de saída após um atraso que pode variar de alguns segundos para vários meses, o que executa as atividades colocadas depois.

## Context of use {#context-of-use}

**[!UICONTROL Wait]** A atividade é usada para permitir um certo tempo de passagem entre duas atividades que estão sendo executadas. Por exemplo, para aguardar vários dias após uma atividade de entrega de email, analise as aberturas e os cliques gerados durante esse período antes de realizar quaisquer operações de acompanhamento (email de lembrete, criação de um público-alvo etc.).

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Wait]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Specify the **[!UICONTROL Duration]** of the wait between when the inbound and outbound transitions of the activity are activated.

   Você pode inserir manualmente a duração ou usar o seletor disponível no campo.

   ![](assets/wait_duration.png)

1. Confirme a configuração da atividade e salve seu fluxo de trabalho.

## Example {#example}

The following example illustrates the **[!UICONTROL Wait]** activity in a typical use case. Um convite por email para um evento é enviado. 24 horas após o envio, os logs de entrega de email são analisados e um e-mail de lembrete é enviado para as pessoas que receberam o primeiro email, mas não se inscreveram.

O fluxo de trabalho é apresentado da seguinte maneira:

![](assets/wait_example_workflow.png)

* A first **[!UICONTROL Query]** targets the profiles that will be sent the email invitation.
* An **[!UICONTROL Email delivery]** sends the invitation for the first time to the profiles selected.
* A **[!UICONTROL Wait]** activity of 24h places a pause between when the invitation was sent and the rest of the workflow.
* A second **[!UICONTROL Query]** targets the profiles that received the first email but did not click on the subscription link inside.
* A second **[!UICONTROL Email delivery]** sends a reminder of the invitation to the people selected.

