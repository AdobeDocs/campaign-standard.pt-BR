---
title: Adicionar conteúdo dinâmico do Target
seo-title: Adicionar conteúdo dinâmico do Target
description: Adicionar conteúdo dinâmico do Target
seo-description: Saiba como adicionar conteúdo dinâmico do Adobe Target em uma de sua entrega do Adobe Campaign.
page-status-flag: nunca ativado
uuid: b 3 cc 045 f -7924-480 e -8 c 61-8246510 f 3 adb
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: trabalho com campanha e destino
discoiquuid: 45 ddf 7 b 7-98 f 7-4 fdd-bb 4 a -49 ec 8490 e 877
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: eed2e3597548c97345f51fe62dd2b56af5042e87

---


# Adding Target dynamic content{#adding-target-dynamic-content}

Com a integração do Adobe Target, imagens dinâmicas podem ser adicionadas em uma entrega para personalizar seu conteúdo, dependendo das experiências.

Ao editar um e-mail, você pode inserir uma imagem dinâmica do Adobe Target que será alterada, dependendo dos destinatários.

Antes de acessar a imagem no Adobe Campaign, as seguintes tarefas devem primeiro ser executadas no Adobe Target:

* Create one or several [redirect offers](https://docs.adobe.com/content/help/en/target/using/experiences/offers/offer-redirect.html), in which you must specify the URL of the image you will be using.
* Create one or several [audiences](https://marketing.adobe.com/resources/help/en_US/target/ov/c_about_segments.html), to define the target of your activity.
* Create a [Form-based experience composer](https://marketing.adobe.com/resources/help/en_US/target/target/t_form_experience_composer.html) activity, in which you have to select a rawbox and specify several experiences, depending on the number of redirect offers created. Para cada experiência, você deve selecionar uma das ofertas de redirecionamento criadas.
* Crie segmentos usando informações do Adobe Campaign para especificar experiências. Para usar dados do Adobe Campaign nas regras de seleção da oferta, você deve especificar os dados na rawbox no Adobe Target.

1. Crie uma entrega de email.
1. When editing the content of an email or a landing page, go to an image block, then select **[!UICONTROL Dynamic image from Adobe Target]** via the contextual menu.

   ![](assets/tar_insert_dynamic_image.png)

1. Selecione a imagem que será exibida por padrão no e-mail. You can directly specify the image URL or select an image shared via [Assets](../../integrating/using/working-with-campaign-and-assets-core-service.md).

   A integração suporta apenas imagens estáticas. O restante do conteúdo não é personalizável.

1. Digite o nome da rawbox especificada no Adobe Target.
1. Se você usar permissões Enterprise nas configurações do Adobe Target, adicione a propriedade correspondente neste campo. Learn more about Target Enterprise permissions in [this page](https://marketing.adobe.com/resources/help/en_US/target/target/properties-overview.html). Esse campo é opcional e não é obrigatório se você não usar permissões corporativas no Target.
1. In **[!UICONTROL Additional decision parameters]**, specify the mapping between the fields defined in the Adobe Target segments and the Adobe Campaign fields.

   Os campos do Adobe Campaign usados devem ter sido especificados no rawbox. Aqui, nós definiremos experiências diferentes dependendo do sexo do destinatário.

   ![](assets/tar_additional_decisionning_parameters.png)

1. Visualize seu e-mail para ver se, ao selecionar perfis diferentes, a imagem inserida muda dependendo dos parâmetros especificados na atividade do Adobe Target e no Adobe Campaign.

A entrega que contém a imagem dinâmica agora pode ser enviada. Os resultados podem ser encontrados no Adobe Target.

**Tópicos relacionados:**

* [Adobe Target Portal](https://marketing.adobe.com/resources/help/en_US/target/a4t/c_campaign_and_target.html)
* [Sobre o design de conteúdo de email](../../designing/using/about-email-content-design.md)
* [Personalizar imagens de email em](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html) vídeo em tempo real

