---
solution: Campaign Standard
product: campaign
title: Atualização dos atributos de uma unidade organizacional
description: Saiba como atualizar os atributos de uma unidade organizacional
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '84'
ht-degree: 11%

---


# Atualização dos atributos de uma unidade organizacional {#updating-organizational-unit-attributes}

1. Execute uma solicitação de GET no recurso **orgUnitBase** para recuperar a unidade organizacional PKey.
1. Execute uma solicitação de PATCH na unidade organizacional, com os atributos a serem atualizados na carga.

<br/>

***Solicitação de amostra***

Recupere a lista das unidades organizacionais.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/ \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Retorna todas as unidades organizacionais. Recupere o PKey da unidade desejada.

```
{
  "PKey": "<PKEY>",
  "created": "2019-04-02 22:36:13.252Z",
  "desc": "",
  "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/<PKEY>",
  "label": "Brand 4",
  "lastModified": "2019-04-03 07:34:56.579Z",
  "name": "brand4",
  "parentTitle": "All (all)",
  "title": "Brand 4 (brand1)"
},
```

Execute uma solicitação de PATCH na unidade organizacional, com os atributos a serem atualizados na carga.

```
-X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
-i
-d {
-d "label":"brand1",
-d "name":"brand1"
-d }
```

<!-- + réponse -->
