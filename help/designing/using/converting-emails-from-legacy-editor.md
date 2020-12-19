---
solution: Campaign Standard
product: campaign
title: 'Convertendo email do editor herdado para o Designer de email '
description: Descubra como usar e-mails criados no Editor herdado e-mail para o Designer de e-mail.
audience: designing
content-type: reference
topic-tags: editing-email-content
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 8%

---


# Convertendo conteúdo de email do editor herdado {#converting-an-html-content}

Start que trabalha com o Email Designer e cria modelos e fragmentos reutilizáveis do seu HTML de email criado no Editor Herdado.

Esse caso de uso permite que você crie um modelo do Email Designer usando um email HTML e dividindo-o em componentes HTML no Designer de email.

>[!NOTE]
>
>Como o modo de compatibilidade, um componente HTML é editável com opções limitadas: você só pode executar edição no local.

>[!IMPORTANT]
>
>Esta seção destina-se a usuários avançados familiarizados com o código HTML.

## Preparando seu conteúdo de email

1. Selecione um email HTML.
1. Identifique as seções para dividir o email HTML.
1. Recorte os diferentes blocos do seu HTML.

## Criar sua estrutura de email

1. Abra o **[!UICONTROL Email Designer]** para criar um conteúdo de email vazio.
1. Defina os atributos de nível de corpo: cores de fundo, largura, etc. Para obter mais informações, consulte [Edição de estilos de email](../../designing/using/styles.md).
1. Adicione quantos componentes de estrutura você tiver seções. Para obter mais informações, consulte [Edição da estrutura do email](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

## Adicionar conteúdo HTML

1. Adicione um componente HTML a cada componente de estrutura. Para obter mais informações, consulte [Inclusão de fragmentos e componentes](../../designing/using/designing-from-scratch.md#defining-the-email-structure).
1. Copie e cole seu HTML em cada componente.

## Gerenciar o estilo do seu email {#manage-the-style-of-your-email}

1. Mude para **[!UICONTROL Mobile view]**. Para obter mais informações, consulte [esta seção](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view).

1. Para corrigir isso, alterne para o modo de código fonte e copie e cole sua seção de estilo em uma nova seção de estilo. Por exemplo:

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
   >Depois disso, adicione seu estilo em outra tag de estilo personalizada.
   >
   >Não modifique o CSS gerado pelo Designer de email:
   >
   >* `<style data-name="default" type="text/css">(##)</style>`
   >* `<style data-name="supportIOS10" type="text/css">(##)</style>`
   >* `<style data-name="mediaIOS8" type="text/css">(##)</style>`
   >* `<style data-name="media-default-max-width-500px" type="text/css">(##)</style>`
   >* `<style data-name="media-default--webkit-min-device-pixel-ratio-0" type="text/css">(##)</style>`


1. Volte para a visualização móvel para verificar se o conteúdo é exibido corretamente e salvar as alterações.

## Caso de uso

Vamos tentar converter este email, criado no editor herdado, em um modelo **[!UICONTROL Email Designer]**.

### Identifique a seção do seu email

Podemos identificar 11 seções neste email.

![](assets/html-dce-view-mail.png)

Para identificar qual elemento é qual seção do HTML, você pode selecioná-lo.

![](assets/breadcrumbs.png)

Para ver a versão HTML do email, clique em **[!UICONTROL Show source]**.

### Criar o modelo de email e sua estrutura

1. Arraste e solte **[!UICONTROL Structure components]** refletindo o layout de nosso email.

1. Repita quantas vezes forem necessárias. Precisamos criar 11 componentes estruturais.

   ![](assets/structure-components-migration.png)

### Inserir componentes de conteúdo HTML

1. Insira um **[!UICONTROL HTML component]** em cada **[!UICONTROL Structure component]**.

   ![](assets/html-components.png)

1. Para cada seção, clique em **[!UICONTROL Show source code]** .

   ![](assets/show-source-code.png)

1. Insira a seção HTML.

1. Clique em **[!UICONTROL Save]**.

Agora você pode verificar a renderização do seu email.

![](assets/migrated-email-result.png)

### Gerenciamento de estilos para ajustar à visualização móvel

1. Insira elementos CSS para garantir que seu email seja adequado para visualização móvel.

1. Alterne para o código-fonte e copie e cole sua seção de estilo em uma nova seção de estilo.

Para obter mais informações, consulte [Gerenciar o estilo do seu email](#manage-the-style-of-your-email).

Seu email legado agora está disponível no Designer de email.