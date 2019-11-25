---
title: Gerenciamento de unidades geográficas
description: Saiba como gerenciar unidades geográficas com APIs.
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


# Gerenciamento de unidades geográficas {#managing-geographical-units}

>[!CAUTION]
>
>O recurso de unidade geográfica foi descontinuado com a versão 18.7 do Campaign Standard.
Como resultado, as novas instâncias do Campaign Standard, bem como as instâncias existentes sem unidades geográficas criadas, não podem ter esse recurso implementado a partir da versão 18.7.
For more on this, refer to the <a href="https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html">Deprecated features</a> page.

O endpoint **geoUnitBase** permite interagir com unidades Geográficas, permitindo, por exemplo, atualizar seus atributos ou atualizar a unidade de um perfil.

O campo Unidade **** geográfica é adicionado a um perfil ao estender o recurso do perfil. Como resultado, lembre-se sempre de usar o endpoint **profileAndServicesExt** para interagir com as unidades Geográficas. Para obter mais informações sobre a extensão de recursos do perfil, consulte a documentação da [Campanha](https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles).

## Recuperando a unidade geográfica de um perfil

1. Execute uma solicitação GET no perfil PKey para recuperar o URL **geoUnit** .
1. Execute uma solicitação GET no URL para recuperar mais detalhes sobre a unidade Geográfica.

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

Ele retorna o URL geoUnit do perfil.

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

Ele retorna detalhes sobre a unidade geográfica.

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

## Atualização da unidade geográfica de um perfil

1. Execute uma solicitação GET no recurso **geoUnitBase** para recuperar o PKey da unidade geográfica.
1. Execute uma solicitação PATCH no perfil PKey, com a unidade Geográfica PKey desejada na carga.

<br/>

***Solicitação de amostra***

Recuperar a lista de unidades geográficas.

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

Execute uma solicitação PATCH no perfil, com o PKey da unidade Geográfica desejada na carga.

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

## Atualização dos atributos de uma unidade geográfica

1. Execute uma solicitação GET no recurso **geoUnitBase** para recuperar o PKey da unidade geográfica.
1. Execute uma solicitação PATCH na unidade Geográfica, com os atributos a serem atualizados na carga.

<br/>

***Solicitação de amostra***

Recuperar a lista de unidades geográficas.

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

Execute uma solicitação PATCH na unidade Geográfica, com os atributos a serem atualizados na carga.

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
