---
title: Recuperação da unidade geográfica de um perfil
description: Saiba como recuperar a unidade geográfica de um perfil com APIs.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 313dbb7f-9cf7-43d4-ab6d-f496b04d92b8
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '80'
ht-degree: 12%

---

# Recuperação da unidade geográfica de um perfil {#retrieving-geographical-unit}

1. Execute uma solicitação GET na PKey do perfil para recuperar a URL **geoUnit**.
1. Execute uma solicitação GET no URL para recuperar mais detalhes sobre a unidade geográfica.

<br/>

***Solicitação de exemplo***

Recupere o registro do perfil.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Retorna o URL da geoUnit do perfil.

```
{
  ...
  "geoUnit": {
    "PKey": "@zYV4vIjP1wpBebml6s71hjGiDhs4_gHgbC_UhuJFk8h7XTZxZ5QnZrPnQPEfB__TxwR2ge6sz61D8RR4zvD75CLDZtc<PKEY>",
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/<PKEY>",
    "title": "All (all)"
    },
  ...
}
```

Execute uma solicitação GET no URL para recuperar mais informações.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/geoUnitBase/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Retorna detalhes sobre a unidade geográfica.

```
{
  "PKey": "<PKEY>",
  "created": "2019-04-02 22:36:13.252Z",
  "desc": "Default geographical entity (accessible to everyone)",
  "label": "All",
  "lastModified": "2019-04-03 08:17:19.100Z",
  "name": "all",
  "parentTitle": "",
  "title": "All (all)"
}
```
