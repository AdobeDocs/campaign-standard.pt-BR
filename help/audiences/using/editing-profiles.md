---
title: Editar perfis
description: Saiba como editar perfis existentes e acessar informações de contato, canais preferidos, logs de rastreamento, subscrições etc.
page-status-flag: never-activated
uuid: 6fcdb719-6149-48fc-b400-64c24a51487f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-profiles
discoiquuid: 8d3ba7bf-90ae-4c6d-aaeb-a48572a69f2f
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 8%

---


# Editar perfis{#editing-profiles}

## Acessar propriedades do perfil {#accessing-profile-properties}

Para editar um perfil existente e consultar os dados associados a ele, ou modificá-lo, as etapas são as seguintes:

1. From the Adobe Campaign home page, click the **[!UICONTROL Customer profiles]** card or the **[!UICONTROL Profiles]** tab.
1. Selecione um contato.
1. Clique no **[!UICONTROL Edit profile properties]** ícone para acessar as informações detalhadas do perfil.

   ![](assets/profile_creation2.png)

   A janela de propriedades do perfil oferta várias guias que concedem acesso a todas as informações do perfil.

   Outras guias também podem ser exibidas dependendo dos recursos personalizados que foram criados ou estendidos no Adobe Campaign. Para obter mais informações sobre recursos personalizados, consulte [Sobre recursos](../../developing/using/data-model-concepts.md)personalizados.

   >[!NOTE]
   >
   >Você só pode modificar as informações na **[!UICONTROL General]** guia - exceto para a **[!UICONTROL Traceability]** seção.

A edição de perfis também é possível usando a API do Adobe Campaign Standard. Para obter mais informações, consulte a [documentação dedicada](../../api/using/updating-profiles.md).

Tópicos relacionados:

* [Perfil de cliente integrado](../../audiences/using/integrated-customer-profile.md)
* [Envio no fuso horário do recipient](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)

## Dados gerais do perfil {#general-profile-data}

A **[!UICONTROL General]** guia agrupa as seguintes informações sobre o perfil:

* Informações de contato, que contêm o nome do recipient, o sobrenome, a data de nascimento, a fotografia, a língua preferencial (para e-mails [](../../channels/using/creating-a-multilingual-email.md)multilíngues), etc.
* Canais nos quais o perfil pode ser contatado, que contêm o endereço de email do recipient, o número do telefone celular, as informações de não participação.
* Endereço postal (para correio [](../../channels/using/about-direct-mail.md)direto) e o fuso horário do contato (para [agendar mensagens em seu fuso](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)horário).
* Autorização de acesso, que indica a unidade organizacional do recipient (para [gerenciar permissões](../../administration/using/about-access-management.md)). Consulte também [Particionamento de perfis](../../administration/using/organizational-units.md#partitioning-profiles).

![](assets/profile_creation4.png)

## Sending and tracking logs {#sending-and-tracking-logs}

As guias **[!UICONTROL Sending logs]** e **[!UICONTROL Tracking logs]** agrupam a lista de delivery que foram enviados para o perfil e todos os dados de rastreamento relacionados.

Para obter mais informações sobre como enviar e logs de rastreamento, consulte as seções [logs do delivery](../../sending/using/monitoring-a-delivery.md#delivery-logs) e mensagens [de](../../sending/using/tracking-messages.md) rastreamento.

## Subscrições {#subscriptions}

As subscrições do contato são listadas na guia correspondente. Para obter mais informações sobre como assinar um serviço, consulte [esta seção](../../audiences/using/about-subscriptions.md).

A **[!UICONTROL Mobile App Subscriptions]** guia se refere às notificações por push. Para obter mais informações, consulte o canal de notificação por [push](../../channels/using/about-push-notifications.md) .
