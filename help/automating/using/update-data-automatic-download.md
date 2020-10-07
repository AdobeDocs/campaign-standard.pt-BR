---
title: Atualização de dados com base em um download automático de arquivo
description: 'O exemplo a seguir mostra o resultado de uma atividade de carregamento de arquivo baixada automaticamente por meio de uma atividade de transferência de arquivo, seguida por uma atividade de atualização de dados. '
page-status-flag: never-activated
uuid: 69af12cc-6f82-4977-9f53-aa7bc26f5d7e
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: 584ff893-9b1b-46c9-9628-714ab349ab88
context-tags: fileImport,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 79%

---


# Atualização de dados com base em um download automático de arquivo {#updating-data-automatic-file-download}

A atividade de carregamento de arquivo estrutura principalmente os dados de uma atividade de transferência de arquivo para integrá-los aos dados existentes.

O exemplo a seguir mostra o resultado de uma atividade de carregamento de arquivo baixada automaticamente por meio de uma atividade de transferência de arquivo, seguida por uma atividade de atualização de dados. Esse fluxo de trabalho tem como objetivo enriquecer o banco de dados do Adobe Campaign com novos perfis ou atualizar os perfis existentes usando os dados recuperados do arquivo importado.

![](assets/load_file_workflow_ex1.png)

Para criar o fluxo de trabalho, siga estas etapas:

1. Arraste e solte uma atividade [Transfer file](../../automating/using/transfer-file.md) no seu fluxo de trabalho.
1. Selecione e abra a atividade usando o botão ![](assets/edit_darkgrey-24px.png) das ações rápidas exibidas.
1. Configure a atividade de uma forma que recupere o arquivo desejado. Na guia **[!UICONTROL Protocol]**, selecione **SFTP**.
1. Selecione a opção **Use parâmetros de conexão definidos em uma conta externa**.
1. Insira o nome da conta externa.
1. Insira o **Caminho do arquivo no servidor remoto**.

   ![](assets/wkf_file_transfer_07.png)

1. Confirme sua atividade.
1. Drag and drop a [Load file](../../automating/using/load-file.md) activity into your workflow and place it after the **[!UICONTROL Transfer file]** activity.
1. Selecione e abra a atividade usando o botão ![](assets/edit_darkgrey-24px.png) das ações rápidas exibidas.
1. Na seção **[!UICONTROL File to load]** da guia **[!UICONTROL Execution]**, marque a opção **[!UICONTROL Use the file specified in the inbound transition]**.

   ![](assets/wkf_file_loading8.png)

1. Configure a atividade conforme especificado anteriormente.
1. Drag and drop an [Update data](../../automating/using/update-data.md) activity into your workflow and place it after the **[!UICONTROL Load file]** activity, then configure it.

Depois que o fluxo de trabalho é iniciado, os dados do arquivo carregado são extraídos e depois usados para enriquecer o banco de dados do Adobe Campaign.
