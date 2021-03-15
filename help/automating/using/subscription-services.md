---
solution: Campaign Standard
product: campaign
title: Serviços de assinatura
description: A atividade de Serviços de assinatura permite assinar ou cancelar a assinatura de um serviço para perfis em massa.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: setOfService,workflow,main
feature: Fluxos de trabalho
role: Arquiteto de dados
level: Intermediário
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '1114'
ht-degree: 97%

---


# Serviços de assinatura {#subscription-services}

## Descrição {#description}

![](assets/wf_subscription.png)

A atividade **[!UICONTROL Subscription Services]** permite assinar ou cancelar a assinatura de um serviço para perfis em massa.

>[!CAUTION]
>
>Ao gerenciar a assinatura no contexto de um fluxo de trabalho, os perfis que assinaram ou cancelaram assinaturas não recebem os diferentes emails de confirmação definidos nas propriedades do serviço.

## Contexto de uso {#context-of-use}

A atividade **[!UICONTROL Subscription Services]** é a única funcionalidade do Adobe Campaign com a qual é possível assinar ou cancelar a assinatura de um serviço para vários perfis em uma única ação.

É possível usar essa atividade depois de ter realizado o direcionamento ou importado um arquivo com dados identificados.

Se especificada em um arquivo por meio de colunas dedicadas, com essa atividade também é possível escolher a ação (assinar ou cancelar a assinatura) e o serviço no qual executar a ação.

**Tópicos relacionados:**

* [Caso de uso: Atualização de vários status de assinatura a partir de um arquivo](../../automating/using/updating-subscriptions-from-file.md)
* [Caso de uso: Assinatura de perfis para um serviço específico a partir de um arquivo](../../automating/using/subscribing-profiles-from-file.md)

## Configuração {#configuration}

