---
title: Sobre a integração do Campaign com o Analytics
description: Coletando os dados de KPI do Adobe Campaign Standard, agora é possível compartilhar dados de campanha com o Adobe Analytics para medir as métricas de marketing por email do Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: ada1a5d1-879b-49cd-b4ef-43d7a40bafdb
TQID: 'https://experienceleague.adobe.com/xTX1m0UTCuDt2YMByv8L6vyJG1W0dRme5ETBJuFG-J4'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
    internal-label: Integrations
subfeature_v2:
  - id: c3bf7e1e-1db5-4c72-9293-e2f0b1ab73d0
    internal-label: Triggers
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: beb7a3c1-66ab-4786-b879-7621375b3c40
    internal-label: Email marketing
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 7%
---
# Sobre a integração do Campaign com o Analytics{#about-campaign-analytics-integration}

Graças à integração do Adobe Analytics no Adobe Campaign, agora é possível rastrear o sucesso de suas entregas de email diretamente no Adobe Analytics.

Essa integração entre o Adobe Campaign Standard e o Adobe Analytics permitirá:

* Compartilhe seus dados de KPI (Key Performance Indicator, principal indicador de desempenho) do Adobe Campaign Standard com a Adobe Analytics.
* Enriqueça as fórmulas de rastreamento com parâmetros do Adobe Analytics.

Isso funcionará primeiro criando uma conta externa vinculada ao Adobe Analytics. Um workflow técnico será iniciado automaticamente e, por padrão, será executado automaticamente a cada 15 minutos. Seus dados de KPI são então enviados para o Analytics.

Essa integração está disponível somente para deliveries por email.

Uma integração entre os **Triggers** do serviço principal da Adobe Analytics e o Adobe Campaign também está disponível. Ele permite enviar emails personalizados para seus clientes como uma reação a comportamentos específicos que são rastreados em seu site pelo Adobe Analytics (em 15 minutos).

**Tópicos relacionados:**

* [Visão geral da integração do Campaign Standard com o Analytics](https://experienceleague.adobe.com/docs/analytics/integration/adobe-campaign.html?lang=pt-BR)
* [Configurar a integração do Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/working-with-campaign-and-analytics/configure-campaign-analytics-integration.html?lang=pt-BR)
* [Dimensões e métricas do Campaign no Analytics](../../integrating/using/campaign-dimensions-and-metrics-in-analytics.md)
