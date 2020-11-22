---
solution: Campaign Standard
product: campaign
title: Atualização de vários status de assinatura diretamente de um arquivo
description: Este caso de uso mostra como importar um arquivo contendo perfis e atualizar sua subscrição para vários serviços especificados no arquivo.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: setOfService,workflow,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 76%

---


# Atualização de vários status de assinatura diretamente de um arquivo {#updating-multiple-subscription-statuses-from-a-file}

Este exemplo ilustra como importar um arquivo contendo perfis e atualizar sua assinatura para vários serviços especificados no arquivo. Após a importação do arquivo, é necessário fazer uma reconciliação para que os dados importados possam ser identificados como perfis com um link para os serviços. Para garantir que o arquivo não contenha nenhuma duplicata, uma atividade de desduplicação é executada nos dados.

O fluxo de trabalho é apresentado da seguinte forma:

![](assets/subscription_activity_example1.png)

* A [Load file](../../automating/using/load-file.md) activity loads the profile file and defines the structure of the imported columns.

   Neste exemplo, o arquivo carregado está no formato .csv e contém os seguintes dados:

   ```
   lastname;firstname;email;birthdate;service;operation
   jackman;megan;megan.jackman@testmail.com;07/08/1975;SVC2;sub
   phillips;edward;phillips@testmail.com;09/03/1986;SVC3;unsub
   weaver;justin;justin_w@testmail.com;11/15/1990;SVC3;sub
   martin;babeth;babeth_martin@testmail.net;11/25/1964;SVC3;unsub
   reese;richard;rreese@testmail.com;02/08/1987;SVC3;sub
   cage;nathalie;cage.nathalie227@testmail.com;07/03/1989;SVC3;sub
   xiuxiu;andrea;andrea.xiuxiu@testmail.com;09/12/1992;SVC4;sub
   grimes;daryl;daryl_890@testmail.com;12/06/1979;SVC3;unsub
   tycoon;tyreese;tyreese_t@testmail.net;10/08/1971;SVC2;sub
   ```

   ![](assets/subscription_example_load_file.png)

   Como você pode ter notado, a operação é especificada no arquivo como &quot;sub&quot; ou &quot;unsub&quot;. O sistema espera que um valor **Booliano** ou **Integer** reconheça a operação a ser executada: &quot;0&quot; para cancelar a assinatura e &quot;1&quot; para assinar. Para corresponder a esse requisito, um remapeamento de valores é executado no detalhe da coluna &quot;operação&quot;.

   ![](assets/subscription_example_remapping.png)

   Se o arquivo já usar &quot;0&quot; e &quot;1&quot; para identificar a operação, não é necessário remapear esses valores. Verifique somente se a coluna é processada como **Booliana** ou **Integer** na guia **[!UICONTROL Column definition]**.

* A [Reconciliation](../../automating/using/reconciliation.md) activity identifies the data from the file as belonging to the profile dimension of the Adobe Campaign database. Na guia **[!UICONTROL Identification]**, o campo de **email** do arquivo corresponde ao campo de **email** do recurso de perfil.

   ![](assets/subscription_activity_example3.png)

   Na guia **[!UICONTROL Relations]**, um link é criado com o recurso de serviço para permitir que o campo de **serviço** do arquivo seja reconhecido. Neste exemplo, os valores correspondem ao campo de **nome** do recurso de serviço.

   ![](assets/subscription_example_service_relation.png)

* A [Deduplication](../../automating/using/deduplication.md) based on the **email** field of the temporary resource (resulting from the reconciliation) identifies duplicates. É importante eliminar duplicatas, caso contrário, haverá falha para todos os dados na assinatura para um serviço.

   ![](assets/subscription_activity_example5.png)

* A [Subscription Services](../../automating/using/subscription-services.md) activity identifies the services to update as coming from the transition, through the link created in the **[!UICONTROL Reconciliation]** activity.

   O **[!UICONTROL Operation type]** é identificado como proveniente do campo de **operação** do arquivo. Somente os campos Booliano ou Integer podem ser selecionados aqui. Se a coluna do arquivo que contém a operação a ser executada não aparecer na lista, verifique se você definiu corretamente o formato da coluna na atividade **[!UICONTROL Load file]**, conforme explicado anteriormente nesse exemplo.

   ![](assets/subscription_activity_example_from_file.png)