1. Arraste e solte uma atividade **[!UICONTROL Subscription Services]** no seu fluxo de trabalho.
1. Conecte-a após outras atividades de direcionamento, como um query ou uma reconciliação após uma importação.
1. Selecione e abra a atividade usando o botão ![](assets/edit_darkgrey-24px.png) das ações rápidas exibidas.
1. Selecione o **[!UICONTROL Service]** para o qual você deseja gerenciar as assinaturas usando uma das seguintes opções:

   * **[!UICONTROL Select a specific service]**: seleciona manualmente um serviço.
   * **[!UICONTROL Select services from the inbound transition]**: o serviço é especificado na transição de entrada. Por exemplo, é possível importar um arquivo que especifica o serviço a ser gerenciado para cada linha. Caso escolha essa opção, verifique se um link foi criado previamente entre os dados e o recurso **Serviço**, conforme mostrado [neste exemplo](#example--updating-multiple-subscription-statuses-from-a-file).

      O serviço no qual executar a operação é então selecionado dinamicamente para cada registro.

1. Selecione o **[!UICONTROL Operation type]** a ser executado usando uma das seguintes opções:

   * **[!UICONTROL Select a specific operation type]**: selecione manualmente se desejar **[!UICONTROL Subscribe]** ou **[!UICONTROL Unsubscribe]** de perfis.
   * **[!UICONTROL Select an operation type from a path of inbound transition]**: selecione a coluna dos dados de entrada que especifica a operação a ser executada para cada registro.

      Nessa coluna, a operação deve ser especificada como Booliana ou Integer. Use **0** para cancelar a assinatura de um registro e **1** para assinar.

      Se os valores contidos em um arquivo importado não corresponderem aos requisitos acima, você ainda poderá usar a opção [Remapeamento de valores](../../automating/using/load-file.md#column-format), disponível na atividade **[!UICONTROL Load file]**.

1. Se os dados de entrada tiverem uma coluna correspondente à data de assinatura do perfil para o serviço, selecione-a. Você pode deixá-la vazia, mas nenhuma data de assinatura é definida ao executar o fluxo de trabalho.
1. Defina a origem da assinatura. Você pode defini-la como um dos campos dos dados de entrada ou como um valor constante de sua escolha, marcando a opção **[!UICONTROL Set a constant as origin]**. Você pode deixá-la vazia, mas nenhuma origem é definida ao executar o fluxo de trabalho.
1. Se necessário, gere uma transição de saída. Essa transição contém exatamente os mesmos dados que os da atividade de entrada.
1. Confirme a configuração da sua atividade e salve o fluxo de trabalho.

   O fluxo de trabalho agora está pronto para ser executado. Depois de executado, é possível exibir os perfis que assinaram ou cancelaram a assinatura do serviço nos detalhes do serviço.

## Exemplo: assinatura de perfis para um serviço específico após a importação de um arquivo {#example--subscribing-profiles-to-a-specific-service-after-importing-a-file}

Este exemplo ilustra como importar um arquivo contendo perfis e fazer a assinatura de todos eles para um serviço existente. Após a importação do arquivo, é necessário fazer uma reconciliação para que os dados importados possam ser identificados como perfis. Para garantir que o arquivo não contenha nenhuma duplicata, uma atividade de desduplicação é executada nos dados.

O fluxo de trabalho é apresentado da seguinte forma:

![](assets/subscription_activity_example1.png)

* Uma atividade **[!UICONTROL Load file]** carrega o arquivo de perfil e define a estrutura das colunas importadas.

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

* Uma atividade **[!UICONTROL Reconciliation]** identifica os dados do arquivo como pertencente à dimensão do perfil do banco de dados do Adobe Campaign. Somente a guia **[!UICONTROL Identification]** está configurada. Ela identifica os dados do arquivo de acordo com os endereços de email dos perfis.

   ![](assets/subscription_activity_example3.png)

* Uma **[!UICONTROL Deduplication]** baseado no campo de **email** do recurso temporário (resultante da reconciliação) identifica duplicatas. Se os dados importados do arquivo tiverem duplicatas, a assinatura para um serviço falhará para todos os dados.

   ![](assets/subscription_activity_example5.png)

* Uma atividade de **[!UICONTROL Subscription Services]** permite selecionar o serviço para o qual os perfis farão assinatura, o campo correspondente à data da assinatura e a origem da assinatura.

   ![](assets/subscription_activity_example4.png)

## Exemplo: atualização de vários status de assinatura diretamente de um arquivo {#example--updating-multiple-subscription-statuses-from-a-file}

Este exemplo ilustra como importar um arquivo contendo perfis e atualizar sua assinatura para vários serviços especificados no arquivo. Após a importação do arquivo, é necessário fazer uma reconciliação para que os dados importados possam ser identificados como perfis com um link para os serviços. Para garantir que o arquivo não contenha nenhuma duplicata, uma atividade de desduplicação é executada nos dados.

O fluxo de trabalho é apresentado da seguinte forma:

![](assets/subscription_activity_example1.png)

* Uma atividade **[!UICONTROL Load file]** carrega o arquivo de perfil e define a estrutura das colunas importadas.

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

* Uma atividade **[!UICONTROL Reconciliation]** identifica os dados do arquivo como pertencente à dimensão do perfil do banco de dados do Adobe Campaign. Na guia **[!UICONTROL Identification]**, o campo de **email** do arquivo corresponde ao campo de **email** do recurso de perfil.

   ![](assets/subscription_activity_example3.png)

   Na guia **[!UICONTROL Relations]**, um link é criado com o recurso de serviço para permitir que o campo de **serviço** do arquivo seja reconhecido. Neste exemplo, os valores correspondem ao campo de **nome** do recurso de serviço.

   ![](assets/subscription_example_service_relation.png)

* Uma **[!UICONTROL Deduplication]**, baseada no campo de **email** do recurso temporário (resultante da reconciliação) identifica duplicatas. É importante eliminar duplicatas, caso contrário, haverá falha para todos os dados na assinatura para um serviço.

   ![](assets/subscription_activity_example5.png)

* Os **[!UICONTROL Subscription Services]** identificam os serviços a serem atualizados como provenientes da transição, por meio do link criado na atividade **[!UICONTROL Reconciliation]**.

   O **[!UICONTROL Operation type]** é identificado como proveniente do campo de **operação** do arquivo. Somente os campos Booliano ou Integer podem ser selecionados aqui. Se a coluna do arquivo que contém a operação a ser executada não aparecer na lista, verifique se você definiu corretamente o formato da coluna na atividade **[!UICONTROL Load file]**, conforme explicado anteriormente nesse exemplo.

   ![](assets/subscription_activity_example_from_file.png)

