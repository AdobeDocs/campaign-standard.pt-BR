---
title: Sobre a integração Campaign-Audience Manager ou do serviço principal do People
description: Com a integração do serviço principal de Audience Manager / Pessoas, você pode compartilhar audiências ou segmentos em diferentes soluções Adobe Experience Cloud.
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
source-git-commit: 1e790f550f6eb84954f199caeda88a8fd90dfd85
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 8%

---


# Sobre a integração Campaign-Audience Manager ou do serviço principal do People{#about-campaign-audience-manager-or-people-core-service-integration}

>[!CAUTION]
>
>Dependendo dos dados trocados, a importação de audiências no Adobe Campaign pode estar sujeita a restrições legais.

A Adobe Campaign permite que você troque e compartilhe audiências/segmentos com diferentes aplicativos Adobe Experience Cloud. A integração do **Adobe Campaign** com o serviço **principal** Pessoas (também conhecido como serviço **principal** Perfis e Audiência) ou Adobe Audience Manager permite:

* Importe audiências/segmentos de diferentes soluções Adobe Experience Cloud para o Adobe Campaign. O Audiência pode ser importado do **[!UICONTROL Audiences]** menu no Adobe Campaign.
* Exporte audiências como audiências/segmentos compartilhados. Esses audiences podem ser usados nas diferentes soluções da Adobe Experience Cloud que você usa. As Audiências podem ser exportadas após a definição de metas de atividades em um fluxo de trabalho, usando a **[!UICONTROL Save audience]** atividade.

A integração suporta dois tipos de Adobe Experience Cloud IDs:

* **ID**do Visitante: esse tipo de ID permite reconciliar visitantes Adobe Experience Cloud com perfis Adobe Campaign. Assim que uma conexão é ativada via Adobe IMS, o serviço de ID do Visitante é ativado, substituindo o cookie permanente usado pela Adobe Campaign. Isso permite identificar um visitante e, em seguida, vinculá-lo a um perfil.
   <br>Uma ID de visitante é vinculada a um perfil assim que o perfil clica em um email enviado via Adobe Campaign:
   * Se o perfil já tiver uma ID de visitante, os dados do navegador do perfil permitirão que a Adobe Campaign recupere e vincule automaticamente o perfil à ID do visitante.
   * Se nenhuma ID de visitante for encontrada, uma nova ID será criada. Essa ID de visitante é armazenada nos logs de rastreamento de perfil.

   A ID será então reconhecida pelos outros aplicativos Adobe Marketing Cloud com o mesmo CNAME.

* **ID**declarada: esse tipo de ID permite reconciliar qualquer tipo de dados com elementos do banco de dados da Adobe Campaign. Ele é representado no Adobe Campaign como uma chave de reconciliação predefinida. Ao trocar dados, os identificadores de banco de dados do Adobe Campaign são hash. Essas IDs com hash são comparadas às IDs com hash da audiência da Adobe Marketing Cloud envolvidas na importação ou exportação.
   <br>Essa integração suporta IDs declaradas regulares, IDs declaradas com hash e IDs declaradas criptografadas.

   >[!CAUTION]
   >
   >A ID declarada só funcionará com a Adobe Audience Manager. A ID declarada não funcionará sem ela.

   A criptografia permite que você compartilhe dados criptografados em fontes de dados (por exemplo, PII) usando a ID declarada especificando o algoritmo de criptografia.

   Por exemplo, com a capacidade de descriptografar endereços de email criptografados ou números de SMS, você também pode enviar mensagens disparadas para seus usuários mesmo se o perfil deles não existir no banco de dados Adobe Campaign.

O diagrama a seguir detalha como essa integração funciona. Aqui, AAM significa Adobe Audience Manager et ACS for Adobe Campaign Standard.

![](assets/aam_diagram.png)