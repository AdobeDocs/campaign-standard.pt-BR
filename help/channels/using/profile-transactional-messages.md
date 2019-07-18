---
title: Mensagens transacionais de perfil
seo-title: Mensagens transacionais de perfil
description: Mensagens transacionais de perfil
seo-description: Saiba como criar e publicar uma mensagem transacional de perfil.
page-status-flag: nunca ativado
uuid: a 8 efe 979-74 ae -46 ff-a 305-b 86 a 90679581
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canais
content-type: reference
topic-tags: transacionais-messaging
discoiquuid: dcb 90 afc -42 c 3-419 e -8345-79 cddf 969 e 41
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 855db33971afdf9f02bf1b00be67c9e3f50bee06

---


# Profile transactional messages{#profile-transactional-messages}

É possível enviar mensagens transacionais com base em perfis de marketing do cliente, que permitem:

* Apply marketing typology rules such as **[!UICONTROL Blacklisted address]** or [fatigue rules](../../administration/using/fatigue-rules.md).
* Inclua o link de cancelamento de assinatura nas mensagens.
* Adicione as mensagens transacionais ao relatório de entrega global.
* Aproveite as mensagens transacionais na jornada do cliente.

Once you have created and published an event (the cart abandonment as per the [example](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle) above), the corresponding transactional message is created automatically.

The configuration steps are presented in the [Configuring an event to send a profile transactional message](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) section.

Para que o evento dispare uma mensagem transacional, é necessário personalizar a mensagem e, em seguida, testar e publicá-la.

>[!NOTE]
>
>To access the transactional messages, you must have administration rights or appear in the **[!UICONTROL Message Center agents]** (mcExec) security group. As regras de esgotamento são compatíveis com as mensagens transacionais do perfil. See [Fatigue rules](../../administration/using/fatigue-rules.md).

## Sending a profile transactional message {#sending-a-profile-transactional-message}

As etapas para criar, personalizar e publicar uma mensagem transacional de perfil são as mesmas de uma mensagem transacional de evento. See [Event transactional messages](../../channels/using/event-transactional-messages.md).

As diferenças estão listadas abaixo.

1. Vá para a mensagem transacional que foi criada para editá-la.
1. In the transactional message, click the **[!UICONTROL Content]** section. In addition to the transactional template, you can also choose the default email template, which targets **[!UICONTROL Profile]**.

   ![](assets/message-center_marketing_templates.png)

1. Selecione o modelo de e-mail padrão.

   Semelhante a todos os e-mails de marketing, ele inclui um link para cancelamento de assinatura.

   ![](assets/message-center_marketing_perso_unsubscription.png)

   Além disso, ao contrário de configurações baseadas em eventos em tempo real, você tem acesso direto a todas as informações de perfil para personalizar a mensagem. See [Inserting a personalization field](../../designing/using/inserting-a-personalization-field.md).

1. Salve as alterações e publique a mensagem. See [Publishing a transactional message](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message).

## Monitoring a profile transactional message delivery {#monitoring-a-profile-transactional-message-delivery}

Quando a mensagem for publicada e a integração do site for feita, você poderá monitorar a entrega.

1. To view the message delivery log, click the icon at the bottom right of the **[!UICONTROL Deployment]** block.

   For more information on accessing the logs, see [Monitoring the delivery](../../sending/using/monitoring-a-delivery.md).

1. Select the **[!UICONTROL Sending logs]** tab. In the **[!UICONTROL Status]** column, **[!UICONTROL Sent]** indicates that a profile has opted in.

   ![](assets/message-center_marketing_sending_logs.png)

1. Select the **[!UICONTROL Exclusions logs]** tab to view recipients who have been excluded from the message target, such as blacklisted addresses.

   ![](assets/message-center_marketing_exclusion_logs.png)

For any profile that has opted out, the **[!UICONTROL Blacklisted address]** typology rule excluded the corresponding recipient.

This rule is part of a specific typology that applies to all transactional messages based on the **[!UICONTROL Profile]** table.

![](assets/message-center_marketing_typology.png)

**Tópicos relacionados**:

* [Integração do site](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)
* [Tipologias](../../administration/using/about-typology-rules.md)

