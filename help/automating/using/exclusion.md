---
title: Exclusão
description: A atividade de exclusão permite excluir elementos de uma população de acordo com determinados critérios.
page-status-flag: never-activated
uuid: b79e7f73-37a0-4ec3-ac5a-5449dc1b1f22
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: d5312fcd-43ad-428e-bde9-90f062e9358c
context-tags: exclusion,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 21faea89b3b38f3e667ed6c4de0be6d07f0b7197
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 2%

---


# Exclusão{#exclusion}

## Descrição {#description}

![](assets/exclusion.png)

A **[!UICONTROL Exclusion]** atividade permite excluir elementos de uma população de acordo com determinados critérios.

## Contexto de utilização {#context-of-use}

A **[!UICONTROL Exclusion]** atividade é utilizada essencialmente para filtrar mais as populações de transições de entrada.

Um conjunto principal é definido entre as transições de entrada. Os membros de outras transições de entrada são excluídos do conjunto principal. A transição de saída da atividade de exclusão contém apenas os membros do conjunto principal que não foram encontrados nas outras transições de entrada.

## Configuração {#configuration}

1. Arraste e solte uma **[!UICONTROL Exclusion]** atividade no seu fluxo de trabalho.
1. Selecione a atividade e abra-a usando o ![](assets/edit_darkgrey-24px.png) botão das ações rápidas que aparecem.
1. Selecione as transições **[!UICONTROL Primary set]** de entrada. Esse é o conjunto a partir do qual os elementos são excluídos. Os outros conjuntos correspondem a elementos antes de serem excluídos do conjunto principal.

   >[!NOTE]
   >
   >As transições de entrada devem conter o mesmo tipo de população. Por exemplo, se o conjunto principal contiver perfis de teste, as outras transições também deverão conter perfis de teste.

1. Se necessário, gerencie as [Transições](../../automating/using/activity-properties.md) de atividade para acessar as opções avançadas para a população de saída.
1. Confirme a configuração da atividade e salve o fluxo de trabalho.

## Exemplo {#example}

O exemplo a seguir mostra duas atividades de query configuradas para filtrar perfis do banco de dados do Adobe Campaign que têm entre 18 e 27 anos e têm um endereço de email inválido. Os perfis com endereços de email inválidos são excluídos do primeiro conjunto. Isso permite que você envie um email, por exemplo.

![](assets/wkf_exclusion_example.png)

