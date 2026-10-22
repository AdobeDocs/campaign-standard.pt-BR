---
title: Atualização de dados com base em um download automático de arquivo
description: O exemplo a seguir mostra o resultado de uma atividade de carregamento de arquivo baixada automaticamente por meio de uma atividade de transferência de arquivo, seguida por uma atividade de atualização de dados.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: fileImport,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 2b21cf45-1c40-4e0e-ae2c-28c9f73e1964
TQID: 'https://experienceleague.adobe.com/q-u5dH48a4wea1yStaF-QekcD9VaS2NjDhWnSQc6QGU'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
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
1. Configure a atividade de forma que ela recupere o arquivo desejado. Na guia **[!UICONTROL Protocol]**, selecione **SFTP**.
1. Selecione a opção **Use parâmetros de conexão definidos em uma conta externa**.
1. Insira o nome da conta externa.
1. Insira o **Caminho do arquivo no servidor remoto**.

   ![](assets/wkf_file_transfer_07.png)

1. Confirme sua atividade.
1. Arraste e solte uma atividade [Carregar arquivo](../../automating/using/load-file.md) no fluxo de trabalho e coloque-a depois da atividade **[!UICONTROL Transfer file]**.
1. Selecione e abra a atividade usando o botão ![](assets/edit_darkgrey-24px.png) das ações rápidas exibidas.
1. Na seção **[!UICONTROL File to load]** da guia **[!UICONTROL Execution]**, marque a opção **[!UICONTROL Use the file specified in the inbound transition]**.

   ![](assets/wkf_file_loading8.png)

1. Configure a atividade conforme especificado anteriormente.
1. Arraste e solte uma atividade [Atualizar dados](../../automating/using/update-data.md) no seu fluxo de trabalho, coloque-a depois da atividade **[!UICONTROL Load file]** e configure-a.

Depois que o fluxo de trabalho é iniciado, os dados do arquivo carregado são extraídos e depois usados para enriquecer o banco de dados do Adobe Campaign.
