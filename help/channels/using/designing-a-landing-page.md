---
title: Criação de uma página de aterrissagem
description: Saiba como projetar o conteúdo de uma página de aterrissagem.
page-status-flag: never-activated
uuid: de6fe190-835c-40fd-8101-a809b430b423
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: bd77d6f0-3143-4030-a91b-988a2bebc534
context-tags: landingPage,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d762c73e6816011340a85a3cf2aaa35f05ee0541

---


# Criação de uma página de aterrissagem{#designing-a-landing-page}

## Sobre o design do conteúdo da página de aterrissagem {#about-content-design}

As páginas de aterrissagem são criadas como qualquer atividade [de marketing](../../start/using/marketing-activities.md#about-marketing-activities).

Ao projetar uma página de aterrissagem, é necessário definir o conteúdo da própria página, a página de confirmação e a página de erro. Use o alternador na barra de ações para exibir e configurar cada uma dessas páginas.

O conteúdo das páginas iniciais foi projetado pelo editor de conteúdo do Campaign.

>[!NOTE]
>
>Se sua instância foi instalada antes da versão 19.0 do Adobe Campaign Standard, você ainda terá acesso ao editor de conteúdo de email herdado. A interface, os princípios de uso e configuração são os mesmos descritos abaixo para as páginas iniciais. No entanto, todos os recursos podem não estar disponíveis ou mantidos no editor de conteúdo de e-mail herdado, que foi substituído a partir da versão 19.0. Para editar rapidamente seu conteúdo de email por meio de uma interface de arrastar e soltar com funcionalidades estendidas, use o [Email Designer](../../designing/using/designing-content-in-adobe-campaign.md).

Esta página descreve as especificidades do editor de conteúdo da página inicial. Para obter mais informações sobre as ações comuns a uma ou mais atividades de marketing, consulte estas seções no guia **Criar conteúdo** de email:

* [Inserção de um campo de personalização](../../designing/using/personalization.md#inserting-a-personalization-field)
* [Adicionar um bloco](../../designing/using/personalization.md#adding-a-content-block)de conteúdo.
* [Inserção de um link](../../designing/using/links.md#inserting-a-link).
* [Inserção de imagens](../../designing/using/images.md).
* [Práticas recomendadas gerais para o design](../../designing/using/designing-content-in-adobe-campaign.md#content-design-best-practices)de conteúdo.

>[!NOTE]
>Se você tiver uma página de aterrissagem que já esteja predefinida no formato HTML, poderá importá-la diretamente usando o **[!UICONTROL Change content]**botão.
>
>Antes de importar uma página HTML no Adobe Campaign, verifique se ela é aberta e exibida corretamente em vários navegadores. Se a página HTML contiver scripts JavaScript, eles precisarão executar sem erros fora do editor. Em geral, evite usar scripts no conteúdo da mensagem para garantir que ele seja processado corretamente pelos clientes de email.

## Interface do editor de conteúdo da página de aterrissagem{#landing-page-content-editor-interface}

O editor de conteúdo da página inicial permite que você defina, modifique e personalize facilmente o conteúdo no Adobe Campaign. Para acessá-lo, clique no **[!UICONTROL Content]**bloco em um painel da página de aterrissagem.

O editor de conteúdo é organizado em três seções diferentes. Essas seções permitem que você visualize e edite o conteúdo.

![](assets/des_lp_content_8.png)

1. A **paleta** no lado esquerdo da tela permite modificar as opções gerais vinculadas a um bloco selecionado. As opções que podem ser modificadas são: cor do plano de fundo, borda, alinhamento do texto, condição de visibilidade etc. See [Inserting a personalization field](../../designing/using/personalization.md#inserting-a-personalization-field).
1. A barra **de** ação contém as opções gerais para a página. Você pode selecionar um modelo e alterar o modo de exibição.
1. A zona **de** edição principal permite interagir diretamente com o conteúdo usando a barra de ferramentas contextual: insira um link em uma imagem, altere a fonte, exclua um campo etc.

A barra **de** ação contém botões diferentes que permitem interagir com o conteúdo que está sendo criado.

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

A **barra** de ferramentas é um elemento contextual da interface do editor que oferece várias funcionalidades dependendo da zona selecionada. Ele contém botões de ação e botões que permitem alterar o estilo do texto. As modificações efetuadas aplicam-se sempre à zona selecionada. Depois de selecionar um bloco, você pode excluí-lo ou duplicá-lo, por exemplo. Depois de selecionar o texto dentro de um bloco, você pode transformá-lo em um link ou torná-lo negrito.

![](assets/delivery_content_17.png)

>[!CAUTION]
>
>Certas funções de barra de ferramentas permitem formatar o conteúdo HTML. However, if the page contains a CSS style sheet, the **instructions** from the style sheet may prove to take **priority** over the instructions specified via the toolbar.

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
   <td> <img height="21px" src="assets/link_Subscribe_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Link</span> de assinatura <br /> </td> 
   <td> Qualquer elemento<br /> </td> 
   <td> Permite inserir um link de assinatura de serviço. Detalhes de como configurar um link são apresentados na seção <a href="../../designing/using/links.md#inserting-a-link">Inserindo um link</a> .<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/link_unSubscribe_darkgrey-24px.png" /> <br /> </td> 
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
   <td> Permite inserir conteúdo dinâmico no conteúdo. Consulte <a href="../../channels/using/designing-a-landing-page.md#defining-dynamic-content-in-a-landing-page">Definição de conteúdo</a>dinâmico.<br /> </td> 
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

## Gerenciamento da estrutura e do estilo da página inicial{#managing-landing-page-structure-and-style}

### Gerenciamento de blocos no editor de conteúdo {#managing-blocks-in-the-content-editor}

Os diferentes elementos de conteúdo HTML são exibidos na página inicial como blocos, correspondendo à tag **&lt;div>** **&lt;/div>** . Selecione um bloco para interagir com ele. Será então cercada por uma caixa azul.

![](assets/des_lp_content_1.png)

Se um bloco for selecionado, os objetos pai do elemento HTML correspondente serão exibidos em uma trilha de navegação localizada na parte inferior da zona de edição.

Quando o mouse passa sobre um dos elementos da navegação estrutural, o elemento em questão é realçado. Portanto, você pode navegar facilmente entre os diferentes blocos e selecionar exatamente o elemento HTML que deseja modificar.

![](assets/des_lp_content_2.png)

Use as opções da paleta e da barra de ferramentas contextual para modificar, excluir ou duplicar o bloco.

Para os blocos que contêm texto, clique novamente no bloco para ativar o modo de edição de texto. O quadro ao redor do bloco fica verde. Em seguida, você pode selecionar ou inserir texto. Use as opções da paleta e da barra de ferramentas contextual para adicionar um link ou modificar a formatação do texto.

![](assets/des_lp_content_3.png)

Os parâmetros definidos para um elemento em um bloco (links, campos de personalização, blocos de conteúdo etc.) pode ser modificada a qualquer momento a partir da paleta.

![](assets/des_lp_content_4.png)

### Adicionar uma borda e um plano de fundo no editor de conteúdo {#adding-a-border-and-a-background-in-the-content-editor}

You can also define a **background color** by selecting a color from the chart. Essa cor é aplicada ao bloco selecionado.

![](assets/des_lp_content_5.png)

You can add a **border** to the selected block.

![](assets/des_lp_content_6.png)

### Alteração do estilo do texto no editor de conteúdo {#changing-the-text-style-in-the-content-editor}

Para alterar o estilo do texto, é necessário clicar dentro de um bloco de texto.

Para alterar o alinhamento do texto, selecione um dos três ícones a seguir na paleta à esquerda:

![](assets/des_lp_content_7.png)

* **Alinhar à esquerda**: alinha o texto à esquerda do bloco selecionado (adiciona style=&quot;text-alignment: esquerda;&quot;).
* **Centro**: centraliza o texto no bloco selecionado (adiciona style=&quot;text-alignment: centro;&quot;).
* **Alinhar à direita**: alinha o texto à direita do bloco selecionado (adiciona style=&quot;text-alignment: right;&quot;).

Você também pode usar a barra de ferramentas para alterar os atributos da fonte: adapte o tamanho da fonte, coloque o texto em negrito ou itálico, sublinhe ou altere a cor do texto. Consulte [esta seção](../../channels/using/designing-a-landing-page.md#landing-page-content-editor-interface).

### Inserir imagens em uma página de aterrissagem {#inserting-images-in-a-landing-page}

1. Em um conteúdo de página inicial, selecione um bloco que contenha uma imagem.
1. Selecione o **[!UICONTROL Insert]**botão.

   ![](assets/des_insert_images_lp_1.png)

1. Escolha **[!UICONTROL Local image]**na barra de ferramentas contextual.

   ![](assets/des_insert_images_lp_2.png)

1. Selecione um arquivo.

   ![](assets/des_insert_images_lp_3.png)

1. Ajuste as propriedades da imagem conforme necessário.

   ![](assets/des_insert_images_lp_4.png)

## Definição de conteúdo dinâmico em uma página de aterrissagem{#defining-dynamic-content-in-a-landing-page}

Para definir o conteúdo dinâmico em uma página de aterrissagem, selecione um bloco usando a navegação estrutural ou clicando diretamente em um elemento.

![](assets/dynamic_content_lp_1.png)

Determinados blocos, como imagens, não podem ser selecionados diretamente. Nesse caso, selecione o bloco pai usando a navegação estrutural. Em seguida, você pode modificar todos os elementos incluídos nesse elemento pai, incluindo imagens. A condição será aplicada a todos os elementos filho dentro do bloco pai.

A navegação estrutural é apresentada na seção [Gerenciamento de blocos](../../channels/using/designing-a-landing-page.md#managing-landing-page-structure-and-style) .

As próximas etapas para definir o conteúdo dinâmico em uma página inicial são semelhantes às etapas a seguir para um email. Consulte [esta seção](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).

>[!NOTE]
>
>Se um elemento de variante for contornado em vermelho, isso significa que uma expressão ainda não foi definida.

É possível navegar entre os diferentes conteúdos dinâmicos de um bloco. Para fazer isso:

1. Selecione o bloco.

   As setas são exibidas nos lados direito e esquerdo da imagem.

1. Clique na seta para a direita para navegar pelo conteúdo dinâmico disponível.

   ![](assets/dynamic_content_lp_2.png)

   As setas em cada lado escurecem de acordo com se você atingiu o último ou o primeiro conteúdo dinâmico disponível.

   ![](assets/dynamic_content_lp_3.png)

1. Para excluir todas as condições aplicadas a um bloco, selecione-o e clique no **[!UICONTROL Disable dynamic content]**ícone.
1. Selecione o conteúdo dinâmico que deseja manter.

   ![](assets/dynamic_content_lp_5.png)

Na paleta:

* Os conteúdos que têm uma expressão inserida não são mais contornados em vermelho, mas exibidos em cinza.
* O conteúdo atualmente selecionado aparece em azul.

![](assets/dynamic_content_lp_4.png)
