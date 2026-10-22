---
title: Sobre a integração de dados do Campaign com os Pontos de interesse
description: Coletando os dados de pontos de interesse dos assinantes do aplicativo móvel, envie mensagens de marketing baseadas em localização para os assinantes por meio da integração no Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
feature: Audiences
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 358194f9-34ce-4dd5-b9b2-1a7d541879ab
TQID: 'https://experienceleague.adobe.com/NMHm-sHLhsjMqprniSnxca27zpoxGEhRGKlt1IJXfVg'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: afa4204e-6d08-4e29-bc35-26aafb656d48
    internal-label: Profiles and audiences
subfeature_v2:
  - id: d6330382-c886-4f7a-a4f7-74e3f36c0d9c
    internal-label: Audiences
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
    internal-label: Data integration
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 6%
---
# Sobre a integração de dados do Campaign com os Pontos de interesse{#about-campaign-points-of-interest-data-integration}

Além de rastrear a presença online dos clientes, você também pode aproveitar seus locais físicos. Por meio da integração com o Adobe Analytics for Mobile, você pode usar o Adobe Campaign para enviar mensagens de marketing baseadas em localização aos assinantes do aplicativo móvel.

Os pontos de interesse consistem em uma latitude, uma longitude e um raio associados a um rótulo. Eles são definidos na interface do [Adobe Mobile Services](https://experienceleague.adobe.com/docs/mobile-services/using/home.html).

Quando um assinante abre seu aplicativo móvel, se o local corresponder a um Ponto de interesse, o Adobe Campaign captura os dados por meio da Experience Cloud Mobile SDK. Você pode usar essas informações para enviar mensagens personalizadas com base na localização do usuário (como emails, notificações por push e mensagens SMS).

Por exemplo, você pode enviar uma oferta de desconto de 10% para clientes que usam seu aplicativo e visitaram uma de suas lojas em Boston nas últimas duas semanas.

Um caso de uso é apresentado na seção [Personalização de mensagens do Campaign com dados de Ponto de interesse](../../integrating/using/personalizing-campaign-messages-with-point-of-interest-data.md).
