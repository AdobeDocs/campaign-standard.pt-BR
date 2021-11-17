---
title: 'Criar emails usando conteúdo existente '
description: Descubra como criar emails usando conteúdo de email existente no Designer de email.
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: 3bda4227-2a6e-4813-a288-93a4388a9787
source-git-commit: 0d645de54106d49452a846ee650335607dbf21d3
workflow-type: tm+mt
source-wordcount: '1282'
ht-degree: 6%

---

# Design com conteúdo existente {#designing-using-existing-content}

## Seleção de conteúdo existente{#selecting-an-existing-content}

O Adobe Campaign vem com um conjunto de conteúdos predefinidos para ajudá-lo a começar. Você pode usar uma dessas opções ou, se o conteúdo da mensagem que você precisa enviar estiver sendo preparado fora do Adobe Campaign, poderá importá-lo do seu computador ou de um URL.

Ao criar um email ou uma landing page, você pode optar por carregar um conteúdo existente de outra fonte.

>[!NOTE]
>
>As imagens abaixo mostram como carregar um conteúdo existente usando o [Email Designer](../../designing/using/designing-content-in-adobe-campaign.md).

1. Após criar o email ou a landing page, abra o conteúdo.
1. Clique no ícone inicial para acessar o **[!UICONTROL Email Designer]** página inicial.

   ![](assets/des_loading_1.png)

