---
title: Sobre a integração de dados do Campaign com os Pontos de interesse
description: Coletando os dados de pontos de interesse dos assinantes do aplicativo móvel, envie mensagens de marketing baseadas em localização para os assinantes por meio da integração no Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
feature: Audiences
role: Data Architect
level: Intermediate
exl-id: 358194f9-34ce-4dd5-b9b2-1a7d541879ab
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 6%

---

# Sobre a integração de dados do Campaign com os Pontos de interesse{#about-campaign-points-of-interest-data-integration}

Além de rastrear a presença online dos clientes, você também pode aproveitar seus locais físicos. Por meio da integração com o Adobe Analytics for Mobile, você pode usar o Adobe Campaign para enviar mensagens de marketing baseadas em localização aos assinantes do aplicativo móvel.

Os pontos de interesse consistem em uma latitude, uma longitude e um raio associados a um rótulo. Eles são definidos na interface do [Adobe Mobile Services](https://experienceleague.adobe.com/docs/mobile-services/using/home.html).

Quando um assinante abre seu aplicativo móvel, se o local corresponder a um Ponto de interesse, o Adobe Campaign captura os dados por meio do SDK móvel do Experience Cloud. Você pode usar essas informações para enviar mensagens personalizadas com base na localização do usuário (como emails, notificações por push e mensagens SMS).

Por exemplo, você pode enviar uma oferta de desconto de 10% para clientes que usam seu aplicativo e visitaram uma de suas lojas em Boston nas últimas duas semanas.

Um caso de uso é apresentado na seção [Personalização de mensagens do Campaign com dados de Ponto de interesse](../../integrating/using/personalizing-campaign-messages-with-point-of-interest-data.md).
