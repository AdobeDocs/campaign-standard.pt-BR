---
solution: Campaign Standard
product: campaign
title: Visão geral
description: Esta seção detalha como chamar um workflow com parâmetros externos.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Fluxos de trabalho
role: Arquiteto de dados
level: Intermediário
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 4%

---


# Visão geral {#calling-a-workflow-with-external-parameters}

O Campaign Standard permite chamar um workflow com parâmetros (um nome de público-alvo para target, um nome de arquivo a ser importado, uma parte do conteúdo da mensagem etc.). Dessa forma, você pode integrar facilmente suas automações do Campaign com seu sistema externo.

Vejamos o exemplo a seguir, onde queremos enviar emails diretamente de um CMS. Nesse caso, você pode configurar o sistema para selecionar o público-alvo e enviar conteúdo por email para o CMS. Clicar em Enviar chamará um workflow de Campanha com esses parâmetros, permitindo que você os use no workflow para definir o público-alvo e o conteúdo do URL a serem usados no delivery.

O processo para chamar um workflow com parâmetros é o seguinte:

1. Declare os parâmetros na atividade **[!UICONTROL External signal]** . Consulte [Declaração dos parâmetros na atividade de sinal externo](../../automating/using/declaring-parameters-external-signal.md).
1. Configure a atividade **[!UICONTROL End]** ou a chamada da API para definir os parâmetros e acionar a atividade **[!UICONTROL External signal]** do workflow. Consulte [esta página](../../automating/using/defining-parameters-calling-workflow.md)
1. Depois que o fluxo de trabalho é acionado, os parâmetros são assimilados nas variáveis de eventos do fluxo de trabalho e podem ser usados dentro dele. Consulte [esta página](../../automating/using/customizing-workflow-external-parameters.md).

![](assets/extsignal_process.png)
