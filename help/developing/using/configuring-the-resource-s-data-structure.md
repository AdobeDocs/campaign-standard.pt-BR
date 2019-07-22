---
title: Configuração da estrutura de dados do recurso
seo-title: Configuração da estrutura de dados do recurso
description: Configuração da estrutura de dados do recurso
seo-description: Saiba como configurar a estrutura dos dados.
page-status-flag: nunca ativado
uuid: 60 fe 80 c 0-9 df 6-4808-a 432-60 a 1977216 EA
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: adição ou extensão-a-resource
discoiquuid: 4 f 22 ee 35-1 d 5 f -4 c 75-95 b 4-3 e 38 b 85 de 26 e
context-tags: Cusresource, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6b642a58fc88779f88f2f860c133b36934c59d21

---


# Configuring the resource's data structure{#configuring-the-resource-s-data-structure}

Depois de criar um novo recurso personalizado, você deve configurar a estrutura dos dados.

When editing the resource, in the **[!UICONTROL Data structure]** tab, you can add:

* [Campos](../../developing/using/configuring-the-resource-s-data-structure.md#adding-fields-to-a-resource)
* [Teclas de identificação](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)
* [Índices](../../developing/using/configuring-the-resource-s-data-structure.md#defining-indexes)
* [Links](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources)
* [Envio de logs](../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension)

## Adding fields to a resource {#adding-fields-to-a-resource}

É possível adicionar novos campos a um recurso para armazenar dados que não fazem parte do modelo de dados da caixa.

1. Use the **[!UICONTROL Create element]** button to create a field.
1. Especifique um rótulo, uma ID, um tipo de campo e defina o comprimento máximo autorizado para esse campo.

   **[!UICONTROL ID]** O campo é obrigatório e deve ser exclusivo para cada campo adicionado.

   >[!NOTE]
   >
   >If you leave the **[!UICONTROL Label]** field empty, it will automatically be completed from the ID.
   >Recomendamos usar o máximo de 30 caracteres.

   ![](assets/schema_extension_4.png)

1. To modify one of the fields, check the **[!UICONTROL Edit Properties]** button.

   ![](assets/schema_extension_24.png)

1. In the **[!UICONTROL Field definition]** screen, you can define a category that will be used for the audience and targeting, or even add a description.

   ![](assets/schema_extension_5.png)

1. Check the **[!UICONTROL Specify a list of authorized values]** option if you need to define values that will be offered to the user (enumeration values).

   Then, click **[!UICONTROL Create element]** and specify a **[!UICONTROL Label]** and **[!UICONTROL Value]**. Adicione quantos valores forem necessários.

1. Once you have added your fields, check the **[!UICONTROL Add audit fields]** box to include fields detailing the creation date, the user that created the resource, the date, and the author of the last modification.
1. Check the **[!UICONTROL Add access authorization management fields]** box to include the fields stating who has access rights to that particular resource.

   Esses campos aparecem nos dados e metadados que podem ser exibidos depois que a atualização do banco de dados é realizada. For more on this, refer to the [Updating the database structure](../../developing/using/updating-the-database-structure.md) section.

1. Check the **[!UICONTROL Add automatic ID]** field to automatically generate an ID. Observe que as entidades existentes permanecerão vazias.
1. To modify the way in which the name of the resource elements will appear in the lists and creation steps, check the **[!UICONTROL Personalize the resource title]** box. Selecione um campo dos que você criou para este recurso.

   ![](assets/schema_extension_18.png)

Os campos de seu recurso agora são definidos.

## Defining identification keys {#defining-identification-keys}

Cada recurso deve ter pelo menos uma chave exclusiva. Por exemplo, você pode especificar uma chave para que dois produtos não possam ter a mesma ID em uma tabela de compra.

1. Specify it in the **[!UICONTROL Automatic primary key]** section the size for the storage if you would like to have a technical key automatically and incrementally generated.

   ![](assets/schema_extension_6.png)

1. Use the **[!UICONTROL Create element]** button to create a key.

   The **[!UICONTROL Label]** and **[!UICONTROL ID]** fields are completed by default but you can edit them.

   >[!NOTE]
   >
   >Recomendamos usar o máximo de 30 caracteres.

1. To define the elements making up this key, click **[!UICONTROL Create element]** and select the fields that you created for this resource.

   ![](assets/schema_extension_7.png)

   Created keys are displayed in the **[!UICONTROL Custom keys]** section.

Suas chaves de identificação para o recurso são criadas agora.

## Defining indexes {#defining-indexes}

Um índice pode fazer referência a um ou vários campos de recursos. Os índices permitem que o banco de dados classifique registros para recuperá-los com mais facilidade. Otimizam o desempenho das consultas SQL.

A definição de índices é recomendada, mas não obrigatória.

1. Use the **[!UICONTROL Create element]** button to create an index.

   ![](assets/schema_extension_26.png)

1. The **[!UICONTROL Label]** and **[!UICONTROL ID]** fields are completed by default, but you can edit them.

   >[!NOTE]
   >
   >Recomendamos usar o máximo de 30 caracteres.

1. Para definir os elementos que compõem esse índice, selecione os campos que você criou para este recurso.

   ![](assets/schema_extension_27.png)

1. Click **[!UICONTROL Confirm]**.

The indexes that were created appear in the list in the **[!UICONTROL Index]** section.

## Defining links with other resources {#defining-links-with-other-resources}

Um link detalha a associação que uma tabela possui com outras tabelas.

1. Use the **[!UICONTROL Create element]** button to create a link to a target resource.
1. Click **[!UICONTROL Select a target resource]**.

   ![](assets/schema_extension_28.png)

1. Os recursos são mostrados em ordem alfabética e podem ser filtrados por nome. Seu nome técnico é exibido entre parênteses.

   Select an element from the list and click **[!UICONTROL Confirm]**.

   ![](assets/schema_extension_9.png)

1. Select the **[!UICONTROL Link type]** according to cardinality. Dependendo do tipo de cardinalidade selecionado, o comportamento se os registros forem excluídos ou duplicados poderá variar.

   Os vários tipos de links são:

   * **[!UICONTROL 1 cardinality simple link]**: uma ocorrência da tabela de origem pode ter no máximo uma ocorrência correspondente da tabela de destino.
   * **[!UICONTROL N cardinality collection link]**: uma ocorrência da tabela de origem pode ter várias ocorrências correspondentes da tabela de destino, mas uma ocorrência da tabela de destino pode ter no máximo uma ocorrência correspondente da tabela de origem.
   * **[!UICONTROL 0 or 1 cardinality simple link]**: uma ocorrência da tabela de origem pode ter no máximo uma ocorrência correspondente da tabela de destino ou nenhum. Note that this kind of **[!UICONTROL Link type]** can cause performance issue.
   ![](assets/schema_extension_29.png)

1. In the **[!UICONTROL New link]** screen, the **[!UICONTROL Label]** and **[!UICONTROL ID]** fields are completed by default, but you can edit them.

   >[!NOTE]
   >
   >Recomendamos usar o máximo de 30 caracteres.

   >[!CAUTION]
   >
   >Não é possível renomear um link após a criação. Para renomear um link, você deve excluí-lo e criar novamente.

1. The **[!UICONTROL Category for the audience and targeting]** list allows you to assign this link to a category making it more visible in the query editor tool.
1. If needed, the **[!UICONTROL Reverse link definition]** section allows you to display the label and ID of the resource in the targeted resource.
1. Define the behavior of the records referenced by the link in the **[!UICONTROL Behavior if deleted/duplicated]** section.

   Por padrão, o registro de destino será excluído depois que não for mais mencionado pelo link.

   ![](assets/schema_extension_16.png)

1. In the **[!UICONTROL Join definition]** section, the default **[!UICONTROL Use the primary keys to make the join]** option is selected but you can choose between two options:

   * **[!UICONTROL Use the primary key to make the join]**: Essa definição de junção permite usar a chave primária dos perfis para se reconciliar com a chave primária das compras.
   * **[!UICONTROL Define specific join conditions]**: Essa definição de junção permite selecionar manualmente os campos que associarão ambos os recursos. Please note that if data are not correctly configured, the **Purchase** record will not be visible.
   ![](assets/schema_extension_17.png)

The links created are displayed in the list in the **[!UICONTROL Links]** section.

**Exemplo: Vincular um recurso criado com o recurso "Perfis"**

In this example, we want to link a new resource **Purchase** with the **Profiles **custom resource:

1. Create your new **Purchase** resource.
1. To link it with the **Profiles** custom resource, unfold the **[!UICONTROL Links]** section in the **[!UICONTROL Data structure]** tab and click **[!UICONTROL Create element]**.
1. Select the target resource, here **[!UICONTROL Profiles (profile)]**.
1. In this example, keep the default **[!UICONTROL 1 cardinality simple link]** Link type selected.

   ![](assets/custom_resource_link_to_profile_2.png)

1. Choose a join definition, here keep the default **[!UICONTROL Use the primary key to make the join]**.

   ![](assets/custom_resource_link_to_profile_3.png)

1. If needed, you can define a detail screen to be able to edit **Purchase** and link it to a profile.

   Unfold the **[!UICONTROL Detail screen configuration]** section and check the **[!UICONTROL Define a detail screen]** to configure the screen that corresponds to each element of the resource. Se você não marcar esta caixa, a exibição detalhada dos elementos desse recurso não estará acessível.

1. Click **[!UICONTROL Create element]**.
1. Select your linked resource and click **[!UICONTROL Add]**.

   Your new resource will then be available in the advanced menu by selecting **[!UICONTROL Client data]** &gt; **[!UICONTROL Purchase]**.

   ![](assets/custom_resource_link_to_profile_4.png)

1. Once your configuration is done, click **[!UICONTROL Confirm]**.

   Agora você pode publicar seu novo recurso.

By adding this link, a **Purchase** tab is added to the profiles detail screen from the **[!UICONTROL Profiles & audiences]** &gt; **[!UICONTROL Profiles]** menu. Please note that this is specific to the **[!UICONTROL Profile]** resource.

![](assets/custom_resource_link_to_profile.png)

## Defining sending logs extension {#defining-sending-logs-extension}

A extensão do log de envio permite:

* to extend dynamic report capabilities by **adding profile custom fields**
* to extend the sending logs data with **segment code and profile data**

**Estender com um código de segmento**

O usuário pode estender os registros com o código do segmento vindo do mecanismo de fluxo de trabalho.

O código do segmento deve ser definido no fluxo de trabalho.

To activate this extension, check the option **[!UICONTROL Add segment code]**.

![](assets/sendinglogsextension_1.png)

For more information on segment code, refer to the [Segmentation](../../automating/using/segmentation.md) section.

**Estender com um campo de perfil**

>[!NOTE]
>
>O administrador deve ter estendido o recurso de Perfil com um campo personalizado.

![](assets/sendinglogsextension_2.png)

Click **[!UICONTROL Add field]** and select any custom field from the profile resource.

In order to generate a new sub-dimension linked to the Profile dimension, check the **[!UICONTROL Add this field in Dynamic reporting as a new dimension]** option.

![](assets/sendinglogsextension_3.png)

Em Relatórios dinâmicos, você pode arrastar e soltar a dimensão de campo personalizado em uma tabela de forma livre.

For more information on Dynamic Reporting, refer to the [List of components](../../reporting/using/list-of-components-.md).

>[!CAUTION]
>
>O número de campos enviados para Relatórios dinâmicos é limitado a 20.

## Editing resource properties {#editing-resource-properties}

In the custom resource screen, the **[!UICONTROL Summary]** pane indicates the status of the newly created resource. Você pode gerenciar seu acesso e suas propriedades gerais.

![](assets/schema_extension_3.png)

1. Click the **[!UICONTROL Edit properties]** button to add a description.

   ![](assets/schema_extension_30.png)

1. Se necessário, modifique a etiqueta e a ID do recurso.

   >[!NOTE]
   >
   >Recomendamos usar o máximo de 30 caracteres.

1. Caso precise restringir o acesso a esse recurso em determinadas unidades organizacionais, especifique-as aqui. Somente usuários de unidades autorizadas poderão trabalhar com esse recurso no aplicativo.
1. Salve as modificações.

Suas modificações são salvas. É necessário publicar o recurso novamente para aplicá-los.

## Generating a unique ID for profiles and custom resources {#generating-a-unique-id-for-profiles-and-custom-resources}

Por padrão, perfis e recursos personalizados não têm ID de negócios quando são criados. Você pode habilitar uma opção que gera automaticamente uma ID exclusiva quando os elementos forem criados. Essa ID pode ser usada para:

* Identifique os registros exportados facilmente em uma ferramenta externa.
* Concilie registros ao importar dados atualizados processados em outro aplicativo.

Ele pode ser ativado apenas para perfis e recursos personalizados.

1. Crie uma extensão para o recurso de perfis ou crie um novo recurso.
1. In the data structure definition, check the **[!UICONTROL Add automatic ID field]** option, under the **[!UICONTROL Fields]** section.
1. Salve e publique a modificação feita no recurso. Se você quiser que esse mecanismo seja aplicado aos elementos criados pela API, verifique a opção para estender a API.

The **[!UICONTROL ACS ID]** field is now available and automatically populated when new elements are created manually, from the API, or inserted from an import workflow. O campo ID do ACS é um campo UUID e é indexado.

When exporting profiles or custom resources, you can now add the **[!UICONTROL ACS ID]** column if it has been enabled for that resource. Você pode reutilizar essa ID em suas ferramentas externas para identificar registros.

![](assets/export_id_field.png)

Ao re-importar dados que foram processados/atualizados em outro aplicativo (por exemplo, um CRM), você pode reconciliá-lo facilmente com essa ID exclusiva.

>[!NOTE]
>
>**[!UICONTROL ACS ID]** O campo não é atualizado para perfis ou elementos criados antes de ativar a opção. Apenas novos registros terão uma ID ACS. Este campo está no modo somente leitura. Não é possível modificá-lo.

