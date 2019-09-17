---
title: Adicionar conteúdo dinâmico do Target
seo-title: Adicionar conteúdo dinâmico do Target
description: Adicionar conteúdo dinâmico do Target
seo-description: Saiba como adicionar conteúdo dinâmico do Adobe Target em uma de suas entregas do Adobe Campaign.
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
source-git-commit: ea825afe573959d95d0f7f3f6e79dd38ac5a678a

---


# Adicionar conteúdo dinâmico do Target{#adding-target-dynamic-content}

Com a integração do Adobe Target, as imagens dinâmicas podem ser adicionadas a uma entrega para personalizar seu conteúdo, dependendo das experiências.

Ao editar um email, você pode inserir uma imagem dinâmica do Adobe Target que será alterada dependendo dos destinatários.

Antes de acessar a imagem no Adobe Campaign, as seguintes tarefas devem ser executadas primeiro no Adobe Target:

* Crie uma ou várias ofertas [de](https://docs.adobe.com/content/help/en/target/using/experiences/offers/offer-redirect.html)redirecionamento, nas quais você deve especificar o URL da imagem que será usada.
* Crie um ou vários [públicos-alvo](https://marketing.adobe.com/resources/help/en_US/target/ov/c_about_segments.html)para definir o alvo de sua atividade.
* Crie uma atividade de compositor [de experiência baseada em](https://marketing.adobe.com/resources/help/en_US/target/target/t_form_experience_composer.html) formulário, na qual você deve selecionar uma rawbox e especificar várias experiências, dependendo do número de ofertas de redirecionamento criadas. Para cada experiência, você deve selecionar uma das ofertas de redirecionamento criadas.
* Crie segmentos usando informações do Adobe Campaign para especificar experiências. Para usar dados do Adobe Campaign nas regras de seleção da oferta, você deve especificar os dados na rawbox no Adobe Target.

1. Crie uma entrega por email.
1. Ao editar o conteúdo de um email ou de uma página de aterrissagem, vá para um bloco de imagem e selecione-o **[!UICONTROL Dynamic image from Adobe Target]** pelo menu contextual.

   ![](assets/tar_insert_dynamic_image.png)

1. Selecione a imagem que aparecerá por padrão no email. Você pode especificar diretamente o URL da imagem ou selecionar uma imagem compartilhada por meio dos [Ativos](../../integrating/using/working-with-campaign-and-assets-core-service.md).

   A integração suporta apenas imagens estáticas. O restante do conteúdo não é personalizável.

1. Digite o nome da rawbox especificada no Adobe Target.
1. Se você usar permissões Enterprise em suas configurações no Adobe Target, adicione a propriedade correspondente neste campo. Saiba mais sobre as permissões do Target Enterprise [nesta página](https://marketing.adobe.com/resources/help/en_US/target/target/properties-overview.html). Esse campo é opcional e não é obrigatório se você não usar permissões Enterprise no Target.
1. Em **[!UICONTROL Additional decision parameters]**, especifique o mapeamento entre os campos definidos nos segmentos do Adobe Target e os campos do Adobe Campaign.

   Os campos do Adobe Campaign usados devem ter sido especificados na rawbox. Aqui, definiremos experiências diferentes dependendo do gênero do destinatário.

   ![](assets/tar_additional_decisionning_parameters.png)

1. Visualize seu email para ver se, ao selecionar perfis diferentes, a imagem inserida muda dependendo dos parâmetros especificados na atividade do Adobe Target e no Adobe Campaign.

Sua entrega contendo a imagem dinâmica agora pode ser enviada. Seus resultados podem ser encontrados no Adobe Target.

**Tópicos relacionados:**

* [Portal do Adobe Target](https://marketing.adobe.com/resources/help/en_US/target/a4t/c_campaign_and_target.html)
* [Sobre o design de conteúdo de email](../../designing/using/overview.md)
* [Personalizar imagens de email em vídeo em tempo](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html) real

