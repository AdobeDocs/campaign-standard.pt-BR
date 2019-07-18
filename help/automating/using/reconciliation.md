---
title: Reconciliação
seo-title: Reconciliação
description: Reconciliação
seo-description: A atividade de Reconciliação permite vincular dados não identificados aos recursos existentes.
page-status-flag: nunca ativado
uuid: 7884 db 8 c -1717-4724-be 15-3 b 0 b 32 ccc 071
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizando
content-type: reference
topic-tags: gerenciamento de dados-atividades
discoiquuid: cb 8 c 43 f 4-9 cdd -4 e 85-99 a 4-004 b 36 b 336 aa
context-tags: reconciliação, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Reconciliation{#reconciliation}

## Description {#description}

![](assets/reconciliation.png)

The **[!UICONTROL Reconciliation]** activity allows you to link unidentified data to existing resources.

## Context of use {#context-of-use}

**[!UICONTROL Reconciliation]** A atividade é usada principalmente para fins de Gerenciamento de dados e implica dois casos de uso diferentes:

* Adding relations: a **[!UICONTROL Links]** tab allows you to add links between the inbound data and several other Adobe Campaign database dimensions.

   Por exemplo, um arquivo que contém dados de compra também pode conter informações para identificar os produtos comprados e o comprador. Two additional dimensions (besides that of **Purchases**) are therefore concerned by the file data: the **Products** and **Profiles** dimensions. Relations then need to be created between these and the **Purchases** dimension (refer to the following example).

   Ao definir uma relação, uma coluna é adicionada aos dados de entrada para fazer referência à chave externa da dimensão vinculada.

   >[!NOTE]
   >
   >Esta operação implica que os dados das dimensões vinculadas já estejam no banco de dados. Por exemplo, se você importar um arquivo de compras que mostra qual produto foi comprado, em que momento, por qual cliente, etc., o produto, assim como o cliente, já deve existir no banco de dados.

* Data identification: an **[!UICONTROL Identification]** tab allows you to simply link inbound data to columns of an existing dimension in the Adobe Campaign database. Após a atividade, os dados são identificados como pertencendo à dimensão definida.

   Por exemplo, você pode realizar um público-alvo salvo, atualização de banco de dados etc.

For example, the **[!UICONTROL Reconciliation]** activity can be placed after a load data activity with the aim of importing non-standard data into the database.

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Reconciliation]** activity into your workflow, following a transition containing a population whose targeting dimension does not directly come from Adobe Campaign. For more on this, referr to [Targeting dimensions and resources](../../automating/using/query.md#targeting-dimensions-and-resources).
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. If you would like to define links between the inbound data and other database dimensions, go to the **[!UICONTROL Links]** tab.

   Adicione quantas relações forem necessárias. Para cada relação, primeiro selecione a dimensão vinculada e, em seguida, nos detalhes do link, especifique os campos correspondentes.

1. If you would like to simply identify the inbound data, go to the **[!UICONTROL Identification]** tab and check the **[!UICONTROL Identify the document from the working data]** box.

   Selecione a dimensão de definição de metas à qual deseja reconciliar os dados de entrada.

   Adicione critérios de reconciliação para vincular um registro de transição de entrada a um registro de dimensão de definição de metas selecionado. Se vários critérios forem especificados, todos devem ser verificados para que o link entre todos os seus dados funcione.

   Choose the **[!UICONTROL Processing unidentified source lines]** mode:

   * **[!UICONTROL Ignore them]**: somente os dados identificáveis são mantidos na transição de saída da atividade.
   * **[!UICONTROL Keep in the outbound population]**: todos os dados da transição de entrada são mantidos na transição de saída da atividade.

1. Confirme a configuração da atividade e salve seu fluxo de trabalho.

## Example 1: Relation definition {#example-1--relation-definition}

O exemplo a seguir demonstra um fluxo de trabalho que atualiza o banco de dados usando os dados de compra em um arquivo. Os dados de compra contêm elementos de referência de dados de outras dimensões, como e-mails do cliente e códigos de produto.

>[!NOTE]
>
>The **Transactions** and **Products** resources used in this example do not exist in the Adobe Campaign database by default. They were therefore created beforehand using the [Custom resources](../../developing/using/data-model-concepts.md) function. Os perfis que correspondem aos endereços de email no arquivo importado, bem como os produtos, foram carregados no banco de dados antecipadamente.

O fluxo de trabalho é constituído pelas seguintes atividades:

![](assets/reconciliation_example1.png)

* A **[!UICONTROL Load file]** activity, which loads and detects the data of the file to import. O arquivo importado contém os seguintes dados:

   * Data da transação
   * Endereço de email do cliente
   * Código de produto comprado
   ```
   date;client;product
   2015-05-19 09:00:00;mail1@email.com;ZZ1
   2015-05-19 09:01:00;mail2@email.com;ZZ2
   2015-05-19 09:01:01;mail3@email.com;ZZ2
   2015-05-19 09:01:02;mail4@email.com;ZZ2
   2015-05-19 09:02:00;mail5@email.com;ZZ3
   2015-05-19 09:03:00;mail6@email.com;ZZ4
   2015-05-19 09:04:00;mail7@email.com;ZZ5
   2015-05-19 09:05:00;mail8@email.com;ZZ7
   2015-05-19 09:06:00;mail9@email.com;ZZ6
   ```

* A **[!UICONTROL Reconciliation]** activity to bind purchasing data to database profiles as well as products. Portanto, é necessário definir uma relação entre os dados do arquivo e a tabela de perfil, bem como a tabela de produtos. This configuration is carried out in the activity's **[!UICONTROL Relations]** tab:

   * Relation with the **Profiles**: the file's **client** column is linked to the **email** field of the **Profiles** dimension.
   * Relation with the **Products**: the file's **product** column is linked to the **productCode** field of the **Profiles** dimension.
   As colunas são adicionadas aos dados de entrada para fazer referência às chaves externas das dimensões vinculadas.

   ![](assets/reconciliation_example3.png)

* An **[!UICONTROL Update data]** activity allows you to define the database fields to update using the imported data. As the data was already identified as belonging to the **Transactions** dimension in the previous activity, here you can use the **[!UICONTROL Directly using the targeting dimension]** identification option.

   By using the option that automatically detects fields to update, the links configured in the previous activity (to profiles and products) are added to the list of **[!UICONTROL Fields to update]**. Você também deve verificar se o campo que corresponde à data da transação foi adicionado corretamente à lista.

   ![](assets/reconciliation_example5.png)

   ![](assets/reconciliation_example4.png)

## Example 2: Identification {#example-2--identification}

O exemplo a seguir demonstra um fluxo de trabalho que cria um público-alvo de perfis diretamente a partir de um arquivo importado que contém novos clientes. É composto pelas seguintes atividades:

![](assets/identification_example2.png)

* A **[!UICONTROL Load file]** activity, which loads and detects the data of the file to import. O arquivo importado contém os seguintes dados:

   ```
   lastname;firstname;email;dateofbirth
   jackman;megan;megan.jackman@testmail.com;07/08/1975
   phillips;edward;phillips@testmail.com;09/03/1986
   weaver;justin;justin_w@testmail.com;11/15/1990
   martin;babeth;babeth_martin@testmail.net;11/25/1964
   reese;richard;rreese@testmail.com;02/08/1987
   cage;nathalie;cage.nathalie227@testmail.com;07/03/1989
   xiuxiu;andrea;andrea.xiuxiu@testmail.com;09/12/1992
   grimes;daryl;daryl_890@testmail.com;12/06/1979
   tycoon;tyreese;tyreese_t@testmail.net;10/08/1971
   ```

* **[!UICONTROL Reconciliation]** Uma atividade, que vincula cada coluna do arquivo carregado a uma coluna de dimensão do perfil. Os registros de arquivo que não podem ser identificados (dados ausentes, tipo de dados incompatível etc.) são ignoradas para preservar a integridade dos dados finais do público-alvo.

   ![](assets/identification_example1.png)

* A **[!UICONTROL Save audience]** activity, which saves the audience of profiles.

   ![](assets/identification_example3.png)

