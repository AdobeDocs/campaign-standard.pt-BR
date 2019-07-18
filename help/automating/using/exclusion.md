---
title: Exclusão
seo-title: Exclusão
description: Exclusão
seo-description: A atividade de Exclusão permite excluir elementos de uma população de acordo com determinados critérios.
page-status-flag: nunca ativado
uuid: b 79 e 7 f 73-37 a 0-4 ec 3-ac 5 a -5449 dc 1 b 1 f 22
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizando
content-type: reference
topic-tags: atividades de definição de metas
discoiquuid: d 5312 fcd -43 ad -428 e-bde 9-90 f 062 e 9358 c
context-tags: exclusão, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e384a0cef325bc01eb5ea050b0f3d926aea9a88f

---


# Exclusion{#exclusion}

## Description {#description}

![](assets/exclusion.png)

The **[!UICONTROL Exclusion]** activity allows you to exclude elements from one population according to certain criteria.

## Context of use {#context-of-use}

**[!UICONTROL Exclusion]** A atividade é usada basicamente para realizar filtragem adicional em populações de transição de entrada.

Um conjunto principal é definido entre as transições de entrada. Os membros de outras transições de entrada são excluídos do conjunto principal. A transição de saída da atividade de exclusão contém apenas os membros do conjunto principal que não foram encontrados nas outras transições de entrada.

## Configuration {#configuration}

1. Drag and drop an **[!UICONTROL Exclusion]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Select the **[!UICONTROL Primary set]** from the inbound transitions. Esse é o conjunto a partir do qual os elementos são excluídos. Os outros conjuntos correspondem antes de serem excluídos do conjunto principal.

   >[!NOTE]
   >
   >As transições de entrada precisam conter o mesmo tipo de população. Por exemplo, se o conjunto principal contiver perfis de teste, as outras transições precisarão conter perfis de teste.

1. If needed, manage the activity's [Transitions](../../automating/using/executing-a-workflow.md#managing-an-activity-s-outbound-transitions) to access the advanced options for the outbound population.
1. Confirme a configuração da atividade e salve seu fluxo de trabalho.

## Example {#example}

O exemplo a seguir mostra duas atividades de consulta configuradas para filtrar perfis do banco de dados do Adobe Campaign que têm entre 18 e 27 anos e um endereço de email inválido. Os perfis com endereços de email inválidos são excluídos do primeiro conjunto. Isso permite enviar um e-mail por exemplo.

![](assets/wkf_exclusion_example.png)

