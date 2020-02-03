---
title: Interação com o histórico de marketing
description: Saiba como interagir com o histórico de marketing dos perfis.
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
source-git-commit: e60ec7790da46d234b66baf4c3db23815056b9fb

---


# Interação com o histórico de marketing {#interacting-with-marketing-history}

O endpoint de **histórico** permite interagir com o histórico de marketing de um perfil.
Dessa forma, você pode, por exemplo, recuperar facilmente a página espelhada para uma entrega enviada para um perfil. Para fazer isso, siga as etapas abaixo:

1. Execute um GET com o terminal do **histórico** e a chave primária do perfil.
1. Execute uma solicitação GET nos **eventos** href retornados.
1. Ele retorna a lista de eventos do perfil com links para páginas espelhadas no nó **mirrorPage** .

<br/>

***Solicitação de amostra ***

Recupere o histórico de marketing do perfil com uma solicitação GET.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/"<PKEY>" \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

O nó &quot;events&quot; retorna o URL que fornece acesso aos eventos no perfil.

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

Execute uma solicitação GET nos eventos que href retornou.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/<PKEY>/events \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Ele retorna a lista de eventos do perfil com links para páginas espelhadas no nó &quot;mirrorPage&quot;.

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
