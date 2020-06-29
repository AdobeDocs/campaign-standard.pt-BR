---
title: Assinatura de perfis de um arquivo para um serviço específico
description: Este caso de uso mostra como importar um arquivo contendo perfis e assiná-los em um serviço existente.
page-status-flag: never-activated
uuid: 56637024-15ab-4145-9c48-3fbd27ab8af8
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: 74a6df0e-fd85-4404-a42c-9a7406512717
context-tags: setOfService,workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 0%

---


# Assinatura de perfis para um serviço específico após a importação de um arquivo {#subscribing-profiles-to-a-specific-service-after-importing-a-file}

Este exemplo ilustra como importar um arquivo contendo perfis e assiná-los em um serviço existente. Após a importação do arquivo, é necessário realizar uma reconciliação para que os dados importados possam ser identificados como perfis. Para garantir que o arquivo não contenha nenhum duplicado, uma atividade desduplicação-duplicada será executada nos dados.

O fluxo de trabalho é apresentado da seguinte forma:

![](assets/subscription_activity_example1.png)

* Uma atividade de arquivo [](../../automating/using/load-file.md) Load carrega o arquivo de perfil e define a estrutura das colunas importadas.

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

* Uma atividade de [Reconciliação](../../automating/using/reconciliation.md) identifica os dados do arquivo como pertencendo à dimensão do perfil do banco de dados do Adobe Campaign. Somente a **[!UICONTROL Identification]** guia está configurada. Ela identifica os dados do arquivo de acordo com os endereços de email dos perfis.

   ![](assets/subscription_activity_example3.png)

* Um [Desduplicação-duplicado](../../automating/using/deduplication.md) com base no campo de **email** do recurso temporário (resultante da reconciliação) identifica quaisquer duplicados. Se os dados importados do arquivo contiverem duplicados, a subscrição para um serviço falhará para todos os dados.

   ![](assets/subscription_activity_example5.png)

* Uma atividade [Subscrição no serviço](../../automating/using/subscription-services.md) permite selecionar o serviço ao qual os perfis devem ser inscritos, o campo correspondente à data da subscrição e a origem da subscrição.

   ![](assets/subscription_activity_example4.png)
