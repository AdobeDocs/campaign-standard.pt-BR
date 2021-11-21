---
title: Recuperação de subscrições
description: Saiba como recuperar assinaturas com APIs.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 6d935074-3196-45c5-97cd-ccb7c80bbba8
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 2%

---

# Recuperação de subscrições {#retrieving-subscriptions}

## Recuperação de perfis que assinaram um serviço

Este é um procedimento em duas etapas.

1. Recupere o URL de assinaturas do serviço desejado.
1. Execute uma solicitação GET no URL de assinaturas. Retorna a lista de subscrições do serviço, com cada perfil associado.

>[!CAUTION]
>
>A API REST retorna a propriedade &quot;href&quot;, que contém o URL a ser usado. <b>Sempre use o URL contido na resposta para fazer a solicitação de API subsequente</b>.

<br/>

***Solicitação de exemplo***

Execute uma solicitação GET para recuperar o serviço.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Retorna o URL de subscrições do serviço.

```
  {
    ...
    "messageType": "email",
    "name": "SVC1",
    "subscriptions": {
                "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>/subscriptions/"
    },
    ...
  },
```

Execute uma solicitação GET no URL de assinaturas.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>/subscriptions \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

A lista de assinaturas do serviço é exibida, com cada perfil associado.

```
  {
    ...
    "service": ...,
    "serviceName": "SVC3",
    "subscriber": {
        "PKey": "<PKEY>",
        "email": "",
        "firstName": "John",
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>",
        "lastName": "Doe",
    },
  }
```

## Recuperação dos serviços aos quais um perfil se inscreveu

Este é um procedimento em duas etapas.

1. Recupere o URL de assinaturas de um determinado perfil.
1. Execute uma solicitação GET no URL. Retorna a lista de assinaturas do perfil, com cada serviço associado.

<br/>

***Solicitação de exemplo***

Execute uma solicitação do GET para recuperar o perfil.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Retorna o URL de assinaturas do perfil.

```
  {
    ...
    "postalAddress":...,
    "preferredLanguage": "none",
    "subscriptions": {
      "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>/subscriptions/"
    },
    ...
  }
```

Execute uma solicitação GET no URL de assinaturas.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>/subscriptions \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Retorna a lista de serviços aos quais o perfil se inscreveu.

```
  {
    ...
    "PKey": "<PKEY>",
    "created": "2017-03-03 10:54:00.363Z",
    "service": {
      "PKey": "<PKEY>",
      "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>",
      "label": "Sport Newsletter",
      "name": "SVC1",
      "title": "Sport Newsletter (SVC1)"
    },
    ...
  }
```
