---
solution: Campaign Standard
product: campaign
title: Recuperação de assinaturas
description: Saiba como recuperar subscrições com APIs.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 2%

---


# Recuperação de assinaturas {#retrieving-subscriptions}

## Recuperando os perfis que se inscreveram em um serviço

Este é um procedimento de duas etapas.

1. Recupere o URL do subscrição para o serviço desejado.
1. Execute uma solicitação de GET no URL do subscrição. Ele retorna a lista do subscrição para o serviço, com cada perfil associado.

>[!CAUTION]
>
>A REST API retorna a propriedade &quot;href&quot;, que contém o URL a ser usado. <b>Sempre use o URL contido na resposta para fazer a solicitação</b> de API subsequente.

<br/>

***Solicitação de amostra***

Execute uma solicitação de GET para recuperar o serviço.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Ele retorna o URL do subscrição para o serviço.

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

Execute uma solicitação de GET no URL do subscrição.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>/subscriptions \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

A lista das subscrições para o serviço é exibida, com cada perfil associado.

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

## Recuperando os serviços aos quais um perfil se inscreveu

Este é um procedimento de duas etapas.

1. Recupere o URL do subscrição para um determinado perfil.
1. Execute uma solicitação de GET no URL. Ele retorna a lista do subscrição para o perfil, com cada serviço associado.

<br/>

***Solicitação de amostra***

Execute uma solicitação de GET para recuperar o perfil.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Ele retorna o URL do subscrição para o perfil.

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

Execute uma solicitação de GET no URL do subscrição.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>/subscriptions \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Ele retorna a lista de serviços aos quais o perfil se inscreveu.

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
