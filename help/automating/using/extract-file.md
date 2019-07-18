---
title: Extrair arquivo
seo-title: Extrair arquivo
description: Extrair arquivo
seo-description: A atividade de arquivo Extrair permite exportar dados do Adobe Campaign na forma de um arquivo externo.
page-status-flag: nunca ativado
uuid: 631 f 0 fbd -9 e 8 d -4 f 77-a 338-fcb 7 f 4 fc 1774
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizando
content-type: reference
topic-tags: gerenciamento de dados-atividades
discoiquuid: a 06509 f 9-4731-4187-b 43 d -3 bfa 361284 d 3
context-tags: Fileexport, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e384a0cef325bc01eb5ea050b0f3d926aea9a88f

---


# Extract file{#extract-file}

## Description {#description}

![](assets/export.png)

The **[!UICONTROL Extract file]** activity allows you to export data from Adobe Campaign in the form of an external file.

## Context of use {#context-of-use}

A maneira como os dados serão extraídos é definida ao configurar a atividade.

>[!CAUTION]
>
>**[!UICONTROL Extract file]** A atividade deve ser colocada após uma **[!UICONTROL Query]** atividade para ser usada.

## Configuration {#configuration}

1. Drag and drop an **[!UICONTROL Extract file]** activity into your workflow.

   ![](assets/wkf_data_export1.png)

1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Enter the label of the **Output file**. A etiqueta do arquivo será concluída automaticamente com a data e a hora em que foi criada para que seja exclusiva. Por exemplo: recipients_20150815_081532.txt para um arquivo gerado em 15 de agosto de 2015 às 0.:1.:32.

   >[!NOTE]
   >
   >It is possible to use the **[!UICONTROL formatDate]** function in this field to specify the file name.

1. If you like, you can zip the output file by selecting **[!UICONTROL Compression]** in the **[!UICONTROL Add a pre-processing step]** field. O arquivo de saída será compactado em um arquivo GZIP (.gz).
1. Click the ![](assets/add_darkgrey-24px.png) or **[!UICONTROL Add an element]** button to add an output column.

   ![](assets/wkf_data_export2.png)

   Uma nova janela será aberta.

   ![](assets/wkf_data_export3.png)

1. Insira uma expressão. To do this, you can select an existing expression or create a new one using the **expression editor**.
1. Confirme sua expressão.

   A expressão é adicionada às colunas de saída.

1. Crie quantas colunas forem necessárias. É possível editar colunas clicando em suas expressões e etiquetas.

   Se você estiver exportando perfis e quiser usá-los em uma ferramenta externa, exporte um identificador único. Por padrão, nem todos os perfis têm um identificador exclusivo, dependendo da forma como são adicionados ao banco de dados. For more information, refer to the [Generating a unique ID for profiles](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources) section.

1. Click the **[!UICONTROL File structure]** tab to configure the output, date, and number formats for the file that will be exported.

   Check the **[!UICONTROL Export labels instead of internal values of enumerations]** option in case you export enumeration values. Essa opção permite recuperar rótulos mais curtos que são fáceis de entender em vez de IDs.

1. In the **[!UICONTROL Properties]** tab, select the **[!UICONTROL Do not generate a file if the inbound transition is empty]** option to avoid creating and uploading empty files on SFTP servers if the inbound transition is empty.
1. Confirme a configuração da atividade e salve seu fluxo de trabalho.

## Example {#example}

The following example illustrates how to configure an **[!UICONTROL Extract file]** activity after a **[!UICONTROL Query]** activity.

O objetivo deste fluxo de trabalho é exportar uma lista de perfis na forma de um arquivo externo para que os dados possam ser usados fora do Adobe Campaign.

1. Drag and drop an **[!UICONTROL Extract file]** activity into your workflow and place it after the **[!UICONTROL Query]** activity.

   Neste exemplo, a consulta é realizada em todos os perfis de aged 8 a 30.

1. Abra a atividade de arquivo Extrair para editá-la.
1. Nomeie o arquivo de saída.
1. Adicionar colunas de saída.

   Neste exemplo, o e-mail, idade, data de nascimento, nome e sobrenome dos perfis são adicionados como colunas de saída.

   ![](assets/wkf_data_export6.png)

1. Click the **[!UICONTROL File structure]** tab to define:

   * Formato de saída CSV

      ![](assets/wkf_data_export7.png)

   * Formato de data

      ![](assets/wkf_data_export9.png)

1. Confirme sua atividade.
1. Drag and drop a **[!UICONTROL Transfer file]** activity after the **[!UICONTROL Extract file]** activity to recover the extract file on an external account.
1. Open the activity and choose the **[!UICONTROL File upload]** action.

   ![](assets/wkf_data_export11.png)

1. Selecione a conta externa e digite o caminho da pasta no servidor.

   ![](assets/wkf_data_export12.png)

1. Confirme sua atividade e salve seu fluxo de trabalho.
1. Inicie o fluxo de trabalho.

   Quando o fluxo de trabalho é executado corretamente, o arquivo extraído fica disponível na conta externa.

