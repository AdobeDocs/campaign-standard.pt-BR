---
title: Chamada de workflow com parâmetros externos
description: Esta seção detalha como chamar um fluxo de trabalho com parâmetros externos.
page-status-flag: never-activated
uuid: beccd1b6-8e6d-4504-9152-9ff537459c4a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 1676da91-55e3-414f-bcd3-bb0804b682bd
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 12%

---


# Definição dos parâmetros ao chamar o workflow {#defining-the-parameters-when-calling-the-workflow}

Esta seção detalha como definir parâmetros ao chamar um fluxo de trabalho. Para obter mais informações sobre como executar essa operação a partir de uma chamada de API, consulte a documentação [](../../api/using/triggering-a-signal-activity.md)REST APIs.

Antes de definir os parâmetros, verifique se:

* Os parâmetros foram declarados na **[!UICONTROL External Signal]** atividade. Consulte [](../../automating/using/declaring-parameters-external-signal.md).
* O fluxo de trabalho que contém a atividade de sinal está em execução.

Para configurar a **[!UICONTROL End]** atividade, siga as etapas abaixo:

1. Open the **[!UICONTROL End]** activity, then select the **[!UICONTROL External signal]** tab.
1. Selecione o fluxo de trabalho e a atividade de sinal externo que você deseja chamar.
1. Clique no **[!UICONTROL Create element]** botão para adicionar um parâmetro e, em seguida, preencha seu nome e valor.

   * **[!UICONTROL Name]**: o nome que foi declarado na **[!UICONTROL External signal]** atividade (consulte [](../../automating/using/declaring-parameters-external-signal.md)).
   * **[!UICONTROL Value]**: o valor que você deseja atribuir ao parâmetro. O valor deve seguir a sintaxe **Padrão, descrita** nesta seção [](../../automating/using/advanced-expression-editing.md#standard-syntax).

   ![](assets/extsignal_definingparameters_2.png)

   >[!CAUTION]
   >
   >Make sure that all the parameters have been declared in the **[!UICONTROL External signal]** activity. Caso contrário, ocorrerá um erro ao executar a atividade.

1. Depois que os parâmetros tiverem sido definidos, confirme a atividade e salve seu fluxo de trabalho.
