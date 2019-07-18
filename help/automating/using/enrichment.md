---
title: Enriquecimento
seo-title: Enriquecimento
description: Enriquecimento
seo-description: A atividade de Enriquecimento é uma atividade avançada que permite que você defina dados adicionais para processar no seu fluxo de trabalho.
page-status-flag: nunca ativado
uuid: 8 c 1693 ef -1312-422 c-b 05 d -263553113 f 8 f
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizando
content-type: reference
topic-tags: atividades de definição de metas
discoiquuid: f 67 c 1 caf -3284-4 c 34-a 5 b 0-8654 a 95640 ae
context-tags: enriquecimento, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Enrichment{#enrichment}

## Description {#description}

![](assets/enrichment.png)

**[!UICONTROL Enrichment]** A atividade é uma atividade avançada que permite que você defina dados adicionais para processar no seu fluxo de trabalho.

## Context of use {#context-of-use}

The **[!UICONTROL Enrichment]** activity is generally used following targeting activities or after importing a file and before activities that allow the use of targeted data.

This activity contains more advanced enrichment functions than the **[!UICONTROL Query]** activity. Some simple cases of enrichment can be directly performed in the [Query activity](../../automating/using/query.md#enriching-data).

With the **[!UICONTROL Enrichment]** activity, you can leverage the inbound transition and configure the activity to complete the output transition with additional data. Ela permite combinar dados provenientes de vários conjuntos ou criar links para um recurso temporário.

## Configuration {#configuration}

To configure an **[!UICONTROL Enrichment]** activity:

1. Drag and drop an **[!UICONTROL Enrichment]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. If the activity has several inbound transitions, select the **[!UICONTROL Primary set]**. Os dados adicionais configurados nesta atividade serão adicionados a esse conjunto principal na transição de saída.

   Se o conjunto principal já contiver dados adicionais, você poderá optar por mantê-los ou removê-los. If you uncheck the **[!UICONTROL Keep all additional data from the main set]** option, only the additional data configured in the **[!UICONTROL Enrichment]** are kept in the outbound transition.

1. If there are several inbound transitions, define relations between the primary set and the other inbound data in the **[!UICONTROL Advanced Relations]** tab of the activity. You can add several relations using the **[!UICONTROL Add element]** button.

   Ao definir uma nova relação, selecione o conjunto de dados de entrada que deseja vincular ao conjunto principal. Em seguida, defina o tipo de relação. Vários tipos de relações estão disponíveis, dependendo dos dados de entrada e do modelo de dados:

   * **[!UICONTROL 1 cardinality simple link]**: cada registro dos dados de entrada está associado a um e apenas um registro do conjunto principal. Cada registro do conjunto principal tem um registro associado nos dados vinculados.
   * **[!UICONTROL N cardinality collection link]**: 0, 1 ou mais (N) registros de dados vinculados podem ser associados a 1 registro do conjunto principal.
   * **[!UICONTROL 0 or 1 cardinality simple link]**: os registros do conjunto principal podem ser associados a 0 ou 1 registros a partir dos dados vinculados, mas não mais do que um.
   Once the **[!UICONTROL Cardinality]** is defined, define a **[!UICONTROL Reconciliation criteria]**. The **[!UICONTROL Source expression]** of the reconciliation criteria can be a field from the target resource, an [expression](../../automating/using/advanced-expression-editing.md) or directly a value specified between quotes.

   Define a **[!UICONTROL Label]** and an **[!UICONTROL ID]** that will be easy to identify later in the workflow.

   >[!NOTE]
   >
   >You can only define relations between the primary set and the other inbound transitions connected to the **[!UICONTROL Enrichment]** activity. For simpler cases aiming at defining relations with database resources, use a [Reconciliation](../../automating/using/reconciliation.md) activity.

1. Define the additional data from the **[!UICONTROL Additional data]** tab of the activity. You can define additional data (simple fields, aggregates and collections) related to the targeting dimension of the primary set or based on the links created in the **[!UICONTROL Advanced relations]** tab of the **[!UICONTROL Enrichment]** activity.

   Consult the [Enriching data](../../automating/using/query.md#enriching-data) section.

1. Confirme a configuração da atividade e salve seu fluxo de trabalho.

The data is now available to use in the activities connected after the **[!UICONTROL Enrichment]**. For example, you can find it under the **[!UICONTROL Additional data (targetData)]** link of the personalization fields explorer in an email content.

## Example: Enriching profile data with data contained in a file {#example--enriching-profile-data-with-data-contained-in-a-file}

Este exemplo mostra como encher dados de perfil com dados de compra contidos em um arquivo. Consideramos que os dados de compra são armazenados em um sistema de terceiros. Cada perfil pode ter várias compras armazenadas no arquivo. A meta final do fluxo de trabalho é enviar um email para os perfis de destino que compraram pelo menos dois itens para agradecer pela fidelidade.

O fluxo de trabalho é configurado da seguinte maneira:

![](assets/enrichment_example_workflow.png)

* A **[!UICONTROL Query]** activity that targets the profiles who will receive the message.
* A **[!UICONTROL Load file]** activity that loads the purchase data. Por exemplo:

   ```
   tcode;tdate;customer;product;tamount
   aze123;21/05/2017;dannymars@example.com;TV;799
   aze124;28/05/2017;dannymars@example.com;Headphones;8
   aze125;31/07/2017;john.smith@example.com;Headphones;8
   aze126;14/12/2017;john.smith@example.com;Plastic Cover;4
   aze127;02/01/2018;dannymars@example.com;Case Cover;79
   aze128;04/03/2017;clara.smith@example.com;Phone;149
   ```

   Com esse arquivo de exemplo, nós usaremos o endereço de email para reconciliar os dados com os perfis de banco de dados. You can also enable unique IDs as described in [this document](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources).

* **[!UICONTROL Enrichment]** Uma atividade que cria um vínculo entre os dados de transação carregados do arquivo e os perfis selecionados no **[!UICONTROL Query]**. The link is defined in the **[!UICONTROL Advanced relations]** tab of the activity. The link is based on the transition coming from the **[!UICONTROL Load file]** activity. Ele usa o campo "email" do recurso de perfil e a coluna "cliente" do arquivo importado como critério de reconciliação.

   ![](assets/enrichment_example_workflow2.png)

   Once the link is created, two sets of **[!UICONTROL Additional data]** are added:

   * Uma coleção de duas linhas correspondendo às duas últimas transações de cada perfil. Para essa coleção, o nome do produto, a data da transação e o preço do produto são adicionados como dados adicionais. Uma classificação decrescente é aplicada nos dados. To create the collection, from the **[!UICONTROL Additional data]** tab:

      Select the link previously defined in the **[!UICONTROL Advanced relations]** tab of the activity.

      ![](assets/enrichment_example_workflow3.png)

      Check **[!UICONTROL Collection]** and specify the number of lines to retrieve (2 in this example). In this screen, you can customize the **[!UICONTROL Alias]** and the **[!UICONTROL Label]** of the collection. Esses valores estarão visíveis nas seguintes atividades do fluxo de trabalho ao se referir a essa coleção.

      ![](assets/enrichment_example_workflow4.png)

      As **[!UICONTROL Data]** to keep for the collection, select the columns that will be used in the final delivery.

      ![](assets/enrichment_example_workflow6.png)

      Aplique uma classificação decrescente na data da transação para recuperar as transações mais recentes.

      ![](assets/enrichment_example_workflow7.png)

   * Uma contagem agregada do número total de transações para cada perfil. Esse agregado será usado posteriormente para filtrar perfis com pelo menos duas transações gravadas. To create the aggregate, from the **[!UICONTROL Additional data]** tab:

      Select the link previously defined in the **[!UICONTROL Advanced relations]** tab of the activity.

      ![](assets/enrichment_example_workflow3.png)

      Select **[!UICONTROL Aggregate]**.

      ![](assets/enrichment_example_workflow8.png)

      As **[!UICONTROL Data]** to keep, define a **Count All** aggregate. Se for necessário, especifique um alias personalizado para encontrá-lo mais rápido nas seguintes atividades.

      ![](assets/enrichment_example_workflow9.png)

* A **[!UICONTROL Segmentation]** activity with only one segment, that retrieves profiles of the initial target that have at least two transactions recorded. Perfis com apenas uma transação são excluídos. Para fazer isso, a consulta da segmentação é feita previamente no agregado definido anteriormente.

   ![](assets/enrichment_example_workflow5.png)

* An **[!UICONTROL Email delivery]** activity that uses the additional data defined in the **[!UICONTROL Enrichment]** to dynamically retrieve the two last purchases made by the profile. The additional data can be found in the **Additional data (TargetData)** node when adding a personalization field.

   ![](assets/enrichment_example_workflow10.png)

