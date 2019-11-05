---
title: Gerenciamento de imagens em emails
description: Descubra como gerenciar imagens em emails com o Designer de email.
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
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Imagens {#images}

## Inserção de imagens{#inserting-images}

Você pode inserir imagens em seus emails e páginas iniciais.

Os seguintes tipos de imagens estão disponíveis, dependendo de sua configuração:

* Imagens locais
* Imagens compartilhadas da Adobe Experience Cloud - consulte [Trabalhar com o Campaign e os ativos Principais serviços](../../integrating/using/working-with-campaign-and-assets-core-service.md) / Ativos sob demanda
* Imagens dinâmicas do Adobe Target - consulte [Trabalhar com o Campaign e o Target](../../integrating/using/about-campaign-target-integration.md)

Se ativado, você pode modificar imagens com o Adobe Creative SDK. Consulte [Modificação de imagens com o Adobe Creative SDK](#modifying-images-with-the-adobe-creative-sdk).

>[!CAUTION]
>
>Se você optar por adicionar uma imagem diretamente editando a versão HTML do email, não deverá chamar arquivos **externos em uma tag** &lt;script&gt; da página HTML. Esses arquivos não serão importados para o servidor do Adobe Campaign.

### Inserir imagens em um email {#inserting-images-in-an-email}

1. Adicione um componente de estrutura. Para obter mais informações, consulte [Edição da estrutura](../../designing/using/designing-from-scratch.md#defining-the-email-structure)de email.
1. Dentro desse componente de estrutura, adicione um componente de **[!UICONTROL Image]** conteúdo.

   ![](assets/des_insert_images_1.png)

1. Click **[!UICONTROL Browse]**. Arraste e solte uma imagem ou clique para selecionar um arquivo de seu computador.

   ![](assets/des_insert_images_2.png)

1. Selecione o componente de conteúdo que você acabou de adicionar.
1. Verifique as propriedades da imagem e ajuste-as, se necessário.

   ![](assets/des_insert_images_3.png)

## Configuração de propriedades de imagem{#setting-up-image-properties}

Quando um bloco que contém uma imagem é selecionado, as seguintes propriedades são oferecidas na paleta:

* **Ativar personalização** permite personalizar a fonte de imagem. Consulte [Personalização de uma fonte](../../designing/using/personalization.md#personalizing-an-image-source)de imagem.
* **Título** da imagem permite definir um título para a imagem.
* **O texto** alternativo (email) ou **Legenda** (página inicial) permite que você defina a legenda vinculada à imagem (corresponde ao atributo HTML **alternativo** ).
* Ao editar um email, o **Estilo** permite especificar o tamanho da imagem, o plano de fundo e a borda.
* Ao editar uma página inicial, as **Dimensões** permitem que você especifique o tamanho da imagem em pixels.

O editor permite trabalhar com **todos os tipos** de imagem cujos formatos são compatíveis com os navegadores. Para serem compatíveis com o editor, as animações **do tipo** "Flash" devem ser inseridas em uma página HTML da seguinte forma:

```
<object type="application/x-shockwave-flash" data="http://www.mydomain.com/flash/your_animation.swf" width="200" height="400">
 <param name="movie" value="http://www.mydomain.com/flash/your_animation.swf" />
 <param name="quality" value="high" />
 <param name="play" value="true"/>
 <param name="loop" value="true"/> 
</object>
```

## Modificação de imagens com o Adobe Creative SDK{#modifying-images-with-the-adobe-creative-sdk}

Você pode editar imagens e usar um conjunto completo de recursos desenvolvidos pelo Adobe Creative SDK para aprimorar suas imagens diretamente no editor de conteúdo ao editar emails ou páginas de aterrissagem.

O editor de imagens oferece um poderoso componente de interface de usuário para edição de imagens, que permite editar imagens e aplicar efeitos e quadros, adesivos originais de alta qualidade, lindas sobreposições, recursos divertidos como mudança de inclinação e apresentação de cores, ajustes de nível pró e muito mais.

Para modificar uma imagem com o Adobe Creative SDK:

1. Selecione a imagem.
1. Na barra de ferramentas, clique no ícone da Creative Cloud.

   ![](assets/des_creative_sdk_icon.png)

1. Selecione a ferramenta que deseja usar pelos ícones na parte superior da janela para modificar a imagem.

   ![](assets/email_designer_ccsdktoolbar.png)

1. Clique **[!UICONTROL Save]** quando as modificações forem feitas. A imagem atualizada é salva no servidor do Adobe Campaign e está pronta para ser usada.

>[!NOTE]
As ferramentas oferecidas no editor de imagens não podem ser personalizadas.
