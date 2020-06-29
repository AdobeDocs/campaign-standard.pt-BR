---
title: Atualização de vários status de subscrição de um arquivo
description: Este caso de uso mostra como importar um arquivo contendo perfis e atualizar sua subscrição para vários serviços especificados no arquivo.
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
source-wordcount: '417'
ht-degree: 0%

---


# Atualização de vários status de subscrição de um arquivo {#updating-multiple-subscription-statuses-from-a-file}

Este exemplo ilustra como importar um arquivo contendo perfis e atualizar sua subscrição para vários serviços especificados no arquivo. Após a importação do arquivo, é necessário realizar uma reconciliação para que os dados importados possam ser identificados como perfis com um link para os serviços. Para garantir que o arquivo não contenha nenhum duplicado, uma atividade desduplicação-duplicada será executada nos dados.

O fluxo de trabalho é apresentado da seguinte forma:

![](assets/subscription_activity_example1.png)

* Uma atividade de arquivo [](../../automating/using/load-file.md) Load carrega o arquivo de perfil e define a estrutura das colunas importadas.

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

* Uma atividade de [Reconciliação](../../automating/using/reconciliation.md) identifica os dados do arquivo como pertencendo à dimensão do perfil do banco de dados do Adobe Campaign. Na **[!UICONTROL Identification]** guia, o campo de **email** do arquivo corresponde ao campo de **email** do recurso de perfil.

   ![](assets/subscription_activity_example3.png)

   Na **[!UICONTROL Relations]** guia, um link é criado com o recurso de serviço para permitir que o campo de **serviço** do arquivo seja reconhecido. Neste exemplo, os valores correspondem ao campo de **nome** do recurso de serviço.

   ![](assets/subscription_example_service_relation.png)

* Um [Desduplicação-duplicado](../../automating/using/deduplication.md) com base no campo de **email** do recurso temporário (resultante da reconciliação) identifica duplicados. É importante eliminar duplicados, pois a subscrição para um serviço falhará para todos os dados no caso de duplicados.

   ![](assets/subscription_activity_example5.png)

* Uma atividade [Subscrição no serviço](../../automating/using/subscription-services.md) identifica os serviços a serem atualizados como provenientes da transição, por meio do link criado na **[!UICONTROL Reconciliation]** atividade.

   O **[!UICONTROL Operation type]** é identificado como vindo do campo de **operação** do arquivo. Somente os campos Booliano ou Inteiro podem ser selecionados aqui. Se a coluna do arquivo que contém a operação a ser executada não for exibida na lista, verifique se você definiu corretamente o formato da coluna na **[!UICONTROL Load file]** atividade, como explicado anteriormente neste exemplo.

   ![](assets/subscription_activity_example_from_file.png)
