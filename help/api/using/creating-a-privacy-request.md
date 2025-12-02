---
title: Criação de uma solicitação de privacidade
description: Saiba como criar uma solicitação de privacidade com APIs
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 06ad2e13-922b-4f35-8726-007427125c63
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 4%

---

# Criação de uma solicitação de privacidade {#creating-a-privacy-request}

>[!CAUTION]
>
>A Integração do [Privacy Core Service](https://developer.adobe.com/experience-platform-apis/references/privacy-service) é o método que deve ser usado para todas as solicitações de acesso e exclusão. <!--Starting 19.4, the use of the Campaign API and interface for access and delete requests is deprecated. For more on Campaign Standard deprecated and removed features, refer to [this page](../../rn/using/deprecated-features.md).-->

As solicitações de privacidade são criadas usando uma solicitação **POST**.

Antes de criar solicitações, é necessário definir o namespace que você usará. Para obter mais informações, consulte a [Documentação sobre o gerenciamento de privacidade](../../start/using/privacy-requests.md).

A carga deve conter os seguintes parâmetros:

* **nome**: um nome interno exclusivo
* **namespace**: o nome do namespace configurado na interface do Campaign Standard
* **reconciliationValue**: o valor de reconciliação com base na chave de reconciliação definida no namespace
* **rótulo**: o rótulo da solicitação
* **tipo**: o tipo de solicitação. Os valores aceitos são &quot;access&quot; ou &quot;delete&quot;.
* **regulation**: o tipo de regulamento. Exemplo: &quot;GDPR&quot;, &quot;CCPA&quot;. Esse parâmetro é obrigatório e está disponível a partir da versão 19.4 do Campaign Standard. Se você estiver em uma build mais antiga, não será necessário adicioná-la à sua carga.

<br/>

***Solicitação de exemplo***

Essa solicitação POST cria uma solicitação de privacidade com base em uma chave de reconciliação de email definida no namespace AMCDS2:

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
