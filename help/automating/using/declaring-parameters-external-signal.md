---
title: Chamada de fluxo de trabalho com parâmetros externos
description: Esta seção detalha como chamar um workflow com parâmetros externos.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: e6148b40-f608-4aab-81f6-756608c6828e
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 5%

---

# Declaração dos parâmetros na atividade External signal {#declaring-the-parameters-in-the-external-signal-activity}

A primeira etapa para chamar um workflow com parâmetros é declará-los em um **[!UICONTROL External signal]** atividade .

1. Abra o **[!UICONTROL External signal]** e, em seguida, selecione a **[!UICONTROL Parameters]** guia .
1. Clique no botão **[!UICONTROL Create element]** , em seguida, especifique o nome e o tipo de cada parâmetro.

   >[!CAUTION]
   >
   >Verifique se o nome e a quantidade de parâmetros são idênticos ao definido ao chamar o fluxo de trabalho (consulte [esta página](../../automating/using/defining-parameters-calling-workflow.md)). Além disso, os tipos de parâmetros devem ser consistentes com os valores esperados.

   ![](assets/extsignal_declaringparameters_1.png)

1. Depois que os parâmetros forem declarados, conclua a configuração do workflow e execute-a.
