---
title: Mecanismo de metadados
description: Saiba mais sobre o mecanismo de metadados.
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


# Mecanismo de metadados {#metadata-mechanism}

Você pode recuperar os metadados dos recursos usando **resourceType** em uma solicitação GET:

`GET /profileAndServices/resourceType/<resourceName>`

A resposta retorna os principais metadados do recurso (todos os outros campos são descritivos ou internos):

* O nó **Conteúdo** retorna os campos do recurso. Para cada campo no nó **content** , podemos encontrar os seguintes campos:

   * "apiName": nome do atributo usado nas APIs.
   * "Tipo": esta é a definição de tipo de alto nível (string, número, link, coleção, enumeração...).
   * "dataPolicy": o valor do campo deve seguir as regras de política fornecidas. Por exemplo, se a regra dataPolicy estiver definida como "email", o valor deverá ser um email válido. Durante um PATCH ou um POST, o dataPolicy pode verificar o valor ou modificar o valor a ser transformado (por exemplo, smartCase).
   * "categoria": fornece a categoria do campo no editor de consultas.
   * "resType": este é o tipo técnico.

      Se "type" for concluído com o valor "link" ou "collection", o valor resTarget será o nome do recurso direcionado pelo link.
Se "type" for concluído com o valor "enumeration", um campo "values" será adicionado e cada valor de enumeração será detalhado no nó de **valores** .

* O nó **Filtros** retorna o URL para recuperar os filtros associados. For more on filters, refer to [this section](../../api/using/filtering.md) section.

<!-- créer une section au même niveau sur les liens -->
<!-- dans l'exemple: birthdate, email +  mettre 2 liens : un de type 1-1 , 1-N
si on prend l'exemple de l'org unit, on aura un bon exemple lien -->
<!-- plus reparler du node Data -->

<br/>

***Solicitação de amostra***

Execute uma solicitação GET no recurso.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Ele retorna a descrição completa do recurso de perfil.

```
{
...
"content": {
  "email": {...},
    ...
    },
"data": "/profileAndServices/profile/",
"filters": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/<PKEY>"
    },
"help": "Identified profiles",
"href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/metadata",
"label": "Profiles",
"mandatory": false,
"name": "profile",
"pkgStatus": "never",
"readOnly": false,
"schema": "nms:recipient",
"type": "item"
}
```
