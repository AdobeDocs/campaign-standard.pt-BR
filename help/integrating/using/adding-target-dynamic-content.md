---
solution: Campaign Standard
product: campaign
title: Adicionar conteúdo dinâmico do Target
description: Saiba como adicionar conteúdo dinâmico Adobe Target em um de seus delivery Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-target
translation-type: tm+mt
source-git-commit: 3672f0bc4ebc551c4eb34660a3a55d44fa726f1a
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 35%

---


# Adicionar conteúdo dinâmico do Target{#adding-target-dynamic-content}

Com a integração do Adobe Target, imagens dinâmicas podem ser adicionadas a um delivery para personalizar seu conteúdo, dependendo das experiências.

Ao editar um email, você pode inserir uma imagem dinâmica do Adobe Target que será alterada dependendo dos recipient.

Antes de acessar a imagem no Adobe Campaign, as seguintes tarefas devem ser executadas primeiro no Adobe Target:

* Crie um ou vários [ofertas de redirecionamento](https://docs.adobe.com/content/help/en/target/using/experiences/offers/offer-redirect.html), nos quais você deve especificar o URL da imagem que será usada.
* Crie um ou vários [públicos](https://docs.adobe.com/content/help/en/target/using/audiences/create-audiences/audiences.html)para definir o target da atividade.
* Crie uma atividade [Criador de experiências baseado em forma](https://docs.adobe.com/content/help/en/target/using/experiences/form-experience-composer.html), na qual você precisa selecionar uma rawbox e especificar várias experiências, dependendo do número de ofertas de redirecionamento criadas. Para cada experiência, você deve selecionar uma das ofertas de redirecionamento criadas.
* Crie segmentos usando informações da Adobe Campaign para especificar experiências. Para usar dados do Adobe Campaign nas regras de seleção da oferta, especifique os dados no rawbox no Adobe Target.

1. Crie um delivery de email
1. Ao editar o conteúdo de um email ou de uma landing page, vá para um bloco de imagem e selecione **[!UICONTROL Dynamic image from Adobe Target]** pelo menu contextual.

   ![](assets/tar_insert_dynamic_image.png)

1. Selecione a imagem que aparecerá por padrão no email. Você pode especificar diretamente o URL da imagem ou selecionar uma imagem compartilhada via [Assets](../../integrating/using/working-with-campaign-and-assets-core-service.md).

   A integração só oferece suporte a imagens estáticas. O restante do conteúdo não é personalizável.

1. Insira o nome do rawbox especificado no Adobe Target.
1. Se você usar permissões do Enterprise em suas configurações no Adobe Target, adicione a propriedade correspondente nesse campo. Saiba mais sobre as permissões do Target Enterprise [nesta página](https://docs.adobe.com/content/help/pt-BR/target/using/administer/manage-users/enterprise/properties-overview.html). Este campo é opcional e não é necessário se você não usar permissões do Enterprise no Target.
1. Em **[!UICONTROL Additional decision parameters]**, especifique o mapeamento entre os campos definidos nos segmentos do Adobe Target e os campos do Adobe Campaign.

   Os campos do Adobe Campaign usados devem ter sido especificados no rawbox. Aqui, definiremos experiências diferentes dependendo do gênero do recipient.

   ![](assets/tar_additional_decisionning_parameters.png)

1. Pré-visualização seu email para ver se, ao selecionar perfis diferentes, a imagem inserida muda dependendo dos parâmetros especificados na atividade do Adobe Target e no Adobe Campaign.

Seu delivery que contém a imagem dinâmica agora pode ser enviado. Seus resultados podem ser encontrados no Adobe Target.

**Tópicos relacionados:**

* [Portal da Adobe Target](https://docs.adobe.com/content/help/en/target/using/integrate/campaign-and-target.html)
* [Sobre o design de conteúdo de email](../../designing/using/designing-content-in-adobe-campaign.md)
* [Personalizar imagens de e-mail em ](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html) vídeo em tempo real

