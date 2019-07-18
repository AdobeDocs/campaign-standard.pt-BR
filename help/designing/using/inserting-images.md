---
title: Inserir imagens
seo-title: Inserir imagens
description: Inserir imagens
seo-description: Saiba como adicionar imagens ao seu conteúdo.
page-status-flag: nunca ativado
uuid: ac 42 b 1 d 3-50 ad -4323-b 474-1 e 50 e 468901 f
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: usando imagens
discoiquuid: ede 832 ac -96 e 5-41 e 1-8390-6669 ba 30 d 4 d 8
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Inserting images{#inserting-images}

Você pode inserir imagens em seus emails e páginas de aterrissagem.

Os seguintes tipos de imagens estão disponíveis, dependendo da sua configuração:

* Imagens locais
* Images shared from Adobe Experience Cloud - refer to [Working with Campaign and Assets Core Service](../../integrating/using/working-with-campaign-and-assets-core-service.md) / Assets On Demand
* Dynamic images from Adobe Target - refer to [Working with Campaign and Target](../../integrating/using/about-campaign-target-integration.md)

Se ativado, você pode modificar imagens com o Adobe Creative SDK. See [Modifying images with the Adobe Creative SDK](../../designing/using/modifying-images-with-the-adobe-creative-sdk.md).

>[!CAUTION]
>
>If you choose to add an image directly by editing the HTML version of the email, you must not call up **external files in a &lt;script&gt; tag** of the HTML page. Esses arquivos não serão importados para o servidor do Adobe Campaign.

## Inserting images in an email {#inserting-images-in-an-email}

1. Adicione um componente de estrutura. For more on this, see [Editing the email structure](../../designing/using/defining-the-email-structure.md#editing-the-email-structure).
1. Inside this structure component, add an **[!UICONTROL Image]** content component.

   ![](assets/des_insert_images_1.png)

1. Click **[!UICONTROL Browse]**. Arraste e solte uma imagem ou clique para selecionar um arquivo do seu computador.

   ![](assets/des_insert_images_2.png)

1. Selecione o componente de conteúdo que você acabou de adicionar.
1. Verifique as propriedades da imagem e ajuste-as, se necessário.

   ![](assets/des_insert_images_3.png)

## Inserting images in a landing page {#inserting-images-in-a-landing-page}

1. Em um conteúdo de página de aterrissagem, selecione um bloco que contenha uma imagem.
1. Select the **[!UICONTROL Insert]** button.

   ![](assets/des_insert_images_lp_1.png)

1. Choose **[!UICONTROL Local image]** from the contextual toolbar.

   ![](assets/des_insert_images_lp_2.png)

1. Selecione um arquivo.

   ![](assets/des_insert_images_lp_3.png)

1. Ajuste as propriedades da imagem conforme necessário.

   ![](assets/des_insert_images_lp_4.png)

