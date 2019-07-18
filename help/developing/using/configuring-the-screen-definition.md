---
title: Configuração da definição da tela
seo-title: Configuração da definição da tela
description: Configuração da definição da tela
seo-description: Saiba como definir novas telas do Adobe Campaign com base na estrutura dos dados de recursos.
page-status-flag: nunca ativado
uuid: 40848197-b 1 a 0-4018-bfc 3-7 df 64 fb 83307
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: adição ou extensão-a-resource
discoiquuid: 9 dabb 328-ac 0 c -49 fd -8996-8 d 56341 ee 7 ac
context-tags: Cusresource, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b3291f7c0cbede6a3180ad4a4ab8a365720f5031

---


# Configuring the screen definition{#configuring-the-screen-definition}

Ao criar um recurso ou ao adicionar novos campos a um recurso existente, você pode definir como deseja que eles sejam exibidos na interface.

Essa etapa não é obrigatória, pois você ainda poderá preencher seu recurso e acessar seus dados por meio de fluxos de trabalho, públicos-alvo e API REST.

In the **[!UICONTROL Screen definition]** tab, you can:

* Adicionar acesso ao recurso personalizado no painel de navegação
* Personalizar a forma como a lista de elementos que compõem o recurso é apresentada
* Defina a maneira como a exibição detalhada de cada elemento do recurso é exibida

## Enabling access from the navigation menu {#enabling-access-from-the-navigation-menu}

Se quiser que seu recurso tenha uma tela dedicada, você pode disponibilizá-lo no menu de navegação.

1. From the **[!UICONTROL Screen definition]** tab of the resource, unfold the **[!UICONTROL Navigation]** section.
1. Check the **[!UICONTROL Add an entry in the 'Client data' section]** box to allow access to this resource from the navigation pane.

   ![](assets/schema_extension_19.png)

The resource will appear as a sub-entry within the **[!UICONTROL Client data]** section.

## Defining the default list configuration {#defining-the-default-list-configuration}

The **[!UICONTROL List configuration]** section of the screen definition lets you define the columns and information that will be displayed by default in the overview of a resource.

1. Check the **[!UICONTROL Customize the list configuration]** box to define the way the columns of the resource are displayed.
1. Use the **[!UICONTROL Create element]** button to select a field from those that you have created.
1. O campo criado é exibido na lista. Você pode editar seu rótulo e sua largura.

   ![](assets/schema_extension_20.png)

1. In the **[!UICONTROL Simple search]** section, check the **[!UICONTROL Specify the fields to be taken into account in the search]** to define which fields will be included in the search.

   >[!CAUTION]
   >
   >Essa configuração substitui os campos usados na pesquisa padrão.

1. In the **[!UICONTROL Advanced filtering]** section, check the **[!UICONTROL Add search fields]** box to add additional fields beyond the simple search field. Por exemplo, se você selecionar o campo "data" nos campos criados, o usuário poderá realizar uma pesquisa que se refere somente à data.
1. É possível modificar a ordem dos campos para os dois tipos de pesquisa.
1. Para uma pesquisa avançada, é possível adicionar campos que vinculam a um recurso vinculado. These filters appear in the **[!UICONTROL Search]** menu of the generated screen.

A tela de visão geral do recurso agora é definida.

## Defining the detail screen configuration {#defining-the-detail-screen-configuration}

The **[!UICONTROL Detail screen configuration]** section of the screen definition lets you define the columns and information that will be displayed in the detail screen of each element of the resource.

1. Unfold the **[!UICONTROL Detail screen configuration]** section and check the **[!UICONTROL Define a detail screen]** to configure the screen that corresponds to each element of the resource. Se você não marcar esta caixa, a exibição detalhada dos elementos desse recurso não estará acessível.
1. Você pode adicionar todos os campos do recurso personalizado em um clique. To do this, click the ![](assets/addallfieldsicon.png) icon or use the **[!UICONTROL Add an element]** button.
1. Selecione um elemento das criadas para este recurso e especifique um tipo de campo:

   * **[!UICONTROL Input field]**: é um campo editável.
   * **[!UICONTROL Value]**: é um campo somente leitura.
   * **[!UICONTROL List]**: é uma tabela.
   * **[!UICONTROL Separator]**: divide seus elementos em categorias.
   ![](assets/schema_extension_23.png)

1. O elemento adicionado é exibido na lista. Você pode editar seu rótulo.

   ![](assets/schema_extension_22.png)

1. Add as many **[!UICONTROL Separator]** as needed to split your elements into different categories.

   Isso permite que você exiba separadores para organizar melhor suas janelas.

   ![](assets/schema_extension_25.png)

A tela de detalhes do recurso agora está configurada.

## Actions on data section {#actions-on-data-section}

Essas configurações permitem exibir uma barra de controle na tela de recurso personalizada. Há três opções disponíveis:

![](assets/schema_extension_actions.png)

* **[!UICONTROL Authorize creating]**: esta opção permite ativar a criação de elementos do recurso. O usuário pode, portanto, adicionar registros adicionais.

   >[!NOTE]
   >
   >Primeiro, você deve ativar a tela de detalhes vinculada ao recurso para tornar essa opção disponível.

* **[!UICONTROL Authorize duplicating]**: esta opção permite ativar registros duplicados vinculados ao recurso personalizado.
* **[!UICONTROL Authorize deleting]**: esta opção permite ativar a exclusão de registros vinculados ao recurso personalizado.

