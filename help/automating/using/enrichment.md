---
title: Enriquecimento
description: A atividade do Enriquecimento é uma atividade avançada que permite definir dados adicionais para serem processados no fluxo de trabalho.
page-status-flag: never-activated
uuid: 8c1693ef-1312-422c-b05d-263553113f8f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: f67c1caf-3284-4c34-a5b0-8654a95640ae
context-tags: enrichment,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 87e0611fae0560aca276caa3c4cf793e9c095d72
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 1%

---


# Enriquecimento{#enrichment}

## Descrição {#description}

![](assets/enrichment.png)

A **[!UICONTROL Enrichment]** atividade é uma atividade avançada que permite definir dados adicionais para serem processados no fluxo de trabalho.

## Contexto de utilização {#context-of-use}

A **[!UICONTROL Enrichment]** atividade é geralmente usada após atividades de definição de metas ou após a importação de um arquivo e antes das atividades que permitem o uso de dados direcionados.

Esta atividade contém funções de enriquecimento mais avançadas do que a **[!UICONTROL Query]** atividade. Alguns casos simples de enriquecimento podem ser executados diretamente na atividade do [Query](../../automating/using/query.md#enriching-data).

Com a **[!UICONTROL Enrichment]** atividade, você pode aproveitar a transição de entrada e configurar a atividade para concluir a transição de saída com dados adicionais. Permite combinar dados provenientes de vários conjuntos ou criar links para um recurso temporário.

**Tópicos relacionados**

* [Caso de uso: Enriquecendo dados de perfil com dados contidos em um arquivo](../../automating/using/enriching-profile-data-file.md).
* [Caso de uso: Envio de um email com campos aprimorados](../../automating/using/sending-email-enriched-fields.md)

## Configuração {#configuration}

Para configurar uma **[!UICONTROL Enrichment]** atividade:

1. Arraste e solte uma **[!UICONTROL Enrichment]** atividade no seu fluxo de trabalho.
1. Selecione a atividade e abra-a usando o ![](assets/edit_darkgrey-24px.png) botão das ações rápidas que aparecem.
1. Se a atividade tiver várias transições de entrada, selecione-as **[!UICONTROL Primary set]**. Os dados adicionais configurados nesta atividade serão adicionados a este conjunto principal na transição de saída.

   Se o conjunto principal já contiver dados adicionais, você poderá optar por mantê-los ou removê-los. Se você desmarcar a **[!UICONTROL Keep all additional data from the main set]** opção, somente os dados adicionais configurados na transição **[!UICONTROL Enrichment]** serão mantidos na  de saída.

1. Se houver várias transições de entrada, defina as relações entre o conjunto principal e os outros dados de entrada na guia **[!UICONTROL Advanced Relations]** da atividade. É possível adicionar várias relações usando o **[!UICONTROL Add element]** botão.

   Ao definir uma nova relação, selecione o conjunto de dados de entrada que você deseja vincular ao conjunto principal. Em seguida, defina o tipo de relação. Vários tipos de relações estão disponíveis, dependendo dos dados de entrada e do modelo de dados:

   * **[!UICONTROL 1 cardinality simple link]**: cada registro dos dados recebidos está associado a um e somente a um registro do conjunto principal. Cada registro do conjunto principal tem um registro associado nos dados vinculados.
   * **[!UICONTROL N cardinality collection link]**: 0, 1 ou mais registros (N) dos dados vinculados podem ser associados a 1 registro do conjunto principal.
   * **[!UICONTROL 0 or 1 cardinality simple link]**: os registros do conjunto principal podem ser associados a 0 ou 1 registro dos dados vinculados, mas não a mais de um.
   Uma vez que o **[!UICONTROL Cardinality]** for definido, defina um **[!UICONTROL Reconciliation criteria]**. O **[!UICONTROL Source expression]** dos critérios de reconciliação pode ser um campo do recurso do público alvo, uma [expressão](../../automating/using/advanced-expression-editing.md) ou um valor especificado diretamente entre aspas.

   Defina um **[!UICONTROL Label]** e um **[!UICONTROL ID]** que será fácil de identificar posteriormente no fluxo de trabalho.

   >[!NOTE]
   >
   >Você só pode definir relações entre o conjunto principal e as outras transições de entrada conectadas à **[!UICONTROL Enrichment]** atividade. Para casos mais simples que visem definir relações com recursos de banco de dados, use uma atividade de [Reconciliação](../../automating/using/reconciliation.md) .

1. Defina os dados adicionais na **[!UICONTROL Additional data]** guia da atividade. É possível definir dados adicionais (campos simples, agregações e coleções) relacionados ao targeting dimension do conjunto principal ou com base nos links criados na **[!UICONTROL Advanced relations]** guia da **[!UICONTROL Enrichment]** atividade.

   Consulte a seção [Enriquecendo dados](../../automating/using/query.md#enriching-data) .

1. Confirme a configuração da atividade e salve o fluxo de trabalho.

Os dados agora estão disponíveis para uso nas atividades conectadas após o **[!UICONTROL Enrichment]**. Por exemplo, você pode encontrá-lo sob o **[!UICONTROL Additional data (targetData)]** link do explorador de campos de personalização em um conteúdo de email.
