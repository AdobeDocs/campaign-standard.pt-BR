---
title: Gerenciamento de estilos
seo-title: Gerenciamento de estilos
description: Gerenciamento de estilos
seo-description: Descubra como gerenciar estilos de email no Designer de email.
page-status-flag: nunca ativado
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: concepção
content-type: referência
topic-tags: edição-email-conteúdo
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 45916918fc9e8008d4eb583a9c92886672c04b71

---


# Gerenciamento de estilos {#managing-styles}

## Editar estilos de email{#editing-email-styles}

### Editar um elemento {#editing-an-element}

No Designer de email, ao selecionar um elemento, várias opções específicas para o tipo de conteúdo selecionado são exibidas no **[!UICONTROL Settings]** painel. Você pode usar essas opções para alterar facilmente o estilo do seu email.

### Selecionar um elemento {#selecting-an-element}

Para selecionar um elemento na interface do Email Designer, é possível:

* clique diretamente no email,
* ou procure a árvore de estrutura disponível nas opções localizadas na **Paleta** esquerda.

![](assets/des_tree_structure.png)

A navegação na árvore de estrutura permite que você faça uma seleção mais precisa. Você pode selecionar:

* toda a componente da estrutura,
* uma das colunas que compõe o componente de estrutura,
* ou somente um componente localizado dentro de uma coluna.

![](assets/des_tree_structure_selection.png)

Para selecionar uma coluna, você também pode fazer o seguinte:

1. Selecione um componente de estrutura (diretamente no email ou usando a árvore de estrutura disponível na **Paleta** esquerda).
1. Na barra de ferramentas **contextual**, clique **[!UICONTROL Select a column]** para escolher a coluna desejada.

