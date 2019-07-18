---
title: Serviços de assinatura
seo-title: Serviços de assinatura
description: Serviços de assinatura
seo-description: A atividade dos Serviços de assinatura permite pegar perfis em massa e assiná-los em um serviço ou cancelá-los a partir de um serviço.
page-status-flag: nunca ativado
uuid: 56637024-15 ab -4145-9 c 48-3 fbbd 27 ab 8 af 8
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizando
content-type: reference
topic-tags: gerenciamento de dados-atividades
discoiquuid: 74 a 6 df 0 e-fd 85-4404-a 42 c -9 a 7406512717
context-tags: Setofservice, fluxo de trabalho, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Subscription Services{#subscription-services}

## Description {#description}

![](assets/wf_subscription.png)

The **[!UICONTROL Subscription Services]** activity allows you to take profiles in mass and subscribe them to a service or unsubscribe them from a service.

>[!CAUTION]
>
>Quando a assinatura gerenciada no contexto de um fluxo de trabalho, os perfis assinados ou não assinados não recebem os diferentes e-mails de confirmação definidos nas propriedades do serviço.

## Context of use {#context-of-use}

**[!UICONTROL Subscription Services]** A atividade é a única funcionalidade do Adobe Campaign que permite que vários perfis sejam inscritos ou cancelados de serem cancelados de um serviço em uma única ação.

Você pode usar essa atividade depois de ter realizado o direcionamento ou ter importado um arquivo com dados identificados.

Se especificado em um arquivo por colunas dedicadas, essa atividade também permite escolher a ação (assinar ou cancelar a inscrição) e o serviço no qual a ação deve ser realizada.

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Subscription Services]** activity into your workflow.
1. Conecte-o depois de outras atividades de definição de metas, como uma consulta ou uma reconciliação após uma importação.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Select the **[!UICONTROL Service]** for which you would like to manage the subscriptions using one of the following options:

   * **[!UICONTROL Select a specific service]**: selecione manualmente um serviço.
   * **[!UICONTROL Select services from the inbound transition]**: o serviço é especificado na transição de entrada. Por exemplo, é possível importar um arquivo que especifica o serviço para gerenciar cada linha. If you choose this option, make sure a link has been created beforehand between the data and the **Service** resource, as shown in [this example](../../automating/using/subscription-services.md#example--updating-multiple-subscription-statuses-from-a-file).

      O serviço no qual executar a operação é selecionado dinamicamente para cada registro.

1. Select the **[!UICONTROL Operation type]** to execute using one of the following options:

   * **[!UICONTROL Select a specific operation type]**: selecione manualmente se deseja **[!UICONTROL Subscribe]****[!UICONTROL Unsubscribe]** ou não.
   * **[!UICONTROL Select an operation type from a path of inbound transition]**: selecione a coluna dos dados de entrada que especifica a operação a ser executada para cada registro.

      Nessa coluna, a operação deve ser especificada como um booliano ou inteiro. Use **0** to unsubscribe a record and **1** to subscribe.

      In case the values contained in an imported file do not match the above requirements, you can still use the [Remapping of values](../../automating/using/load-file.md#column-format) option available in the **[!UICONTROL Load file]** activity

1. Se os dados de entrada contiverem uma coluna com a data de assinatura do perfil ao serviço, selecione-a. Você pode deixá-la vazia, mas nenhuma data de assinatura é definida ao executar o fluxo de trabalho.
1. Defina a origem da assinatura. You can set it to one of the fields of the inbound data or to a constant value of your choice by checking the **[!UICONTROL Set a constant as origin]** option. Você pode deixá-la vazia, mas nenhuma origem é definida ao executar o fluxo de trabalho.
1. Se necessário, é possível gerar uma transição de saída. Essa transição contém exatamente os mesmos dados da atividade de entrada.
1. Confirme a configuração da atividade e salve seu fluxo de trabalho.

   Agora está pronto para ser executado. Depois de executado, você pode exibir os perfis que assinaram ou cancelaram a inscrição do serviço nos detalhes do serviço.

## Example: Subscribing profiles to a specific service after importing a file {#example--subscribing-profiles-to-a-specific-service-after-importing-a-file}

Este exemplo ilustra como importar um arquivo contendo perfis e assiná-los a um serviço existente. Após a importação do arquivo, é necessário realizar uma reconciliação para que os dados importados possam ser identificados como perfis. Para garantir que o arquivo não contenha duplicatas, uma atividade de desduplicação será executada nos dados.

O fluxo de trabalho é apresentado da seguinte maneira:

![](assets/subscription_activity_example1.png)

* A **[!UICONTROL Load file]** activity loads the profile file and defines the structure of the imported columns.

   Neste exemplo, o arquivo carregado está no formato. csv e contém os seguintes dados:

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

* A **[!UICONTROL Reconciliation]** activity identifies the data from the file as belonging to the profile dimension of the Adobe Campaign database. Only the **[!UICONTROL Identification]** tab is configured. Ele identifica os dados do arquivo de acordo com os endereços de email dos perfis.

   ![](assets/subscription_activity_example3.png)

* A **[!UICONTROL Deduplication]** based on the **email** field of the temporary resource (resulting from the reconciliation) identifies any duplicates. Se os dados importados do arquivo contiverem duplicatas, a assinatura de um serviço falhará para todos os dados.

   ![](assets/subscription_activity_example5.png)

* A **[!UICONTROL Subscription Services]** activity lets you select the service to which the profiles must be subscribed, the field corresponding to the subscription date, and the origin of the subscription.

   ![](assets/subscription_activity_example4.png)

## Example: Updating multiple subscription statuses from a file {#example--updating-multiple-subscription-statuses-from-a-file}

Este exemplo ilustra como importar um arquivo contendo perfis e atualizar sua assinatura para vários serviços especificados no arquivo. Após a importação do arquivo, é necessário realizar uma reconciliação para que os dados importados possam ser identificados como perfis com um link para os serviços. Para garantir que o arquivo não contenha duplicatas, uma atividade de desduplicação será executada nos dados.

O fluxo de trabalho é apresentado da seguinte maneira:

![](assets/subscription_activity_example1.png)

* A **[!UICONTROL Load file]** activity loads the profile file and defines the structure of the imported columns.

   Neste exemplo, o arquivo carregado está no formato. csv e contém os seguintes dados:

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

   Como você observou, a operação é especificada no arquivo como "sub" ou "unsub". The system expects a **Boolean** or **Integer** value to recognize the operation to perform: "0" to unsubscribe and "1" to subscribe. Para corresponder a esse requisito, um remapeamento de valores é executado nos detalhes da coluna "operação".

   ![](assets/subscription_example_remapping.png)

   Se o arquivo já usa "0" e "1" para identificar a operação, você não precisa remapear esses valores. Only make sure that the column is processed as a **Boolean** or **Integer** in the **[!UICONTROL Column definition]** tab.

* A **[!UICONTROL Reconciliation]** activity identifies the data from the file as belonging to the profile dimension of the Adobe Campaign database. Through the **[!UICONTROL Identification]** tab, the **email** field of the file is matched to the **email** field of the profile resource.

   ![](assets/subscription_activity_example3.png)

   In the **[!UICONTROL Relations]** tab, a link is created with the service resource to allow the **service** field of the file to be recognized. In this example, the values match the **name** field of the service resource.

   ![](assets/subscription_example_service_relation.png)

* A **[!UICONTROL Deduplication]** based on the **email** field of the temporary resource (resulting from the reconciliation) identifies duplicates. É importante eliminar duplicatas, pois a assinatura de um serviço falha para todos os dados no caso de duplicatas.

   ![](assets/subscription_activity_example5.png)

* A **[!UICONTROL Subscription Services]** identifies the services to update as coming from the transition, through the link created in the **[!UICONTROL Reconciliation]** activity.

   The **[!UICONTROL Operation type]** is identified as coming from the **operation** field of the file. Apenas campos Booleanos ou Inteiros podem ser selecionados aqui. If the column of your file that contains the operation to perform does not appear in the list, make sure that you have correctly set your column format in the **[!UICONTROL Load file]** activity, as explained earlier in this example.

   ![](assets/subscription_activity_example_from_file.png)