1. Selecione a fonte do conteúdo que deseja carregar:

   * [Modelos de conteúdo](../../designing/using/using-reusable-content.md#content-templates): clique no botão **[!UICONTROL Templates]** guia .
   * [Conteúdo do zero](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch), para começar do zero: clique no botão **[!UICONTROL Create]** botão.
   * [Conteúdo do seu computador como um arquivo ZIP ou HTML](#importing-content-from-a-file): clique no botão **[!UICONTROL Upload]** botão.
   * [Conteúdo de um URL existente](#importing-content-from-a-url) (somente para emails): clique no botão **[!UICONTROL Import from URL]** botão.

   ![](assets/des_loading_2.png)

1. Carregue o conteúdo. O conteúdo selecionado substitui o conteúdo atual.

   Depois de importado, o conteúdo pode ser editado e personalizado.

   >[!NOTE]
   >
   >O [Email Designer](../../designing/using/designing-content-in-adobe-campaign.md) O usa marcação específica. O conteúdo de HTML padrão carregado no Campaign deve corresponder à marcação esperada para ser totalmente compatível e editável no Designer de email. Se não for correspondente, seu conteúdo será carregado no [modo de compatibilidade](#compatibility-mode). Para tornar o conteúdo existente compatível, consulte [esta seção](#editing-existing-contents-with-the-email-designer).

**Tópicos relacionados:**

* [Criação de um email](../../channels/using/creating-an-email.md)
* [Gerenciamento de landing pages](../../channels/using/getting-started-with-landing-pages.md)

## Edição de conteúdo existente com o Designer de email{#editing-existing-contents-with-the-email-designer}

Aproveitar totalmente as possibilidades de edição da [Email Designer](../../designing/using/designing-content-in-adobe-campaign.md), o HTML carregado deve conter uma marcação específica que o torna compatível com o editor WYSIWYG.

Se toda ou parte do HTML não tiver essa marcação, o conteúdo será carregado em &#39; [modo de compatibilidade](#compatibility-mode)&quot;.

Para tornar um conteúdo externo existente totalmente editável no Designer de email, consulte o [Criação de email usando conteúdo existente](../../designing/using/using-existing-content.md) seção.

## Importação de conteúdo de email existente {#importing}

### Importação de conteúdo de um arquivo {#importing-content-from-a-file}

Na página inicial do Designer de email, clique no botão **[!UICONTROL Upload]** para carregar um arquivo de seu computador e, em seguida, confirme.

Não há restrições na estrutura do arquivo zip. No entanto, a referência a arquivos HTML deve ser relativa e respeitar a estrutura de árvore da pasta zip.

Os formatos a seguir são suportados para importação:

* Um arquivo HTML com uma folha de estilos incorporada
* Uma pasta .zip contendo o arquivo HTML, a folha de estilos (.CSS) e as imagens

>[!NOTE]
>
>Para conteúdo de email, recomendamos que você importe arquivos HTML únicos com uma folha de estilos incorporada.

#### Importar conteúdo de um URL {#importing-content-from-a-url}

Antes de importar o conteúdo de um URL, verifique se ele cumpre os requisitos abaixo:

* O conteúdo precisa estar disponível publicamente através deste URL.
* Por motivos de segurança, somente os URLs que começam com **[!UICONTROL https]** são permitidas.
* Certifique-se de que todos os recursos (imagens, CSS) estejam definidos em links absolutos e em HTTPS. Caso contrário, após o envio do email, a mirror page seria exibida sem seus recursos. Este é um exemplo de uma definição de link absoluta:

   ```
   <a href="https://www.mywebsite.com/images/myimage.png">
   ```

>[!NOTE]
>
>O carregamento de conteúdo de um URL está disponível somente para o canal de email.

Para recuperar o conteúdo existente de um URL, siga as etapas abaixo:

1. Na página inicial do Designer de email, selecione o **[!UICONTROL Import from URL]** botão.

   ![](assets/email_designer_importfromurl.png)

1. Defina o URL do qual o conteúdo será recuperado.
1. Clique em **[!UICONTROL Confirm]**.

Descubra este recurso no vídeo.

>[!VIDEO](https://video.tv.adobe.com/v/25926?quality=12)

Vídeos tutoriais adicionais do Campaign Standard estão disponíveis [here](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=pt-BR).

### Recuperação de conteúdo de um URL automaticamente no momento de preparação {#retrieving-content-from-a-url-automatically-at-preparation-time}

Importar conteúdo de um URL durante a preparação da mensagem permite recuperar o conteúdo de HTML mais recente sempre que o email for preparado. Dessa forma, o conteúdo de emails recorrentes é sempre atualizado no momento do envio. Esse recurso também permite que você crie uma mensagem agendada em uma data específica, mesmo se o conteúdo ainda não estiver pronto.

Para recuperar o conteúdo no momento da preparação, siga as etapas abaixo:

1. Selecione a opção **[!UICONTROL Content imported during preparation]**.

   ![](assets/email_designer_importfromurl2.png)

1. O conteúdo do URL é exibido no editor como somente leitura.

   >[!CAUTION]
   >
   >Nesta etapa, a exibição HTML no editor de conteúdo não deve ser levada em conta. Ele será recuperado na fase de preparação.

1. Para visualizar o conteúdo do URL que foi recuperado, abra a mensagem depois de criada e clique no link **[!UICONTROL Preview]** botão.

É possível personalizar a URL remota da qual o conteúdo será recuperado. Para fazer isso, siga as etapas abaixo:

1. Clique no rótulo do email na parte superior da tela para acessar o Designer de email **[!UICONTROL Properties]** guia .
1. Encontre a **[!UICONTROL Remote URL]** campo.

   ![](assets/email_designer_importfromurl4.png)

1. Insira o campo de personalização, o bloco de conteúdo ou o texto dinâmico desejado.

   O **[!UICONTROL Current date - YYYYMMDD]** bloco de conteúdo, por exemplo, permite inserir a data do dia.

   >[!NOTE]
   >
   >Os campos de personalização disponíveis estão vinculados a **Delivery** atributos somente (data de criação do email, status, rótulo da campanha...).

Se o download de conteúdo falhar na primeira tentativa, ele poderá ser repetido duas vezes:

1. A segunda tentativa começa 50 ms após a primeira tentativa.
1. A terceira tentativa começa 100 ms após a segunda tentativa.

Essas tentativas são úteis nestes casos:

* Uma falha de serviço de tempo curto em um servidor distante
* Uma falha do servidor em um cluster, nesse caso, as tentativas têm mais probabilidade de ter sucesso graças ao balanceamento de carga para um servidor em funcionamento

### Modo de compatibilidade {#compatibility-mode}

Ao fazer upload de um conteúdo, ele deve conter uma marcação específica para ser totalmente compatível e editável com o editor WYSIWYG do Designer de email.

Se todo ou parte do HTML carregado não for compatível com a marcação esperada, o conteúdo será carregado no &quot;modo de compatibilidade&quot;, o que limita as possibilidades de edição por meio da interface do usuário.

Quando um conteúdo é carregado no modo de compatibilidade, você ainda pode executar as seguintes modificações por meio da interface (as ações não disponíveis estão ocultas):

* Alteração do texto ou alteração de uma imagem
* Inserção de links e campos de personalização
* Edite algumas opções de estilo no bloco de HTML selecionado
* Definição do conteúdo condicional

![](assets/email_designer_compatibility.png)

Outras modificações, como adicionar novas seções ao seu email ou estilo avançado, devem ser feitas diretamente no código-fonte do email por meio do modo HTML.

Para obter mais informações sobre como converter um email existente em um email compatível com o Designer de email, consulte [esta seção](../../designing/using/using-existing-content.md).

**Tópicos relacionados**:

* [Criação de um email](../../channels/using/creating-an-email.md)
* [Vídeo de introdução ao Email Designer](../../designing/using/designing-content-in-adobe-campaign.md#video)
* [Criar um conteúdo de email do zero](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)

## Conversão de conteúdo de HTML {#converting-an-html-content}

Se quiser criar uma estrutura de modelos e fragmentos modulares que podem ser combinados para reutilização em vários emails, considere converter seu HTML de email em um modelo do Designer de email.

Esse caso de uso oferece uma maneira rápida de converter o email do HTML em componentes do Designer de email.

>[!CAUTION]
>
>Esta seção é para usuários avançados familiarizados com o código HTML.

>[!NOTE]
>
>Como o modo de compatibilidade, um componente HTML pode ser editado com opções limitadas: só é possível executar edição no local.

Fora do Designer de email, verifique se o HTML original está dividido em seções reutilizáveis.

Se esse não for o caso, corte os diferentes blocos do seu HTML. Por exemplo:

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

Depois de identificar todos os blocos, no Email Designer, repita o seguinte procedimento para cada seção do email existente:

1. Abra o Designer de email para criar um conteúdo de email vazio.
1. Defina os atributos de nível de corpo: cores de fundo, largura, etc. Para obter mais informações, consulte [Edição de estilos de email](../../designing/using/styles.md).
1. Adicione um componente de estrutura. Para obter mais informações, consulte [Edição da estrutura do email](../../designing/using/designing-from-scratch.md#defining-the-email-structure).
1. Adicione um componente HTML. Para obter mais informações, consulte [Inclusão de fragmentos e componentes](../../designing/using/designing-from-scratch.md#defining-the-email-structure).
1. Copie e cole o HTML nesse componente.
1. Alternar para exibição móvel. Para obter mais informações, consulte [esta seção](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view).

   A exibição responsiva está quebrada, pois seu CSS está ausente.

1. Para corrigir isso, alterne para o modo de código-fonte e copie e cole sua seção de estilo em uma nova seção de estilo. Por exemplo:

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
   >Adicione seu estilo depois disso em outra tag de estilo personalizada.
   >
   >Não modifique o CSS gerado pelo Email Designer:
   >
   >* `<style data-name="default" type="text/css">(##)</style>`
   >* `<style data-name="supportIOS10" type="text/css">(##)</style>`
   >* `<style data-name="mediaIOS8" type="text/css">(##)</style>`
   >* `<style data-name="media-default-max-width-500px" type="text/css">(##)</style>`
   >* `<style data-name="media-default--webkit-min-device-pixel-ratio-0" type="text/css">(##)</style>`


1. Retorne à visualização móvel para verificar se o conteúdo é exibido corretamente e salvar as alterações.
