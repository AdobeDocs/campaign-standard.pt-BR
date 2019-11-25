---
title: Gerenciamento de privacidade
description: Saiba mais sobre o gerenciamento de privacidade com APIs
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c0c0be79613f99a15676343d8ce10d335baf968a

---


# Gerenciamento de privacidade {#privacy-management}

As APIs do Campaign Standard fornecem recursos que permitem o processo automático de solicitações relacionadas a regulamentos de privacidade, como o RGPD e o CCPA.

As ações que você pode executar são as seguintes:

* Criar uma nova solicitação de privacidade,
* Monitorar uma solicitação de privacidade,
* Recuperar um arquivo de dados de privacidade,
* Gerencie o status de recusa do CCPA de um perfil.

O endpoint da API de privacidade é **/privacy/privacyTool**. A descrição do recurso PrivacyTool e os filtros associados estão disponíveis nos metadados do recurso. Consulte Mecanismo [de metadados](../../api/using/metadata-mechanism.md).

A opção de não participação CCPA é gerenciada usando o atributo de perfil **cpaOptOut** .

Para obter mais informações sobre o Adobe Campaign Standard e conformidade com a privacidade, consulte a documentação [](https://helpx.adobe.com/campaign/kb/acs-privacy.html)dedicada.

## Criação de uma solicitação de privacidade {#creating-a-privacy-request}

>[!CAUTION]
>
>A Integração do Serviço [Principal de](https://adobe.io/apis/cloudplatform/gdpr.html) Privacidade é o método que você deve usar para todas as solicitações de acesso e exclusão. A partir da versão 19.4, o uso da API de campanha e da interface para acessar e excluir solicitações está obsoleto. Para obter mais informações sobre os recursos obsoletos e removidos do Campaign Standard, consulte [esta página](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html).

As solicitações de privacidade são criadas usando uma solicitação **POST** .

Antes de criar solicitações, é necessário definir o namespace que será usado. Para obter mais informações, consulte a documentação [do Gerenciamento de](https://helpx.adobe.com/campaign/kb/acs-privacy.html#ManagingPrivacyRequests)privacidade.

A carga deve conter os seguintes parâmetros:

* **name**: um nome interno exclusivo
* **namespace**: o nome do namespace configurado na interface do Campaign Standard
* **validationValue**: o valor de reconciliação com base na chave de reconciliação definida no namespace
* **rótulo**: a etiqueta de solicitação
* **tipo**: o tipo de solicitação. Os valores aceitos são "access" ou "delete".
* **regulamento**: tipo de regulamento. Exemplo: "RGPD", "CCPA". Esse parâmetro é obrigatório e está disponível a partir da versão 19.4 do Campaign Standard. Se você estiver em uma versão mais antiga, não precisará adicioná-la à sua carga útil.

<br/>

***Solicitação de amostra***

Esta solicitação POST cria uma solicitação de privacidade com base em uma chave de reconciliação de email definida no namespace AMCDS2:

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8'

{
"name":"PT11832",
"namespaceName": "AMCDS2",
"reconciliationValue": "customers@adobe.com",
"regulation": "gdpr",
"label":"Delete customers",
"type":"delete"
}
```

Resposta à solicitação POST.

```
{
    "PKey": "<PKEY>",
    "audit": "",
    "created": "2018-03-21 10:41:58.570Z",
    "desc": "",
    "gdprRequestData": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/head/privacyTool/<PKEY>/gdprRequestData/"
    },
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool/<PKEY>",
    "label": "Delete customers",
    "lastModified": "2018-03-21 10:41:58.570Z",
    "name": "PT11832",
    "namespace": {
        "PKey": "<PKEY>",
        "title": "Doc (AMCDS2)"
    },
    "namespaceName": "AMCDS2",
    "reconciliationValue": "customers@adobe.com",
    "regulation": "gdpr",
    "retryCount": 0,
    "status": "new",
    "title": "Delete customers (PT11832)",
    "type": "delete"
}
```

## Monitorando uma solicitação de privacidade

Você pode monitorar informações sobre uma solicitação de privacidade criada usando uma solicitação **GET** .

A descrição da lista de status está disponível na documentação [do Gerenciamento de](https://helpx.adobe.com/campaign/kb/acs-privacy.html#ManagingPrivacyRequests)privacidade.

<br/>

***Solicitação de amostra***

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool \
-H 'Authorization: Bearer <ACCESS_TOKEN>'
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8'
```

Resposta à solicitação GET.

```
{
            "PKey": "<PKEY>",
            "audit": "",
            "created": "2018-03-09 12:28:37.319Z",
            "desc": "",
            "gdprRequestData": {
                "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool/<PKEY>/gdprRequestData/"
            },
            "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool/<PKEY>",
            "label": "Delete customer profile",
            "lastModified": "2018-03-09 12:39:21.232Z",
            "name": "GDPR6",
            "namespace": {
                "PKey": "<PKEY>",
                "title": "Email (defaultNamespace1)"
            },
            "namespaceName": "defaultNamespace1",
            "reconciliationValue": "customers@adobe.com",
            "regulation": "gdpr",
            "retryCount": 0,
            "status": "errorDataNotFound",
            "title": "Delete customer profile (GDPR6)",
            "type": "delete"
        }
```

## Recuperando um arquivo de dados de privacidade

>[!CAUTION]
>
>A Integração do Serviço [Principal de](https://adobe.io/apis/cloudplatform/gdpr.html) Privacidade é o método que você deve usar para todas as solicitações de acesso e exclusão. A partir da versão 19.4, o uso da API de campanha e da interface para acessar e excluir solicitações está obsoleto. Para obter mais informações sobre os recursos obsoletos e removidos do Campaign Standard, consulte [esta página](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html).

Para recuperar o arquivo que contém todas as informações associadas a um valor de reconciliação, siga este procedimento de três etapas:

1. Execute uma solicitação **POST** para criar uma nova solicitação com o atributo **type="access"**, consulte [Criação de uma nova solicitação](#creating-a-privacy-request)de privacidade.

1. Execute uma solicitação **GET** para recuperar informações sobre a solicitação.

1. Recupere o arquivo de dados executando uma solicitação **POST** no URL **privacyRequestData** retornado, com o nome interno da solicitação de privacidade dentro da carga. Por exemplo: {"name":"PT17"}.

<br/>

***Solicitação de amostra***

Crie uma solicitação de privacidade com o atributo type="access".

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8'

{
"name":"PT11832",
"namespaceName": "AMCDS2",
"reconciliationValue": "customers@adobe.com",
"regulation": "gdpr",
"label":"Delete customers",
"type":"access"
}
```

<!-- + réponse -->

Execute uma solicitação GET para recuperar informações sobre a solicitação.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8'
```

Ele retorna o atributo privacyRequestData com um URL associado.

```
{
    ...
    "name": "PR2",
    "namespace": ...,
    "namespaceName": "defaultNamespace1",
    "privacyRequestData": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool/<PKEY>/privacyRequestData/"
    },
    "reconciliationValue": "johndoe@mail.com",
    "regulation": "gdpr",
    "retryCount": 0,
    "status": "complete",
    "title": "EPR (PR2)",
    "type": "access"
    ...
},
```

Execute uma solicitação POST no URL privacyRequestData, com o nome interno da solicitação dentro da carga.

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool/<PKEY>/privacyRequestData \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8'
-d '{"name": "PR1"}'
```

Ele retorna o conteúdo do arquivo.

```
"{data:<gdprRequestData _cs=\" ()\" id=\"8565163\" reconciliationValue=\"'customer@adobe.com'\">\n  <table name=\"nms:recipient\">\n    <rowId='8569152'\n\t\tlastName='customer'\n\t\tfirstName='customer'\n\t\tgender='1'\n\t\temail='customer@adobe.com'\n\t\tcreatedBy-id='8565162'\n\t\tmodifiedBy-id='8565162'\n\t\tlastModified='2018-03-15 13:54:28.708Z'\n\t\tcreated='2018-03-15 13:54:28.708Z'\n\t\tthumbnail='/nl/img/thumbnails/defaultProfil.png'\n\t\temailFormat='2'</row>\n  </table>\n  <table name=\"nms:broadLogRcp\">\n    <row>deliveryLabel='Send via email'\n\t\tdeliveryType='0'\n\t\tcontactDate='2018-03-15 13:58:31.667Z'\n\t\tid='8003'\n\t\taddress='customer@adobe.com'\n\t\tstatus='1'\n\t\tmsg-id='1194'\n\t\teventDate='2018-03-15 13:58:34.726Z'\n\t\tlastModified='2018-03-15 13:59:02.008Z'\n\t\tvariant='default'\n\t\tdelivery-id='8569153'\n\t\tpublicId='1'\n\t\tprofile-id='8569152'</row>\n  </table>\n  <table name=\"nms:trackingLogRcp\">\n    <row>deliveryLabel='Send via email'\n\t\tdeliveryType='0'\n\t\tcontactDate='2018-03-15 13:58:31.667Z'\n\t\turlLabel='Open'\n\t\turlSource=''\n\t\tuserAgent='-1178080215'\n\t\ttrackedDevice='pc'\n\t\tid='5000'\n\t\tlogDate='2018-03-15 14:00:51.650Z'\n\t\tsourceType='html'\n\t\tuserAgent='-1178080215'\n\t\turl-id='1'\n\t\tdelivery-id='8569153'\n\t\tbroadLog-id='8003'\n\t\trecipient-id='8569152'</row>\n    <row>deliveryLabel='Send via email'\n\t\tdeliveryType='0'\n\t\tcontactDate='2018-03-15 13:58:31.667Z'\n\t\turlLabel='Open'\n\t\turlSource=''\n\t\tuserAgent='0'\n\t\ttrackedDevice=''\n\t\tid='6000'\n\t\tlogDate='2018-03-15 16:00:41.110Z'\n\t\tsourceType='html'\n\t\turl-id='1'\n\t\tdelivery-id='8569153'\n\t\tbroadLog-id='8003'\n\t\trecipient-id='8569152'</row>\n  </table>\n</gdprRequestData>}"
```

## Gerenciamento da recusa do CCPA

O status de recusa de CCPA de um perfil pode ser monitorado e gerenciado usando o atributo de perfil **cpaOptOut** e os valores "true" ou "false":

`"ccpaOptOut": <value>`

* **true**:  proíbe a venda de informações pessoais.
* **false**: autoriza a venda de informações pessoais.

>[!CAUTION]
>
>O atributo "CCPA Opt-Out" só está disponível a partir de 19.4. Para ambientes 19.3, é necessário estender o recurso Perfis e adicionar um campo booleano. Esse campo será adicionado à API com o rótulo escolhido. Sugerimos que você use "Recusar para CCPA".
>
>For more on this, refer to the [Privacy management documentation](https://helpx.adobe.com/campaign/kb/acs-privacy.html#ccpa).

<br/>

***Pedidos de amostra***

* Amostra de solicitação GET para recuperar o status de recusa de CCPA de um perfil.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profilesAndServices/profile/<PKEY> \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -H 'Content-Type: application/json;charset=utf-8'
   ```

   Resposta à solicitação GET.

   ```
   {
   "PKey": "<PKEY>",
     "ccpaOptOut": false,
     "firstName": "John",
     "lastName": "Doe",
   ...
   }
   ```

* Amostra de solicitação POST para marcar um perfil para cancelamento CCPA.

   ```
   -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profilesAndServices/profile/ \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -H 'Content-Type: application/json;charset=utf-8'
   -i
   -d {
   -d  "firstName": "John",
   -d  "lastName": "Doe",
   -d  "email": "jdoe@mail.com",
   -d  "ccpaOptOut": true
   -d }'
   ```

   Resposta à solicitação GET.

   ```
   {
       ...
       "email": "john.doe@mail.com",
       "firstName": "John",
       "lastName": "Doe",
       "ccpaOptOut": true,
       ...
   }
   ```

* Amostra de solicitação PATCH para atualizar um perfil para cancelamento CCPA.

   ```
   -X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profilesAndServices/profile/<PKEY> \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -H 'Content-Type: application/json;charset=utf-8'
   -i
   -d {
   -d  "ccpaOptOut": true
   -d }'
   ```

   Resposta à solicitação GET.

   ```
   {
       ...
       "email": "john.doe@mail.com",
       "firstName": "John",
       "lastName": "Doe",
       "ccpaOptOut": true,
       ...
   }
   ```
