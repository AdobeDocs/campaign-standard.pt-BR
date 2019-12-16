---
title: Sobre a integração Campaign-Audience Manager ou a dos principais serviços do People
description: Com a integração do serviço principal Audience Manager/Pessoas, você pode compartilhar públicos-alvo ou segmentos em diferentes soluções da Adobe Experience Cloud.
page-status-flag: never-activated
uuid: 39e3c78e-cccd-4823-afe9-abc7f8aef034
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
discoiquuid: bf718329-f181-46f7-80a2-b525a8dee46d
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0062079addfbcd577faa1b16096f4588a05a8f78

---


# Sobre a integração Campaign-Audience Manager ou a dos principais serviços do People{#about-campaign-audience-manager-or-people-core-service-integration}

O Adobe Campaign permite que você troque e compartilhe públicos-alvo/segmentos com os diferentes aplicativos da Adobe Experience Cloud. A integração do **Adobe Campaign** com o serviço **principal** Pessoas (também conhecido como serviço **principal** Perfis e públicos-alvo) ou o Adobe Audience Manager permite:

* Importe públicos/segmentos de diferentes soluções da Adobe Experience Cloud para o Adobe Campaign. Os públicos-alvo podem ser importados do **[!UICONTROL Audiences]** menu no Adobe Campaign.
* Exporte públicos como públicos/segmentos compartilhados. Esses audiences podem ser usados nas 
								diferentes soluções da Adobe Experience Cloud que você usa. Os públicos-alvo podem ser exportados após a definição de metas de atividades em um fluxo de trabalho, usando a **[!UICONTROL Save audience]** atividade.

A integração oferece suporte a dois tipos de Adobe Experience Cloud IDs:

* **ID** do visitante: esse tipo de ID permite reconciliar os visitantes da Adobe Experience Cloud com os perfis do Adobe Campaign.
* **ID** declarada: esse tipo de ID permite reconciliar qualquer tipo de dados com perfis no banco de dados do Adobe Campaign. Essa integração suporta IDs declaradas regulares, IDs declaradas com hash e IDs declaradas criptografadas.

   A criptografia permite que você compartilhe dados criptografados em fontes de dados (por exemplo, PII) usando a ID declarada especificando o algoritmo de criptografia.

   Por exemplo, com a capacidade de descriptografar endereços de email criptografados ou números de SMS, você também pode enviar mensagens disparadas para seus usuários, mesmo que seu perfil não exista no banco de dados do Adobe Campaign.

>[!CAUTION]
>
>Dependendo dos dados trocados, a importação de públicos-alvo no Adobe Campaign pode estar sujeita a restrições legais

