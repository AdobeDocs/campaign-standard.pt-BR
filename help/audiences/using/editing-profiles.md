---
solution: Campaign Standard
product: campaign
title: Editar perfis
description: Saiba como editar perfis existentes e acessar informações de contato, canais preferidos, logs de rastreamento, assinaturas etc.
audience: audiences
content-type: reference
topic-tags: managing-profiles
feature: Profiles
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 8%

---


# Editar perfis{#editing-profiles}

## Acesso às propriedades do perfil {#accessing-profile-properties}

Para editar um perfil existente e consultar os dados associados a ele, ou modificá-lo, as etapas são as seguintes:

1. Na página inicial do Adobe Campaign, clique no cartão **[!UICONTROL Customer profiles]** ou na guia **[!UICONTROL Profiles]**.
1. Selecione um contato.
1. Clique no ícone **[!UICONTROL Edit profile properties]** para acessar as informações detalhadas do perfil.

   ![](assets/profile_creation2.png)

   A janela de propriedades do perfil oferece várias guias que dão acesso a todas as informações do perfil.

   Outras guias também podem aparecer, dependendo dos recursos personalizados que foram criados ou estendidos no Adobe Campaign. Para obter mais informações sobre recursos personalizados, consulte [Sobre recursos personalizados](../../developing/using/data-model-concepts.md).

   >[!NOTE]
   >
   >Você só pode modificar as informações na guia **[!UICONTROL General]** - exceto na seção **[!UICONTROL Traceability]**.

A edição de perfis também é possível usando a API do Adobe Campaign Standard. Para obter mais informações, consulte a [documentação dedicada](../../api/using/updating-profiles.md).

Tópicos relacionados:

* [Perfil de cliente integrado](../../audiences/using/integrated-customer-profile.md)
* [Envio no fuso horário do recipient](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)

## Dados gerais do perfil {#general-profile-data}

A guia **[!UICONTROL General]** agrupa as seguintes informações sobre o perfil:

* Informações de contato, que contêm o nome, sobrenome, data de nascimento, foto, idioma preferencial do recipient (para [emails multilíngues](../../channels/using/creating-a-multilingual-email.md)), etc.
* Canais nos quais o perfil pode ser contatado, que contêm o endereço de email do recipient, o número do telefone celular e as informações de recusa.
* Endereço postal (para [mala direta](../../channels/using/about-direct-mail.md)) e o fuso horário do contato (para [programar mensagens em seu fuso horário](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)).
* Autorização de acesso, que indica a unidade organizacional do recipient (para [gerenciar permissões](../../administration/using/about-access-management.md)). Consulte também [Particionamento de perfis](../../administration/using/organizational-units.md#partitioning-profiles).

![](assets/profile_creation4.png)

## Envio e rastreamento de logs {#sending-and-tracking-logs}

As guias **[!UICONTROL Sending logs]** e **[!UICONTROL Tracking logs]** agrupam a lista de deliveries que foram enviados ao perfil e todos os dados de rastreamento relacionados.

Para obter mais informações sobre logs de rastreamento e envio, consulte as seções [logs do delivery](../../sending/using/monitoring-a-delivery.md#delivery-logs) e [mensagens de rastreamento](../../sending/using/tracking-messages.md).

## Subscrições {#subscriptions}

As assinaturas do contato são listadas na guia correspondente. Para obter mais informações sobre assinatura de um serviço, consulte [esta seção](../../audiences/using/about-subscriptions.md).

A guia **[!UICONTROL Mobile App Subscriptions]** se refere às notificações por push. Para obter mais informações, consulte o canal de [Notificação por push](../../channels/using/about-push-notifications.md).
