---
title: Atualização do banco de dados com dados externos
description: Esse caso de uso apresenta como adicionar ou atualizar perfis ao banco de dados do Adobe Campaign com os dados recuperados do arquivo.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: writer,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 2df7fbed-b979-4706-bd56-83f712cc3070
TQID: 'https://experienceleague.adobe.com/XLH6Hrqg2q-ZNlT-ZcNNlLlvP9xBSchfZs-mgWscROs'
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
source-wordcount: '106'
ht-degree: 11%
---
# Atualização do banco de dados com dados externos {#update-database-file}

O exemplo a seguir mostra a configuração de uma atividade **[!UICONTROL Update data]** após uma atividade **[!UICONTROL Load file]**. O objetivo desse fluxo de trabalho é adicionar ou atualizar perfis ao banco de dados do Adobe Campaign com os dados recuperados do arquivo.

Neste exemplo, a chave de reconciliação usada é o **endereço de email**. O arquivo carregado na atividade [Carregar arquivo](../../automating/using/load-file.md) é um arquivo de formato **.txt** que contém os seguintes dados de exemplo:

```
lastname;firstname;email;birthdate
jackman;megan;megan.jackman@testmail.com;07/08/1975
phillips;edward;phillips@testmail.com;09/03/1986
weaver;justin;justin_w@testmail.com;11/15/1990
martin;babeth;babeth_martin@testmail.net;11/25/1964
reese;richard;rreese@testmail.com;02/08/1987
cage;nathalie;cage.nathalie227@testmail.com;07/03/1989
xiuxiu;andrea;andrea.xiuxiu@testmail.com;09/12/1992
grimes;daryl;daryl_890@testmail.com;12/06/1979
tycoon;tyreese;tyreese_t@testmail.net;10/08/1971
```

A atividade [Atualizar dados](../../automating/using/update-data.md) está configurada da seguinte maneira:

![](assets/deduplication_example2_writer1.png)

![](assets/deduplication_example2_writer2.png)
