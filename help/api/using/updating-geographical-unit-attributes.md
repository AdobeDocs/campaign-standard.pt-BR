---
solution: Campaign Standard
product: campaign
title: Atualização dos atributos de uma unidade geográfica
description: Saiba como atualizar os atributos de uma unidade geográfica com as APIs
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 11%

---


# Atualização dos atributos de uma unidade geográfica {#managing-geographical-units}

1. Execute uma solicitação de GET no recurso **geoUnitBase** para recuperar o PKey da unidade geográfica.
1. Execute uma solicitação de PATCH na unidade Geográfica, com os atributos a serem atualizados na carga.

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

Retorna todas as unidades Geográficas. Recupere o PKey da unidade desejada.

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

Execute uma solicitação de PATCH na unidade Geográfica, com os atributos a serem atualizados na carga.

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
