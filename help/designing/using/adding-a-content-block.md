---
title: Adicionar um bloco de conteúdo
seo-title: Adicionar um bloco de conteúdo
description: Adicionar um bloco de conteúdo
seo-description: Descubra os diversos blocos de conteúdo dinâmico prontos para uso que você pode usar para personalizar suas mensagens e aprender como criar blocos de conteúdo personalizados.
page-status-flag: nunca ativado
uuid: 08153 ea 0-42 fb -4 c 0 b -8 d 4 b -9407540748 d 6
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: personalização-conteúdo
discoiquuid: 3 ffda 143-f 42 a -4 cf 9-b -e 53 d 24549025
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Adding a content block{#adding-a-content-block}

O Adobe Campaign oferece uma lista de blocos de conteúdo pré-configurados. Esses blocos de conteúdo são dinâmicos, personalizados e têm uma renderização específica. Por exemplo, é possível adicionar uma saudação ou um link à página espelhada.

>[!NOTE]
>
>The images below show how to insert a content block using the [Email Designer](../../designing/using/about-email-content-design.md#about-the-email-designer) for an email.

Para adicionar um bloco de conteúdo:

1. Click inside a text block, click the **[!UICONTROL Personalize]** icon from the contextual toolbar and select **[!UICONTROL Insert content block]**. For more on the Email Designer interface, see [this section](../../designing/using/about-email-content-design.md#email-designer-interface).

   ![](assets/email_content_block_1.png)

1. Selecione o bloco de conteúdo que deseja inserir. Os blocos disponíveis variam dependendo do contexto (e-mail ou página de aterrissagem).

   ![](assets/email_content_block_2.png)

1. Click **[!UICONTROL Save]**.

O nome do bloco de conteúdo aparece no editor e é destacado em amarelo. Isso se ajusta automaticamente ao perfil quando a personalização é gerada.

![](assets/email_content_block_3.png)

Os blocos de conteúdo prontos para uso são:

* **[!UICONTROL Database URL in emails (EmailUrlBase)]**: Esse bloco de conteúdo só pode ser usado em uma **entrega**.
* **[!UICONTROL Mirror page URL (MirrorPageUrl)]**: Esse bloco de conteúdo só pode ser usado em uma **entrega**.
* **[!UICONTROL Link to mirror page (MirrorPage)]**: Esse bloco de conteúdo só pode ser usado em uma **entrega**.
* **[!UICONTROL Greetings (Greetings)]**
* **[!UICONTROL Unsubscription link (UnsubscriptionLink)]**: Esse bloco de conteúdo só pode ser usado em uma **entrega**.
* **[!UICONTROL Social network sharing links (LandingPageViralLinks)]**: Esse bloco de conteúdo só pode ser usado em uma página **de aterrissagem**.
* **[!UICONTROL Default sender name (DefaultSenderName)]**: Esse bloco de conteúdo só pode ser usado em uma **entrega**.
* **[!UICONTROL Name of default reply-to email address (DefaultReplyName)]**: Esse bloco de conteúdo só pode ser usado em uma **entrega**.
* **[!UICONTROL Email address of default sender (DefaultSenderAddress)]**: Esse bloco de conteúdo só pode ser usado em uma **entrega**.
* **[!UICONTROL Default error email address (DefaultErrorAddress)]**: Esse bloco de conteúdo só pode ser usado em uma **entrega**.
* **[!UICONTROL Default reply-to email address (DefaultReplyAddress)]**: Esse bloco de conteúdo só pode ser usado em uma **entrega**.
* **[!UICONTROL Brand name (BrandingUsualName)]**
* **[!UICONTROL Link to the brand website (BrandingWebSiteLink)]**
* **[!UICONTROL Brand logo (BrandingLogo)]**
* **[!UICONTROL Notification style (notificationStyle)]**

## Creating custom content blocks {#creating-custom-content-blocks}

É possível definir novos blocos de conteúdo que serão inseridos em uma mensagem ou página de aterrissagem.

Para criar um bloco de conteúdo, siga estas etapas:

1. Click **[!UICONTROL Resources > Content blocks]** from the advanced menu to access the list of content blocks.
1. Click the **[!UICONTROL Create]** button or duplicate a pre-existing content block.

   ![](assets/content_bloc_01.png)

1. Insira um rótulo.
1. Select the block's **[!UICONTROL Content type]**. Há três opções disponíveis:

   * **[!UICONTROL Shared]**: O bloco de conteúdo pode ser usado em uma entrega ou em uma página de aterrissagem.
   * **[!UICONTROL Delivery]**: O bloco de conteúdo só pode ser usado em uma entrega.
   * **[!UICONTROL Landing page]**: O bloco de conteúdo só pode ser usado em uma página de aterrissagem.
   ![](assets/content_bloc_02.png)

1. You can select a **[!UICONTROL Targeting dimension]**. For more on this, see [About targeting dimension](../../designing/using/adding-a-content-block.md#about-targeting-dimension).

   ![](assets/content_bloc_04.png)

1. You can select the **[!UICONTROL Depends on format]** option to define two different blocks: one for HTML emails, and one for emails in text format. Duas guias serão exibidas no editor (HTML e Texto) para definir o conteúdo correspondente.

   ![](assets/content_bloc_03.png)

1. Enter the content of the content block(s), and click the **[!UICONTROL Create]** button.

O bloco de conteúdo agora pode ser usado no editor de conteúdo de uma mensagem ou de uma página de aterrissagem.

## About targeting dimension {#about-targeting-dimension}

A dimensão de definição de metas permite definir em que tipo de mensagem você pode usar o bloco de conteúdo. Isso serve para evitar o uso de blocos inadequados em uma mensagem, o que pode causar erros.

Na verdade, ao editar uma mensagem, você só pode selecionar blocos de conteúdo com uma dimensão de definição de metas compatível com a dimensão de direcionamento dessa mensagem.

For example, the **[!UICONTROL Unsubscription link]** block's targeting dimension is **[!UICONTROL Profiles]** because it contains personalization fields specific to the **[!UICONTROL Profiles]** resource. Therefore, you cannot use an **[!UICONTROL Unsubscription link]** block in an [event transactional message](../../channels/using/event-transactional-messages.md), because the targeting dimension of that type of message is **[!UICONTROL Real-time events]**. However, you can use the **Unsubscription link** block in a [profile transactional message](../../channels/using/profile-transactional-messages.md), because the targeting dimension of that type of message is **Profiles**. Finally, the **[!UICONTROL Link to mirror page]** block does not have a targeting dimension, so you can use it in any message.

Se você deixar este campo vazio, o bloco de conteúdo será compatível com todas as mensagens, independentemente da dimensão de definição de metas. Se você definir uma dimensão de definição de metas, esse bloco só será compatível com mensagens que têm a mesma dimensão de definição de metas.

For more on this, refer to [Targeting dimensions and resources](../../automating/using/query.md#targeting-dimensions-and-resources).
