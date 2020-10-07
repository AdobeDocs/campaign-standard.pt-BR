---
title: Exportar perfis em um arquivo externo
description: Este caso de uso mostra como exportar uma lista de perfis na forma de um arquivo externo para que os dados possam ser usados fora do Adobe Campaign.
page-status-flag: never-activated
uuid: 631f0fbd-9e8d-4f77-a338-fcb7f4fc1774
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: a06509f9-4731-4187-b43d-3bfa361284d3
context-tags: fileExport,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 68%

---


# Exportar perfis em um arquivo externo {#exporting-profiles-external-file}

O exemplo a seguir ilustra como configurar uma atividade **[!UICONTROL Extract file]** após uma atividade **[!UICONTROL Query]**.

O objetivo desse fluxo de trabalho é exportar uma lista de perfis como um arquivo externo para que os dados sejam usados fora do Adobe Campaign.

1. Drag and drop an [Extract file](../../automating/using/extract-file.md) activity into your workflow and place it after the [Query](../../automating/using/query.md) activity.

   Neste exemplo, o query é realizado em todos os perfis entre 18 e 30 anos.

1. Open the **[!UICONTROL Extract file]** activity to edit it.
1. Nomeie o arquivo de saída.
1. Adicione colunas de saída.

   Neste exemplo, o email, a idade, a data de nascimento, o nome e o sobrenome dos perfis são adicionados como colunas de saída.

   ![](assets/wkf_data_export6.png)

1. Clique na guia **[!UICONTROL File structure]** para definir:

   * O formato de saída CSV

      ![](assets/wkf_data_export7.png)

   * O formato de data

      ![](assets/wkf_data_export9.png)

1. Confirme sua atividade.
1. Drag and drop a [Transfer file](../../automating/using/transfer-file.md) activity after the **[!UICONTROL Extract file]** activity to recover the extract file on an external account.
1. Abra a atividade e escolha a ação **[!UICONTROL File upload]**.

   ![](assets/wkf_data_export11.png)

1. Selecione a conta externa e insira o caminho da pasta no servidor.

   ![](assets/wkf_data_export12.png)

1. Confirme sua atividade e salve o fluxo de trabalho.
1. Inicie o fluxo de trabalho.

   Quando o fluxo de trabalho for executado corretamente, o arquivo extraído estará disponível na conta externa.
