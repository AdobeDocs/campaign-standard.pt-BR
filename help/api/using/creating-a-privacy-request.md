---
title: Criação de uma solicitação de privacidade
description: Saiba como criar uma solicitação de privacidade com APIs
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
source-git-commit: aee0e0437cbfe578cb2f715a2433099c79dd1748

---


# Criação de uma solicitação de privacidade {#creating-a-privacy-request}

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
