---
solution: Campaign Standard
product: campaign
title: Assinatura de perfis para um serviço específico a partir de um arquivo
description: Este caso de uso mostra como importar um arquivo contendo perfis e assiná-los a um serviço existente.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: setOfService,workflow,main
feature: Workflows
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 52%

---


# Assinatura de perfis para um serviço específico após importar um arquivo {#subscribing-profiles-to-a-specific-service-after-importing-a-file}

Este exemplo ilustra como importar um arquivo contendo perfis e fazer a assinatura de todos eles para um serviço existente. Após a importação do arquivo, é necessário fazer uma reconciliação para que os dados importados possam ser identificados como perfis. Para garantir que o arquivo não contenha nenhuma duplicata, uma atividade de desduplicação é executada nos dados.

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

* Uma atividade [Reconciliation](../../automating/using/reconciliation.md) identifica os dados do arquivo como pertencente à dimensão de perfil do banco de dados do Adobe Campaign. Somente a guia **[!UICONTROL Identification]** está configurada. Ela identifica os dados do arquivo de acordo com os endereços de email dos perfis.

   ![](assets/subscription_activity_example3.png)

* Uma [Desduplicação](../../automating/using/deduplication.md) com base no campo **email** do recurso temporário (resultante da reconciliação) identifica duplicatas. Se os dados importados do arquivo tiverem duplicatas, a assinatura para um serviço falhará para todos os dados.

   ![](assets/subscription_activity_example5.png)

* Uma atividade [Subscription Services](../../automating/using/subscription-services.md) permite selecionar o serviço ao qual os perfis devem ser subscritos, o campo correspondente à data da assinatura e a origem da assinatura.

   ![](assets/subscription_activity_example4.png)
