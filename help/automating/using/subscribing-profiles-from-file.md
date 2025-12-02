---
title: Subscrição de perfis para um serviço específico a partir de um arquivo
description: Este caso de uso mostra como importar um arquivo contendo perfis e fazer a assinatura de todos eles para um serviço existente.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: setOfService,workflow,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 06ae4a5c-f112-4aac-b776-437ac35a8f02
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 53%

---

# Assinatura de perfis para um serviço específico após a importação de um arquivo {#subscribing-profiles-to-a-specific-service-after-importing-a-file}

Este exemplo ilustra como importar um arquivo contendo perfis e fazer a assinatura de todos eles para um serviço existente. Após a importação do arquivo, é necessário fazer uma reconciliação para que os dados importados possam ser identificados como perfis. Para garantir que o arquivo não contenha nenhum duplicado, uma atividade de desduplicação é executada nos dados.

O fluxo de trabalho é apresentado da seguinte forma:

![](assets/subscription_activity_example1.png)

* Uma atividade [Load file](../../automating/using/load-file.md) carrega o arquivo de perfil e define a estrutura das colunas importadas.

  Neste exemplo, o arquivo carregado está no formato .csv e contém os seguintes dados:

  ```
  lastname;firstname;email;birthdate;subdate
  jackman;megan;megan.jackman@testmail.com;07/08/1975;10/08/2017
  phillips;edward;phillips@testmail.com;09/03/1986;10/08/2017
  weaver;justin;justin_w@testmail.com;11/15/1990;10/08/2017
  martin;babeth;babeth_martin@testmail.net;11/25/1964;10/08/2017
  reese;richard;rreese@testmail.com;02/08/1987;11/08/2017
  cage;nathalie;cage.nathalie227@testmail.com;07/03/1989;11/08/2017
  xiuxiu;andrea;andrea.xiuxiu@testmail.com;09/12/1992;11/08/2017
  grimes;daryl;daryl_890@testmail.com;12/06/1979;12/08/2017
  tycoon;tyreese;tyreese_t@testmail.net;10/08/1971;12/08/2017
  ```

  ![](assets/subscription_activity_example2.png)

* Uma atividade [Reconciliation](../../automating/using/reconciliation.md) identifica os dados do arquivo como pertencente à dimensão do perfil do banco de dados do Adobe Campaign. Somente a guia **[!UICONTROL Identification]** está configurada. Ela identifica os dados do arquivo de acordo com os endereços de email dos perfis.

  ![](assets/subscription_activity_example3.png)

* Uma [Eliminação de Duplicação](../../automating/using/deduplication.md) baseada no campo **email** do recurso temporário (resultante da reconciliação) identifica duplicatas. Se os dados importados do arquivo tiverem duplicados, a assinatura para um serviço falhará para todos os dados.

  ![](assets/subscription_activity_example5.png)

* Uma atividade de [Serviços de assinatura](../../automating/using/subscription-services.md) permite selecionar o serviço para o qual os perfis devem ser assinados, o campo correspondente à data da assinatura e a origem da assinatura.

  ![](assets/subscription_activity_example4.png)
