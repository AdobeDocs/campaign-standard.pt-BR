---
title: Sobre a integração do Campaign com o Audience Manager ou do Serviço principal de pessoas
description: Com a integração do serviço principal Audience Manager / People, é possível compartilhar públicos ou segmentos nas diferentes soluções da Adobe Experience Cloud.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: e8b96c66-82f7-4adb-88b2-b7e0f7c4a96f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 22%

---

# Sobre a integração do Campaign com o Audience Manager ou do Serviço principal de pessoas{#about-campaign-audience-manager-or-people-core-service-integration}

>[!CAUTION]
>
>Dependendo dos dados trocados, a importação de públicos no Adobe Campaign pode estar sujeita a restrições legais.

O Adobe Campaign permite trocar e compartilhar públicos/segmentos com os diferentes aplicativos da Adobe Experience Cloud. Integração do **Adobe Campaign** com **Serviço principal de pessoas** (também conhecido como **Serviço principal de perfis e públicos-alvo**) ou o Adobe Audience Manager permite:

* Importar públicos/segmentos de diferentes soluções da Adobe Experience Cloud para a Adobe Campaign. Os públicos-alvo podem ser importados da **[!UICONTROL Audiences]** no Adobe Campaign.
* Exportar audiências como audiences/segmentos compartilhados. Esses audiences podem ser usados nas diferentes soluções da Adobe Experience Cloud que você usa. Os públicos podem ser exportados após o direcionamento de atividades em um workflow, usando o **[!UICONTROL Save audience]** atividade.

A integração oferece suporte a dois tipos de Adobe Experience Cloud IDs:

* **Visitor ID**: esse tipo de ID permite reconciliar visitantes do Adobe Experience Cloud com perfis do Adobe Campaign. Assim que uma conexão for habilitada por meio do Adobe IMS, o Serviço de ID de visitante do Marketing Cloud será ativado, substituindo o cookie permanente usado pelo Adobe Campaign. Isso permite identificar um visitante e vinculá-lo a um perfil.
  <br>Uma ID de visitante é vinculada a um perfil assim que ele clica em um email enviado pelo Adobe Campaign:
   * Se o perfil já tiver uma ID de visitante, os dados do navegador do perfil permitirão que o Adobe Campaign recupere e vincule automaticamente o perfil à ID de visitante.
   * Se nenhuma ID de visitante for encontrada, uma nova ID será criada. Essa ID de visitante é armazenada nos logs de rastreamento do perfil.

  A ID será reconhecida pelos outros aplicativos da Adobe Marketing Cloud com o mesmo CNAME.

* **ID declarada**: esse tipo de ID permite reconciliar qualquer tipo de dados com elementos do banco de dados do Adobe Campaign. Ele é representado no Adobe Campaign como uma chave de reconciliação predefinida. Ao trocar dados, os identificadores do banco de dados do Adobe Campaign são transformados em hash. Essas IDs com hash são comparadas com as IDs com hash do público-alvo do Adobe Marketing Cloud envolvido na importação ou exportação.
  <br>Essa integração aceita IDs declaradas regulares, IDs declaradas com hash e IDs declaradas criptografadas.

  >[!NOTE]
  >
  >A fonte de dados de ID declarada agora também pode ser usada com a integração do serviço principal Pessoas.
  >
  >Se você estiver usando a integração do serviço principal Pessoas e quiser adicionar a integração do Audience Manager, será necessária a ajuda de um consultor do Adobe Audience Manager para evitar a perda de todas as sincronizações de ID coletadas durante a transição para o uso dessa fonte de dados de ID declarada em um contexto do Adobe Audience Manager.


  A criptografia permite compartilhar dados criptografados em fontes de dados (por exemplo, PII) usando a ID declarada ao especificar o algoritmo de criptografia.

  Por exemplo, com a capacidade de descriptografar endereços de email criptografados ou números SMS, você também pode enviar mensagens acionadas para seus usuários, mesmo se o perfil deles não existir no banco de dados do Adobe Campaign.

O diagrama a seguir detalha o funcionamento dessa integração. Aqui, AAM significa Adobe Audience Manager e ACS é Adobe Campaign Standard.

![](assets/aam_diagram.png)
