---
solution: Campaign Standard
product: campaign
title: 'Conversão do Editor herdado de email para o Email Designer '
description: Saiba como usar emails criados no Editor herdado Email para o Designer de email.
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Design de email
role: Profissional
level: Intermediário
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 8%

---


# Conversão do conteúdo de email do editor herdado {#converting-an-html-content}

Comece a trabalhar com o Email Designer e crie modelos e fragmentos reutilizáveis do HTML de email criado no Editor herdado.

Esse caso de uso permite criar um modelo do Designer de email usando um email HTML e dividindo-o em componentes HTML no Designer de email.

>[!NOTE]
>
>Como o modo de compatibilidade, um componente HTML é editável com opções limitadas: só é possível executar edição no local.

>[!IMPORTANT]
>
>Esta seção é para usuários avançados familiarizados com o código HTML.

## Preparação do conteúdo do email

1. Selecione um email HTML.
1. Identifique as seções para dividir o email HTML.
1. Recorte os diferentes blocos do seu HTML.

## Criar sua estrutura de email

1. Abra o **[!UICONTROL Email Designer]** para criar um conteúdo de email vazio.
1. Defina os atributos de nível de corpo: cores de fundo, largura, etc. Para obter mais informações, consulte [Edição de estilos de email](../../designing/using/styles.md).
1. Adicione quantos componentes da estrutura tiver seções. Para obter mais informações, consulte [Edição da estrutura do email](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

## Adicionar conteúdo HTML

1. Adicione um componente HTML a cada componente de estrutura. Para obter mais informações, consulte [Inclusão de fragmentos e componentes](../../designing/using/designing-from-scratch.md#defining-the-email-structure).
1. Copie e cole seu HTML em cada componente.

## Gerenciar o estilo do seu email {#manage-the-style-of-your-email}

1. Alterne para **[!UICONTROL Mobile view]**. Para obter mais informações, consulte [esta seção](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view).

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

## Caso de uso

Vamos tentar converter esse email, criado no editor herdado, em um template **[!UICONTROL Email Designer]**.

### Identifique a seção do seu email

Podemos identificar 11 seções neste email.

![](assets/html-dce-view-mail.png)

Para identificar qual elemento é qual seção do HTML, você pode selecioná-lo.

![](assets/breadcrumbs.png)

Para ver a versão HTML do email, clique em **[!UICONTROL Show source]**.

### Criar o modelo de email e sua estrutura

1. Arraste e solte **[!UICONTROL Structure components]** refletindo o layout do nosso email.

1. Repita quantas vezes forem necessárias. Precisamos criar 11 componentes de estrutura.

   ![](assets/structure-components-migration.png)

### Inserção de componentes de conteúdo HTML

1. Insira um **[!UICONTROL HTML component]** em cada **[!UICONTROL Structure component]** .

   ![](assets/html-components.png)

1. Para cada seção, clique em **[!UICONTROL Show source code]** .

   ![](assets/show-source-code.png)

1. Insira a seção HTML .

1. Clique em **[!UICONTROL Save]**.

Agora é possível verificar a renderização do email.

![](assets/migrated-email-result.png)

### Gerenciamento de estilos para ajustar à exibição móvel

1. Insira elementos de CSS para garantir que o email seja adequado para exibição móvel.

1. Alterne para o código-fonte e copie e cole sua seção de estilo em uma nova seção de estilo.

Para obter mais informações, consulte [Gerenciar o estilo do seu email](#manage-the-style-of-your-email).

O email herdado agora está disponível no Designer de email.