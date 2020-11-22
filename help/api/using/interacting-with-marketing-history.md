---
solution: Campaign Standard
product: campaign
title: Interação com o histórico de marketing
description: Saiba como interagir com os históricos de marketing.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 10%

---


# Interação com o histórico de marketing {#interacting-with-marketing-history}

O endpoint de **histórico** permite que você interaja com um histórico de marketing.
Dessa forma, você pode, por exemplo, recuperar facilmente o mirror page de um delivery que foi enviado para um perfil. Para fazer isso, siga as etapas abaixo:

1. Execute um GET com o endpoint do **histórico** e a chave primária do perfil.
1. Execute uma solicitação de GET nos **eventos** que href retornou.
1. Ele retorna a lista de eventos para o perfil com links para mirrores page no nó **mirrorPage** .

<br/>

***Solicitação de amostra***

Recupere o histórico de marketing com uma solicitação de GET.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/"<PKEY>" \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

O nó &quot;eventos&quot; retorna o URL que dá acesso aos eventos do perfil.

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

Execute uma solicitação de GET nos eventos que href retornou.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/<PKEY>/events \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Ele retorna a lista de eventos para o perfil com links para mirrores page no nó &quot;mirrorPage&quot;.

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
