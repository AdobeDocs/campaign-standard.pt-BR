---
title: Atualização de dados usando reconciliação
description: O exemplo a seguir demonstra um fluxo de trabalho que cria um público-alvo de perfis diretamente de um arquivo importado que contém novos clientes.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: reconciliation,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: cfca6202-791d-4baf-b5ed-677d2480cf06
TQID: 'https://experienceleague.adobe.com/cEXfESw1LZcrQVlLsgrlDB8J2aGz4zCoSUrIAshECo0'
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
source-wordcount: '128'
ht-degree: 49%
---
# Atualização de dados usando reconciliação {#data-update-reconciliation}

O exemplo a seguir demonstra um fluxo de trabalho que cria um público-alvo de perfis diretamente de um arquivo importado que contém novos clientes. Ele é composto pelas seguintes atividades:

![](assets/identification_example2.png)

* Uma atividade [Load file](../../automating/using/load-file.md), que carrega e detecta os dados do arquivo a ser importado. O arquivo importado contém os seguintes dados:

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

* Uma atividade [Save audience](../../automating/using/save-audience.md), que salva o público-alvo dos perfis.

  ![](assets/identification_example3.png)
