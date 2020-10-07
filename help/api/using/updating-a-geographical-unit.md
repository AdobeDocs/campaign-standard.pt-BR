---
title: Atualização da unidade geográfica de um perfil
description: Saiba como gerenciar unidades geográficas com APIs.
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '94'
ht-degree: 10%

---


# Atualização da unidade geográfica de um perfil {#updating-a-geographical-unit}

1. Execute uma solicitação de GET no recurso **geoUnitBase** para recuperar o PKey da unidade geográfica.
1. Execute uma solicitação de PATCH na chave do perfil, com a unidade Geográfica PKey desejada na carga.

<br/>

***Solicitação de amostra***

Recuperar a lista das unidades geográficas.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/geoUnitBase/ \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Retorna todas as unidades Geográficas. Recupere o PKey da unidade à qual você deseja atribuir o perfil.

```
{
 "PKey": "<PKEY>",
 "created": "2019-04-06 22:36:19.089Z",
 "desc": "",
 "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/geoUnitBase/<PKEY>",
 "label": "Europe",
 "lastModified": "2019-04-06 22:36:19.086Z",
 "name": "eu",
 "parentTitle": "All (all)",
 "title": "Europe (eu)"
},
```

Execute uma solicitação de PATCH no perfil, com o PKey da unidade Geográfica desejada na carga.

```
-X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
-i
-d {
-d "geoUnit":{
-d    "PKey":"<PKEY>"
-d  }
-d }
```

<!-- + réponse -->
