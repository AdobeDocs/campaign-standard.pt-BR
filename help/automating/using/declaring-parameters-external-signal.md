---
title: Chamada de um fluxo de trabalho com parâmetros externos
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
source-wordcount: '106'
ht-degree: 5%

---


# Declaração dos parâmetros na atividade de sinal Externo {#declaring-the-parameters-in-the-external-signal-activity}

A primeira etapa para chamar um fluxo de trabalho com parâmetros é declará-los em uma **[!UICONTROL External signal]** atividade.

1. Open the **[!UICONTROL External signal]** activity, then select the **[!UICONTROL Parameters]** tab.
1. Clique no **[!UICONTROL Create element]** botão e especifique o nome e o tipo de cada parâmetro.

   >[!CAUTION]
   >
   >Certifique-se de que o nome e o número de parâmetros sejam idênticos ao definido ao chamar o fluxo de trabalho (consulte [](../../automating/using/defining-parameters-calling-workflow.md)). Além disso, os tipos de parâmetros devem ser compatíveis com os valores esperados.

   ![](assets/extsignal_declaringparameters_1.png)

1. Depois que os parâmetros tiverem sido declarados, conclua a configuração do fluxo de trabalho e execute-a.
