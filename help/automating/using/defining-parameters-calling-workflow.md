---
title: Definição dos parâmetros ao chamar o fluxo de trabalho
description: Esta seção detalha como chamar um workflow com parâmetros externos.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: f7de0186-4136-4603-8f80-9f58c641cd9d
TQID: https://experienceleague.adobe.com/-YjlK1Op8P08sxb--BOHl8AWyciX4BqPnCPQ3lpD3Co
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: b12f6872-9271-4369-85e5-86969a0b99a2
subfeature_v2: id: bf97c196-a4d1-4fa3-a151-e68a114c8ac0
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 189
ht-degree: 13%

---

# Definição dos parâmetros ao chamar o fluxo de trabalho {#defining-the-parameters-when-calling-the-workflow}

Esta seção detalha como definir parâmetros ao chamar um workflow. Para obter mais informações sobre como executar esta operação a partir de uma chamada à API, consulte a [documentação sobre APIs REST](../../api/using/triggering-a-signal-activity.md).

Antes de definir os parâmetros, verifique se:

* Os parâmetros foram declarados na atividade **[!UICONTROL External Signal]**. Consulte [esta página](../../automating/using/declaring-parameters-external-signal.md).
* O fluxo de trabalho que contém a atividade de sinal está em execução.

Para configurar a atividade **[!UICONTROL End]**, siga as etapas abaixo:

1. Abra a atividade **[!UICONTROL End]** e selecione a guia **[!UICONTROL External signal]**.
1. Selecione a atividade de workflow e sinal externo que deseja chamar.
1. Clique no botão **[!UICONTROL Create element]** para adicionar um parâmetro e, em seguida, preencha seu nome e valor.

   * **[!UICONTROL Name]**: o nome declarado na atividade **[!UICONTROL External signal]** (consulte [esta página](../../automating/using/declaring-parameters-external-signal.md)).
   * **[!UICONTROL Value]**: o valor que você deseja atribuir ao parâmetro. O valor deve seguir a **Sintaxe padrão**, descrita em [esta seção](../../automating/using/advanced-expression-editing.md#standard-syntax).

   ![](assets/extsignal_definingparameters_2.png)

   >[!CAUTION]
   >
   >Verifique se todos os parâmetros foram declarados na atividade **[!UICONTROL External signal]**. Caso contrário, ocorrerá um erro ao executar a atividade.

1. Depois que os parâmetros forem definidos, confirme a atividade e salve o workflow.
