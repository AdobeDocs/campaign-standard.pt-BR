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
TQID: 'https://experienceleague.adobe.com/au0xUZ7C8m3hiK9wbm3QBiHd9RtpZQW-AEoc-SvnhfE'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '110'
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
