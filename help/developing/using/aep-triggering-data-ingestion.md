---
title: Acionando a assimilação de dados por meio de APIs
description: Saiba como acionar a ingestão de dados por meio de APIs.
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
source-git-commit: 762700893c913d9aea884d00438c84b39a800188
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 5%

---


# Acionando a assimilação de dados por meio de APIs {#triggering-data-ingestion-apis}

>[!IMPORTANT]
>
>O Adobe Experience Platform Data Connector está atualmente em beta, o que pode estar sujeito a atualizações frequentes sem aviso prévio. Os clientes precisam estar hospedados no Azure (atualmente em beta somente para a América do Norte) para acessar esses recursos. Entre em contato com o Atendimento ao cliente do Adobe se desejar acessá-lo.

A Adobe Campaign Standard permite acionar a ingestão imediata de mapeamentos de dados por meio de APIs e recuperar o status de suas solicitações de ingestão.

Esta página descreve como acionar e recuperar o status de ingestão de seus mapeamentos de dados. Para obter informações globais sobre APIs de Campaign Standard, consulte [esta seção](../../api/using/get-started-apis.md).

## Pré-requisitos {#prerequisites}

Antes de usar as APIs, o mapeamento de dados deve ter sido configurado e publicado primeiro na interface do Campaign Standard. Para obter mais informações, consulte estas seções:

* [Definição de mapeamento](../../developing/using/aep-mapping-definition.md)
* [Ativação de mapeamento](../../developing/using/aep-mapping-activation.md)

Depois que o mapeamento de dados é criado, você deve impedir que ele seja executado para que você possa acioná-lo das APIs sempre que desejar. Para fazer isso, siga estes passos:

1. No Campaign Standard, vá para o menu **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** > **[!UICONTROL Status of data export to platform]** .

1. Clique no mapeamento de dados com o duplo do mouse para abri-lo e clique no **[!UICONTROL Stop]** botão.

   ![](assets/aep_datamapping_stop.png)

1. Salve as alterações

A execução do mapeamento de dados agora está parada. Você pode usar as APIs de Campaign Standard para acioná-las manualmente.

## Iniciando a ingestão imediata do mapeamento de dados {#starting-immediate-ingestion}

A ingestão imediata de um mapeamento XDM no Adobe Experience Platform é acionada com uma operação de POST:

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest`

>[!NOTE]
>
>Para executar a chamada de API ingest POST, o usuário deve ter uma função de execução **de função** SQL, que pode ser fornecida por um administrador de Campaign Standard executando abaixo o Script JS:
>
>`var sqlRoleObj = REST.head.roleBase.sql.get();
REST.head.securityGroup.Administrators.roles.post(sqlRoleObj);`

A operação POST retorna informações relacionadas ao status da solicitação criada:

* Solicitação enviada com êxito para o Mapeamento XDM:

```
{
"requestId": <value>,
"info": "Ingestion request submitted successfully for the Mapping ID: <value>",
"status":"Success"
}
```

* Solicitação já em andamento para o Mapeamento XDM:

```
{
"requestId": <value>,
"info": "Ingestion request already in progress for the Mapping ID: <value>",
"status":"In Progress"
}
```

* A solicitação falhou porque o mapeamento XDM não foi publicado ou foi interrompido:

```
{
"info": "Unable to submit data ingestion request, XDM Mapping ID: <value> is not stopped",
"status": "Failed"
}
{
"info": "Unable to submit data ingestion request, XDM Mapping ID: <value> is not published",
"status": "Failed"
}
```

## Recuperando o status de uma solicitação de ingestão {#retrieving-status}

O status de uma solicitação de ingestão pode ser recuperado com uma operação de GET e a ID de solicitação desejada nos parâmetros:

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest
{"requestId"="<value>"}
```

>[!NOTE]
Informações detalhadas sobre o status da solicitação de mapeamento XDM e seus trabalhos relacionados estão disponíveis na interface do Campaign Standard, no **[!UICONTROL Status of data export to platform]** menu (consulte [Mapeamento da ativação](../../developing/using/aep-mapping-activation.md)).

A operação de GET retorna as informações abaixo:

* **batchId**: este campo é preenchido somente se ocorrer uma falha após a preparação e o upload do lote,
* **informações**: a ID de mapeamento XDM,
* **numRecords**: o número de registros que foram assimilados (apenas para o estado de sucesso),
* **status**: o status da solicitação de assimilação (success/failed/in progress)

As possíveis respostas para a operação de GET são:

* Solicitação de assimilação bem-sucedida:

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>. ",
   "numRecords": 15,
   "requestId": 3520,
   "status": "Success"
   }
   ```

* Falha na solicitação de assimilação com 0 registro ingerido:

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>. ACP-880056 Failed to fetch the record from the database.",
   "numRecords": 0,
   "requestId": 3520,
   "status": "Failed"
   }
   ```

* Falha na solicitação de assimilação, com alguns registros carregados em um lote:

   ```
   {
   "batchId": "<value>",
   "info": "Mapping Id: <value>. ACP-880096 Sync Job failed to upload. Please check the error in the Platform UI.",
   "numRecords": 0,
   "requestId": <value>,
   "status": "Failed"
   }
   ```

* Solicitação de assimilação abortada após a ingestão de alguns registros (isso pode ocorrer em cenários de falha):

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>. Ingestion request aborted due to some issue with data ingestion service. Please submit a new request",
   "numRecords": 0,
   "requestId": <value>,
   "status": "Aborted"
   }
   ```

* Solicitação de assimilação em andamento (quando a solicitação carregou os dados em um lote ou quando o lote está sendo preparado para a solicitação):

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>.",
   "numRecords": 0,
   "requestId": <value>,
   "status": "In Progress"
   }
   ```
