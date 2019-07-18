---
title: Edição de perfis
seo-title: Edição de perfis
description: Edição de perfis
seo-description: Saiba como editar perfis existentes e acessar informações de contato, preferir canais, logs, assinaturas etc.
page-status-flag: nunca ativado
uuid: 6 fcdb 719-6149-48 fc-b 400-64 c 24 a 51487 f
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: públicos-alvo
content-type: reference
topic-tags: gerenciamento de perfis
discoiquuid: 8 d 3 ba 7 bf -90 ae -4 c 6 d-aaeb-a 48572 a 69 f 2 f
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6df0e764750a31f29d6fe3ec4d92e19b3f07f728

---


# Editing profiles{#editing-profiles}

## Accessing profile properties {#accessing-profile-properties}

Para editar um perfil existente e consultar os dados associados a ele ou modificá-lo, as etapas são as seguintes:

1. From the Adobe Campaign home page, click the **[!UICONTROL Customer profiles]** card or the **[!UICONTROL Profiles]** tab.
1. Selecione um contato.
1. Click the **[!UICONTROL Edit profile properties]** icon to access the profile's detailed information.

   ![](assets/profile_creation2.png)

   A janela de propriedades do perfil oferece várias guias que fornecem acesso a todas as informações do perfil.

   Outras guias também podem aparecer dependendo dos recursos personalizados que foram criados ou estendidos no Adobe Campaign. For more information about custom resources, see [About custom resources](../../developing/using/data-model-concepts.md).

   >[!NOTE]
   >
   >You can only modify the information in the **[!UICONTROL General]** tab - except for the **[!UICONTROL Traceability]** section.

A edição de perfis também é possível usando a API do Adobe Campaign Standard. For more on this, refer to the [dedicated documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#updating-profiles) .

Tópico relacionado:

* [Perfil do cliente integrado](../../audiences/using/integrated-customer-profile.md)
* [Envio no fuso horário do destinatário](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)

## General profile data {#general-profile-data}

**[!UICONTROL General]** A guia agrupa as seguintes informações sobre o perfil:

* Contact information, which contains the recipient's first name, last name, date of birth, photo, preferred language (for [multilingual emails](../../channels/using/creating-a-multilingual-email.md)), etc.
* Canais nos quais o perfil pode ser contado, que contém o endereço de email do destinatário, o número de telefone celular e as informações de não participação.
* Postal address (for [direct mail](../../channels/using/about-direct-mail.md)), and the contact's time zone (to [schedule messages in its time zone](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)).
* Access authorization, which indicates the recipient's organisational unit (to [manage permissions](../../administration/using/about-access-management.md)). See also [Partitioning profiles](../../administration/using/organizational-units.md#partitioning-profiles).

![](assets/profile_creation4.png)

## Sending and tracking logs {#sending-and-tracking-logs}

The **[!UICONTROL Sending logs]** and **[!UICONTROL Tracking logs]** tabs group the list of deliveries that were sent to the profile, and all related tracking data.

For more on sending and tracking logs, refer to the [delivery logs](../../sending/using/monitoring-a-delivery.md#delivery-logs) and the [tracking messages](../../sending/using/tracking-messages.md) sections.

## Subscriptions {#subscriptions}

As assinaturas do contato são listadas na guia correspondente. For more on subscribing to a service, refer to [this section](../../audiences/using/about-subscriptions.md).

**[!UICONTROL Mobile App Subscriptions]** A guia se refere às notificações por push. For more information, refer to the [Push notification](../../channels/using/about-push-notifications.md) channel.
