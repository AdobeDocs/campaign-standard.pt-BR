---
title: Exportar dados do Campaign para a Adobe Experience Platform
description: Saiba como exportar dados do Campaign Standard para o Adobe Experience Platform.
audience: integrating
content-type: reference
role: Data Architect
level: Intermediate
exl-id: eccd2922-0e75-4525-9b60-b48f628deeae
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 72%

---

# Exportar dados do Campaign para a Adobe Experience Platform {#sources}

Para exportar dados do Campaign Standard para o Adobe Real-time Customer Data Platform (RTCDP), primeiro é necessário criar um fluxo de trabalho no Campaign Standard para exportar para seu serviço de armazenamento do Amazon (S3) ou local de armazenamento do Azure Blob os dados que você deseja compartilhar.

Depois que o fluxo de trabalho tiver sido configurado e os dados forem enviados para o local de armazenamento, será necessário conectar o local de armazenamento de blobs do S3 ou do Azure como uma **Origem** na Adobe Experience Platform.

>[!NOTE]
>
>Observe que é recomendável exportar apenas os dados gerados pelo Campaign (por exemplo, envios, aberturas, cliques etc.) para a Adobe Experience Platform. Os dados assimilados de uma fonte de terceiros (como seu CRM) devem ser importados diretamente para a Adobe Experience Platform.

## Criar um fluxo de trabalho de exportação no Campaign Standard

Para exportar dados do Campaign Standard para o local de armazenamento de blobs do S3 ou do Azure Blob, é necessário criar um fluxo de trabalho para direcionar os dados que você deseja exportar e enviá-los para o local de armazenamento.

Para fazer isso, adicione e configure:

* A **[!UICONTROL Extract file]** atividade para extrair os dados direcionados em um arquivo CSV. Para obter mais informações sobre como configurar esta atividade, consulte [esta seção](../../automating/using/extract-file.md).

  ![](assets/rtcdp-extract-file.png)

* Uma atividade **[!UICONTROL Transfer file]** para transferir o arquivo CSV para o local de armazenamento. Para obter mais informações sobre como configurar uma atividade , consulte [esta seção](../../automating/using/transfer-file.md).

  ![](assets/rtcdp-transfer-file.png)

Como exemplo, o fluxo de trabalho abaixo extrai logs regularmente em um arquivo CSV e o transfere para um local de armazenamento.

![](assets/aep-export.png)

Exemplos de workflows de gerenciamento de dados estão disponíveis no [casos de uso de workflows](../../automating/using/about-workflow-use-cases.md#management) seção.

Tópicos relacionados:

* [Atividades de gerenciamento de dados](../../automating/using/about-data-management-activities.md)
* [Sobre importação e exportação de dados](../../automating/using/about-data-import-and-export.md)


## Conectar seu local de armazenamento como uma Origem

As principais etapas para conectar seu Serviço de Armazenamento do Amazon (S3) ou local de armazenamento de blobs do Azure como um **Origem** na Adobe experience Platform estão listadas abaixo. Informações detalhadas sobre cada uma dessas etapas estão disponíveis na [Documentação dos conectores de origem](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=pt-BR).

1. No menu **[!UICONTROL Sources]** da Adobe Experience Platform, crie uma conexão com o local de armazenamento:

   * [Criar uma conexão de origem do Amazon S3](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/s3.html?lang=pt-BR)
   * [Conector de blob do Azure](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/cloud-storage/blob.html?lang=pt-BR)

   >[!NOTE]
   >
   >O local de armazenamento pode ser Amazon S3, SFTP com senha, SFTP com chave SSH ou conexões de blob do Azure. O método preferido para enviar dados para o Adobe Campaign é por meio do Amazon S3 ou Blob do Azure:

   ![](assets/rtcdp-connector.png)

1. Configure um fluxo de dados para uma conexão em lote de armazenamento na nuvem. Um fluxo de dados é uma tarefa agendada que recupera e assimila dados do local de armazenamento para um conjunto de dados da Adobe Experience Platform. Essas etapas permitem configurar a assimilação de dados do local de armazenamento, incluindo a seleção de dados e o mapeamento dos campos CSV para um esquema XDM.

   Informações detalhadas estão disponíveis [nesta página](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html?lang=pt-BR).

   ![](assets/rtcdp-map-xdm.png)

1. Após a configuração da Origem, a Adobe Experience Platform importará o arquivo do local de armazenamento fornecido.

   Essa operação pode ser agendada de acordo com suas necessidades. Recomendamos executar a exportação até 6 vezes por dia, dependendo da carga já presente na instância.
