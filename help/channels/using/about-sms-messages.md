---
solution: Campaign Standard
product: campaign
title: Sobre mensagens SMS
description: Descubra as principais especificidades do canal SMS no Adobe Campaign.
audience: channels
content-type: reference
topic-tags: sms-messages
delivercontext-tags: deliveryCreation,wizard;delivery,smsContent,back
feature: SMS
role: Business Practitioner
level: Beginner
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 32%

---


# Sobre mensagens SMS{#about-sms-messages}

O Adobe Campaign permite enviar mensagens SMS (Serviço de mensagens curtas).

>[!NOTE]
>
>O canal SMS é um complemento. Verifique o contrato de licença.

Para mensagens SMS, você poderá criar, modificar e personalizar mensagens somente no formato de texto. Você também poderá visualizar suas mensagens SMS antes de enviá-las.

O comprimento de uma mensagem SMS é restrito a 160 caracteres se estiver na codificação GSM e somente a 70 caracteres se estiver em Unicode. No entanto, determinados caracteres especiais podem influenciar o comprimento da mensagem. Para obter mais informações, consulte a seção [Codificação de SMS](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) .

As mensagens SMS podem ser criadas no menu **[!UICONTROL Marketing activities]**, em uma campanha ou em um workflow, consulte [Criação de uma mensagem SMS](../../channels/using/creating-an-sms-message.md).

Para enviar mensagens SMS para um celular, você precisa:

* Uma conta externa de **[!UICONTROL Routing]** configurada no canal **[!UICONTROL Mobile (SMS)]** com o modo **[!UICONTROL Bulk delivery]**. Para mais informações, consulte a seção [Roteamento](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing).
* Um template do delivery vinculado corretamente a essa conta externa.

**Tópicos relacionados:**

* [Gerenciamento de modelos](../../start/using/marketing-activity-templates.md)
* [Configuração de SMS](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)
* [Relatório SMS](../../reporting/using/sms-report.md)
* [Guia para Aplicativos de dispositivos móveis no Campaign Standard](https://helpx.adobe.com/campaign/kb/acs-mobile.html)

## Modelo de delivery de SMS {#sms-delivery-template}

A Adobe Campaign oferece um template do delivery para dispositivos móveis. Esse template deve estar vinculado corretamente à conta externa usada para o canal **[!UICONTROL Mobile (SMS)]**. Para acessá-lo e modificá-lo:

1. Selecione **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** no menu avançado.
1. Passe o mouse sobre o modelo **[!UICONTROL Send via SMS]** com o mouse e selecione a opção **Duplicate element**.
1. Selecione o novo modelo.
1. Clique no botão **[!UICONTROL Edit properties]**.
1. Na seção **[!UICONTROL Advanced parameters]** das propriedades do template, verifique se o template está vinculado à conta externa a ser usada para delivery de SMS.

   ![](assets/sms_template.png)

**Tópicos relacionados:**

* [Gerenciamento de modelos](../../start/using/marketing-activity-templates.md)
