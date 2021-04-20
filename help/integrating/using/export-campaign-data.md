---
solution: Campaign Standard
product: campaign
title: Exportar dados do Campaign para o Adobe Experience Platform
description: Saiba como exportar dados do Campaign Standard para o Adobe Experience Platform.
audience: integrating
content-type: reference
feature: Sources and Destinations
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: bf442b12506ef71cc76aa7fffb0e4c8bb2ce70da
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 1%

---


# Exportar dados do Campaign para o Adobe Experience Platform {#sources}

Para exportar dados do Campaign Standard para a Plataforma de dados do cliente em tempo real (RTCDP) do Adobe, primeiro é necessário criar um fluxo de trabalho no Campaign Standard para exportar para seu local de armazenamento de blobs do S3 ou do Azure os dados que você deseja compartilhar.

Depois que o fluxo de trabalho tiver sido configurado e os dados forem enviados para o local de armazenamento, é necessário conectar o local de armazenamento de blobs do S3 ou do Azure como um **Source** na Adobe experience Platform.

>[!NOTE]

Observe que é recomendável exportar apenas os dados gerados pelo Campaign (por exemplo, envios, aberturas, cliques etc.) para o Adobe Experience Platform. Os dados assimilados de uma fonte de terceiros (como seu CRM) devem ser importados diretamente para o Adobe Experience Platform.

## Criar um workflow de exportação no Campaign Standard

Para exportar dados do Campaign Standard para o local de armazenamento S3 ou Azure Blob, você precisa criar um workflow para direcionar os dados que deseja exportar e enviá-los para o local de armazenamento.

Para fazer isso, adicione e configure:

* Uma atividade **[!UICONTROL Extract file]** para extrair os dados direcionados em um arquivo CSV. Para obter mais informações sobre como configurar essa atividade, consulte [esta seção](../../automating/using/extract-file.md).

   ![](assets/rtcdp-extract-file.png)

* Uma atividade **[!UICONTROL Transfer file]** para transferir o arquivo CSV para o local de armazenamento. Para obter mais informações sobre como configurar essa atividade, consulte [esta seção](../../automating/using/transfer-file.md).

   ![](assets/rtcdp-transfer-file.png)

Como exemplo, o fluxo de trabalho abaixo extrai logs regularmente em um arquivo CSV e o transfere para um local de armazenamento.

![](assets/aep-export.png)

Exemplos de workflows de gerenciamento de dados estão disponíveis na seção [workflows use cases](../../automating/using/about-workflow-use-cases.md#management) .

Tópicos relacionados:

* [Atividades de gestão de dados](../../automating/using/about-data-management-activities.md)
* [Sobre a importação e exportação de dados](../../automating/using/about-data-import-and-export.md)


## Conecte seu local de armazenamento como uma Fonte

As principais etapas para conectar seu local de armazenamento de blobs do S3 ou do Azure como um **Source** na Plataforma de experiência do Adobe estão listadas abaixo. Informações detalhadas sobre cada uma dessas etapas estão disponíveis na [Documentação dos conectores de origem](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html).

1. No menu da Adobe Experience Platform **[!UICONTROL Sources]**, crie uma conexão com o local de armazenamento:

   * [Criar uma conexão de origem Amazon S3](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/s3.html)
   * [Conector Azure Blob](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/cloud-storage/blob.html)

   >[!NOTE]
   >
   >O local de armazenamento pode ser Amazon S3, SFTP com senha, SFTP com chave SSH ou conexões Blob do Azure. O método preferido para enviar dados para o Adobe Campaign é por meio do Amazon S3 ou Azure Blob:

   ![](assets/rtcdp-connector.png)

1. Configure um fluxo de dados para uma conexão em lote de armazenamento na nuvem. Um fluxo de dados é uma tarefa agendada que recupera e assimila dados do local de armazenamento para um conjunto de dados da Adobe Experience Platform. Essas etapas permitem configurar a assimilação de dados do local de armazenamento, incluindo a seleção de dados e o mapeamento dos campos CSV para um esquema XDM.

   Informações detalhadas estão disponíveis em [this page](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html).

   ![](assets/rtcdp-map-xdm.png)

1. Após a configuração da Origem, o Adobe Experience Platform importará o arquivo do local de armazenamento fornecido.

   Essa operação pode ser agendada de acordo com suas necessidades. Recomendamos executar a exportação até 6 vezes por dia, dependendo da carga já presente na instância.
