---
title: Enriquecimento
description: A atividade de Enriquecimento é uma atividade avançada com a qual é possível definir dados adicionais que serão processados no fluxo de trabalho.
page-status-flag: never-activated
uuid: 8c1693ef-1312-422c-b05d-263553113f8f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: f67c1caf-3284-4c34-a5b0-8654a95640ae
context-tags: enrichment,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 96%

---


# Enriquecimento{#enrichment}

## Descrição {#description}

![](assets/enrichment.png)

A atividade de **[!UICONTROL Enrichment]** é uma atividade avançada com a qual é possível definir dados adicionais que serão processados no fluxo de trabalho.

## Contexto de uso {#context-of-use}

A atividade **[!UICONTROL Enrichment]** é geralmente usada após atividades de direcionamento ou após a importação de um arquivo e antes de atividades que permitem o uso de dados direcionados.

Esta atividade contém funções de enriquecimento mais avançadas do que a atividade de **[!UICONTROL Query]**. Alguns casos simples de enriquecimento podem ser executados diretamente na [Atividade de Query](../../automating/using/query.md#enriching-data).

Com a atividade de **[!UICONTROL Enrichment]**, você pode aproveitar a transição de entrada e configurar a atividade para concluir a transição de saída com dados adicionais. Com ela, é possível combinar dados provenientes de vários conjuntos ou criar links para um recurso temporário.

**Tópicos relacionados**

* [Caso de uso: Enriquecendo dados de perfil com dados contidos em um arquivo](../../automating/using/enriching-profile-data-file.md).
* [Caso de uso: Envio de um email com campos aprimorados](../../automating/using/sending-email-enriched-fields.md)

## Configuração {#configuration}

Para configurar uma atividade de **[!UICONTROL Enrichment]**:

1. Arraste e solte uma atividade **[!UICONTROL Enrichment]** no seu workflow.
1. Selecione e abra a atividade usando o botão ![](assets/edit_darkgrey-24px.png) das ações rápidas exibidas.
1. Se a atividade tiver várias transições de entrada, selecione o **[!UICONTROL Primary set]**. Os dados adicionais configurados nessa atividade serão adicionados a este conjunto principal na transição de saída.

   Se o conjunto principal já tiver dados adicionais, você poderá optar por mantê-los ou removê-los. Se você desmarcar a opção **[!UICONTROL Keep all additional data from the main set]**, somente os dados adicionais configurados no **[!UICONTROL Enrichment]** serão mantidos na transição de saída.

1. Se houver várias transições de entrada, defina as relações entre o conjunto principal e os outros dados de entrada na guia da atividade **[!UICONTROL Advanced Relations]**. É possível adicionar várias relações usando o botão **[!UICONTROL Add element]**.

   Ao definir uma nova relação, selecione o conjunto de dados de entrada que deseja vincular ao conjunto principal. Em seguida, defina o tipo de relação. Vários tipos de relações estão disponíveis, dependendo dos dados de entrada e do template de dados:

   * **[!UICONTROL 1 cardinality simple link]**: cada registro dos dados recebidos está associado a um e a somente um registro do conjunto principal. Cada registro do conjunto principal tem um registro associado nos dados vinculados.
   * **[!UICONTROL N cardinality collection link]**: 0, 1 ou mais registros (N) dos dados vinculados podem ser associados a 1 registro do conjunto principal.
   * **[!UICONTROL 0 or 1 cardinality simple link]**: os registros do conjunto principal podem ser associados a 0 ou 1 registro dos dados vinculados, mas não a mais de um.

   Uma vez que a **[!UICONTROL Cardinality]** for definida, defina um **[!UICONTROL Reconciliation criteria]**. A **[!UICONTROL Source expression]** dos critérios de reconciliação pode ser um campo proveniente do recurso do público alvo, uma [expressão](../../automating/using/advanced-expression-editing.md) ou um valor especificado diretamente entre aspas.

   Defina um **[!UICONTROL Label]** e uma **[!UICONTROL ID]** que seja fácil de identificar posteriormente no fluxo de trabalho.

   >[!NOTE]
   >
   >Você só pode definir relações entre o conjunto principal e as outras transições de entrada conectadas à atividade de **[!UICONTROL Enrichment]**. Para casos mais simples cujo objetivo seja definir relações com recursos de banco de dados, use uma atividade de [Reconciliação](../../automating/using/reconciliation.md).

1. Defina os dados adicionais na guia **[!UICONTROL Additional data]** da atividade. É possível definir dados adicionais (campos simples, agregações e coleções) relacionados ao targeting dimension do conjunto principal ou com base nos links criados na guia **[!UICONTROL Advanced relations]** da atividade de **[!UICONTROL Enrichment]**.

   Consulte a seção [Enriquecimento de dados](../../automating/using/query.md#enriching-data).

1. Confirme a configuração da sua atividade e salve o fluxo de trabalho.

Os dados agora estão disponíveis para uso nas atividades conectadas após o **[!UICONTROL Enrichment]**. Por exemplo, você pode encontrá-los no link **[!UICONTROL Additional data (targetData)]** do explorador de campos de personalização em um conteúdo de email.
