---
title: Configurar propriedades de imagem
seo-title: Configurar propriedades de imagem
description: Configurar propriedades de imagem
seo-description: Consulte como gerenciar as propriedades das imagens incluídas no conteúdo.
page-status-flag: nunca ativado
uuid: 1 a 439105-d 9 aa -4 b 30-a 00 d-bcf 731 a 04 e 08
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: usando imagens
discoiquuid: 80 c 9 c 1 a 5-6050-443 d -810 a -6 bb 755 d 39 dca
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Setting up image properties{#setting-up-image-properties}

Quando um bloco que contém uma imagem é selecionado, as seguintes propriedades são oferecidas na paleta:

* **Habilitar a personalização** permite personalizar a fonte da imagem. See [Personalizing an image source](../../designing/using/personalizing-an-image-source.md).
* **Título da imagem** permite definir um título para a imagem.
* **O texto** alternativo (email) ou **legenda** (página de aterrissagem) permite definir a legenda vinculada à imagem (corresponde ao atributo **alt** HTML).
* When editing an email, **Style** lets you specify the image size, background, and border.
* When editing a landing page, **Dimensions** lets you specify the image size in pixels.

The editor allows you to work with **all image types** whose formats are compatible with browsers. To be compatible with the editor, the **"Flash" type animations** have to be inserted in an HTML page as follows:

```
<object type="application/x-shockwave-flash" data="http://www.mydomain.com/flash/your_animation.swf" width="200" height="400">
 <param name="movie" value="http://www.mydomain.com/flash/your_animation.swf" />
 <param name="quality" value="high" />
 <param name="play" value="true"/>
 <param name="loop" value="true"/> 
</object>
```

