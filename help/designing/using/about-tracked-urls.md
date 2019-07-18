---
title: Sobre urls rastreados
seo-title: Sobre urls rastreados
description: Sobre urls rastreados
seo-description: Saiba como gerenciar todos os urls do conteúdo que serão rastreados.
page-status-flag: nunca ativado
uuid: dfe 5146 b -5256-431 c -87 b 3-3 c 54817 eba 36
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: gerenciamento de links
discoiquuid: d 9 b 0 b 3 c 2-874 b -4 cb 4-bce 9-c 0194 a 19 f 25 f
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# About tracked URLs{#about-tracked-urls}

O Adobe Campaign permite que você rastreie o comportamento dos destinatários quando eles clicam em um URL incluído em um e-mail. For more on tracking, see [this section](../../sending/using/tracking-messages.md#about-tracking).

The **[!UICONTROL Links]** icon in the action bar automatically displays the list of all the URLs of your content that will be tracked.

![](assets/des_links.png)

>[!NOTE]
>
>O rastreamento é ativado por padrão. Essa funcionalidade só está disponível para emails, se o rastreamento tiver sido ativado no Adobe Campaign. For more on the tracking parameters, refer to [this section](../../administration/using/configuring-email-channel.md#tracking-parameters).

A URL, a categoria, o rótulo e o tipo de rastreamento de cada link podem ser modificados nessa lista. Para editar um link, clique no ícone correspondente de lápis.

![](assets/des_links_tracking.png)

Para cada URL rastreado, você pode definir o modo de rastreamento para um destes valores:

* **Rastreado**: ativa o rastreamento neste URL.
* **Página espelhada**: considera este URL como um URL de página espelhada.
* **Nunca**: nunca ativa o rastreamento desse URL. Essas informações são salvas: se o URL aparecer novamente em uma mensagem futura, seu rastreamento será desativado automaticamente.
* **Recusar**: considera este URL como um URL de cancelamento ou cancelamento de assinatura.

![](assets/des_link_tracking_type.png)

Você também pode desativar ou ativar o rastreamento de cada URL.

>[!NOTE]
>
>By default in Adobe Campaign, all content URLs are tracked except **Mirror page URL** and **Unsubscription** link.

You can regroup your URLs by editing the **[!UICONTROL Category]** field, depending on the URLs used in the message. These categories can be displayed reports, as for example in [URLs and click streams](../../reporting/using/urls-and-click-streams.md).

![](assets/des_link_tracking_category.png)

When building a report, from the **[!UICONTROL Components]** tab, select **[!UICONTROL Dimension]** and scroll down the list to access the tracking components. For example, drag and drop **[!UICONTROL Tracking URL Category]** into the workspace to display results according to the tracking category of each clicked URL.

![](assets/des_link_tracking_report.png)

For more on building customized reports, see [this section](../../reporting/using/about-dynamic-reports.md).
