---
title: Atualização de dados com base em um download automático de arquivo
description: O exemplo a seguir mostra o resultado de uma atividade de carregamento de arquivo baixada automaticamente por meio de uma atividade de transferência de arquivo, seguida por uma atividade de atualização de dados.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: fileImport,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 2b21cf45-1c40-4e0e-ae2c-28c9f73e1964
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 79%

---

# Atualização de dados com base em um download automático de arquivo {#updating-data-automatic-file-download}

A atividade de carregamento de arquivo estrutura principalmente os dados de uma atividade de transferência de arquivo para integrá-los aos dados existentes.

O exemplo a seguir mostra o resultado de uma atividade de carregamento de arquivo baixada automaticamente por meio de uma atividade de transferência de arquivo, seguida por uma atividade de atualização de dados. Esse fluxo de trabalho tem como objetivo enriquecer o banco de dados do Adobe Campaign com novos perfis ou atualizar os perfis existentes usando os dados recuperados do arquivo importado.

![](assets/load_file_workflow_ex1.png)

Para criar o workflow, siga estas etapas:

1. Arraste e solte uma atividade [Transfer file](../../automating/using/transfer-file.md) no seu fluxo de trabalho.
1. Selecione e abra a atividade usando o botão ![](assets/edit_darkgrey-24px.png) das ações rápidas exibidas.
1. Configure a atividade de uma maneira que ela recupere o arquivo desejado. Na guia **[!UICONTROL Protocol]**, selecione **SFTP**.
1. Selecione a opção **Use parâmetros de conexão definidos em uma conta externa**.
1. Insira o nome da conta externa.
1. Insira o **Caminho do arquivo no servidor remoto**.

   ![](assets/wkf_file_transfer_07.png)

1. Confirme sua atividade.
1. Arraste e solte uma [Carregar arquivo](../../automating/using/load-file.md) atividade no seu fluxo de trabalho e coloque-a depois da variável **[!UICONTROL Transfer file]** atividade .
1. Selecione e abra a atividade usando o botão ![](assets/edit_darkgrey-24px.png) das ações rápidas exibidas.
1. Na seção **[!UICONTROL File to load]** da guia **[!UICONTROL Execution]**, marque a opção **[!UICONTROL Use the file specified in the inbound transition]**.

   ![](assets/wkf_file_loading8.png)

1. Configure a atividade conforme especificado anteriormente.
1. Arraste e solte um [Atualizar dados](../../automating/using/update-data.md) atividade no seu fluxo de trabalho e coloque-a depois da variável **[!UICONTROL Load file]** , em seguida, configure-a.

Depois que o fluxo de trabalho é iniciado, os dados do arquivo carregado são extraídos e depois usados para enriquecer o banco de dados do Adobe Campaign.
