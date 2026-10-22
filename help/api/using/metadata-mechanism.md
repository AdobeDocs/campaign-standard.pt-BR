---
title: Mecanismo de metadados
description: Saiba mais sobre o mecanismo de metadados.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 58ec0999-b28a-4198-8d57-729b074c6a6d
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
    internal-label: APIs
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '228'
ht-degree: 1%
---
# Mecanismo de metadados {#metadata-mechanism}

Você pode recuperar os metadados dos recursos usando **resourceType** em uma solicitação GET:

`GET /profileAndServices/resourceType/<resourceName>`

A resposta retorna os principais metadados do recurso (todos os outros campos são descritivos ou internos):

* O nó **Content** retorna os campos do recurso. Para cada campo no nó **content**, podemos encontrar os seguintes campos:

  * &quot;apiName&quot;: nome do atributo usado nas APIs.
  * &quot;type&quot;: esta é a definição de tipo de alto nível (sequência, número, link, coleção, enumeração...).
  * &quot;dataPolicy&quot;: o valor do campo deve seguir as regras de política fornecidas. Por exemplo, se a regra dataPolicy estiver definida como &quot;email&quot;, o valor deverá ser um email válido. Durante uma PATCH ou POST, a dataPolicy pode verificar o valor ou modificar o valor para transformar (smartCase, por exemplo).
  * &quot;category&quot;: fornece a categoria do campo no editor de consultas.
  * &quot;resType&quot;: é o tipo técnico.

    Se &quot;type&quot; for concluído com o valor &quot;link&quot; ou &quot;collection&quot;, o valor resTarget será o nome do recurso direcionado pelo link.
    Se &quot;type&quot; for concluído com o valor &quot;enumeration&quot;, um campo &quot;values&quot; será adicionado e cada valor de enumeração será detalhado no nó **values**.

* O nó **Filtros** retorna a URL para recuperar os filtros associados. Para obter mais informações sobre filtros, consulte [esta seção](../../api/using/filtering.md).

<!-- créer une section au même niveau sur les liens -->
<!--
dans l'exemple: birthdate, email +  mettre 2 liens : un de type 1-1 , 1-N
si on prend l'exemple de l'org unit, on aura un bon exemple lien
-->
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
