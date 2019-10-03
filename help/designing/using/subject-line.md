---
title: Definir a linha de assunto e o remetente de um email
seo-title: Definir a linha de assunto e o remetente de um email
description: Definir a linha de assunto e o remetente de um email
seo-description: Descubra como definir a linha de assunto e o remetente de um email no Designer de email.
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
source-git-commit: 5847c89b97ede8b03e75d1d90f31c88ed5c8a84e

---


# Definir a linha de assunto e o remetente de um email{#defining-the-subject-line-of-an-email}

O assunto da mensagem é obrigatório para preparar e enviar a mensagem.

>[!NOTE]
>
>Se a linha de assunto estiver vazia, um aviso será exibido no painel de mensagens e no Designer de email.

To configure the email subject, go the **[!UICONTROL Properties]** tab of the Email Designer home page (accessible through the home icon) and fill in the **[!UICONTROL Subject]** section.

**To define the subject line of an email**:

1. Create an email.
1. Close homepage.
1. Go the  tab of the Email Designer home page (accessible through the home icon) and fill in the  section.**[!UICONTROL Properties]****[!UICONTROL Subject]**

![](assets/email_designer_subject.png)

You can also add personalization fields, content blocks and dynamic content to the subject line by clicking the corresponding icons.

**Tópicos relacionados:**

* [Inserção de um campo de personalização](../../designing/using/personalization.md#inserting-a-personalization-field)
* [Adding a content block](../../designing/using/personalization.md#adding-a-content-block)
* [Defining dynamic content in an email](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)

## Predictive subject line {#predictive-subject-line}

When editing an email, you can try out different subject lines and get an estimation of its open rate before you send it.

This feature is disabled by default. Ela é ativada quando o primeiro modelo é importado. A model is the result of training data sets specific to a given industry. Os modelos permitem que o sistema preveja a taxa de abertura do email quando uma nova linha de assunto for enviada.

>[!NOTE]
>
>Este recurso está disponível para mensagens de email e bancos de dados que contêm apenas conteúdo em inglês. O modelo treinado será inconsistente e resultará em resultados incorretos se sua instância contiver emails em outros idiomas. A opção que permite testar um assunto só estará visível se um modelo já estiver disponível em sua instância.

**Tópico relacionado**

* [Teste da linha de assunto de um email](../../sending/using/testing-subject-line-email.md)

## Remetente de email {#email-sender}

Para definir o nome do remetente que aparecerá no cabeçalho das mensagens enviadas, vá para a **[!UICONTROL Properties]** guia da página inicial do Email Designer (acessível por meio do ícone inicial).

![](assets/delivery_content_edition16.png)

* O **[!UICONTROL From: name]** campo permite inserir o nome do remetente. Por padrão, o bloco padrão de nome **do** remetente é inserido automaticamente no campo. O Adobe Campaign se refere à configuração do canal de email (do menu avançado **[!UICONTROL Administration > Channels > Email > Email accounts]** pelo logotipo do Adobe Campaign) para designar esse remetente.

   Você pode alterar o nome do remetente clicando no bloco de nome **do** remetente. O campo se torna editável e você pode inserir o nome que deseja usar.

   Este campo pode ser personalizado. Para fazer isso, você pode adicionar campos de personalização, blocos de conteúdo e conteúdo dinâmico clicando nos ícones abaixo do nome do remetente.

* The **[!UICONTROL From: email address]** field cannot be edited from this section. You can change it by editing the properties of the email from its dashboard. Para obter mais informações, consulte [Lista de parâmetros](../../administration/using/configuring-email-channel.md#advanced-parameters)avançados de email.

>[!NOTE]
>
>Os parâmetros do cabeçalho não devem ficar vazios. O endereço do remetente é obrigatório para possibilitar o envio de um email (padrão RFC). O Adobe Campaign verifica a sintaxe dos endereços de email inseridos.

**Tópicos relacionados:**

* [Inserção de um campo de personalização](../../designing/using/personalization.md#inserting-a-personalization-field)
* [Adding a content block](../../designing/using/personalization.md#adding-a-content-block)
* [Definição de conteúdo dinâmico em um email](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)
