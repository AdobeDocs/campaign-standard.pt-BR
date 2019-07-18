---
title: Configuração da integração do Campaign-Analytics
seo-title: Configuração da integração do Campaign-Analytics
description: Configuração da integração do Campaign-Analytics
seo-description: Saiba como configurar a integração do Adobe Analytics para começar a medir o sucesso das entregas de email.
page-status-flag: nunca ativado
uuid: bdaa 00 b 0-7445-469 c -8268-9 d 06 c 53 ce 2 b 0
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
discoiquuid: 92 b 9004 c-cba 0-41 fd-a 035-32 bee 1 d 6 a 42 c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Configure Campaign-Analytics integration{#configure-campaign-analytics-integration}

Essa integração permite que você compartilhe os dados principais do Indicador de desempenho diretamente do Adobe Campaign para o Adobe Analytics Standard ou Premium.

Para iniciar a integração entre o Adobe Campaign Standard e o Adobe Analytics, primeiro você deve configurar a conta externa vinculada ao Adobe Analytics.

Contas externas e fluxos de trabalho técnicos podem ser gerenciados somente pelo administrador funcional da plataforma.

1. From the advanced menu, via the Adobe Campaign logo, select **[!UICONTROL Administration > Application settings > External accounts]**.
1. Select the **[!UICONTROL Share KPIs with Adobe Analytics]** external account.

   ![](assets/analytics_2.png)

1. Specify your **[!UICONTROL Web services user name]** and **[!UICONTROL Web services share secret]** in the **[!UICONTROL Connection]** field.

   These parameters can be found in Analytics by selecting **[!UICONTROL Admin > Company settings > Web services]**.

   ![](assets/analytics_1.png)

1. Click the **[!UICONTROL Refresh report suites]** button.
1. Select in the **[!UICONTROL Analytics default report suite]** drop-down the Adobe Analytics report suite you want to enrich with Adobe Campaign data.

   Sua conta externa agora está pronta e vinculada ao Adobe Analytics. You can disable it at any time by checking the **[!UICONTROL Enabled]** box.

   ![](assets/analytics.png)

The **[!UICONTROL Share KPIs with Adobe Analytics]** technical workflow will now automatically launch and can be viewed from the advanced menu by selecting **[!UICONTROL Administration > Application settings > Workflow]**. Esse fluxo de trabalho técnico será executado automaticamente a cada 15 minutos e enviará até 6 meses dados antigos no Adobe Analytics.

![](assets/analytics_3.png)

Seus dados agora estão disponíveis no Adobe Analytics.

**Tópicos relacionados:**

* [Contas externas](../../administration/using/external-accounts.md)
* [Fluxos de trabalho técnicos](../../administration/using/technical-workflows.md)
* [Compartilhar kpis para vídeo de relatório](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html) integrado da campanha