Veja um exemplo [nesta seção](../../designing/using/styles.md#example--adjusting-vertical-alignment-and-padding).

### Ajustar configurações de estilo {#adjusting-style-settings}

1. Selecione um elemento no seu email. Para obter mais informações, consulte [Seleção de um elemento](../../designing/using/styles.md#selecting-an-element).
1. Ajuste as configurações de acordo com suas necessidades. Cada elemento selecionado oferece um conjunto diferente de configurações.

   Você pode inserir planos de fundo, alterar tamanhos, modificar o alinhamento horizontal ou vertical, gerenciar cores, adicionar [preenchimento ou margem](../../designing/using/styles.md#selecting-an-element)e assim por diante.

   Para fazer isso, use as opções exibidas no **[!UICONTROL Settings]** painel ou [adicione atributos](../../designing/using/styles.md#adding-inline-styling-attributes)de estilização em linha.

   ![](assets/des_settings_pane.png)

1. Salve o conteúdo.

### Sobre preenchimento e margem {#about-padding-and-margin}

A interface do Designer de email permite que você ajuste rapidamente as configurações de preenchimento e margem.

**[!UICONTROL Padding]**: essa configuração permite gerenciar o espaço localizado dentro da borda de um elemento.

![](assets/des_padding.png)

Por exemplo:

* Use o preenchimento para definir margens nos lados esquerdo e direito de uma imagem.
* Use o preenchimento superior e inferior para adicionar mais espaçamento a um componente **[!UICONTROL Text]** ou a um **[!UICONTROL Divider]** .
* Para definir bordas entre colunas dentro de um elemento de estrutura, defina o preenchimento para cada coluna.

**[!UICONTROL Margin]**: essa configuração permite gerenciar o espaço entre a borda do elemento e o próximo elemento.

![](assets/des_margin.png)

>[!NOTE]
>
>Dependendo da sua seleção (componente de estrutura, coluna ou componente de conteúdo), o resultado não será o mesmo. A Adobe recomenda definir os parâmetros **[!UICONTROL Padding]** e **[!UICONTROL Margin]** no nível da coluna.

Para ambos **[!UICONTROL Padding]** e **[!UICONTROL Margin]**, clique no ícone de cadeado para quebrar a sincronização entre os parâmetros superior e inferior ou direito e esquerdo. Isso permite ajustar cada parâmetro separadamente.

![](assets/des_padding_lock_icon.png)

### Sobre o alinhamento {#about-alignment}

* **Alinhamento** do texto: coloque o cursor do mouse sobre um texto e use a barra de ferramentas contextual para alinhá-lo.

   ![](assets/des_text_alignment.png)

* **O alinhamento** horizontal pode ser aplicado ao texto, imagens e botões - atualmente não aos componentes **[!UICONTROL Divider]** e **[!UICONTROL Social]** .

   ![](assets/des_horizontal_alignment.png)

* Para definir o alinhamento **** vertical, selecione uma coluna dentro de um componente de estrutura e escolha uma opção no painel Configurações.

   ![](assets/des_set_vertical_alignment.png)

### Sobre planos de fundo {#about-backgrounds}

Quando se trata de configurar planos de fundo com o Email Designer, a Adobe recomenda o seguinte:

1. Aplique uma cor de plano de fundo ao corpo do seu email, se exigido pelo seu design.
1. Na maioria dos casos, defina as cores do plano de fundo no nível da coluna.
1. Tente não usar as cores de plano de fundo em componentes de imagem ou texto, pois elas são difíceis de gerenciar.

Abaixo estão as configurações de plano de fundo disponíveis que você pode usar.

* Defina um **[!UICONTROL Background color]** para o email inteiro. Selecione as configurações de corpo na árvore de navegação acessível na paleta esquerda.

   ![](assets/des_background_body.png)

* Defina a mesma cor de plano de fundo para todos os componentes da estrutura selecionando **[!UICONTROL Viewport background color]**. Essa opção permite selecionar uma configuração diferente da cor do plano de fundo.

   ![](assets/des_background_viewport.png)

* Defina uma cor de plano de fundo diferente para cada componente de estrutura. Selecione uma estrutura na árvore de navegação acessível na paleta esquerda para aplicar uma cor de plano de fundo específica somente a essa estrutura.

   ![](assets/des_background_structure.png)

   Certifique-se de não definir uma cor de plano de fundo do visor, pois ela pode ocultar as cores de plano de fundo da estrutura.

* Defina um **[!UICONTROL Background image]** para o conteúdo de um componente de estrutura.

   ![](assets/des_background_image.png)

   >[!NOTE]
   >
   >Alguns programas de email não suportam imagens de fundo. Certifique-se de selecionar uma cor de plano de fundo de fallback apropriada caso a imagem não possa ser exibida.

* Defina uma cor de plano de fundo no nível da coluna.

   ![](assets/des_background_column.png)

   >[!NOTE]
   >
   >Este é o caso de uso mais comum. A Adobe recomenda configurar as cores de plano de fundo no nível da coluna, pois isso permite mais flexibilidade ao editar todo o conteúdo do email.

   Também é possível definir uma imagem de plano de fundo no nível da coluna, mas isso raramente é usado.

#### Exemplo: ajuste do alinhamento vertical e do preenchimento {#example--adjusting-vertical-alignment-and-padding}

Você deseja ajustar o preenchimento e o alinhamento vertical dentro de um componente de estrutura composto de três colunas. Para fazer isso, siga as etapas abaixo:

1. Selecione o componente de estrutura diretamente no email ou usando a árvore de estrutura disponível na **Paleta** esquerda.
1. Na barra de ferramentas **contextual**, clique **[!UICONTROL Select a column]** e escolha a que deseja editar. Também é possível selecioná-lo na árvore de estrutura.

   ![](assets/des_selecting_column.png)

   Os parâmetros editáveis para essa coluna são exibidos no **[!UICONTROL Settings]** painel à direita.

1. Em **[!UICONTROL Vertical alignment]**, selecione **[!UICONTROL Up]**.

   ![](assets/des_vertical_alignment.png)

   O componente de conteúdo é exibido na parte superior da coluna.

1. Em **[!UICONTROL Padding]**, defina o preenchimento superior dentro da coluna. Clique no ícone de bloqueio para interromper a sincronização com o preenchimento inferior.

   Defina o preenchimento à esquerda e à direita para essa coluna.

   ![](assets/des_adjusting_padding.png)

1. Proceda de forma semelhante para ajustar o alinhamento e o preenchimento das outras colunas.

   ![](assets/des_adjusting_columns.png)

1. Salve as alterações.

### Sobre links de estilização {#about-styling-links}

>[!NOTE]
>
>Esse recurso estará disponível a partir da versão 19.4 do Campaign Standard.

Você pode sublinhar um link e selecionar sua cor e destino no Designer de email.

1. Em um componente onde um link é inserido, selecione o texto do rótulo do link.

1. Nas configurações do componente, marque **[!UICONTROL Underline link]** para sublinhar o texto da etiqueta do link.

   ![](assets/stylelinks-selecttext.png)

1. Para selecionar em qual contexto de navegação seu link será aberto, selecione um **[!UICONTROL Target]**.

   ![](assets/stylelinks-target.png)

1. Para alterar a cor do link, clique em **[!UICONTROL Link color]**.

   ![](assets/stylelinks-colorpicker.png)

1. Escolha a cor de que precisa.

   ![](assets/stylelinks-colorchanged.png)

1. Salve as alterações.

### Adicionar atributos de estilo em linha {#adding-inline-styling-attributes}

Na interface do Email Designer, ao selecionar um elemento e exibir suas configurações no painel lateral, você pode personalizar os atributos em linha e seus valores para esse elemento específico.

1. Selecione um elemento no seu conteúdo.
1. No painel lateral, procure as **[!UICONTROL Styles Inline]** configurações.

   ![](assets/email_designer_inlineattributes.png)

1. Modifique os valores dos atributos existentes ou adicione novos usando o botão **+** . Você pode adicionar qualquer atributo e valor que seja compatível com CSS.

O estilo é aplicado ao elemento selecionado. Se os elementos filho não tiverem atributos de estilo específicos definidos, o estilo do elemento pai será herdado.

## Alternar para exibição móvel {#switching-to-mobile-view}

Você pode ajustar o design responsivo de um email editando separadamente todas as opções de estilo para exibição móvel. Por exemplo, você pode adaptar margens e preenchimento, usar tamanhos de fonte menores ou maiores, alterar botões ou aplicar cores de fundo diferentes que serão específicas para a versão móvel do seu email.

Todas as opções de estilo estão disponíveis na exibição móvel. As configurações de estilo do Designer de email são apresentadas na seção [Edição de estilos](../../designing/using/styles.md) de email.

1. Crie um email e comece a editar o conteúdo. Para obter mais informações, consulte [Criar um conteúdo de email do zero](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).
1. Para acessar a exibição móvel dedicada, selecione o **[!UICONTROL Switch to mobile view]** botão.

   ![](assets/email_designer_mobile_view_switch.png)

   A versão móvel do email é exibida. Ele contém todos os componentes e estilos definidos na exibição da área de trabalho.

1. Edite independentemente todas as configurações de estilo, como cor do plano de fundo, alinhamento, preenchimento, margem, família de fontes, cor do texto e assim por diante.

   ![](assets/email_designer_mobile_view.png)

1. Ao editar qualquer configuração de estilo na exibição móvel, as modificações são aplicadas somente à exibição móvel.

   Por exemplo, reduza o tamanho de uma imagem, adicione um plano de fundo verde e altere o preenchimento na exibição móvel.

   ![](assets/email_designer_mobile_view_change.png)

1. Você pode ocultar um componente quando exibido em um dispositivo móvel. Para fazer isso, selecione **[!UICONTROL Show only on desktop devices]** no **[!UICONTROL Display options]**.
Você também pode ocultar esse componente em dispositivos de desktop, o que significa que ele será exibido somente em dispositivos móveis. Para fazer isso, selecione **[!UICONTROL Show only on mobile devices]**.
Por exemplo, essa opção permite que você exiba uma imagem específica em dispositivos móveis e outra imagem em dispositivos desktop.
Você pode definir essa opção na exibição móvel ou na exibição da área de trabalho.

   ![](assets/email_designer_mobile_hide.png)

1. Clique novamente no **[!UICONTROL Switch to mobile view]** botão para voltar à exibição padrão da área de trabalho. As mudanças de estilo que você acabou de fazer não são refletidas.

   ![](assets/email_designer_mobile_view_desktop_no-change.png)

   >[!NOTE]
   >
   >A única exceção são as **[!UICONTROL Style inline]** configurações. Qualquer alteração na configuração em linha de estilo também é aplicada à exibição padrão da área de trabalho.

1. Qualquer outra alteração na estrutura ou no conteúdo do email, como edições de texto, upload de uma nova imagem, adição de um novo componente etc. também é aplicado à exibição padrão.

   Por exemplo, volte para a exibição móvel, edite algum texto e substitua uma imagem.

   ![](assets/email_designer_mobile_view_change_content.png)

   Clique novamente no **[!UICONTROL Switch to mobile view]** botão para voltar à exibição padrão da área de trabalho. As mudanças são refletidas.

   ![](assets/email_designer_mobile_view_desktop_content-change.png)

1. Remover um estilo na exibição móvel leva você de volta ao estilo que foi aplicado no modo desktop.

   Por exemplo, na exibição móvel, aplique uma cor de plano de fundo verde a um botão.

   ![](assets/email_designer_mobile_view_background_mobile.png)

1. Alterne para a exibição da área de trabalho e aplique um plano de fundo cinza ao mesmo botão.

   ![](assets/email_designer_mobile_view_background_desktop.png)

1. Alterne novamente para exibição móvel e desative a **[!UICONTROL Background color]** configuração.

   ![](assets/email_designer_mobile_view_background_mobile_disabled.png)

   A cor de fundo definida na exibição da área de trabalho agora é aplicada: fica cinza (não em branco).

   A única exceção é a **[!UICONTROL Border color]** configuração. Quando desativada na exibição móvel, nenhuma borda é mais aplicada, mesmo se uma cor de borda for definida na exibição da área de trabalho.

>[!NOTE]
>
>A exibição móvel não está disponível em [fragmentos](../../designing/using/using-reusable-content.md#about-fragments).
