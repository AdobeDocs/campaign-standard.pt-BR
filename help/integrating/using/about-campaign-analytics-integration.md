---
title: Sobre a integração do Campaign com o Analytics
description: Coletando os dados de KPI do Adobe Campaign Standard, agora é possível compartilhar dados de campanha com o Adobe Analytics para medir as métricas de marketing por email do Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: ada1a5d1-879b-49cd-b4ef-43d7a40bafdb
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 6%

---

# Sobre a integração do Campaign com o Analytics{#about-campaign-analytics-integration}

Graças à integração do Adobe Analytics no Adobe Campaign, agora é possível rastrear o sucesso de suas entregas de email diretamente no Adobe Analytics.

Essa integração entre o Adobe Campaign Standard e o Adobe Analytics permitirá:

* Compartilhe seus dados de KPI (Key Performance Indicator, principal indicador de desempenho) do Adobe Campaign Standard com a Adobe Analytics.
* Enriqueça as fórmulas de rastreamento com parâmetros do Adobe Analytics.

Isso funcionará primeiro criando uma conta externa vinculada ao Adobe Analytics. Um workflow técnico será iniciado automaticamente e, por padrão, será executado automaticamente a cada 15 minutos. Seus dados de KPI são então enviados para o Analytics.

Essa integração está disponível somente para deliveries por email.

Uma integração entre o serviço principal da Adobe Analytics **Triggers** O e o Adobe Campaign também estão disponíveis. Ele permite enviar emails personalizados para seus clientes como uma reação a comportamentos específicos que são rastreados em seu site pelo Adobe Analytics (em 15 minutos).

**Tópicos relacionados:**

* [Visão geral da integração do Campaign Standard com o Analytics](https://experienceleague.adobe.com/docs/analytics/integration/adobe-campaign.html)
* [Configurar a integração de Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/working-with-campaign-and-analytics/configure-campaign-analytics-integration.html)
* [Dimensões e métricas do Campaign no Analytics](../../integrating/using/campaign-dimensions-and-metrics-in-analytics.md)
