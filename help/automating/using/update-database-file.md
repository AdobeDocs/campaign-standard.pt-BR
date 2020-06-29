---
title: Atualização do banco de dados com dados externos
description: Este caso de uso apresenta como adicionar ou atualizar perfis ao banco de dados do Adobe Campaign com os dados recuperados do arquivo.
page-status-flag: never-activated
uuid: 1dc55db5-affd-4688-b673-adfb8c1338b5
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: 4db83c95-4b75-4a16-8dbf-bd8940431fa9
context-tags: writer,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 0%

---


# Atualização do banco de dados com dados externos {#update-database-file}

O exemplo a seguir mostra a configuração de uma **[!UICONTROL Update data]** atividade após uma **[!UICONTROL Load file]** atividade. O objetivo desse fluxo de trabalho é adicionar ou atualizar perfis ao banco de dados do Adobe Campaign com os dados recuperados do arquivo.

Neste exemplo, a chave de reconciliação usada é o endereço **de** email. O arquivo carregado na atividade [Carregar arquivo](../../automating/using/load-file.md) é um arquivo de formato **.txt** que contém os seguintes dados de exemplo:

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

A atividade de dados [](../../automating/using/update-data.md) Update é configurada da seguinte maneira:

![](assets/deduplication_example2_writer1.png)

![](assets/deduplication_example2_writer2.png)
