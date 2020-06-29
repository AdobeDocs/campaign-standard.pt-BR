---
title: Atualização de dados com base em um download automático de arquivo
description: 'O exemplo a seguir mostra o resultado de uma atividade de arquivo de carregamento automaticamente baixada por meio de uma atividade de arquivo de transferência, seguido por uma atividade de dados de atualização. '
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
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 0%

---


# Atualização de dados com base em um download automático de arquivo {#updating-data-automatic-file-download}

A atividade load file estrutura principalmente os dados de uma atividade de arquivo de transferência para integrá-los aos dados existentes.

O exemplo a seguir mostra o resultado de uma atividade de arquivo de carregamento automaticamente baixada por meio de uma atividade de arquivo de transferência, seguido por uma atividade de dados de atualização. Esse fluxo de trabalho tem como objetivo aprimorar o banco de dados do Adobe Campaign com novos perfis ou atualizar perfis existentes usando os dados recuperados do arquivo importado.

![](assets/load_file_workflow_ex1.png)

Para criar o fluxo de trabalho, siga estas etapas:

1. Arraste e solte uma atividade de arquivo [de](../../automating/using/transfer-file.md) transferência no seu fluxo de trabalho.
1. Selecione a atividade e abra-a usando o ![](assets/edit_darkgrey-24px.png) botão das ações rápidas que aparecem.
1. Configure a atividade de uma forma que recupere o arquivo desejado. In the **[!UICONTROL Protocol]** tab, select **SFTP**.
1. Selecione **Usar parâmetros de conexão definidos em uma opção de conta externa** .
1. Digite o nome da conta externa.
1. Digite o caminho **Arquivo no servidor** remoto.

   ![](assets/wkf_file_transfer_07.png)

1. Confirme sua atividade.
1. Arraste e solte uma atividade [Carregar arquivo](../../automating/using/load-file.md) no fluxo de trabalho e coloque-a depois da **[!UICONTROL Transfer file]** atividade.
1. Selecione a atividade e abra-a usando o ![](assets/edit_darkgrey-24px.png) botão das ações rápidas que aparecem.
1. Na **[!UICONTROL File to load]** seção da **[!UICONTROL Execution]** guia, marque a **[!UICONTROL Use the file specified in the inbound transition]** opção.

   ![](assets/wkf_file_loading8.png)

1. Configure sua atividade conforme especificado anteriormente.
1. Arraste e solte uma atividade [Atualizar dados](../../automating/using/update-data.md) no seu fluxo de trabalho e coloque-a depois da **[!UICONTROL Load file]** atividade e configure-a.

Depois que o fluxo de trabalho é iniciado, os dados do arquivo carregado são extraídos e depois usados para enriquecer o banco de dados do Adobe Campaign.
