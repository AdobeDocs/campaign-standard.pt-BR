---
title: Criar emails usando conteúdo existente
description: Descubra como criar emails usando conteúdo de email existente no Designer de email.
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: 3bda4227-2a6e-4813-a288-93a4388a9787
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '1277'
ht-degree: 5%

---

# Criação usando conteúdo existente {#designing-using-existing-content}

## Seleção de conteúdo existente{#selecting-an-existing-content}

O Adobe Campaign vem com um conjunto de conteúdos predefinidos para ajudar você a começar. Você pode usar uma dessas opções ou, se o conteúdo da mensagem que você precisa enviar estiver sendo preparado fora do Adobe Campaign, você poderá importá-la do seu computador ou de um URL.

Ao criar um email ou uma landing page, você pode optar por carregar um conteúdo existente de outra fonte.

>[!NOTE]
>
>As imagens abaixo mostram como carregar um conteúdo existente usando o [Email Designer](../../designing/using/designing-content-in-adobe-campaign.md).

1. Após criar o email ou a landing page, abra o conteúdo.
1. Clique no ícone da página inicial para acessar a **[!UICONTROL Email Designer]** página inicial.

   ![](assets/des_loading_1.png)

1. Selecione a origem do conteúdo que deseja carregar:

   * [Modelos de conteúdo](../../designing/using/using-reusable-content.md#content-templates): clique na guia **[!UICONTROL Templates]** guia.
   * [Conteúdo do zero](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch), para começar do zero: clique no botão **[!UICONTROL Create]** botão.
   * [Conteúdo do seu computador como um arquivo ZIP ou HTML](#importing-content-from-a-file): clique na guia **[!UICONTROL Upload]** botão.
   * [Conteúdo de um URL existente](#importing-content-from-a-url) (somente para emails): clique no link **[!UICONTROL Import from URL]** botão.

   ![](assets/des_loading_2.png)

1. Carregue o conteúdo. O conteúdo selecionado substitui o conteúdo atual.

   Depois de importado, o conteúdo pode ser editado e personalizado.

   >[!NOTE]
   >
   >A variável [Email Designer](../../designing/using/designing-content-in-adobe-campaign.md) O usa marcação específica. O conteúdo em HTML padrão carregado no Campaign deve corresponder à marcação esperada para ser totalmente compatível e editável no Designer de email. Se não corresponder, seu conteúdo será carregado no [modo de compatibilidade](#compatibility-mode). Para tornar o conteúdo existente compatível, consulte [nesta seção](#editing-existing-contents-with-the-email-designer).

**Tópicos relacionados:**

* [Criação de um email](../../channels/using/creating-an-email.md)
* [Gerenciamento de páginas de destino](../../channels/using/getting-started-with-landing-pages.md)

## Edição de conteúdo existente com o Designer de email{#editing-existing-contents-with-the-email-designer}

Para aproveitar totalmente as possibilidades de edição do [Email Designer](../../designing/using/designing-content-in-adobe-campaign.md), o HTML carregado deve conter uma marcação específica que o torne compatível com o editor WYSIWYG.

Se parte ou a totalidade do HTML não tiver essa marcação, o conteúdo será carregado em &quot; [modo de compatibilidade](#compatibility-mode)&#39;.

Para tornar um conteúdo externo existente totalmente editável no Designer de email, consulte o [Criação de um email usando conteúdo existente](../../designing/using/using-existing-content.md) seção.

## Importação de conteúdo de email existente {#importing}

### Importação de conteúdo de um arquivo {#importing-content-from-a-file}

Na página inicial do Designer de email, clique no link **[!UICONTROL Upload]** botão para carregar um arquivo do seu computador e confirmar.

Não há restrições na estrutura do arquivo zip. No entanto, os arquivos de HTML de referência devem ser relativos e respeitar a estrutura de árvore da pasta zip.

Os seguintes formatos são suportados para importação:

* Um arquivo HTML com uma folha de estilos incorporada
* Uma pasta .zip que contém o arquivo HTML, a folha de estilos (.CSS) e as imagens

>[!NOTE]
>
>Para conteúdo de email, recomendamos que você importe arquivos de HTML único com uma folha de estilos incorporada.

#### Importação de conteúdo de um URL {#importing-content-from-a-url}

Antes de importar conteúdo de um URL, siga os requisitos abaixo:

* O conteúdo precisa estar disponível publicamente por meio desse URL.
* Por motivos de segurança, somente URLs que começam com **[!UICONTROL https]** são permitidos.
* Verifique se todos os recursos (imagens, CSS) estão definidos em links absolutos e em HTTPS. Caso contrário, após o envio do email, a mirror page será exibida sem os recursos. Este é um exemplo de uma definição de link absoluto:

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

Vídeos extras explicativos sobre o Campaign Standard estão disponíveis [aqui](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=pt-BR).

### Recuperação automática de conteúdo de um URL no momento da preparação {#retrieving-content-from-a-url-automatically-at-preparation-time}

A importação de conteúdo de um URL durante a preparação da mensagem permite recuperar o conteúdo de HTML mais recente sempre que o email for preparado. Dessa forma, o conteúdo de emails recorrentes está sempre atualizado no momento do envio. Esse recurso também permite criar uma mensagem agendada em uma data específica, mesmo que o conteúdo ainda não esteja pronto.

Para recuperar o conteúdo no momento da preparação, siga as etapas abaixo:

1. Selecione a opção **[!UICONTROL Content imported during preparation]**.

   ![](assets/email_designer_importfromurl2.png)

1. O conteúdo do URL é exibido no editor como somente leitura.

   >[!CAUTION]
   >
   >Nessa etapa, a exibição do HTML no editor de conteúdo não deve ser considerada. Ele será recuperado na fase de preparação.

1. Para visualizar o conteúdo do URL que foi recuperado, abra a mensagem depois de criá-la e clique no link **[!UICONTROL Preview]** botão.

É possível personalizar o URL remoto do qual o conteúdo será recuperado. Para fazer isso, siga as etapas abaixo:

1. Clique no rótulo do email na parte superior da tela para acessar o Designer de email **[!UICONTROL Properties]** guia.
1. Localize o **[!UICONTROL Remote URL]** campo.

   ![](assets/email_designer_importfromurl4.png)

1. Insira o campo de personalização, o bloco de conteúdo ou o texto dinâmico desejados.

   A variável **[!UICONTROL Current date - YYYYMMDD]** o bloco de conteúdo, por exemplo, permite inserir a data do dia.

   >[!NOTE]
   >
   >Os campos de personalização disponíveis estão vinculados ao **Entrega** somente atributos (data de criação do email, status, rótulo da campanha...).

Se o download de conteúdo falhar na primeira tentativa, ele poderá ser repetido duas vezes:

1. A segunda tentativa começa 50 ms após a primeira tentativa.
1. A terceira tentativa começa 100 ms após a segunda tentativa.

Estas tentativas são úteis nestes casos:

* Falha de serviço de curto prazo em um servidor distante
* Uma falha de servidor em um cluster, caso em que as tentativas têm mais probabilidade de êxito graças ao balanceamento de carga para um servidor em funcionamento

### Modo de compatibilidade {#compatibility-mode}

Ao fazer upload de um conteúdo, ele deve conter marcações específicas para ser totalmente compatível e editável com o editor WYSIWYG do Designer de email.

Se todo ou parte do HTML carregado não estiver em conformidade com a marcação esperada, o conteúdo será carregado no &quot;modo de compatibilidade&quot;, o que limita as possibilidades de edição por meio da interface.

Quando um conteúdo é carregado no modo de compatibilidade, você ainda pode executar as seguintes modificações por meio da interface (as ações indisponíveis estão ocultas):

* Alteração do texto ou de uma imagem
* Inserção de links e campos de personalização
* Editar algumas opções de estilo no bloco de HTML selecionado
* Definição do conteúdo condicional

![](assets/email_designer_compatibility.png)

Outras modificações, como a adição de novas seções ao email ou ao estilo avançado, devem ser feitas diretamente no código-fonte do email por meio do modo HTML.

Para obter mais informações sobre como converter um email existente em um email compatível com o Designer de email, consulte [nesta seção](../../designing/using/using-existing-content.md).

**Tópicos relacionados**:

* [Criação de um email](../../channels/using/creating-an-email.md)
* [Vídeo de introdução ao Email Designer](../../designing/using/designing-content-in-adobe-campaign.md#video)
* [Criar um conteúdo de email do zero](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)

## Conversão de conteúdo de HTML {#converting-an-html-content}

Se você quiser criar uma estrutura de modelos modulares e fragmentos que podem ser combinados para reutilização em vários emails, considere converter seu HTML de email em um modelo do Designer de email.

Esse caso de uso oferece uma maneira rápida de converter emails do HTML em componentes do Designer de email.

>[!CAUTION]
>
>Esta seção é para usuários avançados familiarizados com o código HTML.

>[!NOTE]
>
>Como o modo de compatibilidade, um componente HTML é editável com opções limitadas: você só pode executar a edição no local.

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

Depois de identificar todos os blocos, no Designer de email, repita o procedimento a seguir para cada seção do email existente:

1. Abra o Designer de email para criar um conteúdo de email vazio.
1. Defina os atributos do nível do corpo: cores do plano de fundo, largura etc. Para obter mais informações, consulte [Edição de estilos de email](../../designing/using/styles.md).
1. Adicione um componente de estrutura. Para obter mais informações, consulte [Edição da estrutura do email](../../designing/using/designing-from-scratch.md#defining-the-email-structure).
1. Adicione um componente HTML. Para obter mais informações, consulte [Inclusão de fragmentos e componentes](../../designing/using/designing-from-scratch.md#defining-the-email-structure).
1. Copie e cole seu HTML nesse componente.
1. Alternar para exibição móvel. Para obter mais informações, consulte [esta seção](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view).

   A exibição responsiva foi interrompida porque o CSS está ausente.

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
   >Certifique-se de adicionar o estilo depois disso em outra tag de estilo personalizada.
   >
   >Não modifique o CSS gerado pelo Designer de email:
   >
   >* `<style data-name="default" type="text/css">(##)</style>`
   >* `<style data-name="supportIOS10" type="text/css">(##)</style>`
   >* `<style data-name="mediaIOS8" type="text/css">(##)</style>`
   >* `<style data-name="media-default-max-width-500px" type="text/css">(##)</style>`
   >* `<style data-name="media-default--webkit-min-device-pixel-ratio-0" type="text/css">(##)</style>`

1. Retorne à exibição para dispositivos móveis para verificar se o conteúdo é exibido corretamente e salve as alterações.
