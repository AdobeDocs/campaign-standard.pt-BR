---
title: Configurar a integração do Campaign com o Analytics
description: Saiba como configurar a integração do Adobe Analytics para começar a medir o sucesso de seus deliveries de email.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: a6748b4b-36c5-4961-a599-ace73a8504cc
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 11%

---

# Configurar a integração do Campaign com o Analytics{#configure-campaign-analytics-integration}

Essa integração permite compartilhar seus dados do Indicador-chave de desempenho diretamente do Adobe Campaign para o Adobe Analytics Standard ou Premium.

Para iniciar a integração entre o Adobe Campaign Standard e o Adobe Analytics, primeiro é necessário configurar a conta externa vinculada ao Adobe Analytics.

Contas externas e workflows técnicos só podem ser gerenciados pelo administrador funcional da plataforma.

1. No menu avançado, selecione pelo logotipo do Adobe Campaign **[!UICONTROL Administration > Application settings > External accounts]**.
1. Selecione a conta externa **[!UICONTROL Share KPIs with Adobe Analytics]**.

   ![](assets/analytics_2.png)

1. Especifique seu **[!UICONTROL Web services user name]** e **[!UICONTROL Web services share secret]** no **[!UICONTROL Connection]** campo.

   Esses parâmetros podem ser encontrados no Analytics selecionando **[!UICONTROL Admin > Company settings > Web services]**.

   ![](assets/analytics_1.png)

1. Clique no botão **[!UICONTROL Refresh report suites]**.
1. Selecione no **[!UICONTROL Analytics default report suite]** menu suspenso do conjunto de relatórios do Adobe Analytics que você deseja enriquecer com dados do Adobe Campaign.

   Sua conta externa agora está pronta e vinculada ao Adobe Analytics. Você pode desativá-lo a qualquer momento marcando a **[!UICONTROL Enabled]** caixa.

   ![](assets/analytics.png)

O **[!UICONTROL Share KPIs with Adobe Analytics]** o workflow técnico agora será iniciado automaticamente e poderá ser visualizado no menu avançado selecionando **[!UICONTROL Administration > Application settings > Workflow]**. Esse workflow técnico será executado automaticamente a cada 15 minutos e enviará dados de até 6 meses no Adobe Analytics.

![](assets/analytics_3.png)

Seus dados agora estão disponíveis no Adobe Analytics.

**Tópicos relacionados:**

* [Contas externas](../../administration/using/external-accounts.md)
* [Workflows técnicos](../../administration/using/technical-workflows.md)
* [Compartilhar KPIs para relatórios integrados do Campaign](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html) vídeo
