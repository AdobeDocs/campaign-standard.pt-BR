---
solution: Campaign Standard
product: campaign
title: Sobre a integração Campaign-Audience Manager ou do serviço principal do People
description: Com a integração Audience Manager / Serviços principais de pessoas, você pode compartilhar públicos ou segmentos em diferentes soluções da Adobe Experience Cloud.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: Triggers
role: Arquiteto de dados
level: Intermediário
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 10%

---


# Sobre a integração Campaign-Audience Manager ou do serviço principal do People{#about-campaign-audience-manager-or-people-core-service-integration}

>[!CAUTION]
>
>Dependendo dos dados trocados, a importação de públicos no Adobe Campaign pode estar sujeita a restrições legais.

O Adobe Campaign permite trocar e compartilhar públicos/segmentos com os diferentes aplicativos do Adobe Experience Cloud. A integração de **Adobe Campaign** com **Serviço principal de pessoas** (também conhecido como **Serviço principal de perfis e públicos**) ou Adobe Audience Manager permite:

* Importar públicos/segmentos de diferentes soluções da Adobe Experience Cloud para o Adobe Campaign. Os públicos podem ser importados do menu **[!UICONTROL Audiences]** no Adobe Campaign.
* Exportar públicos-alvo como públicos-alvo/segmentos compartilhados. Esses audiences podem ser usados nas diferentes soluções da Adobe Experience Cloud que você usa. Os públicos podem ser exportados após as atividades de direcionamento em um workflow, usando a atividade **[!UICONTROL Save audience]** .

A integração oferece suporte a dois tipos de Adobe Experience Cloud IDs:

* **ID** do visitante: esse tipo de ID permite reconciliar visitantes do Adobe Experience Cloud com perfis do Adobe Campaign. Assim que uma conexão é habilitada via Adobe IMS, o Serviço de ID do visitante do Marketing Cloud é ativado, o que substitui o cookie permanente usado pelo Adobe Campaign. Isso permite identificar um visitante e vinculá-lo a um perfil.
   <br>Uma ID de visitante é vinculada a um perfil assim que o perfil clica em um email enviado pelo Adobe Campaign:
   * Se o perfil já tiver uma ID de visitante, os dados do navegador do perfil permitirão que o Adobe Campaign recupere e vincule automaticamente o perfil à ID de visitante.
   * Se nenhuma ID de visitante for encontrada, uma nova ID será criada. Essa ID de visitante é armazenada nos logs de rastreamento do perfil.

   A ID será reconhecida pelos outros aplicativos da Adobe Marketing Cloud com o mesmo CNAME.

* **ID** declarada: esse tipo de ID permite reconciliar qualquer tipo de dados com elementos do banco de dados do Adobe Campaign. Ele é representado no Adobe Campaign como uma chave de reconciliação predefinida. Ao trocar dados, os identificadores de banco de dados do Adobe Campaign são atribuídos a hash. Essas IDs com hash são comparadas às IDs com hash do público-alvo da Adobe Marketing Cloud envolvidas na importação ou exportação.
   <br>Essa integração oferece suporte a IDs declaradas comuns, IDs declaradas com hash e IDs declaradas criptografadas.

   >[!CAUTION]
   >
   >A ID declarada funcionará somente com o Adobe Audience Manager. A ID declarada não funcionará sem ela.

   A criptografia permite compartilhar dados criptografados em fontes de dados (por exemplo, PII) usando a ID declarada, especificando o algoritmo de criptografia.

   Por exemplo, com a capacidade de descriptografar endereços de email criptografados ou números de SMS, você também pode enviar mensagens acionadas para seus usuários, mesmo que o perfil não exista no banco de dados do Adobe Campaign.

O diagrama a seguir detalha o funcionamento dessa integração. Aqui, AAM significa Adobe Audience Manager e ACS para Adobe Campaign Standard.

![](assets/aam_diagram.png)