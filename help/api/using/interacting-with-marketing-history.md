---
title: Interação com o histórico de marketing
description: Saiba como interagir com o histórico de marketing dos perfis
feature: API
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 67282d21-b4ed-4af5-b751-848a6d705118
TQID: https://experienceleague.adobe.com/C5r-qK6kpvssv6eFdJNuOw61OXFapg8L8hrlxyb0vcA
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: b12f6872-9271-4369-85e5-86969a0b99a2
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dcid: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 147
ht-degree: 4%

---

# Interação com o histórico de marketing{#interacting-with-marketing-history}

O ponto de extremidade **histórico** permite que você interaja com o histórico de marketing de um perfil.
Dessa forma, você pode, por exemplo, recuperar facilmente a mirror page de um delivery que foi enviado a um perfil. Para fazer isso, siga as etapas abaixo:

1. Execute uma GET com o ponto de extremidade **histórico** e a chave primária do perfil.
1. Execute uma solicitação GET no href **events** retornado.
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
