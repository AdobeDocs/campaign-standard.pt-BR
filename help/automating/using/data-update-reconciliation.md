---
title: Atualização de dados usando reconciliação
description: O exemplo a seguir demonstra um fluxo de trabalho que cria uma audiência de perfis diretamente de um arquivo importado que contém novos clientes.
page-status-flag: never-activated
uuid: 7884db8c-1717-4724-be15-3b0b32ccc071
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: cb8c43f4-9cdd-4e85-99a4-004b36b336aa
context-tags: reconciliation,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 175709a41607bb9d64da7fac77dd749fa84f7360
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 0%

---


# Atualização de dados usando reconciliação {#data-update-reconciliation}

O exemplo a seguir demonstra um fluxo de trabalho que cria uma audiência de perfis diretamente de um arquivo importado que contém novos clientes. É composto pelas seguintes atividades:

![](assets/identification_example2.png)

* Uma atividade de arquivo [](../../automating/using/load-file.md) Load, que carrega e detecta os dados do arquivo a ser importado. O arquivo importado contém os seguintes dados:

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

* Uma atividade de [Reconciliação](../../automating/using/reconciliation.md) , que vincula cada coluna do arquivo carregado a uma coluna de dimensão de perfil. Os registros de arquivos que não podem ser identificados (dados ausentes, tipo de dados incompatível etc.) são ignorados para preservar a integridade dos dados de audiência finais.

   ![](assets/identification_example1.png)

* Uma atividade [Salvar audiência](../../automating/using/save-audience.md) , que salva a audiência dos perfis.

   ![](assets/identification_example3.png)
