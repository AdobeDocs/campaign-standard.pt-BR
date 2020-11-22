---
solution: Campaign Standard
product: campaign
title: Visão geral
description: Esta seção detalha como chamar um fluxo de trabalho com parâmetros externos.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 4%

---


# Visão geral {#calling-a-workflow-with-external-parameters}

O Campaign Standard permite que você chame um fluxo de trabalho com parâmetros (um nome de audiência para público alvo, um nome de arquivo a ser importado, uma parte do conteúdo da mensagem etc.). Dessa forma, você pode integrar facilmente suas automações de Campanha ao seu sistema externo.

Vejamos o exemplo a seguir, no qual queremos enviar emails diretamente de um CMS. Nesse caso, você pode configurar seu sistema para selecionar a audiência e enviar conteúdo por email para o CMS. Clicar em Enviar chamará um fluxo de trabalho de Campanha com esses parâmetros, permitindo que você os use no fluxo de trabalho para definir a audiência e o conteúdo do URL a serem usados no delivery.

O processo para chamar um fluxo de trabalho com parâmetros é o seguinte:

1. Declarar os parâmetros na **[!UICONTROL External signal]** atividade. See [Declaring the parameters in the External signal activity](../../automating/using/declaring-parameters-external-signal.md).
1. Configure a **[!UICONTROL End]** atividade ou a chamada da API para definir os parâmetros e acionar a **[!UICONTROL External signal]** atividade do fluxo de trabalho. Consulte [esta página](../../automating/using/defining-parameters-calling-workflow.md)
1. Depois que o fluxo de trabalho é acionado, os parâmetros são ingeridos nas variáveis de eventos do fluxo de trabalho e podem ser usados no fluxo de trabalho. Consulte [esta página](../../automating/using/customizing-workflow-external-parameters.md).

![](assets/extsignal_process.png)
