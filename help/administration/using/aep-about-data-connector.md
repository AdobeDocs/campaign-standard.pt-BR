---
title: Sobre o Adobe Experience Platform Data Connector
description: Gerencie esquemas XDM para disponibilizar seus dados do Campaign Standard na Adobe Experience Platform.
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
source-git-commit: 8ea3340e9ffb8b438c781aeff1a8554c9160474f

---


# Sobre o Adobe Experience Platform Data Connector {#about-aep-data-connector}

>[!IMPORTANT]
>
>O Adobe Experience Platform Data Connector está atualmente em beta, que pode estar sujeito a atualizações frequentes sem aviso prévio. Os clientes precisam estar hospedados no Azure (atualmente em beta somente para a América do Norte) para acessar esses recursos. Entre em contato com o Atendimento ao cliente da Adobe se desejar acessar.

O Adobe Experience Platform Data Connector ajuda os clientes existentes a disponibilizar seus dados na Adobe Experience Platform, mapeando dados XTK (dados ingeridos no Campaign) para dados do Experience Data Model (XDM) na Adobe Experience Platform.

Observe que o conector é **unidirecional** e envia os dados do Adobe Campaign Standard para a Adobe Experience Platform. Os dados nunca são enviados da Adobe Experience Platform para o Adobe Campaign Standard.

O Adobe Experience Platform Data Connector destina-se a engenheiros **de** dados que entendem os recursos personalizados do Adobe Campaign Standard e têm uma compreensão de como o esquema geral de dados do cliente deve estar dentro da Adobe Experience Platform.

As seções a seguir descrevem as etapas principais para executar um mapeamento de dados entre o Campaign Standard e a Adobe Experience Platform. Isso começa com a criação de um esquema XDM e um conjunto de dados.

Os vídeos passo a passo também estão disponíveis [nesta página](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html).

>[!NOTE]
>Depois que o Adobe Experience Platform Data Connector for configurado e os dados forem assimilados com êxito na Adobe Experience Platform, será necessário ativar o conjunto de dados para que os dados sejam incluídos no Perfil do cliente em tempo real.
>
>Isso pode ser feito por meio das APIs ou da interface da plataforma Adobe Experience. Para obter mais informações, consulte as documentações dedicadas:
>
>* [Ativar um conjunto de dados para o perfil do cliente em tempo real](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/data_ingestion_tutorial/data_ingestion_tutorial.md)
>* [Configurar um conjunto de dados para o Perfil do cliente e o Serviço de identidade em tempo real usando APIs](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/unified_profile_dataset_tutorial/unified_profile_dataset_api_tutorial.md)


## Principais conceitos {#key-concepts}

* O Mapeamento fora da caixa só está disponível para campos que são fornecidos no Campaign Standard por padrão. Para assimilar todos os campos e recursos personalizados, cada cliente precisa definir seu próprio mapeamento.

* O Adobe Experience Platform Data Connector envia os dados do perfil pela plataforma em intervalos regulares. &#x200B; A duração do intervalo é de 15 mn. Esse valor não pode ser modificado.

   >[!NOTE]
   >
   >Essa duração pode ser modificada usando as APIs [da plataforma](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/authenticate_to_acp_tutorial/authenticate_to_acp_tutorial.md)Adobe Experience.

* O engenheiro de dados pode publicar, modificar e pausar o mapeamento do Campaign para o Adobe Experience Platform.

* Qualquer dimensão de definição de metas pode ser mapeada. A recomendação é ter um único mapeamento para todos os campos em uma única dimensão de direcionamento.

* Todas as atualizações de perfil, incluindo opções de canal/opções de não participação, fazem parte da atualização em lote.

* Qualquer alteração no esquema do Adobe Campaign Standard ou XDM precisa ser remapeada manualmente. &#x200B;

* Os dados de log de rastreamento e de Broadlog são assimilados automaticamente à Adobe Experience Platform como Eventos de experiência. Essa ingestão é transmitida em tempo real para a Adobe Experience Platform.

## Limitações {#limitations}

* A transferência predefinida de eventos de assinatura não é suportada. Para transferir eventos de assinatura, você pode criar XDM e conjunto de dados correspondentes na Adobe Experience Platform e, em seguida, configurar um mapeamento de dados personalizado para esses dados.

* Em relação às solicitações de privacidade, os clientes precisam colocar solicitações separadas para o serviço principal de privacidade do Campaign e a plataforma Adobe Experience para acessar e excluir ações.

* Para cada campo XDM, a rotulagem DULE precisa ser feita na Adobe Experience Platform. Esta é a responsabilidade do cliente de aplicar etiquetas DULE.

* As restrições às ações de marketing se tornam aplicáveis somente depois que as etiquetas DULE são aplicadas na Adobe Experience Platform. Antes disso, todos os dados estão disponíveis para todos os tipos de ações de marketing.

* A cada 15 minutos, o trabalho em lote é executado e identifica os registros que foram alterados desde o lote mais recente. Se todos os registros mudarem no mesmo carimbo de data e hora, um gargalo de desempenho pode parecer gerenciar a ingestão de todos os perfis
