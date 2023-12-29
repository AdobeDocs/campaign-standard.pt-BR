---
title: Sobre o Conector de dados da Adobe Experience Platform
description: Gerencie esquemas XDM para disponibilizar seus dados de Campaign Standard no Adobe Experience Platform.
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: f4fcf256-e030-4d7b-b4b7-2448acc2ae1c
hide: true
hidefromtoc: true
source-git-commit: 376f00576ca1d0dfb536b29dbf25d88f7c93b9a8
workflow-type: tm+mt
source-wordcount: '706'
ht-degree: 3%

---

# Sobre o Conector de dados da Adobe Experience Platform {#about-aep-data-connector}

>[!IMPORTANT]
>
>O Conector de dados do Adobe Experience Platform foi descontinuado. Embora os recursos obsoletos ainda estejam disponíveis, eles não serão aprimorados nem terão suporte. Saiba mais [nesta página](../../rn/using/deprecated-features.md)

O Conector de dados do Adobe Experience Platform ajuda os clientes existentes a disponibilizar seus dados no Adobe Experience Platform, mapeando os dados XTK (dados assimilados no Campaign) para dados do Experience Data Model (XDM) no Adobe Experience Platform.

Observe que o conector é **unidirecional** e envia os dados do Adobe Campaign Standard para o Adobe Experience Platform. Os dados nunca são enviados da Adobe Experience Platform para o Adobe Campaign Standard.

O Conector de dados do Adobe Experience Platform é destinado a **engenheiros de dados** que entendem os recursos personalizados da Adobe Campaign Standard e entendem como o esquema de dados geral do cliente deve estar dentro da Adobe Experience Platform.

As seções a seguir descrevem as principais etapas para executar um mapeamento de dados entre o Campaign Standard e o Adobe Experience Platform. Isso começa com a criação de um esquema XDM e um conjunto de dados.

![](assets/do-not-localize/how-to-video.png) [Conheça este recurso no vídeo](#video)

>[!NOTE]
>Depois que o Conector de dados do Adobe Experience Platform estiver configurado e os dados forem assimilados com êxito na Adobe Experience Platform, será necessário ativar o conjunto de dados para que os dados sejam incluídos no Perfil do cliente em tempo real.
>
>Isso pode ser executado por meio das APIs ou da interface do Adobe Experience Platform. Para obter mais informações, consulte as documentações específicas:
>
>* [Ativar um conjunto de dados para o Perfil do cliente em tempo real](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/datasets/dataset.html)
>* [Configurar um conjunto de dados para o Perfil do cliente em tempo real e o Serviço de identidade usando APIs](https://experienceleague.adobe.com/docs/experience-platform/catalog/api/getting-started.html)

## Principais conceitos {#key-concepts}

* O Mapeamento pronto para uso está disponível apenas para campos que são fornecidos em Campaign Standard por padrão. Para assimilar todos os campos e recursos personalizados, cada cliente precisa definir seu próprio mapeamento.

* O Adobe Experience Platform Data Connector enviará dados de perfil por meio da plataforma em intervalos regulares.&#x200B; O intervalo dura 15 minutos. Esse valor pode ser modificado usando [APIs do Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html).

* O engenheiro de dados pode publicar, modificar e pausar o mapeamento do Campaign para o Adobe Experience Platform.

* Qualquer targeting dimension pode ser mapeada. A recomendação é ter um único mapeamento para todos os campos em um único targeting dimension.

* Todas as atualizações de perfil, incluindo aceitação/recusa de canal, fazem parte da atualização em lote.

* Qualquer alteração no esquema do Adobe Campaign Standard ou XDM precisa ser remapeada manualmente.&#x200B;

* Os dados de log de rastreamento e Broadlog são assimilados automaticamente na Adobe Experience Platform como eventos de experiência. Essa assimilação é transmitida em tempo real para a Adobe Experience Platform.

* O Serviço de ID de Experience Cloud (ECID) é um identificador de dispositivo enviado por padrão com Eventos de experiência.

  É uma ID exclusiva e persistente atribuída a um visitante, que pode ser usada pelo Serviço de identidade da plataforma para identificar o mesmo visitante e seus dados em diferentes soluções da Experience Cloud. Para obter mais informações, consulte [Ajuda do Serviço de identidade Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=pt-BR).

  >[!NOTE]
  >
  >Observe que, se dois ou mais perfis compartilharem um mesmo dispositivo, a ECID será a mesma para esses dois perfis no serviço de identidade unificada.

## Limitações {#limitations}

* A transferência de eventos de assinatura pronta para uso não é compatível. Para transferir eventos de assinatura, você pode criar o XDM e o conjunto de dados correspondentes no Adobe Experience Platform e, em seguida, configurar um mapeamento de dados personalizado para esses dados.

* Com relação às solicitações de privacidade (ações de Acesso e Exclusão), os clientes precisam fazer solicitações separadas por meio do [Serviço principal de privacidade](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html#how-to-use-privacy-service-to-manage-privacy-job-requests): um para o Campaign e um para o Adobe Experience Platform. Para obter mais informações, consulte [Sobre solicitações de privacidade](https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy-requests.html?lang=pt-BR#getting-started) e [Gerenciar solicitações de privacidade](https://helpx.adobe.com/br/campaign/kb/acs-privacy.html#ManagingPrivacyRequests) no Campaign.

* Para cada campo XDM, a rotulagem DULE precisa ser feita no Adobe Experience Platform. É responsabilidade do cliente aplicar os rótulos de DULE.

* As restrições em ações de marketing se tornam aplicáveis somente após os rótulos DULE serem aplicados no Adobe Experience Platform. Antes disso, todos os dados estavam disponíveis para todos os tipos de ações de marketing.

* A cada 15 minutos, o processo em lote está em execução e identifica os registros que foram alterados desde o último lote. Se todos os registros forem alterados no mesmo carimbo de data e hora, pode aparecer um gargalo de desempenho para gerenciar a assimilação de todos os perfis

## Tutorial em vídeo {#video}

Este vídeo fornece uma visão geral sobre o Adobe Experience Platform Data Connector.

>[!VIDEO](https://video.tv.adobe.com/v/27304?quality=12&captions=eng)

Vídeos adicionais relacionados ao Conector de dados do Adobe Experience Platform estão disponíveis [aqui](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html).
