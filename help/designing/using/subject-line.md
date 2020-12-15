---
solution: Campaign Standard
product: campaign
title: Definir a linha de assunto e o remetente de um email
description: Descubra como definir a linha de assunto e o remetente de um email no Designer de email.
audience: designing
content-type: reference
topic-tags: editing-email-content
translation-type: tm+mt
source-git-commit: 1e7359db2de1a9c420af33ac85c0597c098ae3f8
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 12%

---


# Definir a linha de assunto e o remetente de um email{#defining-the-subject-line-of-an-email}

## Definição da linha de assunto de um email {#subject-line}

O assunto da mensagem é obrigatório para preparar e enviar a mensagem.

>[!NOTE]
>
>Se a linha de assunto estiver vazia, um aviso será exibido no painel de mensagem e no Designer de email.

1. Criar um email.
1. Vá para a guia **[!UICONTROL Properties]** do home page do Email Designer (acessível pelo ícone inicial).
1. Preencha a seção **[!UICONTROL Subject]**.

   ![](assets/email_designer_subject.png)

1. Você também pode adicionar campos de personalização, blocos de conteúdo e conteúdo dinâmico à linha de assunto clicando nos ícones correspondentes. Para obter mais informações, consulte [Personalização](../../designing/using/personalization.md).

## Definição do remetente de email de um email {#email-sender}

Para definir o nome do remetente que aparecerá no cabeçalho das mensagens enviadas, vá para a guia **[!UICONTROL Properties]** do home page do Email Designer (acessível por meio do ícone inicial).

![](assets/delivery_content_edition16.png)

* O campo **[!UICONTROL From: name]** permite que você insira o nome do remetente. Por padrão, o bloco padrão **Nome do remetente** é inserido automaticamente no campo. O endereço de email do remetente e o nome do remetente padrão estão definidos em **[!UICONTROL Brands]** acessíveis através do logotipo da Adobe Campaign no menu avançado **[!UICONTROL Administration > Instance settings > Brand configuration]**.

   Você pode alterar o nome do remetente clicando no bloco **Nome do remetente**. O campo se torna editável e você pode inserir o nome que deseja usar.

   Este campo pode ser personalizado. Para fazer isso, você pode adicionar campos de personalização, blocos de conteúdo e conteúdo dinâmico clicando nos ícones abaixo do nome do remetente. Para obter mais informações, consulte [Personalização](../../designing/using/personalization.md).

* O campo **[!UICONTROL From: email address]** não pode ser editado desta seção. É possível alterá-lo editando as propriedades do email a partir do painel. Para obter mais informações, consulte [Lista de parâmetros avançados de email](../../administration/using/configuring-email-channel.md#advanced-parameters).

>[!NOTE]
>
>Os parâmetros do cabeçalho não devem ficar vazios. O endereço do remetente é obrigatório para possibilitar o envio de um email (padrão RFC). O Adobe Campaign verifica a sintaxe dos endereços de email inseridos.

**Tópicos relacionados:**

* [Inserção de um campo de personalização](../../designing/using/personalization.md#inserting-a-personalization-field)
* [Inclusão de um bloco de conteúdo](../../designing/using/personalization.md#adding-a-content-block)
* [Definição de conteúdo dinâmico em um email](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)
