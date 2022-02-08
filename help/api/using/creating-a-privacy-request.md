---
title: Criação de uma solicitação de privacidade
description: Saiba como criar uma solicitação de privacidade com APIs
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 06ad2e13-922b-4f35-8726-007427125c63
source-git-commit: e41667405b54a7ed0e02889e3002807e4bfd3a05
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 7%

---

# Criação de uma solicitação de privacidade {#creating-a-privacy-request}

>[!CAUTION]
>
>O [Serviço principal de privacidade](https://adobe.io/apis/cloudplatform/gdpr.html) A integração é o método que você deve usar para todas as solicitações de acesso e exclusão. <!--Starting 19.4, the use of the Campaign API and interface for access and delete requests is deprecated. For more on Campaign Standard deprecated and removed features, refer to [this page](../../rn/using/deprecated-features.md).-->

As solicitações de privacidade são criadas usando um **POST** solicitação.

Antes de criar solicitações, é necessário definir o namespace que será usado. Para obter mais informações, consulte [Documentação de gerenciamento de privacidade](../../start/using/privacy-requests.md).

A carga deve conter os seguintes parâmetros:

* **name**: um nome interno exclusivo
* **namespace**: o nome do namespace configurado na interface do Campaign Standard
* **reconciliationValue**: o valor de reconciliação com base na chave de reconciliação definida no namespace
* **label**: o rótulo da solicitação
* **type**: o tipo de solicitação. Os valores aceitos são &quot;acesso&quot; ou &quot;exclusão&quot;.
* **regulamento**: o tipo de regulamento. Exemplo: &quot;GDPR&quot;, &quot;CCPA&quot;. Esse parâmetro é obrigatório e está disponível a partir da versão do Campaign Standard 19.4. Se você estiver em uma build mais antiga, não precisará adicioná-la à carga útil.

<br/>

***Solicitação de exemplo***

Essa solicitação de POST cria uma solicitação de privacidade com base em uma chave de reconciliação de email definida no namespace AMCDS2:

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

Resposta à solicitação do POST.

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
