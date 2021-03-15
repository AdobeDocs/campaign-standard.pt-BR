---
solution: Campaign Standard
product: campaign
title: Atualização do banco de dados com dados externos
description: Este caso de uso apresenta como adicionar ou atualizar perfis ao banco de dados do Adobe Campaign com os dados recuperados do arquivo.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: writer,main
feature: Fluxos de trabalho
role: Arquiteto de dados
level: Intermediário
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 32%

---


# Atualização do banco de dados com dados externos {#update-database-file}

O exemplo a seguir mostra a configuração de uma atividade **[!UICONTROL Update data]** após uma atividade **[!UICONTROL Load file]** . O objetivo desse fluxo de trabalho é adicionar ou atualizar perfis ao banco de dados do Adobe Campaign com os dados recuperados do arquivo.

Neste exemplo, a chave de reconciliação usada é o **endereço de email**. O arquivo carregado na atividade [Load file](../../automating/using/load-file.md) é um arquivo de formato **.txt** contendo os seguintes exemplos de dados:

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

A atividade [Update data](../../automating/using/update-data.md) é configurada da seguinte maneira:

![](assets/deduplication_example2_writer1.png)

![](assets/deduplication_example2_writer2.png)
