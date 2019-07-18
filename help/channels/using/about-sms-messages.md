---
title: Sobre mensagens SMS
seo-title: Sobre mensagens SMS
description: Sobre mensagens SMS
seo-description: Descubra as principais especificidades do canal SMS no Adobe Campaign.
page-status-flag: nunca ativado
uuid: 14 dc 7434-8171-4 ad 1-9540-52 ca 637659 a 9
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canais
content-type: reference
topic-tags: sms-messages
discoiquuid: 6134 fe 72-77 de -4 fd 0-b 794-4 d 966 effaccf
delivercontext-tags: Deliverycreation, assistente; entrega, smscontent, voltar
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b0cf437ec97153b53bd4502171b24286abb25731

---


# About SMS messages{#about-sms-messages}

O Adobe Campaign permite fornecer mensagens SMS (Serviço de mensagens curtas).

>[!NOTE]
>
>O canal SMS é um suplemento. Verifique seu contrato de licença.

Para mensagens SMS, é possível criar, modificar e personalizar mensagens apenas em formato de texto. Também é possível visualizar suas mensagens SMS antes de serem enviadas.

O tamanho de uma mensagem SMS será restrito a 160 caracteres se estiver na codificação GSM e apenas 70 caracteres se estiver em Unicode. No entanto, determinados caracteres especiais podem influenciar o comprimento da mensagem. For more on this, refer to the [SMS encoding](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) section.

SMS messages can be created from the **[!UICONTROL Marketing activities]** menu, from a campaign, or in a workflow, see [Creating an SMS message](../../channels/using/creating-an-sms-message.md).

Para fornecer mensagens SMS a um telefone celular, é necessário:

* A **[!UICONTROL Routing]** external account configured on the **[!UICONTROL Mobile (SMS)]** channel with the **[!UICONTROL Bulk delivery]** mode. For more on this, refer to the [Routing](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing) section.
* Um modelo de entrega que está corretamente vinculado a esta conta externa.

**Tópicos relacionados:**

* [Gerenciamento de modelos](../../start/using/about-templates.md)
* [Configuração de SMS](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)

## SMS delivery template {#sms-delivery-template}

O Adobe Campaign oferece um modelo de entrega para dispositivos móveis. This template must be correctly linked to the external account used for the **[!UICONTROL Mobile (SMS)]** channel. Para acessá-lo e modificá-lo:

1. Select **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Delivery templates]** from the advanced menu.
1. Hover over the **[!UICONTROL Send via SMS]** template with the mouse and select the **Duplicate element** option.
1. Selecione o novo modelo.
1. Click the **[!UICONTROL Edit properties]** button.
1. In the **[!UICONTROL Advanced parameters]** section of the template properties, make sure that the template is linked to the external account to be used for delivering SMS.

   ![](assets/sms_template.png)

**Tópicos relacionados:**

* [Gerenciamento de modelos](../../start/using/about-templates.md)

