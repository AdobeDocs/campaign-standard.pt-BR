---
title: Promoção de um serviço
description: Use o Adobe Campaign para promover um serviço e envolver seus clientes por meio de páginas de aterrissagem dedicadas, emails ou diretamente no seu site.
audience: audiences
content-type: reference
topic-tags: managing-subscriptions
feature: Audiences
role: User
level: Intermediate
exl-id: c1f8770a-8b25-41db-aa52-828e181a563d
TQID: 'https://experienceleague.adobe.com/7WD3y15WK-NJeWZJFIv-crMu5UZ4m8V3KfYbamSY9WA'
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
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 3%
---
# Promoção de um serviço{#promoting-a-service}

Você pode oferecer assinaturas de um serviço de várias maneiras e dar aos seus visitantes a capacidade de gerenciar suas assinaturas.

Você pode usar o Campaign para promover um serviço ao:

* [Inserindo um link de assinatura ou de cancelamento de assinatura de serviço em um email](../../designing/using/links.md#inserting-a-link).

* [Inserindo um link para uma página de aterrissagem de assinatura ou cancelamento de assinatura em um email](../../designing/using/links.md). Nesse caso, o serviço deve ser referenciado diretamente nas propriedades das páginas de aterrissagem relacionadas (consulte [Vincular uma página de aterrissagem a um serviço](../../channels/using/configuring-landing-page.md#linking-a-landing-page-to-a-service)).

  >[!NOTE]
  >
  >Também é importante dar aos assinantes a possibilidade de cancelar a assinatura. Para fazer isso, insira um serviço <b>Link de unsubscription</b> no email de confirmação (definido nas propriedades do serviço) enviado automaticamente aos novos assinantes, bem como em emails de informativos futuros.

* Disponibilização de uma landing page de subscrição ou unsubscription em um site. Os URLs que dão acesso à landing page devem especificar parâmetros como o serviço associado, bem como a ID do perfil que está acessando-a. Essa ID pode ser definida nos parâmetros da página de aterrissagem (consulte [Configuração de uma página de aterrissagem](../../channels/using/configuring-landing-page.md)).
