---
title: Interface do editor de conteúdo da página inicial
seo-title: Interface do editor de conteúdo da página inicial
description: Interface do editor de conteúdo da página inicial
seo-description: Saiba como usar as diferentes seções do editor, como a barra de ações, para modificar o conteúdo da página inicial.
page-status-flag: nunca ativado
uuid: 53729 a 68-eed 2d-bc 14-02 c 80 e 897 c 44
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: editing-landing-page-content
discoiquuid: 08 e 2 bbda-e 409-467 f-b 462-d 74256 dc 6 ebc
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 76c3d473f6cc7e825fdabadeec2405cb5c13abd1

---


# Landing page content editor interface{#landing-page-content-editor-interface}

O editor de conteúdo da página inicial permite definir, modificar e personalizar facilmente o conteúdo no Adobe Campaign. To access it, click the **[!UICONTROL Content]** block in a landing page dashboard.

O editor de conteúdo é organizado em três seções diferentes. Essas seções permitem exibir e editar o conteúdo.

![](assets/des_lp_content_8.png)

1. The **palette** on the left-hand side of the screen allows you to modify the general options linked to a selected block. As opções que podem ser modificadas são: cor do plano de fundo, borda, alinhamento de texto, condição de visibilidade etc. See [Inserting a personalization field](../../designing/using/inserting-a-personalization-field.md).
1. The **action bar** contains the general options for the page. Você pode selecionar um modelo e alterar o modo de exibição. See [Landing page editor action bar](../../designing/using/landing-page-content-editor-interface.md#landing-page-editor-action-bar).
1. The main **editing zone** allows you to directly interact with the content using the contextual toolbar: insert a link into an image, change the font, delete a field, etc. See [Landing page editor toolbar](../../designing/using/landing-page-content-editor-interface.md#landing-page-editor-toolbar).

## Landing page editor action bar {#landing-page-editor-action-bar}

A barra de ações contém botões diferentes que permitem interagir com o conteúdo que está sendo criado.

![](assets/des_lp_content_9.png)

<table> 
 <thead> 
  <tr> 
   <th> Icon<br /> </th> 
   <th> Button name<br /> </th> 
   <th> Channel<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <img height="21px" src="assets/download_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Alterar conteúdo</span><br /> </td> 
   <td> Landing page and email<br /> </td> 
   <td> Permite selecionar conteúdo predefinido ou importar seu próprio conteúdo HTML. Refer to <a href="../../designing/using/selecting-an-existing-content.md">Loading an existing content</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/undo_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Desfazer</span><br /> </td> 
   <td> All<br /> </td> 
   <td> Cancels the last action carried out.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/redo_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Refazer</span><br /> </td> 
   <td> All<br /> </td> 
   <td> Redoes the last action that you canceled.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/display_block_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Mostrar blocos</span><br /> </td> 
   <td> Landing page and email<br /> </td> 
   <td> Allows you to show the boxes around the content blocks (corresponds to the <strong>&lt;div&gt;</strong> HTML tag).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/code_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Mostrar fonte</span><br /> </td> 
   <td> Landing page and email<br /> </td> 
   <td> Allows you to show the HTML source code of the page.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Landing page editor toolbar {#landing-page-editor-toolbar}

The toolbar is a **contextual element** of the editor interface that offers various functionalities depending on the zone selected. Ele contém botões de ação e botões que permitem alterar o estilo do texto. As modificações executadas sempre se aplicam à zona selecionada. Depois de selecionar um bloco, você pode excluí-lo ou duplicá-lo por exemplo. Depois de selecionar o texto em um bloco, você pode transformá-lo em um link ou torná-lo negrito.

![](assets/delivery_content_17.png)

>[!CAUTION]
>
>Certas funções da barra de ferramentas permitem formatar o conteúdo HTML. However, if the page contains a CSS style sheet, the **instructions** from the style sheet may prove to take **priority** over the instructions specified via the toolbar.

<table> 
 <thead> 
  <tr> 
   <th> Icon<br /> </th> 
   <th> Button name<br /> </th> 
   <th> Context<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <img height="21px" src="assets/link_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Link para um URL externo</span><br /> </td> 
   <td> Any element<br /> </td> 
   <td> Permite adicionar um link a um URL. Details of how to configure a link are presented in the <a href="../../designing/using/inserting-a-link.md">Inserting a link</a> section.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/linkpage_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Link para uma página de aterrissagem</span><br /> </td> 
   <td> Any element<br /> </td> 
   <td> Permite acesso a uma página de aterrissagem do Adobe Campaign. Details of how to configure a link are presented in the <a href="../../designing/using/inserting-a-link.md">Inserting a link</a> section.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/link_subscribe_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Link para assinatura</span><br /> </td> 
   <td> Any element<br /> </td> 
   <td> Permite inserir um link de assinatura de serviço. Details of how to configure a link are presented in the <a href="../../designing/using/inserting-a-link.md">Inserting a link</a> section.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/link_unsubscribe_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Link Cancelar assinatura</span><br /> </td> 
   <td> Any element<br /> </td> 
   <td> Permite inserir um link de cancelamento de assinatura de serviço. Details of how to configure a link are presented in the <a href="../../designing/using/inserting-a-link.md">Inserting a link</a> section.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/linkoff_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Remover link</span><br /> </td> 
   <td> Link<br /> </td> 
   <td> Allows you to delete the link, as well as all the configurations linked to it, after confirming.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/personalization_field_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Inserir um campo de personalização</span><br /> </td> 
   <td> Text element<br /> </td> 
   <td> Permite adicionar um campo do banco de dados ao conteúdo. Refer to <a href="../../designing/using/inserting-a-personalization-field.md">Inserting a personalization field</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/personalization_block_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Inserir um bloco de conteúdo</span><br /> </td> 
   <td> Text element<br /> </td> 
   <td> Permite adicionar um bloco de personalização ao conteúdo. Refer to <a href="../../designing/using/adding-a-content-block.md">Adding a content block</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/dynamiccontent_24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Ativar conteúdo dinâmico</span><br /> </td> 
   <td> Text element<br /> </td> 
   <td> Permite inserir conteúdo dinâmico no conteúdo. Refer to <a href="../../designing/using/defining-dynamic-content-in-a-landing-page.md">Defining dynamic content</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/dynamiccontentdisable_24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Desativar conteúdo dinâmico</span><br /> </td> 
   <td> Text element<br /> </td> 
   <td> Allows you to delete dynamic content.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/increase_fontsize_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Aumentar fonte</span><br /> </td> 
   <td> Text element<br /> </td> 
   <td> Increases the size of the selected text (adds <strong>&lt;span style="font-size:"&gt;</strong>).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/decrease_fontsize_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Reduzir fonte</span><br /> </td> 
   <td> Text element<br /> </td> 
   <td> Reduces the size of the selected text (adds <strong>&lt;span style="font-size:"&gt;</strong>).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/textbold_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Negrito</span><br /> </td> 
   <td> Text element<br /> </td> 
   <td> Adds the bold style to the selected text (wraps the text with the <strong>&lt;strong&gt;</strong><strong>&lt;/strong&gt;</strong> tags).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/textitalic_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Itálico</span><br /> </td> 
   <td> Text element<br /> </td> 
   <td> Adds the italic style to the selected text (wraps the text with the <strong>&lt;em&gt;</strong><strong>&lt;/em&gt;</strong> tags).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/textunderline_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Sublinhado</span><br /> </td> 
   <td> Text element<br /> </td> 
   <td> Underlines the selected text (wraps the selected text with the <strong>&lt;span style="text-decoration: underline;"&gt;</strong> tag).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/colorselector_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Alterar a cor de fundo</span><br /> </td> 
   <td> Text element<br /> </td> 
   <td> Allows you to change the background color of the block selected (adds style="background-color: rgba(170, 86, 255, 0.87)).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/textcolor_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Alterar cor da fonte</span><br /> </td> 
   <td> Text element<br /> </td> 
   <td> Allows you to change the color of all the text in the block or just the text selected in the block (<strong>&lt;span style="color: #56ff56;"&gt;</strong>).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/image_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Imagem</span><br /> </td> 
   <td> Block containing an image<br /> </td> 
   <td> Allows you to insert an image from a file saved locally.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/delete_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Excluir</span><br /> </td> 
   <td> Any block<br /> </td> 
   <td> Deletes the block and its content.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/duplicate_fontsize_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Duplicar</span><br /> </td> 
   <td> Any block<br /> </td> 
   <td> Duplicates the block including any styles linked to it.<br /> </td> 
  </tr> 
 </tbody> 
</table>

