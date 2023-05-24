---
title: Edição de perfis
description: Saiba como editar perfis existentes e acessar informações de contato, canais preferenciais, logs de rastreamento, assinaturas, etc.
audience: audiences
content-type: reference
topic-tags: managing-profiles
feature: Profiles
role: User
level: Intermediate
exl-id: d0c7dc09-6f2b-4336-b545-7afe3a704164
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 8%

---

# Edição de perfis{#editing-profiles}

## Acesso às propriedades do perfil {#accessing-profile-properties}

Para editar um perfil existente e consultar os dados associados a ele ou modificá-lo, siga estas etapas:

1. Na página inicial do Adobe Campaign, clique no link **[!UICONTROL Customer profiles]** ou o **[!UICONTROL Profiles]** guia.
1. Selecione um contato.
1. Clique em **[!UICONTROL Edit profile properties]** para acessar as informações detalhadas do perfil.

   ![](assets/profile_creation2.png)

   A janela de propriedades do perfil oferece várias guias que dão acesso a todas as informações do perfil.

   Outras guias também podem aparecer, dependendo dos recursos personalizados que foram criados ou estendidos no Adobe Campaign. Para obter mais informações sobre recursos personalizados, consulte [Sobre recursos personalizados](../../developing/using/data-model-concepts.md).

   >[!NOTE]
   >
   >Você só pode modificar as informações na variável **[!UICONTROL General]** guia - exceto para **[!UICONTROL Traceability]** seção.

A edição de perfis também é possível usando a API do Adobe Campaign Standard. Para obter mais informações, consulte a [documentação dedicada](../../api/using/updating-profiles.md).

Tópicos relacionados:

* [Perfil de cliente integrado](../../audiences/using/integrated-customer-profile.md)
* [Envio no fuso horário do recipient](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)

## Dados gerais do perfil {#general-profile-data}

A variável **[!UICONTROL General]** A guia agrupa as seguintes informações sobre o perfil:

* Informações de contato, que contêm o nome, sobrenome, data de nascimento, foto, idioma preferencial do recipient (para [emails multilíngues](../../channels/using/creating-a-multilingual-email.md)), etc.
* Canais nos quais o perfil pode ser contatado, que contêm o endereço de email do recipient, o número do telefone celular e as informações de recusa.
* Endereço postal (para [correspondência direta](../../channels/using/about-direct-mail.md)) e o fuso horário do contato (para [agendar mensagens em seu fuso horário](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)).
* autorização de acesso, que indica a unidade organizacional do destinatário (para [gerenciar permissões](../../administration/using/about-access-management.md)). Consulte também [Particionamento de perfis](../../administration/using/organizational-units.md#partitioning-profiles).

![](assets/profile_creation4.png)

## Envio e rastreamento de logs {#sending-and-tracking-logs}

A variável **[!UICONTROL Sending logs]** e **[!UICONTROL Tracking logs]** As guias agrupam a lista de deliveries que foram enviados ao perfil e todos os dados de rastreamento relacionados.

Para obter mais informações sobre envio e logs de rastreamento, consulte [logs do delivery](../../sending/using/monitoring-a-delivery.md#delivery-logs) e a variável [rastreamento de mensagens](../../sending/using/tracking-messages.md) seções.

## Assinaturas {#subscriptions}

As subscrições do contato são listadas na guia correspondente. Para obter mais informações sobre assinatura de serviço, consulte [nesta seção](../../audiences/using/about-subscriptions.md).

A variável **[!UICONTROL Mobile App Subscriptions]** consulte as notificações por push. Para obter mais informações, consulte [Notificação por push](../../channels/using/about-push-notifications.md) canal.
