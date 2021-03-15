---
solution: Campaign Standard
product: campaign
title: Sobre a integração de dados do Campaign com os Pontos de interesse
description: Ao coletar os dados de Pontos de interesse dos assinantes do aplicativo móvel, envie mensagens de marketing de acordo com a localização para seus assinantes por meio da integração no Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
feature: Públicos
role: Arquiteto de dados
level: Intermediário
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 6%

---


# Sobre a integração de dados do Campaign com os Pontos de interesse{#about-campaign-points-of-interest-data-integration}

Além de rastrear a presença online dos clientes, você também pode aproveitar seus locais físicos. Por meio da integração com o Adobe Analytics for Mobile, você pode usar o Adobe Campaign para enviar mensagens de marketing de acordo com a localização para os assinantes do aplicativo móvel.

Os Pontos de interesse consistem em latitude, longitude e um raio associado a um rótulo. Eles são definidos na interface [Adobe Mobile Services](https://docs.adobe.com/content/help/en/mobile-services/using/home.html).

Quando um assinante abre seu aplicativo móvel, se o local corresponder a um Ponto de interesse, o Adobe Campaign captura os dados por meio do SDK do Experience Cloud Mobile. Você pode usar essas informações para enviar mensagens personalizadas com base na localização do usuário (como emails, notificações por push, mensagens SMS).

Por exemplo, você pode enviar uma oferta de desconto de 10% para clientes que usam seu aplicativo e visitaram uma de suas lojas em Boston nas últimas duas semanas.

Um caso de uso é apresentado na seção [Personalização de mensagens do Campaign com dados de Ponto de interesse](../../integrating/using/personalizing-campaign-messages-with-point-of-interest-data.md) .
