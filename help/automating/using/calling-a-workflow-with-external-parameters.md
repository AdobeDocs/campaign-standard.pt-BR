---
title: Visão geral
description: Esta seção detalha como chamar um workflow com parâmetros externos.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 538056e6-b5c0-4258-a34b-524fe6e3cbbe
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 4%

---

# Visão geral {#calling-a-workflow-with-external-parameters}

O Campaign Standard permite chamar um workflow com parâmetros (um nome de público-alvo para target, um nome de arquivo a ser importado, uma parte do conteúdo da mensagem etc.). Dessa forma, você pode integrar facilmente suas automações do Campaign com seu sistema externo.

Vejamos o exemplo a seguir, onde queremos enviar emails diretamente de um CMS. Nesse caso, você pode configurar o sistema para selecionar o público-alvo e enviar conteúdo por email para o CMS. Clicar em Enviar chamará um workflow de Campanha com esses parâmetros, permitindo que você os use no workflow para definir o público-alvo e o conteúdo do URL a serem usados no delivery.

O processo para chamar um workflow com parâmetros é o seguinte:

1. Declare os parâmetros no **[!UICONTROL External signal]** atividade . Consulte [Declaração dos parâmetros na atividade External signal](../../automating/using/declaring-parameters-external-signal.md).
1. Configure o **[!UICONTROL End]** ou a chamada da API para definir os parâmetros e acionar o workflow **[!UICONTROL External signal]** atividade . Consulte [esta página](../../automating/using/defining-parameters-calling-workflow.md)
1. Depois que o fluxo de trabalho é acionado, os parâmetros são assimilados nas variáveis de eventos do fluxo de trabalho e podem ser usados dentro dele. Consulte [esta página](../../automating/using/customizing-workflow-external-parameters.md).

![](assets/extsignal_process.png)
