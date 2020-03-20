---
title: Serviços de assinatura
description: A atividade dos Serviços de assinatura permite que você pegue perfis em massa e assine-os em um serviço ou cancele sua assinatura de um serviço.
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
source-git-commit: 9048e11fe063707e1c6b5a86de095f72d22800c1

---


# Serviços de assinatura{#subscription-services}

## Descrição {#description}

![](assets/wf_subscription.png)

A **[!UICONTROL Subscription Services]** atividade permite que você pegue perfis em massa e assine-os em um serviço ou cancele sua assinatura de um serviço.

>[!CAUTION]
>
>Quando a assinatura é gerenciada no contexto de um fluxo de trabalho, os perfis inscritos ou cancelados não recebem os e-mails de confirmação diferentes definidos nas propriedades do serviço.

## Contexto de utilização {#context-of-use}

A **[!UICONTROL Subscription Services]** atividade é a única funcionalidade do Adobe Campaign que permite que vários perfis sejam inscritos ou sejam cancelados de uma assinatura de um serviço em uma única ação.

Você pode usar essa atividade depois de ter realizado a definição de metas ou importado um arquivo com dados identificados.

Se especificada em um arquivo por meio de colunas dedicadas, essa atividade também permite que você escolha a ação (assinar ou cancelar a assinatura) e o serviço no qual executar a ação.

## Configuração {#configuration}

