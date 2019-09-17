---
title: 'Criar emails usando conteúdo existente '
seo-title: 'Criar emails usando conteúdo existente '
description: 'Criar emails usando conteúdo existente '
seo-description: Descubra como projetar emails usando conteúdo de email existente no Designer de email.
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
source-git-commit: a7de545e9eec675444245576cddc6eaf8dce05f4

---

# Criar usando conteúdo existente {#designing-using-existing-content}

## Selecionar um conteúdo existente{#selecting-an-existing-content}

O Adobe Campaign vem com um conjunto de conteúdos predefinidos para ajudá-lo a começar. Você pode usar uma dessas opções ou, se o conteúdo da mensagem que você precisa enviar estiver sendo preparado fora do Adobe Campaign, você pode importá-lo do seu computador ou de um URL.

Ao criar um email ou uma página inicial, você pode optar por carregar um conteúdo existente de outra fonte.

>[!NOTE]
>
>As imagens abaixo mostram como carregar um conteúdo existente usando o [Email Designer](../../designing/using/overview.md).

1. Depois de criar o email ou a página de aterrissagem, abra o conteúdo.
1. Clique no ícone inicial para acessar a página **[!UICONTROL Email Designer]** inicial.

   ![](assets/des_loading_1.png)

1. Selecione a origem do conteúdo que deseja carregar:

   * [Modelos](../../designing/using/using-reusable-content.md#content-templates)de conteúdo: clique na **[!UICONTROL Templates]** guia.
   * [Conteúdo do zero](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch), para começar fresco: clique no **[!UICONTROL Create]** botão.
   * [Conteúdo do seu computador como um arquivo](../../designing/using/using-existing-content.md#importing-content-from-a-file)ZIP ou HTML: clique no **[!UICONTROL Upload]** botão.
   * [Conteúdo de um URL](../../designing/using/using-existing-content.md#importing-content-from-a-url) existente (somente para e-mails): clique no **[!UICONTROL Import from URL]** botão.
   ![](assets/des_loading_2.png)

1. Carregue o conteúdo. O conteúdo selecionado substitui o conteúdo atual.

   Depois de importado, o conteúdo pode ser editado e personalizado.

   >[!NOTE]
   >
   >O [Email Designer](../../designing/using/overview.md) usa marcação específica. O conteúdo HTML padrão carregado no Campaign deve corresponder à marcação esperada para ser totalmente compatível e editável no Designer de email. Se não for correspondente, seu conteúdo será carregado no modo [de](../../designing/using/using-existing-content.md#compatibility-mode)compatibilidade. Para tornar o conteúdo existente compatível, consulte [esta seção](../../designing/using/using-existing-content.md#editing-existing-contents-with-the-email-designer).

**Tópicos relacionados:**

* [Criação de um email](../../channels/using/creating-an-email.md)
* [Gerenciamento de páginas de aterrissagem](../../channels/using/about-landing-pages.md)

## Editar conteúdo existente com o Designer de email{#editing-existing-contents-with-the-email-designer}

Para aproveitar totalmente as possibilidades de edição do [Email Designer](../../designing/using/overview.md), seu HTML carregado deve conter tags específicas que o tornem compatível com o editor WYSIWYG.

Se todo o HTML ou parte dele não tiver essa marcação, o conteúdo será carregado no "modo [de](../../designing/using/using-existing-content.md#compatibility-mode)compatibilidade".

Para tornar um conteúdo externo existente totalmente editável no Designer de email, consulte a seção [Projetando um email usando o conteúdo](../../designing/using/using-existing-content.md) existente.

## Importação {#importing}

### Importar conteúdo de um arquivo {#importing-content-from-a-file}

Na página inicial do Email Designer, clique no **[!UICONTROL Upload]** botão para fazer upload de um arquivo do computador e, em seguida, confirme.

Não há restrições na estrutura do arquivo zip. No entanto, a referência a arquivos HTML deve ser relativa e respeitar a estrutura em árvore da pasta zip.

Os seguintes formatos são suportados para importação:

* Um arquivo HTML com uma folha de estilos incorporada
* Uma pasta .zip contendo o arquivo HTML, a folha de estilos (.CSS) e as imagens

>[!NOTE]
>
>Para conteúdo de email, recomendamos que você importe arquivos HTML únicos com uma folha de estilos incorporada.

#### Importar conteúdo de um URL {#importing-content-from-a-url}

Antes de importar o conteúdo de um URL, certifique-se de seguir os requisitos abaixo:

* O conteúdo precisa estar publicamente disponível por meio deste URL.
* Por motivos de segurança, somente URLs que começam com **[!UICONTROL https]** são permitidos.
* Verifique se todos os recursos (imagens, CSS) estão definidos em links absolutos e em HTTPS. Caso contrário, após o envio do email, a página espelhada seria exibida sem seus recursos. Este é um exemplo de uma definição de link absoluta:

   ```
   <a href="https://www.mywebsite.com/images/myimage.png">
   ```

>[!NOTE]
>
>O carregamento de conteúdo de um URL está disponível somente para o canal de email.

Para recuperar o conteúdo existente de um URL, siga as etapas abaixo:

1. Na página inicial do Email Designer, selecione o **[!UICONTROL Import from URL]** botão.

   ![](assets/email_designer_importfromurl.png)

1. Defina o URL do qual o conteúdo será recuperado.
1. Click **[!UICONTROL Confirm]**.

**Tópico relacionado:**

[Importar conteúdo de um vídeo de URL](https://helpx.adobe.com/campaign/kt/acs/using/acs-email-designer-tutorial.html#Workingwithexistingcontent)

### Recuperar conteúdo de um URL automaticamente no momento da preparação {#retrieving-content-from-a-url-automatically-at-preparation-time}

A importação de conteúdo de um URL durante a preparação da mensagem permite que você recupere o conteúdo HTML mais recente sempre que o email for preparado. Dessa forma, o conteúdo de emails recorrentes é sempre atualizado no momento do envio. Esse recurso também permite que você crie uma mensagem programada em uma data específica, mesmo se o conteúdo ainda não estiver pronto.

Para recuperar o conteúdo no momento da preparação, siga as etapas abaixo:

1. Selecione a **[!UICONTROL Content imported during preparation]** opção.

   ![](assets/email_designer_importfromurl2.png)

1. O conteúdo do URL é exibido no editor como somente leitura.

   >[!CAUTION]
   >
   >Nesta etapa, a exibição HTML no editor de conteúdo não deve ser considerada. Será recuperado na fase de preparação.

1. Para visualizar o conteúdo do URL que foi recuperado, abra a mensagem depois de criada e clique no **[!UICONTROL Preview]** botão.

É possível personalizar o URL remoto do qual o conteúdo será recuperado. Para fazer isso, siga as etapas abaixo:

1. Clique no rótulo de e-mail na parte superior da tela para acessar a **[!UICONTROL Properties]** guia Email Designer.
1. Encontre o **[!UICONTROL Remote URL]** campo.

   ![](assets/email_designer_importfromurl4.png)

1. Insira o campo de personalização, o bloco de conteúdo ou o texto dinâmico desejados.

   O bloco de **[!UICONTROL Current date - YYYYMMDD]** conteúdo, por exemplo, permite inserir a data do dia.

   >[!NOTE]
   >
   >Os campos de personalização disponíveis são vinculados somente aos atributos de **entrega** (data de criação do email, status, rótulo da campanha...).

### Modo de compatibilidade {#compatibility-mode}

Quando você carrega um conteúdo, ele deve conter uma marcação específica para ser totalmente compatível e editável com o editor WYSIWYG do Designer de email.

Se todo ou parte do HTML carregado não for compatível com a marcação esperada, o conteúdo será carregado em "modo de compatibilidade", o que limita as possibilidades de edição por meio da interface do usuário.

Quando um conteúdo é carregado no modo de compatibilidade, você ainda pode executar as seguintes modificações por meio da interface (as ações não disponíveis estão ocultas):

* Alteração do texto ou alteração de uma imagem
* Inserção de links e campos de personalização
* Editar algumas opções de estilização no bloco HTML selecionado
* Definição de conteúdo condicional

![](assets/email_designer_compatibility.png)

Outras modificações, como adicionar novas seções ao seu email ou estilo avançado, devem ser feitas diretamente no código fonte do email por meio do modo HTML.

Para obter mais informações sobre como converter um email existente em um email compatível com o Designer de email, consulte [esta seção](../../designing/using/using-existing-content.md).

**Tópico** relacionado:

* [Criação de um email](../../channels/using/creating-an-email.md)
* [Vídeo de introdução ao Email Designer](https://video.tv.adobe.com/v/22771/?autoplay=true&hidetitle=true&captions=por_br)
* [Criar um conteúdo de email do zero](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)

## Converter um conteúdo HTML {#converting-an-html-content}

Se quiser criar uma estrutura de modelos modulares e fragmentos que podem ser combinados para reutilização em vários emails, considere converter seu HTML de email em um modelo do Designer de email.

Este caso de uso oferece uma maneira rápida de converter um email HTML em componentes do Email Designer.

>[!CAUTION]
>
>Esta seção destina-se a usuários avançados familiarizados com o código HTML.

>[!NOTE]
>
>Como o modo de compatibilidade, um componente HTML é editável com opções limitadas: você só pode executar edição no local.

Fora do Designer de email, verifique se o HTML original está dividido em seções reutilizáveis.

Se esse não for o caso, recorte os diferentes blocos do seu HTML.  Por exemplo:

```
<!-- 3 COLUMN w/CTA (SCALED) -->
<table width="100%" align="center" cellspacing="0" cellpadding="0" border="0" role="presentation" style="max-width:680px;">
<tbody>
<tr>
<td class="padh10" align="center" valign="top" style="padding:0 5px 20px 5px;">
<table width="100%" cellspacing="0" cellpadding="0" border="0" role="presentation">
<tbody>
<tr>
...
</tr>
</tbody>
</table>
</td>
</tr>
</tbody>
</table>
<!-- //3 COLUMN w/CTA (SCALED) -->
```

Depois de identificar todos os blocos, no Designer de email, repita o seguinte procedimento para cada seção do email existente:

1. Abra o Designer de email para criar um conteúdo de email vazio.
1. Defina os atributos de nível de corpo: cores de fundo, largura, etc. Para obter mais informações, consulte [Edição de estilos](../../designing/using/styles.md)de email.
1. Adicione um componente de estrutura. Para obter mais informações, consulte [Edição da estrutura](../../designing/using/designing-from-scratch.md#defining-the-email-structure)de email.
1. Adicione um componente HTML. Para obter mais informações, consulte [Adicionar fragmentos e componentes](../../designing/using/designing-from-scratch.md#defining-the-email-structure).
1. Copie e cole seu HTML nesse componente.
1. Alternar para exibição móvel. Para obter mais informações, consulte [esta seção](../../designing/using/styles.md#switching-to-mobile-view).

   A exibição responsiva está quebrada, pois seu CSS está ausente.

1. Para corrigir isso, alterne para o modo de código fonte e copie e cole sua seção de estilo em uma nova seção de estilo.  Por exemplo:

   ```
   <style type="text/css">
   a {text-decoration:none;}
   body {min-width:100% !important; margin:0 auto !important; padding:0 !important;}
   img {line-height:100%; text-decoration:none; -ms-interpolation-mode:bicubic;}
   ...
   </style>
   ```

   >[!NOTE]
   >
   >Não modifique o CSS gerado pelo Designer de email: `<style acrite-template-css="true">` e `<style acrite-custom-styles="" type="text/css">`. Depois disso, adicione seu estilo.

1. Retorne à exibição móvel para verificar se o conteúdo é exibido corretamente e salvar as alterações.
