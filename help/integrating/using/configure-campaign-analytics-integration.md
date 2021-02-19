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

1. No menu avançado, por meio do logotipo Adobe Campaign, selecione **[!UICONTROL Administration > Application settings > External accounts]**.
1. Selecione a conta externa **[!UICONTROL Share KPIs with Adobe Analytics]**.

   ![](assets/analytics_2.png)

1. Especifique **[!UICONTROL Web services user name]** e **[!UICONTROL Web services share secret]** no campo **[!UICONTROL Connection]**.

   Esses parâmetros podem ser encontrados no Analytics selecionando **[!UICONTROL Admin > Company settings > Web services]**.

   ![](assets/analytics_1.png)

1. Clique no botão **[!UICONTROL Refresh report suites]**.
1. Selecione na lista suspensa **[!UICONTROL Analytics default report suite]** o conjunto de relatórios da Adobe Analytics que você deseja enriquecer com dados da Adobe Campaign.

   Sua conta externa agora está pronta e vinculada ao Adobe Analytics. Você pode desativá-la a qualquer momento marcando a caixa **[!UICONTROL Enabled]**.

   ![](assets/analytics.png)

O fluxo de trabalho técnico **[!UICONTROL Share KPIs with Adobe Analytics]** agora será iniciado automaticamente e poderá ser visualizado no menu avançado selecionando **[!UICONTROL Administration > Application settings > Workflow]**. Esse fluxo de trabalho técnico será executado automaticamente a cada 15 minutos e enviará até 6 meses de dados antigos no Adobe Analytics.

![](assets/analytics_3.png)

Seus dados agora estão disponíveis no Adobe Analytics.

**Tópicos relacionados:**

* [Contas externas](../../administration/using/external-accounts.md)
* [Workflows técnicos](../../administration/using/technical-workflows.md)
* [Compartilhar KPIs para vídeo de ](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html) relatório de Campanha integrada

