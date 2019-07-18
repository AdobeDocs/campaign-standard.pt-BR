---
title: Configuração da definição de filtro
seo-title: Configuração da definição de filtro
description: Configuração da definição de filtro
seo-description: Descubra o recurso de filtro para gerenciar um conjunto de dados grande.
page-status-flag: nunca ativado
uuid: c 9 db 95 fe-e 9 aa -40 f 8-9 c 0 a-e 74 bb 24 ac 14 b
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: adição ou extensão-a-resource
discoiquuid: 993 ab 2 bd-e 05 f -468 e -9 ef 8-a 603761247 f 8
context-tags: Cusresource, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 806dc4736ffb395a0eea102090c688102478aaca

---


# Configuring filter definition{#configuring-filter-definition}

In the **[!UICONTROL Filter definition]** tab, you can create advanced filters that users can directly access when creating complex queries, such as when defining an audience.

Essa etapa não é obrigatória, pois você ainda poderá preencher seu recurso e acessar seus dados por meio de fluxos de trabalho, públicos-alvo e API REST.

![](assets/custom_resource_filter-definition.png)

Esses filtros são usados no editor de consultas na forma de regras pré-definidas. Eles permitem limitar o número de etapas necessárias para obter a configuração desejada, o que pode ser especialmente benéfico para segmentações repetitivas.

Por exemplo, você pode criar um filtro que permita selecionar todas as transações maiores que um determinado valor nos últimos três meses.

To do this, you need to extend the **[!UICONTROL Profiles]** resource and define a filter linking to a transaction table (that you have previously created) with a rule indicating that the transaction price must be greater than or equal to a given parameter and that the transaction date must fall within a range corresponding to the last three months.

1. Certifique-se de criar e publicar uma tabela de transação. See [Creating or extending the resource](../../developing/using/creating-or-extending-the-resource.md).

   >[!NOTE]
   >
   >Esse procedimento usa o exemplo de uma tabela de transação personalizada. Para seu caso, ajuste-o às suas necessidades de negócios.

1. Before defining a filter related to the transaction table in the **[!UICONTROL Profiles]** resource, make sure you define the link to this table and publish your changes. See [Defining links with other resources](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources) and [Updating the database structure](../../developing/using/updating-the-database-structure.md).
1. In the **[!UICONTROL Definition]** tab of your new filter's definition screen, select the transaction table.

   ![](assets/custom_resource_filter-definition_example-empty.png)

1. In the **[!UICONTROL Add a rule - Profiles/Transactions]** window, drag and drop the transaction table into the workspace. Na próxima janela exibida, selecione o campo que deseja usar.

   ![](assets/custom_resource_filter-definition_example-field.png)

1. In the **[!UICONTROL Optional parameter settings]** of the **[!UICONTROL Add a rule - Transactions]** window, check the **[!UICONTROL Switch to parameters]** box.

   In the **[!UICONTROL Filter conditions]**, select the **[!UICONTROL Greater than or equal to]** operator. In the **[!UICONTROL Parameters]** field, enter a name and click the plus sign to create the new parameter.

   ![](assets/custom_resource_filter-definition_example-parameter.png)

1. Confirme suas alterações. Essa definição corresponde a um campo configurável que o usuário deve preencher posteriormente para executar a consulta.

   ![](assets/custom_resource_filter-definition_ex_edit-rule.png)

1. Combine essa regra com outra regra especificando que a data da transação deve estar dentro de um intervalo correspondente aos últimos três meses.

   ![](assets/custom_resource_filter-definition_example.png)

1. Escolha a categoria na qual seu filtro será exibido.

   ![](assets/custom_resource_filter-definition_category.png)

1. In the **[!UICONTROL Parameters]** tab of the filter definition screen, modify the description and the label to clearly indicate the subject of your filter to the users. Essas informações aparecerão no editor de consultas.

   ![](assets/custom_resource_filter-definition_parameters.png)

   Se você definir vários campos configuráveis, poderá modificar a ordem em que eles aparecem na interface.

1. Salve as alterações e publique os recursos. For more on this, refer to the [Updating the database structure](../../developing/using/updating-the-database-structure.md) section.

Once the **[!UICONTROL Profiles]** resource extension is published, the users will see this filter under the shortcuts tab in the [query editor](../../automating/using/editing-queries.md) interface.

Isso permitirá que o usuário defina facilmente seu público-alvo ao criar um email para enviar a todos os clientes que gastaram mais do que um determinado valor nos últimos três meses.

![](assets/custom_resource_filter-definition_email-audience.png)

Em vez de configurá-lo, basta inserir o valor desejado na caixa de diálogo exibida.

![](assets/custom_resource_filter-definition_email-audience_filter.png)

