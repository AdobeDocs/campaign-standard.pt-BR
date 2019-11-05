---
title: Iniciar e finalizar
description: As atividades Início e Fim permitem que você marque claramente onde seu fluxo de trabalho começa e termina.
page-status-flag: nunca ativado
uuid: 146b6337-122c-453d-8ffd-5c157db29217
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: automatização
content-type: referência
topic-tags: atividades de execução
discoiquuid: a0a8a725-8ede-4626-9798-b86924b58beb
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Iniciar e finalizar{#start-and-end}

## Descrição {#description}

![](assets/start.png)

![](assets/end.png)

As atividades **[!UICONTROL Start]** e **[!UICONTROL End]** permitem que você marque claramente onde seu fluxo de trabalho começa e termina.

## Contexto de utilização {#context-of-use}

A execução de um fluxo de trabalho é iniciada com atividades sem uma transição de entrada e é interrompida quando não há mais tarefas em andamento. No entanto, você pode adicionar **[!UICONTROL Start]** e **[!UICONTROL End]** atividades para marcar claramente os pontos de partida e de término de um fluxo de trabalho. Isso é especialmente útil para fluxos de trabalho relativamente complexos.

É uma prática recomendada usar uma **[!UICONTROL End]** atividade em vez de deixar a última transição de um fluxo de trabalho por conta própria para garantir que o fluxo de trabalho seja concluído corretamente.

## Configuração {#configuration}

1. Arraste e solte uma atividade **[!UICONTROL Start]** ou **[!UICONTROL End]** atividade em seu fluxo de trabalho.
1. Coloque a **[!UICONTROL Start]** atividade em frente a outras atividades, como consultas, e a **[!UICONTROL End]** atividade após uma série de atividades.
1. Selecione a atividade e abra-a usando o ![](assets/edit_darkgrey-24px.png) botão das ações rápidas que aparecem.
1. Você pode configurar o objeto **End** para que ele interrompa todas as tarefas em andamento do fluxo de trabalho, incluindo aquelas que ainda não foram concluídas. Para fazer isso, selecione a opção correspondente.
1. Confirme a configuração da atividade e salve o fluxo de trabalho.

## Acionando outro fluxo de trabalho {#triggering-another-workflow}

Usando a **[!UICONTROL External signal]** guia de uma **[!UICONTROL End]** atividade, é possível acionar outro fluxo de trabalho. Consulte a seção Sinal [](../../automating/using/external-signal.md) externo.

## Exemplo {#example}

O exemplo a seguir mostra como um fluxo de trabalho complexo é executado com uma **[!UICONTROL Start]** atividade e várias **[!UICONTROL End]** atividades. A **[!UICONTROL Stop all tasks in progress]** caixa foi marcada para a primeira **[!UICONTROL End]** atividade. Quando a tarefa correspondente for concluída, todo o fluxo de trabalho será interrompido: terá o mesmo efeito que se o ![](assets/stop_darkgrey-24px.png) botão tivesse sido selecionado (consulte a seção da barra [de](../../automating/using/workflow-interface.md#action-bar) ação).

![](assets/wkf_start_end_example.png)

