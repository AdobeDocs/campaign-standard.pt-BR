---
title: Definição da linha de assunto e do remetente de um email
description: Saiba como definir a linha de assunto e o remetente de um email no Designer de email.
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Beginner
exl-id: 22112517-40f7-4966-84bf-40794e5d0f79
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 12%

---

# Definição da linha de assunto e do remetente de um email{#defining-the-subject-line-of-an-email}

## Definição da linha de assunto de um email {#subject-line}

O assunto da mensagem é obrigatório para preparar e enviar a mensagem.

>[!NOTE]
>
>Se a linha de assunto estiver vazia, um aviso será exibido no painel de mensagens e no Designer de email.

1. Criar um email.
1. Vá para **[!UICONTROL Properties]** da página inicial do Designer de email (acessível pelo ícone inicial).
1. Preencha o **[!UICONTROL Subject]** seção.

   ![](assets/email_designer_subject.png)

1. Também é possível adicionar campos de personalização, blocos de conteúdo e conteúdo dinâmico à linha de assunto clicando nos ícones correspondentes. Para obter mais informações, consulte [Personalização](../../designing/using/personalization.md).

## Definição do remetente de email de um email {#email-sender}

Para definir o nome do remetente que aparecerá no cabeçalho das mensagens enviadas, acesse **[!UICONTROL Properties]** da página inicial do Designer de email (acessível pelo ícone inicial).

![](assets/delivery_content_edition16.png)

* O **[!UICONTROL From: name]** permite inserir o nome do remetente. Por padrão, a variável **Nome do remetente** bloco é inserido automaticamente no campo . O endereço de email do remetente padrão e o nome do remetente são definidos em **[!UICONTROL Brands]** acessível através do logotipo do Adobe Campaign no menu avançado **[!UICONTROL Administration > Instance settings > Brand configuration]** .

   Você pode alterar o nome do remetente clicando no botão **Nome do remetente** bloco. O campo se torna editável e você pode inserir o nome que deseja usar.

   Esse campo pode ser personalizado. Para fazer isso, é possível adicionar campos de personalização, blocos de conteúdo e conteúdo dinâmico clicando nos ícones abaixo do nome do remetente. Para obter mais informações, consulte [Personalização](../../designing/using/personalization.md).

* O **[!UICONTROL From: email address]** não é possível editar o campo nesta seção. Você pode alterá-lo editando as propriedades do email no painel. Para obter mais informações, consulte [Lista de parâmetros avançados de email](../../administration/using/configuring-email-channel.md#advanced-parameters).

>[!NOTE]
>
>Os parâmetros do cabeçalho não devem ficar vazios. O endereço do remetente é obrigatório para possibilitar o envio de um email (padrão RFC). O Adobe Campaign verifica a sintaxe dos endereços de email inseridos.

**Tópicos relacionados:**

* [Inserção de um campo de personalização](../../designing/using/personalization.md#inserting-a-personalization-field)
* [Inclusão de um bloco de conteúdo](../../designing/using/personalization.md#adding-a-content-block)
* [Definição de conteúdo dinâmico em um email](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)
