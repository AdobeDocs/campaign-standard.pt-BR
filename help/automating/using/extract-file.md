---
title: Extrair arquivo
description: A atividade Extract file permite exportar dados do Adobe Campaign na forma de um arquivo externo.
page-status-flag: never-activated
uuid: 631f0fbd-9e8d-4f77-a338-fcb7f4fc1774
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: a06509f9-4731-4187-b43d-3bfa361284d3
context-tags: fileExport,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2a8cb9aa0d018fec9d5b256beba079c5ec3afaf0
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 2%

---


# Extrair arquivo{#extract-file}

## Descrição {#description}

![](assets/export.png)

A **[!UICONTROL Extract file]** atividade permite exportar dados do Adobe Campaign na forma de um arquivo externo.

## Contexto de utilização {#context-of-use}

A forma como os dados serão extraídos é definida ao configurar a atividade.

>[!CAUTION]
>
>A **[!UICONTROL Extract file]** atividade deve ser colocada após uma **[!UICONTROL Query]** atividade para ser usada.

## Configuração {#configuration}

1. Arraste e solte uma **[!UICONTROL Extract file]** atividade no seu fluxo de trabalho.

   ![](assets/wkf_data_export1.png)

1. Selecione a atividade e abra-a usando o ![](assets/edit_darkgrey-24px.png) botão das ações rápidas que aparecem.
1. Insira o rótulo do arquivo **** de Saída. O rótulo do arquivo será automaticamente preenchido com a data e a hora em que foi criado para que seja exclusivo. Por exemplo: recipient_20150815_081532.txt para um arquivo gerou o dia 15 de agosto de 2015 às 08:15:32.

   >[!NOTE]
   >
   >É possível usar a **[!UICONTROL formatDate]** função neste campo para especificar o nome do arquivo.

1. Se desejar, você pode compactar o arquivo de saída selecionando-o **[!UICONTROL Compression]** no **[!UICONTROL Add a pre-processing step]** campo. O arquivo de saída será compactado em um arquivo GZIP (.gz).

   O **[!UICONTROL Add a pre-processing step]** campo também permite criptografar um arquivo antes de extraí-lo. Para obter mais informações sobre como trabalhar com arquivos criptografados, consulte [esta seção](../../automating/using/managing-encrypted-data.md)

1. Clique no botão ![](assets/add_darkgrey-24px.png) ou **[!UICONTROL Add an element]** para adicionar uma coluna de saída.

   ![](assets/wkf_data_export2.png)

   Uma nova janela será aberta.

   ![](assets/wkf_data_export3.png)

1. Insira uma expressão. Para fazer isso, você pode selecionar uma expressão existente ou criar uma nova usando o editor **de** expressões.
1. Confirme sua expressão.

   A expressão é adicionada às colunas de saída.

1. Crie quantas colunas forem necessárias. É possível editar colunas clicando em suas expressões e rótulos.

   Se você estiver exportando perfis e quiser usá-los em uma ferramenta externa, certifique-se de exportar um identificador exclusivo. Por padrão, nem todos os perfis têm um identificador exclusivo, dependendo da forma como são adicionados ao banco de dados. Para obter mais informações, consulte a seção [Geração de uma ID exclusiva para perfis](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources) .

1. Clique na **[!UICONTROL File structure]** guia para configurar os formatos de saída, data e número para o arquivo que será exportado.

   Marque a **[!UICONTROL Export labels instead of internal values of enumerations]** opção caso você exporte valores de lista discriminada. Essa opção permite recuperar rótulos mais curtos, fáceis de entender em vez de IDs.

1. Na **[!UICONTROL Properties]** guia, selecione a **[!UICONTROL Do not generate a file if the inbound transition is empty]** opção para evitar a criação e o upload de arquivos vazios em servidores SFTP se a transição de entrada estiver vazia.
1. Confirme a configuração da atividade e salve o fluxo de trabalho.

## Exemplo {#example}

O exemplo a seguir ilustra como configurar uma **[!UICONTROL Extract file]** atividade após uma **[!UICONTROL Query]** atividade.

O objetivo desse fluxo de trabalho é exportar uma lista de perfis na forma de um arquivo externo para que os dados possam ser usados fora do Adobe Campaign.

1. Arraste e solte uma **[!UICONTROL Extract file]** atividade no seu fluxo de trabalho e coloque-a depois da **[!UICONTROL Query]** atividade.

   Neste exemplo, o query é realizado em todos os perfis com idade entre 18 e 30 anos.

1. Abra a atividade Extrair arquivo para editá-la.
1. Nomeie o arquivo de saída.
1. Adicionar colunas de saída.

   Neste exemplo, o email, a idade, a data de nascimento, o nome e o sobrenome dos perfis são adicionados como colunas de saída.

   ![](assets/wkf_data_export6.png)

1. Clique na **[!UICONTROL File structure]** guia para definir:

   * Formato de saída CSV

      ![](assets/wkf_data_export7.png)

   * Formato de data

      ![](assets/wkf_data_export9.png)

1. Confirme sua atividade.
1. Arraste e solte uma **[!UICONTROL Transfer file]** atividade após a **[!UICONTROL Extract file]** atividade para recuperar o arquivo de extração em uma conta externa.
1. Abra a atividade e escolha a **[!UICONTROL File upload]** ação.

   ![](assets/wkf_data_export11.png)

1. Selecione a conta externa e insira o caminho da pasta no servidor.

   ![](assets/wkf_data_export12.png)

1. Confirme sua atividade e salve seu fluxo de trabalho.
1. Inicie o workflow.

   Quando o fluxo de trabalho for executado corretamente, o arquivo extraído estará disponível na conta externa.

