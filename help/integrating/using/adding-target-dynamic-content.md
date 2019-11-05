---
title: Adicionar conteúdo dinâmico do Target
description: Saiba como adicionar conteúdo dinâmico do Adobe Target em uma de suas entregas do Adobe Campaign.
page-status-flag: nunca ativado
uuid: b3cc045f-7924-480e-8c61-8246510f3adb
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: integrando
content-type: referência
topic-tags: trabalhar com campanha e meta
discoiquuid: 45ddf7b7-98f7-4fdd-bb4a-49ec8490e877
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Adicionar conteúdo dinâmico do Target{#adding-target-dynamic-content}

Com a integração do Adobe Target, as imagens dinâmicas podem ser adicionadas a uma entrega para personalizar seu conteúdo, dependendo das experiências.

Ao editar um email, você pode inserir uma imagem dinâmica do Adobe Target que será alterada dependendo dos destinatários.

Antes de acessar a imagem no Adobe Campaign, as seguintes tarefas devem ser executadas primeiro no Adobe Target:

* Create one or several [redirect offers](https://docs.adobe.com/content/help/en/target/using/experiences/offers/offer-redirect.html), in which you must specify the URL of the image you will be using.
* Crie um ou vários [públicos](https://marketing.adobe.com/resources/help/en_US/target/ov/c_about_segments.html)para definir o target da atividade.
* Create a [Form-based experience composer](https://marketing.adobe.com/resources/help/en_US/target/target/t_form_experience_composer.html) activity, in which you have to select a rawbox and specify several experiences, depending on the number of redirect offers created. Para cada experiência, você deve selecionar uma das ofertas de redirecionamento criadas.
* Crie segmentos usando informações do Adobe Campaign para especificar experiências. Para usar dados do Adobe Campaign nas regras de seleção da oferta, especifique os dados no rawbox no Adobe Target.

1. Crie um delivery de email
1. Ao editar o conteúdo de um email ou de uma página de aterrissagem, vá para um bloco de imagem e selecione-o **[!UICONTROL Dynamic image from Adobe Target]** pelo menu contextual.

   ![](assets/tar_insert_dynamic_image.png)

1. Selecione a imagem que aparecerá por padrão no email. Você pode especificar diretamente o URL da imagem ou selecionar uma imagem compartilhada por meio dos [Ativos](../../integrating/using/working-with-campaign-and-assets-core-service.md).

   A integração só oferece suporte a imagens estáticas. O restante do conteúdo não é personalizável.

1. Insira o nome do rawbox especificado no Adobe Target.
1. Se você usar permissões do Enterprise em suas configurações no Adobe Target, adicione a propriedade correspondente nesse campo. Saiba mais sobre as permissões do Target Enterprise [nesta página](https://marketing.adobe.com/resources/help/en_US/target/target/properties-overview.html). Este campo é opcional e não é necessário se você não usar permissões do Enterprise no Target.
1. In **[!UICONTROL Additional decision parameters]**, specify the mapping between the fields defined in the Adobe Target segments and the Adobe Campaign fields.

   Os campos do Adobe Campaign usados devem ter sido especificados no rawbox. Aqui, definiremos experiências diferentes dependendo do gênero do destinatário.

   ![](assets/tar_additional_decisionning_parameters.png)

1. Visualize seu email para ver se, ao selecionar perfis diferentes, a imagem inserida muda dependendo dos parâmetros especificados na atividade do Adobe Target e no Adobe Campaign.

Sua entrega contendo a imagem dinâmica agora pode ser enviada. Seus resultados podem ser encontrados no Adobe Target.

**Tópicos relacionados:**

* [Portal do Adobe Target](https://marketing.adobe.com/resources/help/en_US/target/a4t/c_campaign_and_target.html)
* [Sobre o design de conteúdo de email](../../designing/using/overview.md)
* [Personalizar imagens de email em vídeo em tempo](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html) real

