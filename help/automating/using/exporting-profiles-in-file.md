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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 2%

---


# Exportar perfis em um arquivo externo {#exporting-profiles-external-file}

O exemplo a seguir ilustra como configurar uma **[!UICONTROL Extract file]** atividade após uma **[!UICONTROL Query]** atividade.

O objetivo desse fluxo de trabalho é exportar uma lista de perfis na forma de um arquivo externo para que os dados possam ser usados fora do Adobe Campaign.

1. Arraste e solte uma atividade de arquivo [](../../automating/using/extract-file.md) Extract (Extrair) no fluxo de trabalho e coloque-a depois da atividade do [Query](../../automating/using/query.md) .

   Neste exemplo, o query é realizado em todos os perfis com idade entre 18 e 30 anos.

1. Abra a **[!UICONTROL Extract file]** atividade para editá-la.
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
1. Arraste e solte uma atividade [Transferir arquivo](../../automating/using/transfer-file.md) após a **[!UICONTROL Extract file]** atividade para recuperar o arquivo de extração em uma conta externa.
1. Abra a atividade e escolha a **[!UICONTROL File upload]** ação.

   ![](assets/wkf_data_export11.png)

1. Selecione a conta externa e insira o caminho da pasta no servidor.

   ![](assets/wkf_data_export12.png)

1. Confirme sua atividade e salve seu fluxo de trabalho.
1. Inicie o workflow.

   Quando o fluxo de trabalho for executado corretamente, o arquivo extraído estará disponível na conta externa.
