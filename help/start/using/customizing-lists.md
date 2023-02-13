---
title: Personalização de listas
description: "Saiba como personalizar a exibição e atuar em telas de lista no Adobe Campaign Standard: classificação, filtragem, exclusão ou duplicação de elementos. Lista as telas que exibem elementos de um ou vários recursos especificados."
audience: start
content-type: reference
topic-tags: discovering-the-interface
feature: Campaigns
role: User
level: Intermediate
exl-id: 651a53b4-e02f-4963-99e6-2e2c324b1c8c
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 1%

---

# Personalização de listas{#customizing-lists}

**Lista** telas permitem exibir elementos de um ou vários recursos específicos.

O Adobe Campaign tem dois tipos de listas:

* A **homogêneo** , que é quando contém um único tipo de recurso. Por exemplo, a lista de perfis contém apenas perfis.
* A **heterogêneo** , que é quando contém vários tipos de recursos. Por exemplo, a lista de atividades de marketing contém páginas de aterrissagem, fluxos de trabalho, emails, SMS, etc.

As listas são exibidas em colunas. Cada coluna pode ser classificada em ordem crescente ou decrescente, uma de cada vez.

Os elementos de uma lista têm uma caixa de seleção que permite selecioná-los. Ao selecionar um ou vários elementos, é possível realizar várias ações, como editar, duplicar e excluir esses elementos.

Ao passar o cursor do mouse sobre um elemento da lista, **ações rápidas**. Essas ações permitem que o usuário execute várias ações no elemento focalizado, como editar, selecionar, excluir ou mostrar detalhes.

![](assets/overview_list_quickactions.png)

Você também pode configurar se as colunas em uma lista devem ser exibidas ou não. Para adicionar ou remover colunas:

1. Certifique-se de que a tela está no **Lista** modo.

   ![](assets/export_list_mode_switch.png)

1. Vá para a janela de configuração da lista selecionando o ![](assets/columnsettings.png) na barra de ações.

   ![](assets/list_configuration1.png)

1. Adicione as colunas que deseja incluir na lista. Para fazer isso, selecione uma coluna no lado esquerdo da janela e use o ![](assets/arrowright.png) na barra de ações para adicionar uma coluna.

   As colunas selecionáveis correspondem ao recurso de lista.

   Para cada coluna adicionada, especifique se deseja aplicar a classificação por padrão:

   * **[!UICONTROL NO]**: Não há classificação na coluna
   * **[!UICONTROL ASC]**: Aplica uma classificação crescente (ascendente) na coluna
   * **[!UICONTROL DESC]**: Aplica uma classificação decrescente (decrescente) na coluna .

1. Exclua as colunas que você não deseja que sejam exibidas marcando as caixas correspondentes às colunas a serem excluídas. Em seguida, use o ![](assets/delete.png) na barra de ações para confirmar a exclusão.
1. Depois que a lista contiver as colunas corretas, você poderá alterar a ordem em que são exibidas na lista marcando as colunas que deseja mover. Em seguida, use o ![](assets/arrowdown.png) e ![](assets/arrowup.png) setas.
1. Confirme a configuração da lista selecionando **[!UICONTROL OK]**.

Sua lista agora é exibida conforme você a configurou.
