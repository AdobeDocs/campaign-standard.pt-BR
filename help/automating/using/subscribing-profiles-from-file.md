---
solution: Campaign Standard
product: campaign
title: Assinatura de perfis para um serviço específico a partir de um arquivo
description: Este caso de uso mostra como importar um arquivo contendo perfis e assiná-los em um serviço existente.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: setOfService,workflow,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 53%

---


# Inscrever perfis em um serviço específico após importar um arquivo {#subscribing-profiles-to-a-specific-service-after-importing-a-file}

Este exemplo ilustra como importar um arquivo contendo perfis e fazer a assinatura de todos eles para um serviço existente. Após a importação do arquivo, é necessário fazer uma reconciliação para que os dados importados possam ser identificados como perfis. Para garantir que o arquivo não contenha nenhuma duplicata, uma atividade de desduplicação é executada nos dados.

O fluxo de trabalho é apresentado da seguinte forma:

![](assets/subscription_activity_example1.png)

* Uma atividade [Carregar arquivo](../../automating/using/load-file.md) carrega o arquivo de perfil e define a estrutura das colunas importadas.

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

* Uma atividade [Reconciliation](../../automating/using/reconciliation.md) identifica os dados do arquivo como pertencendo à dimensão do perfil do banco de dados Adobe Campaign. Somente a guia **[!UICONTROL Identification]** está configurada. Ela identifica os dados do arquivo de acordo com os endereços de email dos perfis.

   ![](assets/subscription_activity_example3.png)

* Um [Desduplicação-duplicado](../../automating/using/deduplication.md) baseado no campo **email** do recurso temporário (resultante da reconciliação) identifica quaisquer duplicados. Se os dados importados do arquivo tiverem duplicatas, a assinatura para um serviço falhará para todos os dados.

   ![](assets/subscription_activity_example5.png)

* Uma atividade [Subscrição no serviço](../../automating/using/subscription-services.md) permite selecionar o serviço ao qual os perfis devem ser inscritos, o campo correspondente à data da subscrição e a origem da subscrição.

   ![](assets/subscription_activity_example4.png)
