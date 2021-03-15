---
solution: Campaign Standard
product: campaign
title: Chamada de workflow com parâmetros externos
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
source-wordcount: '112'
ht-degree: 6%

---


# Declaração dos parâmetros na atividade de sinal externo {#declaring-the-parameters-in-the-external-signal-activity}

A primeira etapa para chamar um workflow com parâmetros é declará-los em uma atividade **[!UICONTROL External signal]**.

1. Abra a atividade **[!UICONTROL External signal]** e selecione a guia **[!UICONTROL Parameters]** .
1. Clique no botão **[!UICONTROL Create element]** e especifique o nome e o tipo de cada parâmetro.

   >[!CAUTION]
   >
   >Certifique-se de que o nome e o número de parâmetros sejam idênticos ao definido ao chamar o workflow (consulte [esta página](../../automating/using/defining-parameters-calling-workflow.md)). Além disso, os tipos de parâmetros devem ser consistentes com os valores esperados.

   ![](assets/extsignal_declaringparameters_1.png)

1. Depois que os parâmetros forem declarados, conclua a configuração do workflow e execute-a.
