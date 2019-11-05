---
title: Sobre mensagens SMS
description: Descubra as principais especificidades do canal SMS no Adobe Campaign.
page-status-flag: nunca ativado
uuid: 14dc7434-8171-4ad1-9540-52ca637659a9
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: canais
content-type: referência
topic-tags: sms-messages
discoiquuid: 6134fe72-77de-4fd0-b794-4d966effaccf
delivercontext-tags: delivery,assistente;delivery,smsContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Sobre mensagens SMS{#about-sms-messages}

O Adobe Campaign permite que você entregue mensagens SMS (Short Message Service).

>[!NOTE]
>
>O canal SMS é um suplemento. Verifique o contrato de licença.

Para mensagens SMS, você poderá criar, modificar e personalizar mensagens somente no formato de texto. Você também poderá visualizar suas mensagens SMS antes de enviá-las.

O comprimento de uma mensagem SMS é restrito a 160 caracteres se estiver na codificação GSM e somente a 70 caracteres se estiver em Unicode. No entanto, determinados caracteres especiais podem influenciar o comprimento da mensagem. For more on this, refer to the [SMS encoding](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) section.

As mensagens SMS podem ser criadas a partir do **[!UICONTROL Marketing activities]** menu, de uma campanha ou em um fluxo de trabalho, consulte [Criar uma mensagem](../../channels/using/creating-an-sms-message.md)SMS.

Para enviar mensagens SMS para um telefone celular, é necessário:

* Uma conta **[!UICONTROL Routing]** externa configurada no **[!UICONTROL Mobile (SMS)]** canal com o **[!UICONTROL Bulk delivery]** modo. For more on this, refer to the [Routing](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing) section.
* Um modelo de entrega vinculado corretamente a esta conta externa.

**Tópicos relacionados:**

* [Gerenciamento de modelos](../../start/using/about-templates.md)
* [Configuração SMS](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)
* [Relatório SMS](../../reporting/using/sms-report.md)

## Modelo de entrega SMS {#sms-delivery-template}

O Adobe Campaign oferece um modelo de entrega para dispositivos móveis. Esse modelo deve estar vinculado corretamente à conta externa usada para o **[!UICONTROL Mobile (SMS)]** canal. Para acessar e modificar:

1. Selecione **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Delivery templates]** no menu avançado.
1. Passe o mouse sobre o **[!UICONTROL Send via SMS]** modelo e selecione a opção **Duplicar elemento** .
1. Selecione o novo modelo.
1. Click the **[!UICONTROL Edit properties]** button.
1. Na **[!UICONTROL Advanced parameters]** seção das propriedades do modelo, verifique se o modelo está vinculado à conta externa a ser usada para fornecer SMS.

   ![](assets/sms_template.png)

**Tópicos relacionados:**

* [Gerenciamento de modelos](../../start/using/about-templates.md)

