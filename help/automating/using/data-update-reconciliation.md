---
solution: Campaign Standard
product: campaign
title: Atualização de dados usando reconciliação
description: O exemplo a seguir demonstra um fluxo de trabalho que cria um público-alvo de perfis diretamente de um arquivo importado que contém novos clientes.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: reconciliation,main
feature: Fluxos de trabalho
role: Arquiteto de dados
level: Intermediário
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 66%

---


# Atualização de dados usando reconciliação {#data-update-reconciliation}

O exemplo a seguir demonstra um fluxo de trabalho que cria um público-alvo de perfis diretamente de um arquivo importado que contém novos clientes. Ele é composto pelas seguintes atividades:

![](assets/identification_example2.png)

* Uma atividade [Load file](../../automating/using/load-file.md) , que carrega e detecta os dados do arquivo a ser importado. O arquivo importado contém os seguintes dados:

   ```
   lastname;firstname;email;dateofbirth
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

* Uma atividade [Reconciliation](../../automating/using/reconciliation.md), que vincula cada coluna do arquivo carregado a uma coluna de dimensão de perfil. Os registros de arquivo que não podem ser identificados (dados ausentes, tipos de dados incompatíveis etc.) são ignorados para preservar a integridade dos dados finais do público-alvo.

   ![](assets/identification_example1.png)

* Uma atividade [Save audience](../../automating/using/save-audience.md) , que salva o público-alvo dos perfis.

   ![](assets/identification_example3.png)
