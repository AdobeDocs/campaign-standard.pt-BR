---
title: Gerenciamento de estilos de email
description: Descubra como gerenciar estilos de email no Designer de email.
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: 8daeb12d-4170-464f-ba33-afb681f72a91
source-git-commit: 5435e1dbfbe08399c488322320ac5bb8e681a79d
workflow-type: tm+mt
source-wordcount: '1038'
ht-degree: 26%

---

# Gerenciamento de estilos de email {#managing-styles}


No Designer Email, ao selecionar um elemento, várias opções específicas para o tipo de conteúdo selecionado são exibidas no painel **[!UICONTROL Settings]**. Você pode usar essas opções para alterar facilmente o estilo do seu email.

## Selecionar um elemento {#selecting-an-element}

Para selecionar um elemento na interface do Email Designer, é possível:

* clique diretamente no email,
* ou procure a árvore de estrutura disponível nas opções localizadas na **Paleta** esquerda.

![](assets/des_tree_structure.png)

Navegar pela árvore de estrutura permite fazer uma seleção mais precisa. É possível selecionar:

* a componente de estrutura completa,
* uma das colunas que compõem o componente de estrutura,
* ou somente um componente localizado em uma coluna.

![](assets/des_tree_structure_selection.png)

Para selecionar uma coluna, você também pode fazer o seguinte:

1. Selecione um componente de estrutura (diretamente no email ou usando a árvore de estrutura disponível na **Paleta** esquerda).
1. Na **barra de ferramentas contextual**, clique em **[!UICONTROL Select a column]** para escolher a coluna desejada.

