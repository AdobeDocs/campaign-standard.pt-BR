---
title: AND-join
description: A atividade de junção AND permite sincronizar várias ramificações de execução de um fluxo de trabalho.
page-status-flag: nunca ativado
uuid: 9b54fd4c-9915-400f-a494-74e52c329b8a
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: automatização
content-type: referência
topic-tags: atividades de execução
discoiquuid: 4b55efa2-652e-4493-bfa7-eaee59b383ca
context-tags: andjoin,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# AND-join{#and-join}

## Descrição {#description}

![](assets/and_join.png)

A **[!UICONTROL AND-join]** atividade permite sincronizar várias ramificações de execução de um fluxo de trabalho.

## Contexto de utilização {#context-of-use}

A **[!UICONTROL AND-join]** atividade aciona sua transição de saída somente depois que todas as transições de entrada forem ativadas, em outras palavras, depois que todas as atividades anteriores tiverem sido concluídas.

## Configuração {#configuration}

1. Solte várias atividades, como consultas, em seu fluxo de trabalho para formar pelo menos duas ramificações de execução diferentes.
1. Arraste e solte uma **[!UICONTROL AND-join]** atividade em seu fluxo de trabalho.
1. Conecte-o depois das duas ramificações diferentes que você deseja sincronizar.
1. Selecione a atividade e abra-a usando o ![](assets/edit_darkgrey-24px.png) botão das ações rápidas que aparecem.
1. Selecione o conjunto principal a ser mantido na transição de saída. Se você não selecionar nenhum conjunto, uma população aleatória será enviada da atividade.
1. Confirme a configuração da atividade e salve o fluxo de trabalho.

## Exemplo {#example}

O exemplo a seguir mostra duas ramificações de fluxo de trabalho antes de serem unidas à **[!UICONTROL AND-join]** atividade. A extração de arquivos só pode ocorrer quando as três transições de entrada da **[!UICONTROL AND-join]** atividade estiverem ativadas.

![](assets/wkf_and-join_example.png)

