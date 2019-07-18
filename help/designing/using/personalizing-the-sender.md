---
title: Personalização do remetente
seo-title: Personalização do remetente
description: Personalização do remetente
seo-description: Saiba como personalizar o nome ou o endereço do remetente das suas mensagens.
page-status-flag: nunca ativado
uuid: 7 aa 08 d 5 d -9 e 6 c -4 dac-bff 8-6 fde 85368 c 2 d
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: personalização-conteúdo
discoiquuid: 49532 f 6 b -3 cd 0-4 d 03-932 e-bcb 7 d 05 c 74 d 4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Personalizing the sender{#personalizing-the-sender}

## Email sender {#email-sender}

To define the name of the sender which will appear in the header of messages sent, go the **[!UICONTROL Properties]** tab of the Email Designer home page (accessible through the home icon).

![](assets/delivery_content_edition16.png)

* **[!UICONTROL From: name]** O campo permite que você insira o nome do remetente. By default, the default **Sender name** block is automatically entered in the field. Adobe Campaign refers to the email channel configuration (from the advanced menu **[!UICONTROL Administration > Channels > Email > Email accounts]** via the Adobe Campaign logo) to designate this sender.

   You can change the sender name by clicking the **Sender name** block. O campo torna-se editável e você pode inserir o nome que deseja usar.

   Esse campo pode ser personalizado. Para fazer isso, você pode adicionar campos de personalização, blocos de conteúdo e conteúdo dinâmico clicando nos ícones abaixo do nome do remetente.

* The **[!UICONTROL From: email address]** field cannot be edited from this section. Você pode alterá-la editando as propriedades do email de seu painel. For more on this, see [List of email advanced parameters](../../administration/using/configuring-email-channel.md#advanced-parameters).

>[!NOTE]
>
>Os parâmetros do cabeçalho não devem estar vazios. O endereço do remetente é obrigatório para permitir que um email seja enviado (padrão RFC). O Adobe Campaign verifica a sintaxe dos endereços de email inseridos.

**Tópicos relacionados:**

* [Inserir um campo de personalização](../../designing/using/inserting-a-personalization-field.md)
* [Adicionar um bloco de conteúdo](../../designing/using/adding-a-content-block.md)
* [Definição de conteúdo dinâmico em um email](../../designing/using/defining-dynamic-content-in-an-email.md)

## SMS sender {#sms-sender}

Você pode personalizar o nome do remetente do SMS. For more on this, refer to the [SMS configuration](../../administration/using/configuring-sms-channel.md#configuring-sms-properties) section.
