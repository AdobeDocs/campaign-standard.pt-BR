---
solution: Campaign Standard
product: campaign
title: Configurar a integração do Campaign com o Analytics
description: Saiba como configurar a integração do Adobe Analytics para o start que mede o sucesso de seus delivery de email.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 11%

---


# Configurar a integração do Campaign com o Analytics{#configure-campaign-analytics-integration}

Essa integração permite que você compartilhe seus dados do Indicador-chave de desempenho diretamente da Adobe Campaign para a Adobe Analytics Standard ou Premium.

Para start da integração entre o Adobe Campaign Standard e o Adobe Analytics, primeiro é necessário configurar a conta externa vinculada ao Adobe Analytics.

Contas externas e workflows técnicos só podem ser gerenciados pelo administrador funcional da plataforma.

1. From the advanced menu, via the Adobe Campaign logo, select **[!UICONTROL Administration > Application settings > External accounts]**.
1. Selecione a conta externa **[!UICONTROL Share KPIs with Adobe Analytics]**.

   ![](assets/analytics_2.png)

1. Especifique seu **[!UICONTROL Web services user name]** e **[!UICONTROL Web services share secret]** no **[!UICONTROL Connection]** campo.

   Esses parâmetros podem ser encontrados no Analytics selecionando **[!UICONTROL Admin > Company settings > Web services]**.

   ![](assets/analytics_1.png)

1. Clique no botão **[!UICONTROL Refresh report suites]**.
1. Selecione na **[!UICONTROL Analytics default report suite]** lista suspensa o conjunto de relatórios da Adobe Analytics que deseja enriquecer com os dados da Adobe Campaign.

   Sua conta externa agora está pronta e vinculada ao Adobe Analytics. Você pode desativá-la a qualquer momento marcando a **[!UICONTROL Enabled]** caixa.

   ![](assets/analytics.png)

O fluxo de trabalho **[!UICONTROL Share KPIs with Adobe Analytics]** técnico será iniciado automaticamente e poderá ser visualizado no menu avançado selecionando **[!UICONTROL Administration > Application settings > Workflow]**. Esse fluxo de trabalho técnico será executado automaticamente a cada 15 minutos e enviará até 6 meses de dados antigos no Adobe Analytics.

![](assets/analytics_3.png)

Seus dados agora estão disponíveis no Adobe Analytics.

**Tópicos relacionados:**

* [Contas externas](../../administration/using/external-accounts.md)
* [Fluxos de trabalho técnicos](../../administration/using/technical-workflows.md)
* [Compartilhar KPIs para vídeo integrado de relatórios](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html) de Campanha