1. Arraste e solte uma **[!UICONTROL Subscription Services]** atividade em seu fluxo de trabalho.
1. Conecte-o depois de outras atividades de definição de metas, como uma consulta ou reconciliação, após uma importação.
1. Selecione a atividade e abra-a usando o ![](assets/edit_darkgrey-24px.png) botão das ações rápidas que aparecem.
1. Selecione o **[!UICONTROL Service]** para o qual você deseja gerenciar as assinaturas usando uma das seguintes opções:

   * **[!UICONTROL Select a specific service]**: selecionar manualmente um serviço.
   * **[!UICONTROL Select services from the inbound transition]**: o serviço é especificado na transição de entrada. Por exemplo, você pode importar um arquivo que especifica o serviço a ser gerenciado para cada linha. Se você escolher essa opção, certifique-se de que um link tenha sido criado previamente entre os dados e o recurso **Serviço** , como mostrado [neste exemplo](#example--updating-multiple-subscription-statuses-from-a-file).

      O serviço no qual executar a operação é então selecionado dinamicamente para cada registro.

1. Selecione a opção **[!UICONTROL Operation type]** a ser executada usando uma das seguintes opções:

   * **[!UICONTROL Select a specific operation type]**: selecione manualmente se desejar **[!UICONTROL Subscribe]** ou **[!UICONTROL Unsubscribe]** perfis.
   * **[!UICONTROL Select an operation type from a path of inbound transition]**: selecione a coluna dos dados de entrada que especifica a operação a ser executada para cada registro.

      Nesta coluna, a operação deve ser especificada como Booliana ou Integer. Use **0** para cancelar a assinatura de um registro e **1** para assinar.

      Se os valores contidos em um arquivo importado não corresponderem aos requisitos acima, você ainda poderá usar a opção [Remapeamento de valores](../../automating/using/load-file.md#column-format) disponível na **[!UICONTROL Load file]** atividade.

1. Se os dados de entrada contiverem uma coluna correspondente à data de assinatura do perfil para o serviço, selecione-a. Você pode deixá-la vazia, mas nenhuma data de assinatura é definida ao executar o fluxo de trabalho.
1. Defina a origem da assinatura. Você pode defini-la como um dos campos dos dados de entrada ou como um valor constante de sua escolha marcando a **[!UICONTROL Set a constant as origin]** opção. Você pode deixá-lo vazio, mas nenhuma origem é definida ao executar o fluxo de trabalho.
1. Se necessário, você pode gerar uma transição de saída. Essa transição contém exatamente os mesmos dados da atividade de entrada.
1. Confirme a configuração da atividade e salve o fluxo de trabalho.

   Está agora pronto para ser executado. Depois de executados, você pode exibir os perfis que se inscreveram ou cancelaram a assinatura do serviço nos detalhes do serviço.

## Exemplo: Assinatura de perfis para um serviço específico após a importação de um arquivo {#example--subscribing-profiles-to-a-specific-service-after-importing-a-file}

Este exemplo ilustra como importar um arquivo contendo perfis e assiná-los em um serviço existente. Após a importação do arquivo, é necessário realizar uma reconciliação para que os dados importados possam ser identificados como perfis. Para garantir que o arquivo não contenha nenhuma duplicação, uma atividade de desduplicação será executada nos dados.

O fluxo de trabalho é apresentado da seguinte forma:

![](assets/subscription_activity_example1.png)

* Uma **[!UICONTROL Load file]** atividade carrega o arquivo de perfil e define a estrutura das colunas importadas.

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

* Uma **[!UICONTROL Reconciliation]** atividade identifica os dados do arquivo como pertencendo à dimensão de perfil do banco de dados do Adobe Campaign. Somente a **[!UICONTROL Identification]** guia está configurada. Ela identifica os dados do arquivo de acordo com os endereços de email dos perfis.

   ![](assets/subscription_activity_example3.png)

* Um **[!UICONTROL Deduplication]** baseado no campo de **email** do recurso temporário (resultante da reconciliação) identifica quaisquer duplicatas. Se os dados importados do arquivo contiverem duplicatas, a assinatura de um serviço falhará para todos os dados.

   ![](assets/subscription_activity_example5.png)

* Uma **[!UICONTROL Subscription Services]** atividade permite selecionar o serviço ao qual os perfis devem ser inscritos, o campo correspondente à data da assinatura e a origem da assinatura.

   ![](assets/subscription_activity_example4.png)

## Exemplo: Atualização de vários status de assinatura de um arquivo {#example--updating-multiple-subscription-statuses-from-a-file}

Este exemplo ilustra como importar um arquivo que contém perfis e atualizar sua assinatura para vários serviços especificados no arquivo. Após a importação do arquivo, é necessário realizar uma reconciliação para que os dados importados possam ser identificados como perfis com um link para os serviços. Para garantir que o arquivo não contenha nenhuma duplicação, uma atividade de desduplicação será executada nos dados.

O fluxo de trabalho é apresentado da seguinte forma:

![](assets/subscription_activity_example1.png)

* Uma **[!UICONTROL Load file]** atividade carrega o arquivo de perfil e define a estrutura das colunas importadas.

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

   Como você pode ter notado, a operação é especificada no arquivo como &quot;sub&quot; ou &quot;unsub&quot;. O sistema espera que um valor **Booliano** ou **Integer** reconheça a operação a ser executada: &quot;0&quot; para cancelar a inscrição e &quot;1&quot; para assinar. Para corresponder a esse requisito, um remapeamento de valores é executado no detalhe da coluna &quot;operação&quot;.

   ![](assets/subscription_example_remapping.png)

   Se o arquivo já usar &quot;0&quot; e &quot;1&quot; para identificar a operação, não será necessário mapear novamente esses valores. Verifique apenas se a coluna é processada como **Booliana** ou **Inteiro** na **[!UICONTROL Column definition]** guia.

* Uma **[!UICONTROL Reconciliation]** atividade identifica os dados do arquivo como pertencendo à dimensão de perfil do banco de dados do Adobe Campaign. Na **[!UICONTROL Identification]** guia, o campo de **email** do arquivo corresponde ao campo de **email** do recurso de perfil.

   ![](assets/subscription_activity_example3.png)

   Na **[!UICONTROL Relations]** guia, um link é criado com o recurso de serviço para permitir que o campo de **serviço** do arquivo seja reconhecido. Neste exemplo, os valores correspondem ao campo de **nome** do recurso de serviço.

   ![](assets/subscription_example_service_relation.png)

* Um **[!UICONTROL Deduplication]** baseado no campo de **email** do recurso temporário (resultante da reconciliação) identifica duplicatas. É importante eliminar duplicatas, pois a assinatura de um serviço falhará para todos os dados em caso de duplicatas.

   ![](assets/subscription_activity_example5.png)

* Um **[!UICONTROL Subscription Services]** identifica os serviços a serem atualizados como provenientes da transição, por meio do link criado na **[!UICONTROL Reconciliation]** atividade.

   O **[!UICONTROL Operation type]** é identificado como vindo do campo de **operação** do arquivo. Somente os campos Booliano ou Inteiro podem ser selecionados aqui. Se a coluna do arquivo que contém a operação a ser executada não for exibida na lista, verifique se você definiu corretamente o formato da coluna na **[!UICONTROL Load file]** atividade, como explicado anteriormente neste exemplo.

   ![](assets/subscription_activity_example_from_file.png)

