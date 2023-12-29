---
title: Interação com o histórico de marketing
description: Saiba como interagir com o histórico de marketing dos perfis
feature: API
role: Data Engineer
level: Experienced
exl-id: 67282d21-b4ed-4af5-b751-848a6d705118
source-git-commit: 64f24fb692754973331b4fb2f7b95e9a6f31cd0d
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 4%

---

# Interação com o histórico de marketing{#interacting-with-marketing-history}

A variável **histórico** permite interagir com o histórico de marketing de um perfil.
Dessa forma, você pode, por exemplo, recuperar facilmente a mirror page de um delivery que foi enviado a um perfil. Para fazer isso, siga as etapas abaixo:

1. Execute uma GET com o **histórico** e a chave primária do perfil.
1. Execute uma solicitação GET no **events** href retornado.
1. Ele retorna a lista de eventos do perfil com links para mirror pages na **mirrorPage** nó.

<br/>

***Exemplo de solicitação***

Recupere o histórico de marketing do perfil com uma solicitação GET.

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

Execute uma solicitação GET no href de eventos retornado.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/<PKEY>/events \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Ele retorna a lista de eventos do perfil com links para mirror pages no nó &quot;mirrorPage&quot;.

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
