---
solution: Campaign Standard
product: campaign
title: Interação com o histórico de marketing
description: Saiba como interagir com o histórico de marketing dos perfis.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 10%

---


# Interação com o histórico de marketing {#interacting-with-marketing-history}

O endpoint **history** permite interagir com o histórico de marketing de um perfil.
Dessa forma, você pode, por exemplo, recuperar facilmente a mirror page de um delivery enviado a um perfil. Para fazer isso, siga as etapas abaixo:

1. Execute um GET com o endpoint **history** e a chave primária do perfil.
1. Execute uma solicitação de GET no href **events** retornado.
1. Retorna a lista de eventos do perfil com links para mirror pages no nó **mirrorPage**.

<br/>

***Solicitação de exemplo***

Recupere o histórico de marketing do perfil com uma solicitação do GET.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/"<PKEY>" \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

O nó &quot;events&quot; retorna o URL que dá acesso aos eventos no perfil.

```
{
  "PKey": "<PKEY>",
  "firstName": "John",
  "lastName":"Doe",
  "birthDate": "1980-10-24",
  "events": {
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/<PKEY>/events/",
    "metadata": "subHisto"
    },
}
```

Execute uma solicitação de GET na href de eventos retornada.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/<PKEY>/events \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Retorna a lista de eventos do perfil com links para mirror pages no nó &quot;mirrorPage&quot;.

```
    {
      "PKey": "<PKEY>",
      "category": "email",
      "date": "2018-05-17 08:44:49.366Z",
      "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/<PKEY>/events/<PKEY>",
      "label": "Send via email",
      "mirrorPage": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/<PKEY>/events/<PKEY>/mirrorPage/"
      },
      "type": "outbound"
    }
```
