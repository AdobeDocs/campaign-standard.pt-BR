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
source-wordcount: '192'
ht-degree: 13%

---


# Definição dos parâmetros ao chamar o workflow {#defining-the-parameters-when-calling-the-workflow}

Esta seção detalha como definir parâmetros ao chamar um workflow. Para obter mais informações sobre como executar essa operação a partir de uma chamada de API, consulte a [documentação sobre APIs REST](../../api/using/triggering-a-signal-activity.md).

Antes de definir os parâmetros, verifique se:

* Os parâmetros foram declarados na atividade **[!UICONTROL External Signal]** . Consulte [esta página](../../automating/using/declaring-parameters-external-signal.md).
* O fluxo de trabalho que contém a atividade de sinal está em execução.

Para configurar a atividade **[!UICONTROL End]**, siga as etapas abaixo:

1. Abra a atividade **[!UICONTROL End]** e selecione a guia **[!UICONTROL External signal]** .
1. Selecione o workflow e a atividade de sinal externo que deseja chamar.
1. Clique no botão **[!UICONTROL Create element]** para adicionar um parâmetro e, em seguida, preencha o nome e o valor.

   * **[!UICONTROL Name]**: o nome que foi declarado na  **[!UICONTROL External signal]** atividade (consulte  [esta página](../../automating/using/declaring-parameters-external-signal.md)).
   * **[!UICONTROL Value]**: o valor que você deseja atribuir ao parâmetro. O valor deve seguir a **Sintaxe padrão**, descrita em [esta seção](../../automating/using/advanced-expression-editing.md#standard-syntax).

   ![](assets/extsignal_definingparameters_2.png)

   >[!CAUTION]
   >
   >Verifique se todos os parâmetros foram declarados na atividade **[!UICONTROL External signal]** . Caso contrário, ocorrerá um erro ao executar a atividade.

1. Após definir os parâmetros, confirme a atividade e salve o fluxo de trabalho.
