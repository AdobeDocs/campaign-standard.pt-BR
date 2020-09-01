---
title: Visão geral
description: Esta seção detalha como chamar um fluxo de trabalho com parâmetros externos.
page-status-flag: never-activated
uuid: beccd1b6-8e6d-4504-9152-9ff537459c4a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 1676da91-55e3-414f-bcd3-bb0804b682bd
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 51e98bb6212ad96d9c11b848df9dcad25b3f1b61
workflow-type: tm+mt
source-wordcount: '181'
ht-degree: 1%

---


# Visão geral {#calling-a-workflow-with-external-parameters}

O Campaign Standard permite que você chame um fluxo de trabalho com parâmetros (um nome de audiência para público alvo, um nome de arquivo a ser importado, uma parte do conteúdo da mensagem etc.). Dessa forma, você pode integrar facilmente suas automações de Campanha ao seu sistema externo.

Vejamos o exemplo a seguir, no qual queremos enviar emails diretamente de um CMS. Nesse caso, você pode configurar seu sistema para selecionar a audiência e enviar conteúdo por email para o CMS. Clicar em Enviar chamará um fluxo de trabalho de Campanha com esses parâmetros, permitindo que você os use no fluxo de trabalho para definir a audiência e o conteúdo do URL a serem usados no delivery.

O processo para chamar um fluxo de trabalho com parâmetros é o seguinte:

1. Declarar os parâmetros na **[!UICONTROL External signal]** atividade. Consulte [Declaração dos parâmetros na atividade](../../automating/using/declaring-parameters-external-signal.md)de sinal externo.
1. Configure a **[!UICONTROL End]** atividade ou a chamada da API para definir os parâmetros e acionar a **[!UICONTROL External signal]** atividade do fluxo de trabalho.

Depois que o fluxo de trabalho é acionado, os parâmetros são ingeridos nas variáveis de eventos do fluxo de trabalho e podem ser usados no fluxo de trabalho. Consulte [](../../automating/using/customizing-workflow-external-parameters.md).

![](assets/extsignal_process.png)
