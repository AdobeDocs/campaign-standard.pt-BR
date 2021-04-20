---
solution: Campaign Standard
product: campaign
title: AND-join
description: A atividade AND-join permite sincronizar várias ramificações de execução de um fluxo de trabalho.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: andjoin,main
feature: Workflows
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 98%

---


# AND-join{#and-join}

## Descrição {#description}

![](assets/and_join.png)

A atividade **[!UICONTROL AND-join]** permite sincronizar várias ramificações de execução de um fluxo de trabalho.

## Contexto de uso {#context-of-use}

A atividade **[!UICONTROL AND-join]** só acionará a transição de saída depois que todas as transições de entrada estiverem ativadas, ou seja, depois que todas as atividades anteriores estiverem concluídas.

## Configuração {#configuration}

1. Solte várias atividades, como consultas, no fluxo de trabalho para formar pelo menos duas ramificações de execução diferentes.
1. Arraste e solte uma atividade **[!UICONTROL AND-join]** no seu workflow.
1. Conecte-a depois das duas ramificações diferentes que você quer sincronizar.
1. Selecione e abra a atividade usando o botão ![](assets/edit_darkgrey-24px.png) das ações rápidas exibidas.
1. Selecione o conjunto principal a ser mantido na transição de saída. Se você não selecionar nenhum conjunto, uma população aleatória será enviada da atividade.
1. Confirme a configuração da sua atividade e salve o fluxo de trabalho.

## Exemplo {#example}

O exemplo a seguir mostra duas ramificações de fluxo de trabalho antes de elas serem unidas à atividade **[!UICONTROL AND-join]**. A extração de arquivos só poderá ocorrer quando as três transições de entrada da atividade **[!UICONTROL AND-join]** estiverem ativadas.

![](assets/wkf_and-join_example.png)

