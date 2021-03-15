---
solution: Campaign Standard
product: campaign
title: Mecanismo de metadados
description: Saiba mais sobre o mecanismo de metadados.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Engenheiro de dados
level: Experienciado
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 2%

---


# Mecanismo de metadados {#metadata-mechanism}

Você pode recuperar os metadados de recursos usando **resourceType** em uma solicitação de GET:

`GET /profileAndServices/resourceType/<resourceName>`

A resposta retorna os metadados principais do recurso (todos os outros campos são descritivos ou internos):

* O nó **Content** retorna os campos do recurso. Para cada campo no nó **content**, podemos encontrar os seguintes campos:

   * &quot;apiName&quot;: nome do atributo usado nas APIs.
   * &quot;type&quot;: essa é a definição do tipo de alto nível (cadeia de caracteres, número, link, coleção, enumeração...).
   * &quot;dataPolicy&quot;: o valor do campo deve seguir as regras de política fornecidas. Por exemplo, se a regra dataPolicy estiver definida como &quot;email&quot;, o valor deverá ser um email válido. Durante um PATCH ou POST, o dataPolicy pode verificar o valor ou modificar o valor a ser transformado (por exemplo, smartCase).
   * &quot;categoria&quot;: fornece a categoria do campo no editor de consultas.
   * &quot;resType&quot;: esse é o tipo técnico.

      Se &quot;type&quot; for concluído com o valor &quot;link&quot; ou &quot;collection&quot;, o valor resTarget será o nome do recurso direcionado pelo link.
Se &quot;type&quot; for concluído com o valor &quot;enumeration&quot;, um campo &quot;values&quot; será adicionado e cada valor de enumeração será detalhado no nó **values**.

* O nó **Filters** retorna o URL para recuperar os filtros associados. Para obter mais informações sobre filtros, consulte [esta seção](../../api/using/filtering.md).

<!-- créer une section au même niveau sur les liens -->
<!-- dans l'exemple: birthdate, email +  mettre 2 liens : un de type 1-1 , 1-N
si on prend l'exemple de l'org unit, on aura un bon exemple lien -->
<!-- plus reparler du node Data -->

<br/>

***Solicitação de exemplo***

Execute uma solicitação GET no recurso.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Retorna a descrição completa do recurso de perfil.

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
