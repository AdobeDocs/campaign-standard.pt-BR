---
title: Acionando a ingestão de dados por meio de APIs
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
source-git-commit: 57b87896281efa7dd1e6a612926f59061a0fdcb8

---


# Acionando a ingestão de dados por meio de APIs {#triggering-data-ingestion-apis}

>[!IMPORTANT]
>
>O Adobe Experience Platform Data Connector está atualmente em beta, que pode estar sujeito a atualizações frequentes sem aviso prévio. Os clientes precisam estar hospedados no Azure (atualmente em beta somente para a América do Norte) para acessar esses recursos. Entre em contato com o Atendimento ao cliente da Adobe se desejar acessar.

Adobe Campaign Standard allows you to trigger the immediate ingestion of data mappings via APIs, and retrieve the status of your ingestion requests.

This page describes how to trigger and retrieve the ingestion status of your data mappings. For global information on Campaign Standard APIs, refer to [this section](../../api/using/about-campaign-standard-apis.md).

## Pré-requisitos {#prerequisites}

Before using the APIs, the data mapping must first have been configured and published within Campaign Standard interface. Para obter mais informações, consulte estas seções:

* [Definição de mapeamento](../../administration/using/aep-mapping-definition.md)
* [Ativação de mapeamento](../../administration/using/aep-mapping-activation.md)

Depois que o mapeamento de dados é criado, você deve impedir que ele seja executado para que você possa acioná-lo das APIs sempre que desejar. Para fazer isso, siga estas etapas:

1. In Campaign Standard, go to the **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** > **[!UICONTROL Status of data export to platform]** menu.

1. Double-click the data mapping to open it, then click the **[!UICONTROL Stop]** button.

   ![](assets/aep_datamapping_stop.png)

1. Salve as alterações

A execução do mapeamento de dados agora está parada. You can use Campaign Standard APIs to trigger it manually.

## Iniciando a ingestão imediata do mapeamento de dados {#starting-immediate-ingestion}

A ingestão imediata de um mapeamento XDM na Adobe Experience Platform é acionada com uma operação POST:

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest`

>[!NOTE]
>
>Para executar a chamada de API de assimilação POST, o usuário deve ter uma função de execução **de função** SQL, que pode ser fornecida por um administrador de Campaign Standard executando abaixo o Script JS:
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

* Request already in progress for the XDM Mapping:

```
{
"requestId": <value>,
"info": "Ingestion request already in progress for the Mapping ID: <value>",
"status":"In Progress"
}
```

* Request failed because the XDM mapping is not published or is stopped:

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

## Retrieving the status of an ingestion request {#retrieving-status}

The status of an ingestion request can be retrieved with a GET operation and the desired request ID in the parameters:

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest
{"requestId"="<value>"}
```

>[!NOTE]
Detailed information about the XDM mapping request status and its related jobs is available in Campaign Standard interface, in the **!UICONTROL [Status of data export to platform ]**menu (see[Mapping activation](../../administration/using/aep-mapping-activation.md)).

A operação GET retorna as informações abaixo:

* **batchId**: este campo é preenchido somente se ocorrer uma falha após a preparação e o upload do lote,
* **informações**: a ID de mapeamento XDM,
* **numRecords**: o número de registros que foram assimilados (apenas para o estado de sucesso),
* **status**: o status da solicitação de assimilação (success/failed/in progress)

As possíveis respostas à operação GET são:

* Ingest request successfull:

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>. ",
   "numRecords": 15,
   "requestId": 3520,
   "status": "Success"
   }
   ````

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

   ````
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
