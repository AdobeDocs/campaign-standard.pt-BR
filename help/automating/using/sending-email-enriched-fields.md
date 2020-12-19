---
solution: Campaign Standard
product: campaign
title: Envio de email com campos enriquecidos
description: O exemplo abaixo mostra como enviar um email usando dados adicionais recuperados de um arquivo externo por meio da atividade de carregamento de arquivo.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: fileImport,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 75%

---


# Envio de email com campos enriquecidos {#sending-email-enriched-fields}

<!--A new example showing how to send an email containing additional data retrieved from a load file activity has been added. [Read more](example-2-email-with-enriched-fields)-->

A atividade de carregamento de arquivo também permite enviar um email enriquecido com dados adicionais de um arquivo externo no mesmo fluxo de trabalho.

O exemplo abaixo mostra como enviar um email usando dados adicionais recuperados de um arquivo externo por meio da atividade de carregamento de arquivo. No exemplo, o arquivo externo contém uma lista de perfis e os números de conta associados. Você deseja importar esses dados para enviar um email a cada perfil com o número da conta.

![](assets/load_file_workflow_ex2.png)

Para criar o fluxo de trabalho, siga estas etapas:

1. Arraste e solte uma atividade [Query](../../automating/using/query.md) no seu fluxo de trabalho e abra-a para definir o público alvo principal.

   <!--The Query activity is presented in the [Query](../../automating/using/query.md) section.-->

1. Arraste e solte uma atividade [Carregar arquivo](../../automating/using/load-file.md) para atribuir alguns dados a um perfil. No exemplo, carregue um arquivo com os números de conta correspondentes a alguns perfis do banco de dados.

   ![](assets/load_file_activity.png)

1. Arraste e solte uma atividade [Enriquecimento](../../automating/using/enrichment.md) no seu fluxo de trabalho e vincule o arquivo de carregamento e as atividades do query a ele.

1. Na guia **[!UICONTROL Advanced relations]** da atividade de enriquecimento, selecione o **[!UICONTROL 0 or 1 cardinality simple link]** e defina os campos que serão usados para reconciliação. Aqui usamos o sobrenome para reconciliar os dados com os perfis do banco de dados.

   ![](assets/load_file_enrichment_relation.png)

1. Na guia **[!UICONTROL Additional data]**, selecione os elementos que deseja usar no email. Aqui, selecione Account number (coluna do arquivo que você recuperou por meio da atividade de carregamento de arquivo).

   ![](assets/load_file_enrichment_select_element.png)

   <!--![](assets/load_file_enrichment_additional_data.png)-->

   Para saber mais, consulte a seção [Enriquecimento](../../automating/using/enrichment.md).

1. Arraste e solte uma atividade [Segmentation](../../automating/using/segmentation.md) no seu fluxo de trabalho e abra-a para refinar o público alvo principal.

   ![](assets/load_file_segmentation.png)

   Para saber mais, consulte a seção [Segmentação](../../automating/using/segmentation.md).

1. Arraste e solte uma atividade [delivery de e-mail](../../automating/using/email-delivery.md) no seu fluxo de trabalho e abra-a.

   <!--The Email delivery activity is presented in the [Email delivery](../../automating/using/email-delivery.md) section.-->

1. Adicione um campo de personalização e selecione os dados adicionais definidos na atividade de enriquecimento (aqui é Account number) do nó **[!UICONTROL Additional data (targetData)]**. Assim, é possível recuperar dinamicamente o número de conta de cada perfil no conteúdo do email.

   ![](assets/load_file_perso_field.png)

1. Salve o email e inicie o fluxo de trabalho.

O email é enviado para o público-alvo. Cada perfil recebe o email com o número de conta correspondente.

![](assets/load_file_email.png)
