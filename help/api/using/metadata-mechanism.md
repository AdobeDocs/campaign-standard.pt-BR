---
title: Mecanismo de metadados
description: Saiba mais sobre o mecanismo de metadados.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 58ec0999-b28a-4198-8d57-729b074c6a6d
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 1%

---

# Mecanismo de metadados {#metadata-mechanism}

Você pode recuperar os metadados dos recursos usando **resourceType** em uma solicitação GET:

`GET /profileAndServices/resourceType/<resourceName>`

A resposta retorna os metadados principais do recurso (todos os outros campos são descritivos ou internos):

* O **Conteúdo** retorna os campos do recurso. Para cada campo no **conteúdo** , podemos encontrar os seguintes campos:

   * &quot;apiName&quot;: nome do atributo usado nas APIs.
   * &quot;type&quot;: essa é a definição do tipo de alto nível (cadeia de caracteres, número, link, coleção, enumeração...).
   * &quot;dataPolicy&quot;: o valor do campo deve seguir as regras de política fornecidas. Por exemplo, se a regra dataPolicy estiver definida como &quot;email&quot;, o valor deverá ser um email válido. Durante um PATCH ou POST, o dataPolicy pode verificar o valor ou modificar o valor a ser transformado (por exemplo, smartCase).
   * &quot;categoria&quot;: fornece a categoria do campo no editor de consultas.
   * &quot;resType&quot;: esse é o tipo técnico.

      Se &quot;type&quot; for concluído com o valor &quot;link&quot; ou &quot;collection&quot;, o valor resTarget será o nome do recurso direcionado pelo link.
Se &quot;type&quot; for concluído com o valor &quot;enumeration&quot;, um campo &quot;values&quot; será adicionado e cada valor de enumeração será detalhado na variável **values** nó .

* O **Filtros** retorna o URL para recuperar os filtros associados. Para obter mais informações sobre filtros, consulte [esta seção](../../api/using/filtering.md) seção.

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
