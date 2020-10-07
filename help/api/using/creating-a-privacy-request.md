---
title: Criação de uma solicitação de acesso a dados pessoais
description: Saiba como criar uma solicitação de privacidade com APIs
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 16%

---


# Criação de uma solicitação de acesso a dados pessoais {#creating-a-privacy-request}

>[!CAUTION]
>
>The [Privacy Core Service](https://adobe.io/apis/cloudplatform/gdpr.html) Integration is the method you should use for all access and delete requests. A partir da versão 19.4, o uso da API e da interface do Campaign para solicitações de acesso e exclusão ficará obsoleto. Para obter mais informações sobre os recursos desaprovados e removidos do Campaign Standard, consulte [esta página](https://helpx.adobe.com/br/campaign/kb/acs-deprecated-and-removed-features.html).

As solicitações de privacidade são criadas usando uma solicitação de **POST** .

Antes de criar solicitações, é necessário definir a namespace que será usada. Para obter mais informações, consulte a documentação [do Gerenciamento de](https://helpx.adobe.com/br/campaign/kb/acs-privacy.html#ManagingPrivacyRequests)privacidade.

A carga deve conter os seguintes parâmetros:

* **name**: um nome interno exclusivo
* **namespace**: o nome da namespace configurado na interface do Campaign Standard
* **validationValue**: o valor de reconciliação com base na chave de reconciliação definida na namespace
* **rótulo**: a etiqueta de solicitação
* **tipo**: o tipo de solicitação. Os valores aceitos são &quot;access&quot; ou &quot;delete&quot;.
* **regulamento**: tipo de regulamento. Exemplo: &quot;RGPD&quot;, &quot;CCPA&quot;. Esse parâmetro é obrigatório e está disponível a partir da versão de Campaign Standard 19.4. Se você estiver em uma versão mais antiga, não precisará adicioná-la à sua carga útil.

<br/>

***Solicitação de amostra***

Esta solicitação de POST cria uma solicitação de privacidade com base em uma chave de reconciliação de email definida na namespace AMCDS2:

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

Resposta à solicitação de POST.

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
