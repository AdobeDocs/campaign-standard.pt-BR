---
title: Interface do editor de conteúdo da página de aterrissagem
seo-title: Interface do editor de conteúdo da página de aterrissagem
description: Interface do editor de conteúdo da página de aterrissagem
seo-description: Saiba como usar as diferentes seções do editor, como a barra de ações, para modificar o conteúdo da página de aterrissagem.
page-status-flag: nunca ativado
uuid: 53729a68-eed2-4c5d-bc14-02c80e897c44
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: concepção
content-type: referência
topic-tags: edição-página-inicial-conteúdo
discoiquuid: 08e2bda-e409-467f-b462-d74256dc6ebc
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 68d96b23f34f505c0a47a74a5e33bc3530fc4d72

---


# Interface do editor de conteúdo da página de aterrissagem{#landing-page-content-editor-interface}

O editor de conteúdo da página inicial permite que você defina, modifique e personalize facilmente o conteúdo no Adobe Campaign. Para acessá-lo, clique no **[!UICONTROL Content]** bloco em um painel da página de aterrissagem.

O editor de conteúdo é organizado em três seções diferentes. Essas seções permitem que você visualize e edite o conteúdo.

![](assets/des_lp_content_8.png)

1. A **paleta** no lado esquerdo da tela permite modificar as opções gerais vinculadas a um bloco selecionado. As opções que podem ser modificadas são: cor do plano de fundo, borda, alinhamento do texto, condição de visibilidade etc. Consulte [Inserir um campo](../../designing/using/personalization.md#inserting-a-personalization-field)de personalização.
1. A barra **de** ação contém as opções gerais para a página. Você pode selecionar um modelo e alterar o modo de exibição. Consulte Barra de ação do editor de página [de aterrissagem](../../channels/using/landing-page-content-editor-interface.md#landing-page-editor-action-bar).
1. A zona **de** edição principal permite interagir diretamente com o conteúdo usando a barra de ferramentas contextual: insira um link em uma imagem, altere a fonte, exclua um campo etc. Consulte Barra de ferramentas [do editor de página](../../channels/using/landing-page-content-editor-interface.md#landing-page-editor-toolbar)de aterrissagem.

## Barra de ação do editor de página inicial {#landing-page-editor-action-bar}

A barra de ações contém botões diferentes que permitem interagir com o conteúdo que está sendo criado.

![](assets/des_lp_content_9.png)

<table> 
 <thead> 
  <tr> 
   <th> Ícone<br /> </th> 
   <th> Nome do botão<br /> </th> 
   <th> Canal<br /> </th> 
   <th> Descrição<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <img height="21px" src="assets/download_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Alterar conteúdo</span><br /> </td> 
   <td> Página de aterrissagem e email<br /> </td> 
   <td> Permite que você selecione conteúdo pronto para uso ou importe seu próprio conteúdo HTML. Consulte <a href="../../designing/using/using-existing-content.md">Carregar um conteúdo</a>existente.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/undo_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Desfazer</span><br /> </td> 
   <td> Todos<br /> </td> 
   <td> Cancela a última ação realizada.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/redo_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Refazer</span><br /> </td> 
   <td> Todos<br /> </td> 
   <td> Refaz a última ação que você cancelou.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/display_block_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Mostrar blocos</span><br /> </td> 
   <td> Página de aterrissagem e email<br /> </td> 
   <td> Permite que você mostre as caixas ao redor dos blocos de conteúdo (corresponde à tag <strong>&lt;div&gt;</strong> HTML).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/code_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Mostrar origem</span><br /> </td> 
   <td> Página de aterrissagem e email<br /> </td> 
   <td> Permite que você mostre o código fonte HTML da página.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Barra de ferramentas do editor de página inicial {#landing-page-editor-toolbar}

A barra de ferramentas é um elemento **** contextual da interface do editor que oferece várias funcionalidades dependendo da zona selecionada. Ele contém botões de ação e botões que permitem alterar o estilo do texto. As modificações efetuadas aplicam-se sempre à zona selecionada. Depois de selecionar um bloco, você pode excluí-lo ou duplicá-lo, por exemplo. Depois de selecionar o texto dentro de um bloco, você pode transformá-lo em um link ou torná-lo negrito.

![](assets/delivery_content_17.png)

>[!CAUTION]
>
>Determinadas funções da barra de ferramentas permitem que você formate o conteúdo HTML. No entanto, se a página contiver uma folha de estilos CSS, as **instruções** da folha de estilos poderão provar ter **prioridade** sobre as instruções especificadas por meio da barra de ferramentas.

<table> 
 <thead> 
  <tr> 
   <th> Ícone<br /> </th> 
   <th> Nome do botão<br /> </th> 
   <th> Contexto<br /> </th> 
   <th> Descrição<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <img height="21px" src="assets/link_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Link para um URL</span> externo <br /> </td> 
   <td> Qualquer elemento<br /> </td> 
   <td> Permite adicionar um link a um URL. Detalhes de como configurar um link são apresentados na seção <a href="../../designing/using/links.md#inserting-a-link">Inserindo um link</a> .<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/linkpage_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Link para uma página</span> de aterrissagem <br /> </td> 
   <td> Qualquer elemento<br /> </td> 
   <td> Permite acessar uma página de aterrissagem do Adobe Campaign. Detalhes de como configurar um link são apresentados na seção <a href="../../designing/using/links.md#inserting-a-link">Inserindo um link</a> .<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/link_subscribe_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Link</span> de assinatura <br /> </td> 
   <td> Qualquer elemento<br /> </td> 
   <td> Permite inserir um link de assinatura de serviço. Detalhes de como configurar um link são apresentados na seção <a href="../../designing/using/links.md#inserting-a-link">Inserindo um link</a> .<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/link_unsubscribe_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Cancelar assinatura do link</span><br /> </td> 
   <td> Qualquer elemento<br /> </td> 
   <td> Permite inserir um link de cancelamento de assinatura do serviço. Detalhes de como configurar um link são apresentados na seção <a href="../../designing/using/links.md#inserting-a-link">Inserindo um link</a> .<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/linkoff_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Remover link</span><br /> </td> 
   <td> Link<br /> </td> 
   <td> Permite que você exclua o link, bem como todas as configurações vinculadas a ele, após a confirmação.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/personalization_field_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Inserir um campo</span> de personalização <br /> </td> 
   <td> Elemento de texto<br /> </td> 
   <td> Permite adicionar um campo do banco de dados ao conteúdo. Consulte <a href="../../designing/using/personalization.md#inserting-a-personalization-field">Inserir um campo</a>de personalização.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/personalization_block_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Inserir um bloco</span> de conteúdo <br /> </td> 
   <td> Elemento de texto<br /> </td> 
   <td> Permite adicionar um bloco de personalização ao conteúdo. Consulte <a href="../../designing/using/personalization.md#adding-a-content-block">Adicionar um bloco</a>de conteúdo.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/dynamiccontent_24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Ativar conteúdo</span> dinâmico <br /> </td> 
   <td> Elemento de texto<br /> </td> 
   <td> Permite inserir conteúdo dinâmico no conteúdo. Consulte <a href="../../channels/using/defining-dynamic-content-in-a-landing-page.md">Definição de conteúdo</a>dinâmico.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/dynamiccontentdisable_24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Desativar conteúdo</span> dinâmico <br /> </td> 
   <td> Elemento de texto<br /> </td> 
   <td> Permite excluir conteúdo dinâmico.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/increase_fontsize_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Aumentar fonte</span><br /> </td> 
   <td> Elemento de texto<br /> </td> 
   <td> Aumenta o tamanho do texto selecionado (adiciona <strong>&lt;span style="font-size:"&gt;</strong>).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/decrease_fontsize_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Reduzir fonte</span><br /> </td> 
   <td> Elemento de texto<br /> </td> 
   <td> Reduz o tamanho do texto selecionado (adiciona <strong>&lt;span style="font-size:"&gt;</strong>).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/textbold_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Negrito</span><br /> </td> 
   <td> Elemento de texto<br /> </td> 
   <td> Adiciona o estilo em negrito ao texto selecionado (quebra o texto com as tags <strong>&lt;strong&gt;</strong><strong>&lt;/strong&gt;</strong> ).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/textitalic_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Itálico</span><br /> </td> 
   <td> Elemento de texto<br /> </td> 
   <td> Adiciona o estilo em itálico ao texto selecionado (quebra o texto com as tags <strong>&lt;em&gt;</strong><strong>&lt;/em&gt;</strong> ).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/textunderline_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Sublinhado</span><br /> </td> 
   <td> Elemento de texto<br /> </td> 
   <td> Sublinha o texto selecionado (quebra o texto selecionado com a <strong>&lt;span style="text-decoration: underline;"&gt;</strong> tag).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/colorselector_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Alterar cor</span> de plano de fundo <br /> </td> 
   <td> Elemento de texto<br /> </td> 
   <td> Permite alterar a cor de plano de fundo do bloco selecionado (adiciona style="background-color: rgba(170, 86, 255, 0,87)).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/textcolor_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Alterar cor</span> da fonte <br /> </td> 
   <td> Elemento de texto<br /> </td> 
   <td> Permite alterar a cor de todo o texto do bloco ou apenas o texto selecionado no bloco (<strong>&lt;span style="color: #56ff56;"&gt;</strong>).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/image_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Imagem</span><br /> </td> 
   <td> Bloco que contém uma imagem<br /> </td> 
   <td> Permite inserir uma imagem de um arquivo salvo localmente.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/delete_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Excluir</span><br /> </td> 
   <td> Qualquer bloco<br /> </td> 
   <td> Exclui o bloco e seu conteúdo.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/duplicate_fontsize_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Duplicar</span><br /> </td> 
   <td> Qualquer bloco<br /> </td> 
   <td> Duplica o bloco, incluindo todos os estilos vinculados a ele.<br /> </td> 
  </tr> 
 </tbody> 
</table>

