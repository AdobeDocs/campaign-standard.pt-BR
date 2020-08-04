---
title: Design de uma landing page
description: Saiba como criar o conteúdo de uma página de aterrissagem.
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
translation-type: ht
source-git-commit: d762c73e6816011340a85a3cf2aaa35f05ee0541
workflow-type: ht
source-wordcount: '1662'
ht-degree: 100%

---


# Design de uma landing page{#designing-a-landing-page}

## Sobre o design de conteúdo de uma página de aterrissagem {#about-content-design}

Páginas de aterrissagem são criadas como qualquer [atividade de marketing](../../start/using/marketing-activities.md#about-marketing-activities).

Ao criar uma página de aterrissagem, é necessário definir o conteúdo da própria página, a página de confirmação e a página de erro. Use o alternador na barra de ações para exibir e configurar cada uma dessas páginas.

O conteúdo da página de aterrissagem é projetado por meio do editor de conteúdo do Campaign.

>[!NOTE]
>
>Se sua instância foi instalada antes da versão 19.0 do Adobe Campaign Standard, você ainda terá acesso ao editor herdado de conteúdo de email. A interface, os princípios de uso e a configuração são os mesmos descritos abaixo para páginas de aterrissagem. No entanto, todos os recursos podem não estar disponíveis ou mantidos no editor herdado de conteúdo de email, que foi substituído a partir da versão 19.0. Para editar rapidamente o conteúdo de email por meio de uma interface de arrastar e soltar com funcionalidades estendidas, use o [Designer de email](../../designing/using/designing-content-in-adobe-campaign.md).

Esta página descreve as especificidades do editor de conteúdo das páginas de aterrissagem. Para mais informações sobre as ações comuns a uma ou mais atividades de marketing, consulte estas seções do guia **Criação do conteúdo de email** l:

* [Inserção de um campo de personalização](../../designing/using/personalization.md#inserting-a-personalization-field)
* [Inclusão de um bloco de conteúdo](../../designing/using/personalization.md#adding-a-content-block).
* [Inserção de um link](../../designing/using/links.md#inserting-a-link).
* [Inserção de imagens](../../designing/using/images.md).
* [Práticas recomendadas gerais para design de conteúdo](../../designing/using/designing-content-in-adobe-campaign.md#content-design-best-practices).

>[!NOTE]
>Se você tiver uma página de aterrissagem que já esteja predefinida no formato HTML, poderá importá-la diretamente usando o botão **[!UICONTROL Change content]**.
>
>Antes de importar uma página HTML no Adobe Campaign, confirme que ela seja aberta e exibida corretamente nos diversos navegadores. Se a página HTML contiver scripts JavaScript, eles precisarão executar sem erros fora do editor. Em geral, evite usar scripts no conteúdo da mensagem para garantir que ele seja processado corretamente pelos clientes de email.

## Interface do editor de conteúdo de páginas de aterrissagem{#landing-page-content-editor-interface}

O editor de conteúdo de páginas de aterrissagem permite que você defina, modifique e personalize facilmente o conteúdo no Adobe Campaign. Para acessá-lo, clique no bloco **[!UICONTROL Content]** no painel de uma página de aterrissagem.

O editor de conteúdo é organizado em três seções diferentes. Estas seções permitem que você exiba e edite o conteúdo.

![](assets/des_lp_content_8.png)

1. A **paleta** no lado esquerdo da tela permite modificar as opções gerais vinculadas a um bloco selecionado. As opções que podem ser modificadas são: cor do plano de fundo, borda, alinhamento do texto, condição de visibilidade etc. Consulte [Inserção de um campo de personalização](../../designing/using/personalization.md#inserting-a-personalization-field).
1. A **barra de ação** contém as opções gerais da página. Você pode selecionar um modelo e alterar o modo de exibição.
1. A **zona de edição** principal permite interagir diretamente com o conteúdo usando a barra de ferramentas contextual: insira um link em uma imagem, altere a fonte, exclua um campo etc.

A **barra de ação** contém botões diferentes que permitem a interação com o conteúdo que está sendo criado.

![](assets/des_lp_content_9.png)

<table> 
 <thead> 
  <tr> 
   <th> Ícone<br /> </th> 
   <th> Nome do botão<br /> </th> 
   <th> Canal <br /> </th> 
   <th> Descrição<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <img height="21px" src="assets/download_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Alterar conteúdo</span> <br /> </td> 
   <td> Página de aterrissagem e email<br /> </td> 
   <td> Permite que você selecione conteúdo pronto para uso ou importe seu próprio conteúdo HTML. Consulte <a href="../../designing/using/using-existing-content.md">Carregamento de um conteúdo existente</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/undo_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Desfazer</span> <br /> </td> 
   <td> Todos<br /> </td> 
   <td> Cancela a última ação realizada.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/redo_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Refazer</span> <br /> </td> 
   <td> Todos<br /> </td> 
   <td> Refaz a última ação que você cancelou.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/display_block_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Mostrar blocos</span> <br /> </td> 
   <td> Página de aterrissagem e email<br /> </td> 
   <td> Permite que você mostre as caixas ao redor dos blocos de conteúdo (corresponde à tag HTML <strong>&lt;div&gt;</strong>).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/code_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Mostrar origem</span> <br /> </td> 
   <td> Página de aterrissagem e email<br /> </td> 
   <td> Permite que você mostre o código fonte HTML da página.<br /> </td> 
  </tr> 
 </tbody> 
</table>

A **barra de ferramentas** é um elemento contextual da interface do editor que oferece várias funcionalidades dependendo da zona selecionada. Ele contém botões de ação e botões que permitem alterar o estilo do texto. As modificações efetuadas aplicam-se sempre à zona selecionada. Após selecionar um bloco, você pode excluí-lo ou duplicá-lo, por exemplo. Após selecionar o texto dentro de um bloco, você pode transformá-lo em um link ou deixá-lo em negrito.

![](assets/delivery_content_17.png)

>[!CAUTION]
>
>Certas funções de barra de ferramentas permitem formatar o conteúdo HTML. No entanto, se a página contiver uma folha de estilos CSS, as **instruções** da folha de estilos podem provar ter **prioridade** sobre as instruções especificadas pela barra de ferramentas.

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
   <td> <span class="uicontrol">Link para um URL externo</span> <br /> </td> 
   <td> Qualquer elemento<br /> </td> 
   <td> Permite adicionar um link a um URL. Detalhes de como configurar um link são apresentados na seção <a href="../../designing/using/links.md#inserting-a-link">Inserção de um link</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/linkpage_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Link para uma página de aterrissagem</span> <br /> </td> 
   <td> Qualquer elemento<br /> </td> 
   <td> Permite acesso a uma página de aterrissagem do Adobe Campaign. Detalhes de como configurar um link são apresentados na seção <a href="../../designing/using/links.md#inserting-a-link">Inserção de um link</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/link_Subscribe_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Link de assinatura</span> <br /> </td> 
   <td> Qualquer elemento<br /> </td> 
   <td> Permite inserir um link de assinatura de serviço. Detalhes de como configurar um link são apresentados na seção <a href="../../designing/using/links.md#inserting-a-link">Inserção de um link</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/link_unSubscribe_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Link de cancelamento de assinatura</span>.<br /> </td> 
   <td> Qualquer elemento<br /> </td> 
   <td> Permite inserir um link de cancelamento de assinatura de serviço. Detalhes de como configurar um link são apresentados na seção <a href="../../designing/using/links.md#inserting-a-link">Inserção de um link</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/linkoff_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Remover link</span> <br /> </td> 
   <td> Link<br /> </td> 
   <td> Permite que você exclua o link, bem como todas as configurações vinculadas a ele após a confirmação.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/personalization_field_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Inserir um campo de personalização</span> <br /> </td> 
   <td> Elemento de texto<br /> </td> 
   <td> Permite adicionar um campo do banco de dados ao conteúdo. Consulte <a href="../../designing/using/personalization.md#inserting-a-personalization-field">Inserção de um campo de personalização</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/personalization_block_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Inserir um bloco de conteúdo</span> <br /> </td> 
   <td> Elemento de texto<br /> </td> 
   <td> Permite adicionar um bloco de personalização ao conteúdo. Consulte <a href="../../designing/using/personalization.md#adding-a-content-block">Inclusão de um bloco de conteúdo</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/dynamiccontent_24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Ativar conteúdo dinâmico</span> <br /> </td> 
   <td> Elemento de texto<br /> </td> 
   <td> Permite inserir conteúdo dinâmico no conteúdo. Consulte <a href="../../channels/using/designing-a-landing-page.md#defining-dynamic-content-in-a-landing-page">Definição de conteúdo dinâmico</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/dynamiccontentdisable_24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Desativar conteúdo dinâmico</span> <br /> </td> 
   <td> Elemento de texto<br /> </td> 
   <td> Permite excluir conteúdo dinâmico.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/increase_fontsize_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Ampliar fonte</span> <br /> </td> 
   <td> Elemento de texto<br /> </td> 
   <td> Aumenta o tamanho do texto selecionado (adiciona <strong>&lt;span style="font-size:"&gt;</strong>).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/decrease_fontsize_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Reduzir fonte</span> <br /> </td> 
   <td> Elemento de texto<br /> </td> 
   <td> Reduz o tamanho do texto selecionado (adiciona <strong>&lt;span style="font-size:"&gt;</strong>).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/textbold_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Negrito</span> <br /> </td> 
   <td> Elemento de texto<br /> </td> 
   <td> Adiciona o estilo em negrito ao texto selecionado (envolve o texto com as tags <strong>&lt;strong&gt;</strong><strong>&lt;/strong&gt;</strong> ).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/textitalic_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Itálico</span> <br /> </td> 
   <td> Elemento de texto<br /> </td> 
   <td> Adiciona o estilo em itálico ao texto selecionado (envolve o texto com as tags <strong>&lt;em&gt;</strong><strong>&lt;/em&gt;</strong> ).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/textunderline_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Sublinhado</span> <br /> </td> 
   <td> Elemento de texto<br /> </td> 
   <td> Sublinha o texto selecionado (envolve o texto selecionado com a tag <strong>&lt;span style="text-decoration: underline;"&gt;</strong> ).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/colorselector_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Alterar cor de plano de fundo</span> <br /> </td> 
   <td> Elemento de texto<br /> </td> 
   <td> Permite alterar a cor de plano de fundo do bloco selecionado (adiciona style="background-color: rgba(170, 86, 255, 0,87)).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/textcolor_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Alterar cor da fonte</span> <br /> </td> 
   <td> Elemento de texto<br /> </td> 
   <td> Permite alterar a cor de todo o texto do bloco ou apenas o texto selecionado no bloco (<strong>&lt;span style="color: #56ff56;"&gt;</strong>).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/image_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Imagem</span> <br /> </td> 
   <td> Bloco que contém uma imagem<br /> </td> 
   <td> Permite inserir uma imagem de um arquivo salvo localmente.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/delete_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Excluir</span> <br /> </td> 
   <td> Qualquer bloco<br /> </td> 
   <td> Exclui o bloco e seu conteúdo.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/duplicate_fontsize_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Duplicar</span> <br /> </td> 
   <td> Qualquer bloco<br /> </td> 
   <td> Duplica o bloco, incluindo todos os estilos vinculados a ele.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Gerenciamento da estrutura e do estilo da página de aterrissagem{#managing-landing-page-structure-and-style}

### Gerenciamento de blocos no editor de conteúdo {#managing-blocks-in-the-content-editor}

Os diferentes elementos de conteúdo HTML são exibidos na página de aterrissagem como blocos, correspondendo à tag **&lt;div>** **&lt;/div>**. Selecione um bloco para interagir com ele. Ele então será cercado por uma caixa azul.

![](assets/des_lp_content_1.png)

Se um bloco for selecionado, os objetos principais do elemento HTML correspondente serão exibidos em uma navegação estrutural localizada na parte inferior da zona de edição.

Quando o mouse passa sobre um dos elementos da navegação estrutural, o elemento em questão é realçado. Portanto, você pode navegar facilmente entre os diferentes blocos e selecionar exatamente o elemento HTML que deseja modificar.

![](assets/des_lp_content_2.png)

Use as opções da paleta e da barra de ferramentas contextual para modificar, excluir ou duplicar o bloco.

Para os blocos que contêm texto, clique novamente no bloco para ativar o modo de edição de texto. O quadro ao redor do bloco passa a ser verde. Em seguida, você pode selecionar ou inserir texto. Use as opções da paleta e da barra de ferramentas contextual para adicionar um link ou modificar a formatação do texto.

![](assets/des_lp_content_3.png)

Os parâmetros definidos para um elemento em um bloco (links, campos de personalização, blocos de conteúdo etc.) podem ser modificados a qualquer momento a partir da paleta.

![](assets/des_lp_content_4.png)

### Inclusão de uma borda e de um plano de fundo no editor de conteúdo {#adding-a-border-and-a-background-in-the-content-editor}

Você também pode definir uma **cor de plano de fundo** selecionando uma cor no gráfico. Essa cor é aplicada ao bloco selecionado.

![](assets/des_lp_content_5.png)

Você pode adicionar uma **borda** ao bloco selecionado.

![](assets/des_lp_content_6.png)

### Alteração do estilo do texto no editor de conteúdo {#changing-the-text-style-in-the-content-editor}

Para alterar o estilo do texto, é necessário clicar dentro de um bloco de texto.

Para alterar o alinhamento do texto, selecione um dos três ícones a seguir na paleta à esquerda:

![](assets/des_lp_content_7.png)

* **Alinhar à esquerda**: alinha o texto à esquerda do bloco selecionado (adiciona style=&quot;text-align: left;&quot;).
* **Centralizar**: centraliza o texto no bloco selecionado (adiciona style=&quot;text-align: center;&quot;).
* **Alinhar à direita**: alinha o texto à direita do bloco selecionado (adiciona style=&quot;text-align: right;&quot;).

Você também pode usar a barra de ferramentas para alterar os atributos da fonte: adapte o tamanho da fonte, deixe o texto em negrito ou itálico, sublinhe ou altere a cor do texto. Consulte [esta seção](../../channels/using/designing-a-landing-page.md#landing-page-content-editor-interface).

### Inserir imagens em uma página de aterrissagem {#inserting-images-in-a-landing-page}

1. Em um conteúdo de página de aterrissagem, selecione um bloco que contenha uma imagem.
1. Selecione o botão **[!UICONTROL Insert]**.

   ![](assets/des_insert_images_lp_1.png)

1. Escolha **[!UICONTROL Local image]** na barra de ferramentas contextual.

   ![](assets/des_insert_images_lp_2.png)

1. Selecione um arquivo.

   ![](assets/des_insert_images_lp_3.png)

1. Ajuste as propriedades da imagem conforme necessário.

   ![](assets/des_insert_images_lp_4.png)

## Definição de conteúdo dinâmico em uma página de aterrissagem{#defining-dynamic-content-in-a-landing-page}

Para definir o conteúdo dinâmico em uma página de aterrissagem, selecione um bloco usando a navegação estrutural ou clicando diretamente em um elemento.

![](assets/dynamic_content_lp_1.png)

Determinados blocos, como imagens, não podem ser selecionados diretamente. Nesse caso, selecione o bloco principal usando a navegação estrutural. Em seguida, você pode modificar todos os elementos incluídos nesse elemento principal, incluindo imagens. A condição será aplicada a todos os elementos secundários dentro do bloco principal.

A navegação estrutural é apresentada na seção [Gerenciamento de blocos](../../channels/using/designing-a-landing-page.md#managing-landing-page-structure-and-style).

As próximas etapas para definir o conteúdo dinâmico em uma página de aterrissagem são semelhantes às etapas a seguir para um email. Consulte [esta seção](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).

>[!NOTE]
>
>Se um elemento de variante for contornado em vermelho, significa que uma expressão ainda não foi definida.

É possível navegar entre os diferentes conteúdos dinâmicos de um bloco. Para fazer isso:

1. Selecione o bloco.

   Setas são exibidas nos lados direito e esquerdo da imagem.

1. Clique na seta direita para navegar pelos conteúdos dinâmicos disponíveis.

   ![](assets/dynamic_content_lp_2.png)

   As setas em cada lado escurecem conforme você atinge o último ou o primeiro conteúdo dinâmico disponível.

   ![](assets/dynamic_content_lp_3.png)

1. Para excluir todas as condições aplicadas a um bloco, selecione esse bloco e clique no ícone **[!UICONTROL Disable dynamic content]**.
1. Selecione o conteúdo dinâmico que deseja manter.

   ![](assets/dynamic_content_lp_5.png)

Na paleta:

* Os conteúdos que têm uma expressão inserida não são mais contornados em vermelho, mas são mostrados em cinza.
* O conteúdo atualmente selecionado aparece em azul.

![](assets/dynamic_content_lp_4.png)
