---
title: Adicionar conteúdo dinâmico do Target
description: Saiba como adicionar conteúdo dinâmico Adobe Target em um de seus delivery Adobe Campaign.
page-status-flag: never-activated
uuid: b3cc045f-7924-480e-8c61-8246510f3adb
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-target
discoiquuid: 45ddf7b7-98f7-4fdd-bb4a-49ec8490e877
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 33%

---


# Adicionar conteúdo dinâmico do Target{#adding-target-dynamic-content}

Com a integração do Adobe Target, imagens dinâmicas podem ser adicionadas a um delivery para personalizar seu conteúdo, dependendo das experiências.

Ao editar um email, você pode inserir uma imagem dinâmica do Adobe Target que será alterada dependendo dos recipient.

Antes de acessar a imagem no Adobe Campaign, as seguintes tarefas devem ser executadas primeiro no Adobe Target:

* Create one or several [redirect offers](https://docs.adobe.com/content/help/en/target/using/experiences/offers/offer-redirect.html), in which you must specify the URL of the image you will be using.
* Crie um ou vários [públicos](https://docs.adobe.com/content/help/en/target/using/audiences/create-audiences/audiences.html)para definir o target da atividade.
* Create a [Form-based experience composer](https://docs.adobe.com/content/help/en/target/using/experiences/form-experience-composer.html) activity, in which you have to select a rawbox and specify several experiences, depending on the number of redirect offers created. Para cada experiência, você deve selecionar uma das ofertas de redirecionamento criadas.
* Crie segmentos usando informações da Adobe Campaign para especificar experiências. Para usar dados do Adobe Campaign nas regras de seleção da oferta, especifique os dados no rawbox no Adobe Target.

1. Crie um delivery de email
1. Ao editar o conteúdo de um email ou de uma landing page, vá para um bloco de imagem e selecione-o **[!UICONTROL Dynamic image from Adobe Target]** pelo menu contextual.

   ![](assets/tar_insert_dynamic_image.png)

1. Selecione a imagem que aparecerá por padrão no email. Você pode especificar diretamente o URL da imagem ou selecionar uma imagem compartilhada por meio dos [Ativos](../../integrating/using/working-with-campaign-and-assets-core-service.md).

   A integração só oferece suporte a imagens estáticas. O restante do conteúdo não é personalizável.

1. Insira o nome do rawbox especificado no Adobe Target.
1. Se você usar permissões do Enterprise em suas configurações no Adobe Target, adicione a propriedade correspondente nesse campo. Saiba mais sobre as permissões do Target Enterprise [nesta página](https://docs.adobe.com/content/help/en/target/using/administer/manage-users/enterprise/properties-overview.html). Este campo é opcional e não é necessário se você não usar permissões do Enterprise no Target.
1. Em **[!UICONTROL Additional decision parameters]**, especifique o mapeamento entre os campos definidos nos segmentos do Adobe Target e os campos do Adobe Campaign.

   Os campos do Adobe Campaign usados devem ter sido especificados no rawbox. Aqui, definiremos experiências diferentes dependendo do gênero do recipient.

   ![](assets/tar_additional_decisionning_parameters.png)

1. Pré-visualização seu email para ver se, ao selecionar perfis diferentes, a imagem inserida muda dependendo dos parâmetros especificados na atividade do Adobe Target e no Adobe Campaign.

Seu delivery que contém a imagem dinâmica agora pode ser enviado. Seus resultados podem ser encontrados no Adobe Target.

**Tópicos relacionados:**

* [Portal da Adobe Target](https://docs.adobe.com/content/help/pt-BR/target/using/integrate/campaign-and-target.html)
* [Sobre o design de conteúdo de email](../../designing/using/designing-content-in-adobe-campaign.md)
* [Personalizar imagens de e-mail em vídeo em tempo](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html) real

