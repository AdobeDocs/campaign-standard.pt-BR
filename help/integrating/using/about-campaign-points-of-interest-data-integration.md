---
title: Sobre a integração de dados do Campaign com os Pontos de interesse
description: Ao coletar os dados de Pontos de interesse dos assinantes de seu aplicativo móvel, envie mensagens de marketing baseadas em localização para seus assinantes por meio da integração no Adobe Campaign.
page-status-flag: never-activated
uuid: 1e6840c8-0472-4da2-85ed-f9a65147555a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
discoiquuid: bc10c650-80cd-4146-ae82-c5981fc62bec
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 6%

---


# Sobre a integração de dados do Campaign com os Pontos de interesse{#about-campaign-points-of-interest-data-integration}

Além de rastrear a presença on-line dos clientes, você também pode aproveitar suas localizações físicas. Por meio da integração com o Adobe Analytics for Mobile, você pode usar o Adobe Campaign para enviar mensagens de marketing baseadas em localização aos assinantes do aplicativo móvel.

Os Pontos de interesse consistem em uma latitude, uma longitude e um raio associados a um rótulo. Eles são definidos na interface do [Adobe Mobile Services](https://docs.adobe.com/content/help/en/mobile-services/using/home.html) .

Quando um assinante abre seu aplicativo móvel, se o local corresponder a um Ponto de interesse, a Adobe Campaign captura os dados por meio do SDK do Experience Cloud Mobile. Você pode usar essas informações para enviar mensagens personalizadas com base no local do usuário (como emails, notificações por push, mensagens SMS).

Por exemplo, você pode enviar uma oferta de desconto de 10% para os clientes que usam seu aplicativo e visitaram uma de suas lojas em Boston nas últimas duas semanas.

Um caso de uso é apresentado na seção [Personalizando mensagens de Campanha com dados](../../integrating/using/personalizing-campaign-messages-with-point-of-interest-data.md) de Ponto de interesse.
