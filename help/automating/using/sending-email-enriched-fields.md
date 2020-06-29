---
title: Envio de um email com campos aprimorados
description: O exemplo abaixo mostra como enviar um email usando dados adicionais recuperados de um arquivo externo por meio da atividade de arquivo de carregamento.
page-status-flag: never-activated
uuid: 69af12cc-6f82-4977-9f53-aa7bc26f5d7e
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: 584ff893-9b1b-46c9-9628-714ab349ab88
context-tags: fileImport,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 0%

---


# Envio de um email com campos aprimorados {#sending-email-enriched-fields}

<!--A new example showing how to send an email containing additional data retrieved from a load file activity has been added. [Read more](example-2-email-with-enriched-fields)-->

A atividade de carregamento de arquivo também permite enviar um email enriquecido com dados adicionais de um arquivo externo no mesmo fluxo de trabalho.

O exemplo abaixo mostra como enviar um email usando dados adicionais recuperados de um arquivo externo por meio da atividade de arquivo de carregamento. Neste exemplo, o arquivo externo contém uma lista de perfis com seu número de conta associado. Você deseja importar esses dados para enviar um email para cada perfil com o número da conta.

![](assets/load_file_workflow_ex2.png)

Para criar o fluxo de trabalho, siga estas etapas:

1. Arraste e solte uma atividade de [Query](../../automating/using/query.md) em seu fluxo de trabalho e abra-a para definir o público alvo principal.

   <!--The Query activity is presented in the [Query](../../automating/using/query.md) section.-->

1. Arraste e solte uma atividade [Carregar arquivo](../../automating/using/load-file.md) para atribuir alguns dados a um perfil. Neste exemplo, carregue um arquivo contendo números de conta correspondentes a alguns perfis do banco de dados.

   ![](assets/load_file_activity.png)

1. Arraste e solte uma atividade de [Enriquecimento](../../automating/using/enrichment.md) em seu fluxo de trabalho e vincule o arquivo de carregamento e as atividades de query a ele.

1. Na **[!UICONTROL Advanced relations]** guia da atividade do enriquecimento, selecione **[!UICONTROL 0 or 1 cardinality simple link]** e defina os campos a serem usados para reconciliação. Aqui usamos o sobrenome para reconciliar os dados com os perfis do banco de dados.

   ![](assets/load_file_enrichment_relation.png)

1. Na **[!UICONTROL Additional data]** guia, selecione os elementos que deseja usar no seu email. Aqui, selecione Número da conta (coluna do arquivo que você recuperou por meio da atividade do arquivo de carregamento).

   ![](assets/load_file_enrichment_select_element.png)

   <!--![](assets/load_file_enrichment_additional_data.png)-->

   For more on this, see the [Enrichment](../../automating/using/enrichment.md) section.

1. Arraste e solte uma atividade de [Segmentação](../../automating/using/segmentation.md) no fluxo de trabalho e abra-a para refinar o público alvo principal.

   ![](assets/load_file_segmentation.png)

   For more on this, see the [Segmentation](../../automating/using/segmentation.md) section.

1. Arraste e solte uma atividade de delivery [](../../automating/using/email-delivery.md) de e-mail em seu fluxo de trabalho e abra-a.

   <!--The Email delivery activity is presented in the [Email delivery](../../automating/using/email-delivery.md) section.-->

1. Adicione um campo de personalização e selecione os dados adicionais definidos na atividade do enriquecimento (aqui Número da conta) do **[!UICONTROL Additional data (targetData)]** nó. Isso permite recuperar dinamicamente o número de conta de cada perfil no conteúdo do email.

   ![](assets/load_file_perso_field.png)

1. Salve o e-mail e o start do fluxo de trabalho.

O email é enviado ao público alvo. Cada perfil recebe o e-mail com seu número de conta correspondente.

![](assets/load_file_email.png)
