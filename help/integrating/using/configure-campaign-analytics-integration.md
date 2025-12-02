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
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 9%

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
