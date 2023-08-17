---
title: Exportação de perfis em um arquivo externo
description: Esse caso de uso mostra como exportar uma lista de perfis como um arquivo externo para que os dados possam ser usados fora do Adobe Campaign.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: fileExport,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 3fc286a9-bba4-4e3d-95cd-600eed4943e7
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 68%

---

# Exportação de perfis em um arquivo externo {#exporting-profiles-external-file}

O exemplo a seguir ilustra como configurar uma atividade **[!UICONTROL Extract file]** após uma atividade **[!UICONTROL Query]**.

O objetivo desse fluxo de trabalho é exportar uma lista de perfis como um arquivo externo para que os dados sejam usados fora do Adobe Campaign.

1. Arraste e solte um [Extrair arquivo](../../automating/using/extract-file.md) atividade no seu fluxo de trabalho e coloque-a depois da variável [Query](../../automating/using/query.md) atividade.

   Neste exemplo, o query é realizado em todos os perfis entre 18 e 30 anos.

1. Abra o **[!UICONTROL Extract file]** atividade para editá-la.
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
1. Arraste e solte uma [Transferir arquivo](../../automating/using/transfer-file.md) atividade após o **[!UICONTROL Extract file]** atividade para recuperar o arquivo de extração em uma conta externa.
1. Abra a atividade e escolha a ação **[!UICONTROL File upload]**.

   ![](assets/wkf_data_export11.png)

1. Selecione a conta externa e insira o caminho da pasta no servidor.

   ![](assets/wkf_data_export12.png)

1. Confirme sua atividade e salve o fluxo de trabalho.
1. Inicie o fluxo de trabalho.

   Quando o fluxo de trabalho for executado corretamente, o arquivo extraído estará disponível na conta externa.
