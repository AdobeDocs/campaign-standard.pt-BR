---
title: Sobre o Conector de dados da Adobe Experience Platform
description: Gerencie schemas XDM para disponibilizar seus dados de Campaign Standard na Adobe Experience Platform.
page-status-flag: never-activated
uuid: 867b1c4b-4c79-4c52-9d0a-ef71993e50a2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 406c955a-b2d2-4099-9918-95f5fa966067
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1dff41bc7b64d2f7ed7c88e002675e50e68a825f

---


# Sobre o Conector de dados da Adobe Experience Platform {#about-aep-data-connector}

>[!IMPORTANT]
>
>O Adobe Experience Platform Data Connector está atualmente em beta, que pode estar sujeito a atualizações frequentes sem aviso prévio. Os clientes precisam estar hospedados no Azure (atualmente em beta somente para a América do Norte) para acessar esses recursos. Entre em contato com o Atendimento ao cliente da Adobe se desejar acessar.

O Adobe Experience Platform Data Connector ajuda os clientes existentes a disponibilizarem seus dados na Adobe Experience Platform, mapeando dados XTK (dados ingeridos na Campanha) para dados do Experience Data Model (XDM) na Adobe Experience Platform.

Observe que o conector é **unidirecional** e envia os dados do Adobe Campaign Standard para a Adobe Experience Platform. Os dados nunca são enviados da Adobe Experience Platform para o Adobe Campaign Standard.

O Adobe Experience Platform Data Connector destina-se aos engenheiros **de** dados que entendem os recursos personalizados do Adobe Campaign Standard e que têm um entendimento de como o schema de dados geral do cliente deve estar dentro da Adobe Experience Platform.

As seções a seguir descrevem as etapas principais para executar um mapeamento de dados entre o Campaign Standard e a Adobe Experience Platform. Isso start com a criação de um schema XDM e um conjunto de dados.

Os vídeos passo a passo também estão disponíveis [nesta página](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html).

>[!NOTE]
>Depois que o Adobe Experience Platform Data Connector for configurado e os dados forem assimilados com êxito na Adobe Experience Platform, será necessário ativar o conjunto de dados para que os dados sejam incluídos no Perfil do cliente em tempo real.
>
>Isso pode ser feito por meio das APIs ou da interface da plataforma Adobe Experience. Para obter mais informações, consulte as documentações dedicadas:
>
>* [Ativar um conjunto de dados para o Perfil do cliente em tempo real](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/datasets/dataset.html)
>* [Configurar um conjunto de dados para o Perfil do cliente em tempo real e o serviço de identidade usando APIs](https://docs.adobe.com/content/help/en/experience-platform/catalog/api/getting-started.html)


## Principais conceitos {#key-concepts}

* O Mapeamento fora da caixa só está disponível para campos que são fornecidos no Campaign Standard por padrão. Para assimilar todos os campos e recursos personalizados, cada cliente precisa definir seu próprio mapeamento.

* O Adobe Experience Platform Data Connector envia os dados do perfil pela plataforma em intervalos regulares. &#x200B; A duração do intervalo é de 15 mn. Esse valor pode ser modificado usando as APIs [da plataforma](https://docs.adobe.com/content/help/en/experience-platform/ingestion/home.html)Adobe Experience.

* O engenheiro de dados pode publicar, modificar e pausar o mapeamento da Campanha para a Adobe Experience Platform.

* Qualquer targeting dimension pode ser mapeado. A recomendação é ter um único mapeamento para todos os campos em um único targeting dimension.

* Todas as atualizações de perfis, incluindo opções/opções de não participação de canais, fazem parte da atualização em lote.

* Qualquer alteração de schema Adobe Campaign Standard ou XDM precisa ser remapeada manualmente. &#x200B;

* Os dados de log de rastreamento e de Broadlog são assimilados automaticamente à Adobe Experience Platform como Eventos de experiência. Essa ingestão é transmitida em tempo real para a Adobe Experience Platform.

* O Serviço da Experience Cloud ID (ECID) é um identificador de dispositivo enviado por padrão com os Eventos da Experience Cloud.

   É uma ID exclusiva e persistente atribuída a um visitante, que pode ser usada pelo Serviço de identificação da plataforma para identificar o mesmo visitante e seus dados em diferentes soluções da Experience Cloud. Para obter mais informações, consulte a Ajuda [do Serviço de identidade da](https://docs.adobe.com/content/help/en/id-service/using/home.html)Experience Cloud.

   >[!NOTE]
   >
   >Esteja ciente de que, se dois ou mais perfis compartilharem um mesmo dispositivo, o ECID será o mesmo para esses dois perfis no serviço de identidade unificada.

## Limitações {#limitations}

* A transferência predefinida de eventos de subscrição não é suportada. Para transferir eventos de subscrição, você pode criar XDM e conjunto de dados correspondentes na Adobe Experience Platform e, em seguida, configurar um mapeamento de dados personalizado para esses dados.

* Quanto às solicitações de privacidade (tanto as ações de Acesso quanto Excluir), os clientes precisam colocar solicitações separadas por meio do [Privacy Core Service](https://docs.adobe.com/content/help/en/experience-platform/privacy/home.html#how-to-use-privacy-service-to-manage-privacy-job-requests): um para a Campanha e outro para a Adobe Experience Platform. Para obter mais informações, consulte [Sobre solicitações](https://helpx.adobe.com/campaign/kb/acs-privacy.html#righttoaccess) de privacidade e [Gerenciar solicitações](https://helpx.adobe.com/campaign/kb/acs-privacy.html#ManagingPrivacyRequests) de privacidade na Campanha.

* Para cada campo XDM, a rotulação DULE precisa ser feita na Adobe Experience Platform. Esta é a responsabilidade do cliente de aplicar etiquetas DULE.

* As restrições às ações de marketing se tornam aplicáveis somente depois que as etiquetas DULE são aplicadas na Adobe Experience Platform. Antes disso, todos os dados estão disponíveis para todos os tipos de ações de marketing.

* A cada 15 minutos, o trabalho em lote é executado e identifica os registros que foram alterados desde o lote mais recente. Se todos os registros mudarem no mesmo carimbo de data e hora, um gargalo de desempenho pode parecer gerenciar a ingestão de todos os perfis
