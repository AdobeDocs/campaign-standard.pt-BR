---
title: Configuração da definição da tela
description: Saiba como definir novas telas de Adobe Campaign com base na estrutura de dados de recursos.
page-status-flag: never-activated
uuid: 40848197-b1a0-4018-bfc3-7df64fb83307
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
discoiquuid: 9dabb328-ac0c-49fd-8996-8d56341ee7ac
context-tags: cusResource,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8852adb5edeb42eba1acf2911c988071104f1401

---


# Configuração da definição da tela{#configuring-the-screen-definition}

Ao criar um recurso ou ao adicionar novos campos a um recurso existente, você pode definir como deseja que eles apareçam na interface.

Esta etapa não é obrigatória, pois você ainda poderá preencher seu recurso e acessar seus dados por meio de workflows, audiência e REST API.

Na **[!UICONTROL Screen definition]** guia, é possível:

* Adicionar acesso ao recurso personalizado no painel de navegação
* Personalizar a forma como a lista de elementos que compõem o recurso é apresentada
* Definir a forma como a visualização detalhada de cada elemento do recurso é exibida

## Ativação do acesso no menu de navegação {#enabling-access-from-the-navigation-menu}

Se quiser que seu recurso tenha uma tela dedicada, você pode disponibilizá-la no menu de navegação.

1. Na **[!UICONTROL Screen definition]** guia do recurso, desenhe a **[!UICONTROL Navigation]** seção.
1. Marque a **[!UICONTROL Add an entry in the 'Client data' section]** caixa para permitir o acesso a este recurso a partir do painel de navegação.

   ![](assets/schema_extension_19.png)

O recurso será exibido como uma subentrada na **[!UICONTROL Client data]** seção.

## Definição da configuração de lista padrão {#defining-the-default-list-configuration}

A **[!UICONTROL List configuration]** seção da definição de tela permite definir as colunas e as informações que serão exibidas por padrão na visão geral de um recurso.

1. Marque a **[!UICONTROL Customize the list configuration]** caixa para definir a forma como as colunas do recurso são exibidas.
1. Use o **[!UICONTROL Create element]** botão para selecionar um campo dentre os que você criou.
1. O campo criado é exibido na lista. Você pode editar seu rótulo e sua largura.

   ![](assets/schema_extension_20.png)

1. Na **[!UICONTROL Simple search]** seção, marque o para definir **[!UICONTROL Specify the fields to be taken into account in the search]** quais campos serão incluídos na pesquisa.

   >[!IMPORTANT]
   >
   >Essa configuração substitui os campos usados na pesquisa padrão.

1. Na **[!UICONTROL Advanced filtering]** seção, marque a **[!UICONTROL Add search fields]** caixa para adicionar campos adicionais além do campo de pesquisa simples. Por exemplo, se você selecionar o campo &quot;data&quot; nos campos criados, o usuário poderá realizar uma pesquisa que se refere apenas à data.
1. É possível modificar a ordem dos campos para os dois tipos de pesquisa.
1. Para uma pesquisa avançada, você pode adicionar campos que se vinculam a um recurso vinculado. Esses filtros são exibidos no **[!UICONTROL Search]** menu da tela gerada.

A tela de visão geral do recurso agora está definida.

## Definição da configuração detalhada da tela {#defining-the-detail-screen-configuration}

A **[!UICONTROL Detail screen configuration]** seção da definição de tela permite definir as colunas e as informações que serão exibidas na tela de detalhes de cada elemento do recurso.

1. Desdobre a **[!UICONTROL Detail screen configuration]** seção e marque a tela **[!UICONTROL Define a detail screen]** para configurar a tela que corresponde a cada elemento do recurso. Se você não marcar essa caixa, a visualização detalhada dos elementos deste recurso não estará acessível.
1. É possível adicionar todos os campos do recurso personalizado com um clique. Para fazer isso, clique no ![](assets/addallfieldsicon.png) ícone ou use o **[!UICONTROL Add an element]** botão.
1. Selecione um elemento dentre os criados para este recurso e especifique um tipo de campo:

   * **[!UICONTROL Input field]**: é um campo editável.
   * **[!UICONTROL Value]**: é um campo somente leitura.
   * **[!UICONTROL List]**: é uma mesa.
   * **[!UICONTROL Separator]**: divide seus elementos em categorias.
   ![](assets/schema_extension_23.png)

1. O elemento adicionado é exibido na lista. Você pode editar seu rótulo.

   ![](assets/schema_extension_22.png)

1. Adicione quantos forem necessários **[!UICONTROL Separator]** para dividir seus elementos em categorias diferentes.

   Isso permite que você exiba separadores para melhor organizar suas janelas.

   ![](assets/schema_extension_25.png)

A tela de detalhes do recurso agora está configurada.

## Ações na seção de dados {#actions-on-data-section}

Essas configurações permitem exibir uma barra de controle na tela de recursos personalizados. Há três opções disponíveis:

![](assets/schema_extension_actions.png)

* **[!UICONTROL Authorize creating]**: essa opção permite ativar a criação de elementos do recurso. O usuário pode, portanto, adicionar registros adicionais.

   >[!NOTE]
   >
   >Primeiro, ative a tela de detalhes vinculada ao recurso para disponibilizar essa opção.

* **[!UICONTROL Authorize duplicating]**: essa opção permite ativar registros duplicados vinculados ao recurso personalizado.
* **[!UICONTROL Authorize deleting]**: essa opção permite ativar a exclusão de registros vinculados ao recurso personalizado.
