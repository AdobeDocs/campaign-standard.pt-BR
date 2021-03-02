---
solution: Campaign Standard
product: campaign
title: Extrair arquivo
description: A atividade Extract file permite exportar dados do Adobe Campaign como um arquivo externo.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: fileExport,main
translation-type: tm+mt
source-git-commit: c29eff0d241cd561a7e609ab44222700e2a8868d
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 89%

---


# Extrair arquivo{#extract-file}

## Descrição {#description}

![](assets/export.png)

A atividade **[!UICONTROL Extract file]** permite exportar dados do Adobe Campaign como um arquivo externo.

## Contexto de uso {#context-of-use}

O modo como os dados serão extraídos é definido na configuração da atividade.

>[!CAUTION]
>
>A atividade **[!UICONTROL Extract file]** deve ser colocada após uma atividade **[!UICONTROL Query]** para ser usada.

**Tópicos relacionados:**

* [Caso de uso: Exportar perfis em um arquivo externo](../../automating/using/exporting-profiles-in-file.md)

## Configuração {#configuration}

1. Arraste e solte uma atividade **[!UICONTROL Extract file]** no seu workflow.

   ![](assets/wkf_data_export1.png)

1. Selecione e abra a atividade usando o botão ![](assets/edit_darkgrey-24px.png) das ações rápidas exibidas.
1. Insira o rótulo do **arquivo de saída**. O rótulo do arquivo será automaticamente preenchido com a data e hora de criação para ser exclusivo. Por exemplo: recipient_20150815_081532.txt para um arquivo gerado no dia 15 de agosto de 2015 às 08:15:32.

   >[!NOTE]
   >
   >É possível usar a função **[!UICONTROL formatDate]** neste campo para especificar o nome do arquivo.

1. Se desejar, você pode compactar o arquivo de saída selecionando **[!UICONTROL Compression]** no campo **[!UICONTROL Add a post-processing stage]**. O arquivo de saída será compactado em um arquivo GZIP (.gz).

   O campo **[!UICONTROL Add a post-processing stage]** também permite criptografar um arquivo antes de extraí-lo. Para obter mais informações sobre como trabalhar com arquivos criptografados, consulte [esta seção](../../automating/using/managing-encrypted-data.md)

1. Clique no botão **[!UICONTROL Create element]** para adicionar uma coluna de saída.

   ![](assets/wkf_data_export2.png)

   Uma nova janela será aberta.

   ![](assets/wkf_data_export3.png)

1. Insira uma expressão. Para isso, selecione uma expressão ou crie uma nova usando o **editor de expressão**.
1. Confirme a expressão.

   A expressão é adicionada às colunas de saída.

1. Crie quantas colunas forem necessárias. Você pode editar as colunas clicando nas expressões e nos rótulos.

   Se estiver exportando perfis e quiser usá-los em uma ferramenta externa, exporte um identificador exclusivo. Por padrão, nem todos os perfis têm um identificador exclusivo, dependendo de como são adicionados ao banco de dados. Para saber mais, consulte a seção [Geração de uma ID exclusiva para perfis](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources).

1. Clique na guia **[!UICONTROL File structure]** para configurar os formatos de saída, data e número para o arquivo que será exportado.

   Marque a opção **[!UICONTROL Export labels instead of internal values of enumerations]** caso exporte valores de uma lista discriminada. Essa opção permite recuperar rótulos mais curtos, que são fáceis de entender, em vez de IDs.

1. Na guia **[!UICONTROL Properties]**, selecione a opção **[!UICONTROL Do not generate a file if the inbound transition is empty]** para evitar a criação e o upload de arquivos vazios em servidores SFTP se a transição de entrada estiver vazia.
1. Confirme a configuração da sua atividade e salve o fluxo de trabalho.
