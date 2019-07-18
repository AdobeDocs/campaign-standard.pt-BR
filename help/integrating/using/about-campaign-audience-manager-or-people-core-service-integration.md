---
title: Sobre a integração de serviço principal do Campaign ou do People Manager
seo-title: Sobre a integração de serviço principal do Campaign ou do People Manager
description: Sobre a integração de serviço principal do Campaign ou do People Manager
seo-description: Com a integração de serviço principal do Audience Manager/Pessoas, você pode compartilhar públicos-alvo ou segmentos dentro das diferentes soluções da Adobe Experience Cloud.
page-status-flag: nunca ativado
uuid: 39 e 3 c 78 e-cccd -4823-afe 9-abc 7 f 8 aef 034
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
discoiquuid: bf 718329-f 181-46 f 7-80 a 2-b 525 a 8 dee 46 d
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# About Campaign-Audience Manager or People core service integration{#about-campaign-audience-manager-or-people-core-service-integration}

O Adobe Campaign permite trocar e compartilhar públicos-alvo/segmentos com os diferentes aplicativos da Adobe Experience Cloud. Integrating **Adobe Campaign** with **People core service** (also known as **Profiles &amp; Audiences core service**) or Adobe Audience Manager allows you to:

* Importe públicos/segmentos de soluções diferentes da Adobe Experience Cloud para o Adobe Campaign. Audiences can be imported from the **[!UICONTROL Audiences]** menu in Adobe Campaign.
* Exportar públicos-alvo como públicos-alvo/segmentos compartilhados. Esses públicos-alvo podem ser usados nas diferentes soluções da Adobe Experience Cloud que você usa. Audiences can be exported after targeting activities in a workflow, using the **[!UICONTROL Save audience]** activity.

A integração suporta dois tipos de Adobe Experience Cloud IDs:

* **ID do visitante**: esse tipo de ID permite que você reconcilie os visitantes da Adobe Experience Cloud com os perfis do Adobe Campaign.
* **ID declarada**: esse tipo de ID permite que você reconcilie qualquer tipo de dados com perfis no banco de dados do Adobe Campaign. Essa integração suporta IDs declaradas regulares, oculta IDs declaradas e IDs declaradas criptografadas.

   A criptografia permite compartilhar dados criptografados em fontes de dados (por exemplo PII) usando a ID declarada especificando o algoritmo de criptografia.

   Por exemplo, com a capacidade de descriptografar endereços de email criptografados ou números de SMS, você também pode enviar mensagens acionadas para os usuários, mesmo se o perfil não existir no banco de dados do Adobe Campaign.

>[!CAUTION]
>
>Dependendo dos dados trocados, a importação de públicos-alvo no Adobe Campaign pode estar sujeita a restrições legais

