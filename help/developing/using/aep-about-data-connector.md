---
solution: Campaign Standard
product: campaign
title: Sobre o Conector de dados da Adobe Experience Platform
description: Gerencie schemas XDM para disponibilizar seus dados de Campaign Standard no Adobe Experience Platform.
audience: administration
content-type: reference
topic-tags: configuring-channels
translation-type: tm+mt
source-git-commit: 2729852365a2e74d2a603d95f75285fe54313e71
workflow-type: tm+mt
source-wordcount: '783'
ht-degree: 6%

---


# Sobre o Conector de dados da Adobe Experience Platform {#about-aep-data-connector}

>[!IMPORTANT]
>
>O Adobe Experience Platform Data Connector está atualmente em beta, o que pode estar sujeito a atualizações frequentes sem aviso prévio. Os clientes precisam estar hospedados no Azure (atualmente em beta somente para a América do Norte) para acessar esses recursos. Entre em contato com o Atendimento ao cliente do Adobe se desejar acessá-lo.

O Adobe Experience Platform Data Connector ajuda os clientes existentes a disponibilizarem seus dados no Adobe Experience Platform, mapeando dados XTK (dados ingeridos na Campanha) para dados do Experience Data Model (XDM) no Adobe Experience Platform.

Observe que o conector é **uni-directional** e envia os dados da Adobe Campaign Standard para a Adobe Experience Platform. Os dados nunca são enviados da Adobe Experience Platform para a Adobe Campaign Standard.

O Adobe Experience Platform Data Connector destina-se a **engenheiros de dados** que compreendem os recursos personalizados da Adobe Campaign Standard e têm uma compreensão de como o schema de dados geral do cliente deve estar dentro da Adobe Experience Platform.

As seções a seguir descrevem as etapas principais para executar um mapeamento de dados entre o Campaign Standard e o Adobe Experience Platform. Isso start com a criação de um schema XDM e um conjunto de dados.

![](assets/do-not-localize/how-to-video.png) [Descubra este recurso no vídeo](#video)

>[!NOTE]
>Depois que o Adobe Experience Platform Data Connector for configurado e os dados forem ingeridos com êxito no Adobe Experience Platform, será necessário ativar o conjunto de dados para que os dados sejam incluídos no Perfil Cliente em tempo real.
>
>Isso pode ser feito por meio das APIs ou da interface do Adobe Experience Platform. Para obter mais informações, consulte as documentações dedicadas:
>
>* [Ativar um conjunto de dados para o Perfil do cliente em tempo real](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/datasets/dataset.html)
>* [Configurar um conjunto de dados para o Perfil do cliente em tempo real e o serviço de identidade usando APIs](https://docs.adobe.com/content/help/en/experience-platform/catalog/api/getting-started.html)


## Principais conceitos {#key-concepts}

* O Mapeamento fora da caixa só está disponível para campos que são fornecidos no Campaign Standard por padrão. Para assimilar todos os campos e recursos personalizados, cada cliente precisa definir seu próprio mapeamento.

* O Adobe Experience Platform Data Connector envia dados do perfil pela plataforma em intervalos regulares. &#x200B; A duração do intervalo é de 15 minutos. Esse valor pode ser modificado usando [APIs do Adobe Experience Platform](https://docs.adobe.com/content/help/en/experience-platform/ingestion/home.html).

* O engenheiro de dados pode publicar, modificar e pausar o mapeamento da Campanha para o Adobe Experience Platform.

* Qualquer targeting dimension pode ser mapeado. A recomendação é ter um único mapeamento para todos os campos em um único targeting dimension.

* Todas as atualizações de perfis, incluindo opções/opções de não participação de canais, fazem parte da atualização em lote.

* Qualquer alteração no schema Adobe Campaign Standard ou XDM precisa ser remapeada manualmente. &#x200B;

* Os dados de log de rastreamento e de Broadlog são assimilados automaticamente à Adobe Experience Platform como Eventos da experiência. Essa ingestão é transmitida em tempo real para a Adobe Experience Platform.

* Serviço de ID de Experience Cloud (ECID) é um identificador de dispositivo enviado por padrão com Eventos de experiência.

   É uma ID exclusiva e persistente atribuída a um visitante, que pode ser usada pelo Serviço de identificação da plataforma para identificar o mesmo visitante e seus dados em diferentes soluções de Experience Cloud. Para obter mais informações, consulte a [Ajuda do Experience Cloud Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html).

   >[!NOTE]
   >
   >Esteja ciente de que, se dois ou mais perfis compartilharem um mesmo dispositivo, o ECID será o mesmo para esses dois perfis no serviço de identidade unificada.

## Limitações {#limitations}

* A transferência predefinida de eventos de subscrição não é suportada. Para transferir eventos de subscrição, você pode criar XDM e conjunto de dados correspondentes no Adobe Experience Platform e, em seguida, configurar um mapeamento de dados personalizado para esses dados.

* Quanto às solicitações de privacidade (tanto as ações de Acesso quanto Excluir), os clientes precisam colocar solicitações separadas por meio do [Privacy Core Service](https://docs.adobe.com/content/help/en/experience-platform/privacy/home.html#how-to-use-privacy-service-to-manage-privacy-job-requests): um para Campanha e outro para Adobe Experience Platform. Para obter mais informações, consulte [Sobre solicitações de privacidade](https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy-requests.html?lang=pt-BR#getting-started) e [Gerenciando solicitações de privacidade](https://helpx.adobe.com/br/campaign/kb/acs-privacy.html#ManagingPrivacyRequests) na Campanha.

* Para cada campo XDM, a rotulação DULE precisa ser feita no Adobe Experience Platform. Esta é a responsabilidade do cliente de aplicar etiquetas DULE.

* As restrições às ações de marketing tornam-se aplicáveis somente depois que as etiquetas DULE são aplicadas no Adobe Experience Platform. Antes disso, todos os dados estão disponíveis para todos os tipos de ações de marketing.

* A cada 15 minutos, o trabalho em lote é executado e identifica os registros que foram alterados desde o lote mais recente. Se todos os registros mudarem no mesmo carimbo de data e hora, um gargalo de desempenho pode parecer gerenciar a ingestão de todos os perfis

## Vídeo tutorial {#video}

Este vídeo fornece uma visão geral sobre o Adobe Experience Platform Data Connector.

>[!VIDEO](https://video.tv.adobe.com/v/27304?quality=12&captions=eng)

Vídeos adicionais relacionados ao Adobe Experience Platform Data Connector estão disponíveis [aqui](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html?lang=pt-BR#administrating).
