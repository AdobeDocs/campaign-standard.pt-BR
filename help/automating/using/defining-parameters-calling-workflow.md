---
title: Definição dos parâmetros ao chamar o fluxo de trabalho
description: Esta seção detalha como chamar um workflow com parâmetros externos.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: f7de0186-4136-4603-8f80-9f58c641cd9d
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 13%

---

# Definição dos parâmetros ao chamar o fluxo de trabalho {#defining-the-parameters-when-calling-the-workflow}

Esta seção detalha como definir parâmetros ao chamar um workflow. Para obter mais informações sobre como executar essa operação a partir de uma chamada de API, consulte [Documentação das APIs REST](../../api/using/triggering-a-signal-activity.md).

Antes de definir os parâmetros, verifique se:

* Os parâmetros foram declarados na variável **[!UICONTROL External Signal]** atividade. Consulte [esta página](../../automating/using/declaring-parameters-external-signal.md).
* O fluxo de trabalho que contém a atividade de sinal está em execução.

Para configurar o **[!UICONTROL End]** siga as etapas abaixo:

1. Abra o **[!UICONTROL End]** e selecione a **[!UICONTROL External signal]** guia.
1. Selecione a atividade de workflow e sinal externo que deseja chamar.
1. Clique em **[!UICONTROL Create element]** botão para adicionar um parâmetro, em seguida, preencha o nome e o valor.

   * **[!UICONTROL Name]**: o nome que foi declarado no **[!UICONTROL External signal]** atividade (consulte [esta página](../../automating/using/declaring-parameters-external-signal.md)).
   * **[!UICONTROL Value]**: o valor que você deseja atribuir ao parâmetro. O valor deve seguir o **Sintaxe padrão**, descrito em [nesta seção](../../automating/using/advanced-expression-editing.md#standard-syntax).

   ![](assets/extsignal_definingparameters_2.png)

   >[!CAUTION]
   >
   >Verifique se todos os parâmetros foram declarados no **[!UICONTROL External signal]** atividade. Caso contrário, ocorrerá um erro ao executar a atividade.

1. Depois que os parâmetros forem definidos, confirme a atividade e salve o workflow.
