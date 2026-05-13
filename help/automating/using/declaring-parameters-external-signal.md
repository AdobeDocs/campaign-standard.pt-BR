---
title: Declaração dos parâmetros na atividade de sinal externo
description: Esta seção detalha como chamar um workflow com parâmetros externos.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: e6148b40-f608-4aab-81f6-756608c6828e
TQID: https://experienceleague.adobe.com/au0xUZ7C8m3hiK9wbm3QBiHd9RtpZQW-AEoc-SvnhfE
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 110
ht-degree: 0%

---

# Declaração dos parâmetros na atividade de sinal externo {#declaring-the-parameters-in-the-external-signal-activity}

A primeira etapa para chamar um fluxo de trabalho com parâmetros é declará-los em uma atividade **[!UICONTROL External signal]**.

1. Abra a atividade **[!UICONTROL External signal]** e selecione a guia **[!UICONTROL Parameters]**.
1. Clique no botão **[!UICONTROL Create element]** e especifique o nome e o tipo de cada parâmetro.

   >[!CAUTION]
   >
   >Verifique se o nome e a quantidade de parâmetros são idênticos ao definido ao chamar o fluxo de trabalho (consulte [esta página](../../automating/using/defining-parameters-calling-workflow.md)). Além disso, os tipos de parâmetros devem ser consistentes com os valores esperados.

   ![](assets/extsignal_declaringparameters_1.png)

1. Depois que os parâmetros forem declarados, conclua a configuração do workflow e execute-o.
