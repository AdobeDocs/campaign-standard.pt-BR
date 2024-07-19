---
title: Atualização dos atributos de uma unidade geográfica
description: Saiba como atualizar atributos de uma unidade geográfica com APIs
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 86810821-6f62-46ab-ba0b-2175797fe9dd
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 0%

---

# Atualização dos atributos de uma unidade geográfica {#managing-geographical-units}

1. Execute uma solicitação GET no recurso **geoUnitBase** para recuperar a PKey da unidade geográfica.
1. Execute uma solicitação PATCH na unidade geográfica, com os atributos a serem atualizados na carga.

<br/>

***Solicitação de exemplo***

Recuperar a lista de Unidades geográficas.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/geoUnitBase/ \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Retorna todas as unidades geográficas. Recupere a PKey da unidade desejada.

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

Execute uma solicitação PATCH na unidade geográfica, com os atributos a serem atualizados na carga.

```
-X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
-i
-d {
-d "label":"Asia",
-d "name":"asia"
-d }
```

<!-- + réponse -->
