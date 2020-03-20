---
title: Definir a linha de assunto e o remetente de um email
description: Descubra como definir a linha de assunto e o remetente de um email no Designer de email.
page-status-flag: never-activated
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6f89b420f0f98c13da1bfff8f9b1b29e015aef89

---


# Definir a linha de assunto e o remetente de um email{#defining-the-subject-line-of-an-email}

## Defining the subject line of an email {#subject-line}

O assunto da mensagem é obrigatório para preparar e enviar a mensagem.

>[!NOTE]
>
>Se a linha de assunto estiver vazia, um aviso será exibido no painel de mensagens e no Designer de email.

1. Crie um email.
1. Vá para a **[!UICONTROL Properties]** guia da página inicial do Email Designer (acessível pelo ícone inicial).
1. Preencha a **[!UICONTROL Subject]** seção.

   ![](assets/email_designer_subject.png)

1. Também é possível adicionar campos de personalização, blocos de conteúdo e conteúdo dinâmico à linha de assunto clicando nos ícones correspondentes. For more on this, see [Personalization](../../designing/using/personalization.md).
1. Você pode testar diferentes linhas de assunto para obter uma estimativa da sua taxa de abertura de email antes de enviá-la. Para obter mais informações, consulte [Testando a linha de assunto de um email](../../sending/using/testing-subject-line-email.md).

## Definição do remetente de email de um email {#email-sender}

Para definir o nome do remetente que aparecerá no cabeçalho das mensagens enviadas, vá para a **[!UICONTROL Properties]** guia da página inicial do Email Designer (acessível por meio do ícone inicial).

![](assets/delivery_content_edition16.png)

* O **[!UICONTROL From: name]** campo permite que você insira o nome do remetente. Por padrão, o bloco padrão de nome **do** remetente é inserido automaticamente no campo. O endereço de e-mail do remetente e o nome do remetente padrão são definidos em **[!UICONTROL Brands]** acessível através do logotipo do Adobe Campaign no menu avançado **[!UICONTROL Administration > Instance settings > Brand configuration]** .

   Você pode alterar o nome do remetente clicando no bloco de nome **do** remetente. O campo se torna editável e você pode inserir o nome que deseja usar.

   Este campo pode ser personalizado. Para fazer isso, você pode adicionar campos de personalização, blocos de conteúdo e conteúdo dinâmico clicando nos ícones abaixo do nome do remetente. For more on this, see [Personalization](../../designing/using/personalization.md).

* O **[!UICONTROL From: email address]** campo não pode ser editado desta seção. É possível alterá-lo editando as propriedades do email a partir de seu painel. Para obter mais informações, consulte [Lista de parâmetros](../../administration/using/configuring-email-channel.md#advanced-parameters)avançados de email.

>[!NOTE]
>
>Os parâmetros do cabeçalho não devem ficar vazios. O endereço do remetente é obrigatório para possibilitar o envio de um email (padrão RFC). O Adobe Campaign verifica a sintaxe dos endereços de email inseridos.

**Tópicos relacionados:**

* [Inserção de um campo de personalização](../../designing/using/personalization.md#inserting-a-personalization-field)
* [Adicionar um bloco de conteúdo](../../designing/using/personalization.md#adding-a-content-block)
* [Definição de conteúdo dinâmico em um email](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)
