---
title: Gerenciamento de recusa do CCPA
description: Saiba como gerenciar o cancelamento da CCPA com APIs
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
old-role: Data Architect
role: Developer
level: Experienced
exl-id: bfc52511-f66f-4948-a939-d0d77e8ef03c
TQID: https://experienceleague.adobe.com/XcgCy73XQYn-JyB0N41X3n30nGGo1tHVzmn-UQ1TOJQ
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: b12f6872-9271-4369-85e5-86969a0b99a2
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 103
ht-degree: 7%

---

# Gerenciamento de recusa do CCPA {#managing-ccpa-optout}

O status de recusa do CCPA de um perfil pode ser monitorado e gerenciado usando o atributo de perfil **ccpaOptOut** e os valores &quot;true&quot; ou &quot;false&quot;:

`"ccpaOptOut": <value>`

* **true**: proíbe a venda de informações pessoais.
* **false**: autoriza a venda de informações pessoais.

<!--
The “CCPA Opt-Out” attribute is only available starting 19.4. For 19.3 environments, you need to extend the Profiles resource and add a boolean field. This field will be added to the API with the chosen label. We suggest you use “Opt-Out for CCPA”.
>
>For more on this, refer to the [Managing Privacy requests documentation](../../start/using/privacy-requests.md#sale-of-personal-information-ccpa).
-->

<br/>

***Solicitações de exemplo***

* Exemplo de solicitação do GET para recuperar o status de recusa do CCPA de um perfil.

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profilesAndServices/profile/<PKEY> \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>' \
  -H 'Content-Type: application/json;charset=utf-8'
  ```

  Resposta à solicitação do GET.

  ```
  {
  "PKey": "<PKEY>",
    "ccpaOptOut": false,
    "firstName": "John",
    "lastName": "Doe",
  ...
  }
  ```

* Exemplo de solicitação POST para marcar um perfil para recusa do CCPA.

  ```
  -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profilesAndServices/profile/ \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>' \
  -H 'Content-Type: application/json;charset=utf-8'
  -i
  -d {
  -d  "firstName": "John",
  -d  "lastName": "Doe",
  -d  "email": "jdoe@mail.com",
  -d  "ccpaOptOut": true
  -d }'
  ```

  Resposta à solicitação do GET.

  ```
  {
      ...
      "email": "john.doe@mail.com",
      "firstName": "John",
      "lastName": "Doe",
      "ccpaOptOut": true,
      ...
  }
  ```

* Exemplo de solicitação do PATCH para atualizar um perfil para recusa do CCPA.

  ```
  -X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profilesAndServices/profile/<PKEY> \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>' \
  -H 'Content-Type: application/json;charset=utf-8'
  -i
  -d {
  -d  "ccpaOptOut": true
  -d }'
  ```

  Resposta à solicitação do GET.

  ```
  {
      ...
      "email": "john.doe@mail.com",
      "firstName": "John",
      "lastName": "Doe",
      "ccpaOptOut": true,
      ...
  }
  ```
