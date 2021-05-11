---
solution: Campaign Standard
product: campaign
title: Acionando a assimilação de dados por meio de APIs
description: Saiba como acionar a assimilação de dados por meio de APIs.
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Integração do Microsoft CRM
role: Data Architect
level: Experienced
exl-id: d67a796a-0730-4502-802c-d0b3583dd1dc
translation-type: tm+mt
source-git-commit: a4e1edc23cf750e44026f388f7b0fff3a80ec663
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 5%

---

# Acionando a assimilação de dados por meio de APIs {#triggering-data-ingestion-apis}

>[!IMPORTANT]
>
>No momento, o Adobe Experience Platform Data Connector está em beta, o que pode estar sujeito a atualizações frequentes sem aviso prévio. Os clientes precisam ser hospedados no Azure (atualmente em beta somente para a América do Norte) para acessar esses recursos. Entre em contato com o Atendimento ao cliente do Adobe se desejar acesso.

O Adobe Campaign Standard permite acionar a assimilação imediata de mapeamentos de dados por meio de APIs e recuperar o status das solicitações de assimilação.

Esta página descreve como acionar e recuperar o status de assimilação de seus mapeamentos de dados. Para obter informações globais sobre APIs do Campaign Standard, consulte [esta seção](../../api/using/get-started-apis.md).

## Pré-requisitos {#prerequisites}

Antes de usar as APIs, o mapeamento de dados deve ter sido configurado e publicado primeiro na interface do Campaign Standard. Para obter mais informações, consulte estas seções:

* [Definição de mapeamento](../../integrating/using/aep-mapping-definition.md)
* [Ativação de mapeamento](../../integrating/using/aep-mapping-activation.md)

Depois que o mapeamento de dados for criado, é necessário impedi-lo de ser executado para que possa acioná-lo a partir das APIs sempre que desejar. Para fazer isso, siga estes passos:

1. No Campaign Standard, vá para o menu **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** > **[!UICONTROL Status of data export to platform]**.

1. Clique duas vezes no mapeamento de dados para abri-lo, depois clique no botão **[!UICONTROL Stop]**.

   ![](assets/aep_datamapping_stop.png)

1. Salve as alterações

A execução do mapeamento de dados agora está interrompida. Você pode usar as APIs do Campaign Standard para acioná-las manualmente.

## Iniciando a assimilação imediata de mapeamento de dados {#starting-immediate-ingestion}

A assimilação imediata de um mapeamento XDM no Adobe Experience Platform é acionada com uma operação de POST:

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest`

>[!NOTE]
>
>Para executar a chamada de assimilar POST API, o usuário deve ter uma função **SQL function execution**, que pode ser fornecida por um administrador do Campaign Standard executando abaixo o Script JS:
>
>
```
>var sqlRoleObj = REST.head.roleBase.sql.get();
>REST.head.securityGroup.Administrators.roles.post(sqlRoleObj);
>```

A operação POST retorna informações sobre o status da solicitação criada:

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

* A solicitação falhou porque o mapeamento XDM não foi publicado ou está parado:

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

## Recuperar o status de uma solicitação de assimilação {#retrieving-status}

O status de uma solicitação de assimilação pode ser recuperado com uma operação GET e a ID de solicitação desejada nos parâmetros:

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest
{"requestId"="<value>"}
```

>[!NOTE]
>
>Informações detalhadas sobre o status da solicitação de mapeamento XDM e suas tarefas relacionadas estão disponíveis na interface do Campaign Standard, no menu **[!UICONTROL Status of data export to platform]** (consulte [Ativação de mapeamento](../../integrating/using/aep-mapping-activation.md)).

A operação GET retorna as informações abaixo:

* **batchId**: este campo é preenchido somente se ocorrer uma falha após a preparação e o upload do lote,
* **informações**: a ID de mapeamento XDM,
* **numRecords**: o número de registros que foram assimilados (somente status de sucesso),
* **status**: o status da solicitação de assimilação (sucesso/falha/em andamento)

As possíveis respostas para a operação do GET são:

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

* Falha na solicitação de assimilação com registro 0 assimilado:

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

* Solicitação de assimilação abortada após a assimilação de alguns registros (isso pode ocorrer em cenários de falha):

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
