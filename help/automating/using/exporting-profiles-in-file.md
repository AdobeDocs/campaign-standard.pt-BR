---
title: Exportação de perfis em um arquivo externo
description: Esse caso de uso mostra como exportar uma lista de perfis como um arquivo externo para que os dados possam ser usados fora do Adobe Campaign.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: fileExport,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 3fc286a9-bba4-4e3d-95cd-600eed4943e7
TQID: 'https://experienceleague.adobe.com/wVo-oDNJNFmaNcb7p6fACNIfrPG-2Y-VbXxXG0P8XTQ'
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
source-wordcount: '229'
ht-degree: 68%
---
# Exportação de perfis em um arquivo externo {#exporting-profiles-external-file}

O exemplo a seguir ilustra como configurar uma atividade **[!UICONTROL Extract file]** após uma atividade **[!UICONTROL Query]**.

O objetivo desse fluxo de trabalho é exportar uma lista de perfis como um arquivo externo para que os dados sejam usados fora do Adobe Campaign.

1. Arraste e solte uma atividade [Extrair arquivo](../../automating/using/extract-file.md) no seu fluxo de trabalho e coloque-a após a atividade [Consulta](../../automating/using/query.md).

   Neste exemplo, a consulta é realizada em todos os perfis entre 18 e 30 anos.

1. Abra a atividade **[!UICONTROL Extract file]** para editá-la.
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
1. Arraste e solte uma atividade [Transferir arquivo](../../automating/using/transfer-file.md) após a atividade **[!UICONTROL Extract file]** para recuperar o arquivo de extração em uma conta externa.
1. Abra a atividade e escolha a ação **[!UICONTROL File upload]**.

   ![](assets/wkf_data_export11.png)

1. Selecione a conta externa e insira o caminho da pasta no servidor.

   ![](assets/wkf_data_export12.png)

1. Confirme sua atividade e salve o fluxo de trabalho.
1. Inicie o fluxo de trabalho.

   Quando o fluxo de trabalho for executado corretamente, o arquivo extraído estará disponível na conta externa.
