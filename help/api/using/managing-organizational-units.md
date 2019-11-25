---
title: Gerenciar unidades organizacionais
description: Saiba como gerenciar unidades organizacionais com APIs.
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
source-git-commit: c0c0be79613f99a15676343d8ce10d335baf968a

---


# Gerenciar unidades organizacionais {#managing-organizational-units}

O endpoint **orgUnitBase** permite interagir com unidades organizacionais, permitindo, por exemplo, atualizar seus atributos ou atualizar a unidade organizacional de um perfil. Para obter mais informações sobre unidades organizacionais no Campaign, consulte a documentação [da](https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html)Campanha.

O campo Unidade **** organizacional é adicionado a um perfil ao estender o recurso do perfil. Como resultado, lembre-se sempre de usar o endpoint **profileAndServicesExt** para interagir com as unidades Geográficas. Para obter mais informações sobre a extensão de recursos do perfil, consulte a documentação da [Campanha](https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles).

## Recuperando a unidade Organização de um perfil

1. Execute uma solicitação GET no perfil PKey para recuperar o URL **orgUnit** .
1. Execute uma solicitação GET no URL para recuperar mais detalhes sobre a unidade organizacional.

<br/>

***Solicitação de amostra***

Recupere o registro do perfil.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Ele retorna o URL orgUnit do perfil.

```
{
  ...
  "orgUnit": {
    "PKey": "<PKEY>",
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/<PKEY>",
    "title": "All (all)"
    },
  ...
}
```

Execute uma solicitação GET no URL para recuperar mais informações.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Ele retorna detalhes sobre a unidade organizacional.

```
{
  "PKey": "<PKEY>",
  "created": "2019-04-02 22:36:13.252Z",
  "desc": "",
  "label": "Brand 4",
  "lastModified": "2019-04-03 08:17:19.100Z",
  "name": "brand4",
  "parentTitle": "All (all)",
  "title": "Brand 4 (brand4)"
}
```

## Atualização da unidade organizacional de um perfil

1. Execute uma solicitação GET no recurso **orgUnitBase** para recuperar a unidade organizacional PKey
1. Execute uma solicitação PATCH na chave de perfil, com a unidade organizacional desejada PKey na carga.

<br/>

***Solicitação de amostra***

Recuperar a lista de unidades organizacionais.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/ \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Retorna todas as unidades organizacionais. Recupere o PKey da unidade à qual você deseja atribuir o perfil.

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

Execute uma solicitação PATCH no perfil, com o PKey da unidade organizacional desejada na carga.

```
-X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
-i
-d {
-d "orgUnit":{
-d    "PKey":"<PKEY>"
-d  }
-d }
```

<!-- + réponse -->

## Atualização de atributos de uma unidade organizacional

1. Execute uma solicitação GET no recurso **orgUnitBase** para recuperar a unidade organizacional PKey.
1. Execute uma solicitação PATCH na unidade organizacional, com os atributos a serem atualizados na carga.

<br/>

***Solicitação de amostra***

Recuperar a lista de unidades organizacionais.

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

Execute uma solicitação PATCH na unidade organizacional, com os atributos a serem atualizados na carga.

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
