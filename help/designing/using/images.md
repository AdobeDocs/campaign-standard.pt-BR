---
title: Trabalhar com imagens
description: Descubra como gerenciar imagens em emails com o Designer de email.
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: b58a378d-18da-4c0f-b4e7-5d0a02aab4c2
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 7%

---

# Trabalho com imagens {#images}

## Inserção de imagens{#inserting-images}

Você pode inserir imagens em seus emails e landing pages.

Dependendo da sua configuração, os seguintes tipos de imagens estarão disponíveis:

* Imagens locais
* Imagens compartilhadas da Adobe Experience Cloud - consulte [Trabalho com o Campaign e o Assets Core Service](../../integrating/using/working-with-campaign-and-assets-core-service.md) / Assets On Demand
* Imagens dinâmicas do Adobe Target - consulte [Trabalho com o Campaign e o Target](../../integrating/using/about-campaign-target-integration.md)

>[!CAUTION]
>
>Se você optar por adicionar uma imagem diretamente editando a versão do HTML do email, você não deve chamar **arquivos externos em uma &lt;script> tag** da página HTML. Esses arquivos não serão importados para o servidor do Adobe Campaign.

### Inserção de imagens em um email {#inserting-images-in-an-email}

1. Adicione um componente de estrutura. Para obter mais informações, consulte [Edição da estrutura do email](../../designing/using/designing-from-scratch.md#defining-the-email-structure).
1. Dentro deste componente de estrutura, adicione um componente de conteúdo **[!UICONTROL Image]**.

   ![](assets/des_insert_images_1.png)

1. Clique em **[!UICONTROL Browse]**. Arraste e solte uma imagem ou clique para selecionar um arquivo do seu computador.

   ![](assets/des_insert_images_2.png)

1. Selecione o componente de conteúdo que você acabou de adicionar.
1. Verifique as propriedades da imagem e ajuste-as se necessário.

   ![](assets/des_insert_images_3.png)

## Configuração das propriedades da imagem{#setting-up-image-properties}

Ao selecionar um bloco que contém uma imagem, as seguintes propriedades são oferecidas na paleta:

* **Habilitar personalização** permite personalizar a fonte da imagem. Consulte [Personalizando uma fonte de imagem](../../designing/using/personalization.md#personalizing-an-image-source).
* **Título da imagem** permite que você defina um título para a imagem.
* O **Alt text** (email) ou a **Caption** (página de aterrissagem) permite definir a legenda vinculada à imagem (corresponde ao atributo HTML **alt**).
* Ao editar um email, o **Estilo** permite especificar o tamanho da imagem, o plano de fundo e a borda.
* Ao editar uma página de aterrissagem, **Dimension** permite especificar o tamanho da imagem em pixels.

O editor permite trabalhar com **todos os tipos de imagem** cujos formatos sejam compatíveis com os navegadores. Para ser compatível com o editor, as **animações** do tipo &quot;Flash&quot; devem ser inseridas em uma página de HTML da seguinte maneira:

```
<object type="application/x-shockwave-flash" data="http://www.mydomain.com/flash/your_animation.swf" width="200" height="400">
 <param name="movie" value="http://www.mydomain.com/flash/your_animation.swf" />
 <param name="quality" value="high" />
 <param name="play" value="true"/>
 <param name="loop" value="true"/> 
</object>
```

<!--
## Modifying images with the Adobe Creative SDK{#modifying-images-with-the-adobe-creative-sdk}

You can edit images and use a complete set of features powered by the Adobe Creative SDK to enhance your images directly in the content editor when editing emails or landing pages.

The image editor offers a powerful, full-featured image editing UI component that allows you to edit images and apply effects and frames, original high-quality stickers, beautiful overlays, fun features like tilt shift and color splash, pro-level adjustments and more.

To modify an image with the Adobe Creative SDK:

1. Select the image.
1. In the toolbar, click the Creative Cloud icon.

   ![](assets/des_creative_sdk_icon.png)

1. Select the tool you want to use through the icons on the top of the window to modify the image.

   ![](assets/email_designer_ccsdktoolbar.png)

1. Click **[!UICONTROL Save]** when modifications are done. The updated image is saved on Adobe Campaign server and ready to be used.

>[!NOTE]
>
>Tools offered in the image editor cannot be customized.
-->
