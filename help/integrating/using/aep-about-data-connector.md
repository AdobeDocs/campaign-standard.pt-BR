---
solution: Campaign Standard
product: campaign
title: Sobre o Conector de dados da Adobe Experience Platform
description: Gerencie esquemas XDM para disponibilizar os dados do Campaign Standard na Adobe Experience Platform.
audience: administration
content-type: reference
topic-tags: configuring-channels
translation-type: tm+mt
source-git-commit: 35d61efce8d752ea30b7eaad55e6c23d4debd853
workflow-type: tm+mt
source-wordcount: '783'
ht-degree: 6%

---


# Sobre o Conector de dados da Adobe Experience Platform {#about-aep-data-connector}

>[!IMPORTANT]
>
>O Conector de dados da Adobe Experience Platform está atualmente em beta, que pode estar sujeito a atualizações frequentes sem aviso prévio. Os clientes precisam ser hospedados no Azure (atualmente em beta somente para a América do Norte) para acessar esses recursos. Entre em contato com o Atendimento ao cliente da Adobe se desejar acesso.

O Adobe Experience Platform Data Connector ajuda os clientes existentes a disponibilizar seus dados na Adobe Experience Platform, mapeando dados XTK (dados assimilados no Campaign) para dados do Experience Data Model (XDM) na Adobe Experience Platform.

Observe que o conector é **uni-direcional** e envia os dados do Adobe Campaign Standard para a Adobe Experience Platform. Os dados nunca são enviados da Adobe Experience Platform para o Adobe Campaign Standard.

O Adobe Experience Platform Data Connector é destinado a **engenheiros de dados** que compreendem os recursos personalizados do Adobe Campaign Standard e têm uma compreensão de como o schema de dados geral do cliente deve estar dentro da Adobe Experience Platform.

As seções a seguir descrevem as principais etapas para executar um mapeamento de dados entre o Campaign Standard e a Adobe Experience Platform. Isso começa com a criação de um esquema XDM e um conjunto de dados.

![](assets/do-not-localize/how-to-video.png) [Descubra este recurso no vídeo](#video)

>[!NOTE]
>Depois que o Conector de dados da Adobe Experience Platform é configurado e os dados são assimilados com êxito na Adobe Experience Platform, é necessário ativar o conjunto de dados para que os dados sejam incluídos no Perfil do cliente em tempo real.
>
>Isso pode ser executado por meio das APIs ou da interface da Adobe Experience Platform. Para obter mais informações, consulte as documentações dedicadas:
>
>* [Ativar um conjunto de dados para o Perfil do cliente em tempo real](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/datasets/dataset.html)
>* [Configurar um conjunto de dados para o Perfil do cliente em tempo real e o Serviço de identidade usando APIs](https://docs.adobe.com/content/help/en/experience-platform/catalog/api/getting-started.html)


## Principais conceitos {#key-concepts}

* Mapeamento pronto para uso está disponível somente para campos fornecidos no Campaign Standard por padrão. Para assimilar todos os campos e recursos personalizados, cada cliente precisa definir seu próprio mapeamento.

* O Conector de dados da Adobe Experience Platform enviará dados do perfil pela plataforma em intervalos regulares. &#x200B; A duração do intervalo é de 15 minutos. Esse valor pode ser modificado usando [APIs da Adobe Experience Platform](https://docs.adobe.com/content/help/en/experience-platform/ingestion/home.html).

* O engenheiro de dados pode publicar, modificar e pausar o mapeamento do Campaign para a Adobe Experience Platform.

* Qualquer targeting dimension pode ser mapeada. A recomendação é ter um único mapeamento para todos os campos em um único targeting dimension.

* Todas as atualizações de perfil, incluindo opções/recusas de canal, fazem parte da atualização em lote.

* Qualquer alteração no esquema do Adobe Campaign Standard ou XDM precisa ser remapeada manualmente &#x200B;

* Os dados de log de rastreamento e Broadlog são assimilados automaticamente na Adobe Experience Platform como Eventos de experiência. Essa assimilação é transmitida em tempo real para a Adobe Experience Platform.

* O Serviço da Experience Cloud ID (ECID) é um identificador de dispositivo enviado por padrão com os Eventos de experiência.

   É uma ID exclusiva e persistente atribuída a um visitante, que pode ser usada pelo serviço de identidade da plataforma para identificar o mesmo visitante e seus dados em diferentes soluções da Experience Cloud. Para obter mais informações, consulte a [Ajuda do serviço de identidade da Experience Cloud](https://docs.adobe.com/content/help/en/id-service/using/home.html).

   >[!NOTE]
   >
   >Observe que, se dois ou mais perfis compartilharem um mesmo dispositivo, a ECID será a mesma para esses dois perfis no serviço de identidade unificada.

## Limitações {#limitations}

* A transferência pronta para uso de eventos de assinatura não é compatível. Para transferir eventos de assinatura, você pode criar XDM e conjunto de dados correspondentes na Adobe Experience Platform e, em seguida, configurar um mapeamento de dados personalizado para esses dados.

* Em relação às solicitações de privacidade (ações de Acesso e Exclusão ), os clientes precisam fazer solicitações separadas por meio do [Privacy Core Service](https://docs.adobe.com/content/help/en/experience-platform/privacy/home.html#how-to-use-privacy-service-to-manage-privacy-job-requests): um para Campaign e outro para Adobe Experience Platform. Para obter mais informações, consulte [Sobre solicitações de privacidade](https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy-requests.html?lang=pt-BR#getting-started) e [Gerenciando solicitações de privacidade](https://helpx.adobe.com/br/campaign/kb/acs-privacy.html#ManagingPrivacyRequests) no Campaign.

* Para cada campo XDM, a rotulagem DULE precisa ser feita na Adobe Experience Platform. Essa é a responsabilidade do cliente de aplicar rótulos de DULE.

* As restrições em ações de marketing se tornam aplicáveis somente após a aplicação de rótulos de DULE na Adobe Experience Platform. Antes disso, todos os dados estão disponíveis para todos os tipos de ações de marketing.

* A cada 15 minutos, o trabalho em lote é executado e identifica os registros que foram alterados desde o último lote. Se todos os registros forem alterados no mesmo carimbo de data e hora, um gargalo de desempenho poderá aparecer para gerenciar a assimilação de todos os perfis

## Vídeo tutorial {#video}

Este vídeo fornece uma visão geral sobre o Conector de dados da Adobe Experience Platform.

>[!VIDEO](https://video.tv.adobe.com/v/27304?quality=12&captions=eng)

Vídeos adicionais relacionados ao Conector de dados da Adobe Experience Platform estão disponíveis [aqui](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html?lang=pt-BR#administrating).
