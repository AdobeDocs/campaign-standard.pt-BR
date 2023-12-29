---
title: Sobre mensagens SMS
description: Descubra as principais especificidades do canal de SMS no Adobe Campaign.
audience: channels
content-type: reference
topic-tags: sms-messages
delivercontext-tags: deliveryCreation,wizard;delivery,smsContent,back
feature: SMS
role: User
level: Beginner
exl-id: a7f22d92-dbf9-4c2b-8fc1-1e31d1e5e79c
source-git-commit: b5e98c07ee55cab0b6a628a97162ccd64711501a
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 29%

---

# Sobre mensagens SMS{#about-sms-messages}

O Adobe Campaign permite que você entregue mensagens SMS (Short Message Service).

>[!NOTE]
>
>O canal SMS é um complemento. Verifique o contrato de licença.

Para mensagens SMS, você poderá criar, modificar e personalizar mensagens somente no formato de texto. Você também poderá visualizar suas mensagens SMS antes de enviá-las.

O comprimento de uma mensagem SMS é restrito a 160 caracteres se estiver na codificação GSM e somente 70 caracteres se estiver em Unicode. No entanto, alguns caracteres especiais podem influenciar o comprimento da mensagem. Para obter mais informações, consulte [Codificação de SMS](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) seção.

As mensagens SMS podem ser criadas no **[!UICONTROL Marketing activities]** , de uma campanha ou de um fluxo de trabalho, consulte [Criação de uma mensagem SMS](../../channels/using/creating-an-sms-message.md).

Para enviar mensagens SMS para um telefone celular, você precisa:

* Uma conta externa de **[!UICONTROL Routing]** configurada no canal **[!UICONTROL Mobile (SMS)]** com o modo **[!UICONTROL Bulk delivery]**. Para mais informações, consulte a seção [Roteamento](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing).
* Um template da entrega vinculado corretamente a essa conta externa.

**Tópicos relacionados:**

* [Gerenciamento de modelos](../../start/using/marketing-activity-templates.md)
* [Configuração de SMS](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)
* [Relatório de SMS](../../reporting/using/sms-report.md)
* [Guia do Campaign Standard Mobile](../../channels/using/get-started-communication-channels.md)

## Template de entrega de SMS {#sms-delivery-template}

O Adobe Campaign oferece um template de delivery para dispositivos móveis. Esse template deve estar vinculado corretamente à conta externa usada para o **[!UICONTROL Mobile (SMS)]** canal. Para acessá-lo e modificá-lo:

1. Selecionar **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** no menu avançado.
1. Passe o mouse sobre **[!UICONTROL Send via SMS]** modelo com o mouse e selecione o **Duplicar elemento** opção.
1. Selecione o novo modelo.
1. Clique no botão **[!UICONTROL Edit properties]**.
1. No **[!UICONTROL Advanced parameters]** das propriedades do template, verifique se o template está vinculado à conta externa que será usada para delivery do SMS.

   ![](assets/sms_template.png)

**Tópicos relacionados:**

* [Gerenciamento de modelos](../../start/using/marketing-activity-templates.md)