Veja um exemplo em [esta seção](#example--adjusting-vertical-alignment-and-padding).

## Ajuste das configurações de estilo {#adjusting-style-settings}

1. Selecione um elemento no seu email. Para obter mais informações, consulte [Seleção de um elemento](#selecting-an-element).
1. Ajuste as configurações de acordo com suas necessidades. Cada elemento selecionado oferece um conjunto diferente de configurações.

   Você pode inserir planos de fundo, alterar tamanhos, modificar o alinhamento horizontal ou vertical, gerenciar cores, adicionar [preenchimento ou margem](#selecting-an-element) e assim por diante.

   Para fazer isso, use as opções exibidas no painel **[!UICONTROL Settings]** ou [adicione atributos de estilo embutidos](#adding-inline-styling-attributes).

   ![](assets/des_settings_pane.png)

1. Salve o conteúdo.

## Ajustar o preenchimento e a margem {#about-padding-and-margin}

A interface Email Designer permite ajustar rapidamente as configurações de preenchimento e margem.

**[!UICONTROL Padding]**: essa configuração permite gerenciar o espaço localizado dentro da borda de um elemento.

![](assets/des_padding.png)

Por exemplo:

* Use o preenchimento para definir as margens nos lados esquerdo e direito de uma imagem.
* Use o preenchimento superior e inferior para adicionar mais espaçamento a um componente **[!UICONTROL Text]** ou **[!UICONTROL Divider]**.
* Para definir bordas entre colunas dentro de um elemento de estrutura, defina o preenchimento para cada coluna.

**[!UICONTROL Margin]**: essa configuração permite gerenciar o espaço entre a borda do elemento e o próximo elemento.

![](assets/des_margin.png)

>[!NOTE]
>
>Dependendo da sua seleção (componente de estrutura, coluna ou componente de conteúdo), o resultado não será o mesmo. O Adobe recomenda definir os parâmetros **[!UICONTROL Padding]** e **[!UICONTROL Margin]** no nível da coluna.

Para **[!UICONTROL Padding]** e **[!UICONTROL Margin]**, clique no ícone de bloqueio para interromper a sincronização entre os parâmetros superior e inferior ou direito e esquerdo. Isso permite ajustar cada parâmetro separadamente.

![](assets/des_padding_lock_icon.png)

## Alinhamento de estilo {#about-alignment}

* **Alinhamento de texto**: coloque o cursor do mouse em algum texto e use a barra de ferramentas contextual para alinhá-lo.

  ![](assets/des_text_alignment.png)

* **O alinhamento horizontal** pode ser aplicado ao texto, às imagens e aos botões; no momento, não se aplica aos componentes **[!UICONTROL Divider]** e **[!UICONTROL Social]**.

  ![](assets/des_horizontal_alignment.png)

* Para definir o **alinhamento vertical**, selecione uma coluna dentro de um componente de estrutura e escolha uma opção no painel Configurações.

  ![](assets/des_set_vertical_alignment.png)

## Configuração de planos de fundo {#about-backgrounds}

>[!CONTEXTUALHELP]
>id="ac_edition_backgroundimage"
>title="Configurações de fundo"
>abstract="O Designer de email permite que você personalize a cor do fundo ou a imagem do fundo para o seu conteúdo. Observe que a imagem do fundo não é compatível com todos os clientes de email."

Quando se trata de definir planos de fundo com o Designer de email, a Adobe recomenda o seguinte:

1. Aplique uma cor de fundo ao corpo do email se isso for necessário para o design.
1. Na maioria dos casos, defina as cores do plano de fundo no nível da coluna.
1. Tente não usar as cores de fundo em componentes de imagem ou texto, pois isso dificulta o gerenciamento.

Veja abaixo as configurações de fundo disponíveis para uso.

* Defina um **[!UICONTROL Background color]** para o email inteiro. Certifique-se de selecionar as configurações de corpo na árvore de navegação acessível na Paleta esquerda.

  ![](assets/des_background_body.png)

* Defina a mesma cor de fundo para todos os componentes da estrutura selecionando **[!UICONTROL Viewport background color]**. Essa opção permite selecionar uma configuração de cor de fundo diferente.

  ![](assets/des_background_viewport.png)

* Defina uma cor de fundo diferente para cada componente da estrutura. Selecione uma estrutura na árvore de navegação acessível na Paleta esquerda para aplicar uma cor de fundo específica somente a essa estrutura.

  ![](assets/des_background_structure.png)

  Certifique-se de não definir uma cor de fundo do visor, pois isso pode ocultar as cores de fundo da estrutura.

* Defina um **[!UICONTROL Background image]** para o conteúdo de um componente de estrutura.

  ![](assets/des_background_image.png)

  >[!NOTE]
  >
  >Alguns programas de email não são compatíveis com imagens de fundo. Quando não houver suporte, a cor do plano de fundo da linha será usada. Certifique-se de selecionar uma cor de fundo sobressalente apropriada caso a imagem não possa ser exibida.

* Definir uma cor de fundo no nível da coluna.

  ![](assets/des_background_column.png)

  >[!NOTE]
  >
  >Esse é o caso de uso mais comum. A Adobe recomenda configurar as cores de fundo no nível da coluna, pois isso permite mais flexibilidade ao editar todo o conteúdo do email.

  Também é possível definir uma imagem de fundo no nível da coluna, mas isso raramente é usado.

### Exemplo: ajuste do alinhamento vertical e do preenchimento {#example--adjusting-vertical-alignment-and-padding}

Você deseja ajustar o preenchimento e o alinhamento vertical dentro de um componente de estrutura composto por três colunas. Para fazer isso, siga as etapas abaixo:

1. Selecione o componente de estrutura diretamente no email ou usando a árvore de estrutura disponível na **Paleta** esquerda.
1. Na **barra de ferramentas contextual**, clique em **[!UICONTROL Select a column]** e escolha a que deseja editar. Também é possível selecioná-la na árvore de estrutura.

   ![](assets/des_selecting_column.png)

   Os parâmetros editáveis para essa coluna são exibidos no painel **[!UICONTROL Settings]** à direita.

1. Em **[!UICONTROL Vertical alignment]**, selecione **[!UICONTROL Up]**.

   ![](assets/des_vertical_alignment.png)

   O componente de Conteúdo é exibido na parte superior da coluna.

1. Em **[!UICONTROL Padding]**, defina o preenchimento superior dentro da coluna. Clique no ícone de bloqueio para interromper a sincronização com o preenchimento inferior.

   Defina o preenchimento esquerdo e direito para essa coluna.

   ![](assets/des_adjusting_padding.png)

1. Proceda de forma semelhante para ajustar o alinhamento e o preenchimento das outras colunas.

   ![](assets/des_adjusting_columns.png)

1. Salve as alterações.

## Links de estilo {#about-styling-links}

É possível sublinhar um link e selecionar a cor e o público alvo no Designer de email.

1. Em um componente em que um link é inserido, selecione o texto do rótulo do seu link.

1. Nas configurações do componente, marque **[!UICONTROL Underline link]** para sublinhar o texto do rótulo do seu link.

   ![](assets/stylelinks-selecttext.png)

1. Para selecionar em qual contexto de navegação seu link será aberto, selecione um **[!UICONTROL Target]**.

   ![](assets/stylelinks-target.png)

1. Para alterar a cor do seu link, clique em **[!UICONTROL Link color]**.

   ![](assets/stylelinks-colorpicker.png)

1. Escolha a cor necessária.

   ![](assets/stylelinks-colorchanged.png)

1. Salve as alterações.

## Adição de atributos de estilo em linha {#adding-inline-styling-attributes}

Na interface do Designer de email, ao selecionar um elemento e exibir suas configurações no painel lateral, você pode personalizar os atributos em linha e seus valores para esse elemento específico.

1. Selecione um elemento no seu conteúdo.
1. No painel lateral, procure as configurações de **[!UICONTROL Styles Inline]**.

   ![](assets/email_designer_inlineattributes.png)

1. Modifique os valores dos atributos existentes ou adicione novos usando o botão **+**. É possível adicionar qualquer atributo e valor que seja compatível com CSS.

O estilo é aplicado ao elemento selecionado. Se os elementos derivados não tiverem atributos de estilo específicos definidos, o estilo do elemento principal será herdado.
