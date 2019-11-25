---
title: Editar perfis
description: Saiba como editar perfis existentes e acessar informações de contato, canais preferidos, registros de rastreamento, assinaturas etc.
page-status-flag: never-activated
uuid: 6fcdb719-6149-48fc-b400-64c24a51487f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-profiles
discoiquuid: 8d3ba7bf-90ae-4c6d-aaeb-a48572a69f2f
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b06edadfa963881403328c4ab37d25d701bc8237

---


# Editar perfis{#editing-profiles}

## Acesso às propriedades do perfil {#accessing-profile-properties}

Para editar um perfil existente e consultar os dados associados a ele, ou modificá-lo, as etapas são as seguintes:

1. Na página inicial do Adobe Campaign, clique no **[!UICONTROL Customer profiles]** cartão ou na **[!UICONTROL Profiles]** guia.
1. Selecione um contato.
1. Clique no **[!UICONTROL Edit profile properties]** ícone para acessar as informações detalhadas do perfil.

   ![](assets/profile_creation2.png)

   A janela de propriedades do perfil oferece várias guias que concedem acesso a todas as informações do perfil.

   Outras guias também podem ser exibidas dependendo dos recursos personalizados que foram criados ou estendidos no Adobe Campaign. Para obter mais informações sobre recursos personalizados, consulte [Sobre recursos](../../developing/using/data-model-concepts.md)personalizados.

   >[!NOTE]
   >
   >Você só pode modificar as informações na **[!UICONTROL General]** guia - exceto para a **[!UICONTROL Traceability]** seção.

A edição de perfis também é possível usando a API do Adobe Campaign Standard. For more on this, refer to the [dedicated documentation](../../api/using/managing-profiles.md) .

Tópico relacionado:

* [Perfil de cliente integrado](../../audiences/using/integrated-customer-profile.md)
* [Envio no fuso horário do destinatário](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)

## Dados gerais do perfil {#general-profile-data}

A **[!UICONTROL General]** guia agrupa as seguintes informações sobre o perfil:

* Informações de contato, que contêm o nome do destinatário, o sobrenome, a data de nascimento, a foto, a língua preferencial (para emails [](../../channels/using/creating-a-multilingual-email.md)multilíngues), etc.
* Canais nos quais o perfil pode ser contatado, que contêm o endereço de email do destinatário, o número do telefone celular, as informações de recusa.
* Endereço postal (para correio [](../../channels/using/about-direct-mail.md)direto) e o fuso horário do contato (para [agendar mensagens em seu fuso](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)horário).
* Autorização de acesso, que indica a unidade organizacional do destinatário (para [gerenciar permissões](../../administration/using/about-access-management.md)). Consulte também Perfis [de](../../administration/using/organizational-units.md#partitioning-profiles)particionamento.

![](assets/profile_creation4.png)

## Sending and tracking logs {#sending-and-tracking-logs}

As guias **[!UICONTROL Sending logs]** e **[!UICONTROL Tracking logs]** agrupam a lista de entregas enviadas para o perfil e todos os dados de rastreamento relacionados.

Para obter mais informações sobre como enviar e rastrear registros, consulte os registros [de](../../sending/using/monitoring-a-delivery.md#delivery-logs) entrega e as seções de mensagens [de](../../sending/using/tracking-messages.md) rastreamento.

## Subscrições {#subscriptions}

As assinaturas do contato são listadas na guia correspondente. Para obter mais informações sobre como assinar um serviço, consulte [esta seção](../../audiences/using/about-subscriptions.md).

A **[!UICONTROL Mobile App Subscriptions]** guia se refere às notificações por push. Para obter mais informações, consulte o canal de notificação [por](../../channels/using/about-push-notifications.md) push.
