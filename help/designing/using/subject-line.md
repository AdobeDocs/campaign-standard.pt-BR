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
source-git-commit: 0cf4807fc3d617b0c5ca33705b6344d1f3994ab3

---


# Definir a linha de assunto e o remetente de um email{#defining-the-subject-line-of-an-email}

O assunto da mensagem é obrigatório para preparar e enviar a mensagem.

>[!NOTE]
>
>Se a linha de assunto estiver vazia, um aviso será exibido no painel de mensagens e no Designer de email.

Para configurar o assunto do email, vá para a **[!UICONTROL Properties]** guia da página inicial do Email Designer (acessível pelo ícone inicial) e preencha a seção **[!UICONTROL Subject]** .

**To define the subject line of an email**:

1. Create an email.
1. Close homepage.
1. Go the  tab of the Email Designer home page (accessible through the home icon) and fill in the  section.**[!UICONTROL Properties]****[!UICONTROL Subject]**

![](assets/email_designer_subject.png)

You can also add personalization fields, content blocks and dynamic content to the subject line by clicking the corresponding icons.

**Related topics:**

* [Inserting a personalization field](../../designing/using/personalization.md#inserting-a-personalization-field)
* [Adding a content block](../../designing/using/personalization.md#adding-a-content-block)
* [Defining dynamic content in an email](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)

## Predictive subject line {#predictive-subject-line}

When editing an email, you can try out different subject lines and get an estimation of its open rate before you send it.

This feature is disabled by default. It is enabled when the first model is imported. Um modelo é o resultado de conjuntos de dados de treinamento específicos para um determinado setor. Models allow the system to predict the open rate of the email when a new subject line is submitted.

>[!NOTE]
>
>Este recurso está disponível para mensagens de email e bancos de dados que contêm apenas conteúdo em inglês. The trained model will be inconsistent and will lead to erroneous results if your instance contains emails in other languages. A opção que permite testar um assunto só estará visível se um modelo já estiver disponível em sua instância.

**Tópico relacionado**

* [Testando uma linha de assunto](../../sending/using/testing-subject-line-email.md)

## Remetente de email {#email-sender}

Para definir o nome do remetente que aparecerá no cabeçalho das mensagens enviadas, vá para a **[!UICONTROL Properties]** guia da página inicial do Email Designer (acessível por meio do ícone inicial).

![](assets/delivery_content_edition16.png)

* O **[!UICONTROL From: name]** campo permite inserir o nome do remetente. Por padrão, o bloco padrão de nome **do** remetente é inserido automaticamente no campo. O Adobe Campaign se refere à configuração do canal de email (do menu avançado **[!UICONTROL Administration > Channels > Email > Email accounts]** pelo logotipo do Adobe Campaign) para designar esse remetente.

   Você pode alterar o nome do remetente clicando no bloco de nome **do** remetente. O campo se torna editável e você pode inserir o nome que deseja usar.

   Este campo pode ser personalizado. Para fazer isso, você pode adicionar campos de personalização, blocos de conteúdo e conteúdo dinâmico clicando nos ícones abaixo do nome do remetente.

* O **[!UICONTROL From: email address]** campo não pode ser editado desta seção. É possível alterá-lo editando as propriedades do email a partir de seu painel. Para obter mais informações, consulte [Lista de parâmetros](../../administration/using/configuring-email-channel.md#advanced-parameters)avançados de email.

>[!NOTE]
>
>Os parâmetros do cabeçalho não devem estar vazios. O endereço do remetente é obrigatório para permitir o envio de um email (padrão RFC). O Adobe Campaign verifica a sintaxe dos endereços de email inseridos.

**Tópicos relacionados:**

* [Inserir um campo de personalização](../../designing/using/personalization.md#inserting-a-personalization-field)
* [Adicionar um bloco de conteúdo](../../designing/using/personalization.md#adding-a-content-block)
* [Definição de conteúdo dinâmico em um email](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)