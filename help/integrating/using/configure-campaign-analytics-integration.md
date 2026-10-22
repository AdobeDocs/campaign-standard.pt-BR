---
title: Configurar a integração do Campaign com o Analytics
description: Saiba como configurar a integração do Adobe Analytics para começar a medir o sucesso de suas entregas de email.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: a6748b4b-36c5-4961-a599-ace73a8504cc
TQID: 'https://experienceleague.adobe.com/bt1FQbafwhEuRao-YFhynO-ecg5EaiUDskSFvxuFv-k'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
    internal-label: Integrations
subfeature_v2:
  - id: ca3c1dd6-bdd2-41a9-bc5a-e35f5cca9e63
    internal-label: Application settings
  - id: c3bf7e1e-1db5-4c72-9293-e2f0b1ab73d0
    internal-label: Triggers
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '228'
ht-degree: 12%
---
# Configurar a integração do Campaign com o Analytics{#configure-campaign-analytics-integration}

Essa integração permite compartilhar seus dados principais de indicadores de desempenho diretamente do Adobe Campaign com a Adobe Analytics Standard ou Premium.

Para iniciar a integração entre o Adobe Campaign Standard e o Adobe Analytics, primeiro é necessário configurar a conta externa vinculada ao Adobe Analytics.

As contas externas e os workflows técnicos só podem ser gerenciados pelo administrador funcional da plataforma.

1. No menu avançado, selecione **[!UICONTROL Administration > Application settings > External accounts]** por meio do logotipo do Adobe Campaign.
1. Selecione a conta externa **[!UICONTROL Share KPIs with Adobe Analytics]**.

   ![](assets/analytics_2.png)

1. Especifique seus **[!UICONTROL Web services user name]** e **[!UICONTROL Web services share secret]** no campo **[!UICONTROL Connection]**.

   Esses parâmetros podem ser encontrados no Analytics selecionando **[!UICONTROL Admin > Company settings > Web services]**.

   ![](assets/analytics_1.png)

1. Clique no botão **[!UICONTROL Refresh report suites]**.
1. Selecione no menu suspenso **[!UICONTROL Analytics default report suite]** o conjunto de relatórios do Adobe Analytics que deseja enriquecer com dados do Adobe Campaign.

   Sua conta externa agora está pronta e vinculada ao Adobe Analytics. Você pode desabilitá-lo a qualquer momento marcando a caixa **[!UICONTROL Enabled]**.

   ![](assets/analytics.png)

O fluxo de trabalho técnico **[!UICONTROL Share KPIs with Adobe Analytics]** agora será iniciado automaticamente e poderá ser visualizado no menu avançado selecionando **[!UICONTROL Administration > Application settings > Workflow]**. Esse fluxo de trabalho técnico pode reter broadlogs de até 6 meses. Observe que esse workflow é incremental e enviará dados do dia anterior.

![](assets/analytics_3.png)

Seus dados agora estão disponíveis no Adobe Analytics.

**Tópicos relacionados:**

* [Contas externas](../../administration/using/external-accounts.md)
* [Fluxos de trabalho técnicos](../../administration/using/technical-workflows.md)
* [Compartilhar KPIs para vídeo integrado de relatórios do Campaign](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html)
