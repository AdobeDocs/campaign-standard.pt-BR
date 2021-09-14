---
title: Criação de perfis
description: Saiba mais sobre como criar perfis com APIs.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 69e8d034-6bdd-4b82-bcd7-1ef4be0a59b3
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 3%

---

# Criação de perfis {#creating-profiles}

A criação de perfis é executada com uma solicitação **POST** no recurso de perfil.

>[!CAUTION]
>
>Se quiser associar um <b>orgUnit</b> ao perfil criado, é necessário estender o recurso de perfil a este campo e, após a publicação da extensão, executar uma solicitação de POST no terminal <b>ProfileAndServicesExt</b>.
>
>Para obter mais informações sobre a extensão de recurso do perfil, consulte a <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles">documentação do Campaign</a>.

<br/>

***Solicitação de exemplo***

Amostra de solicitação do POST para criar um perfil com o email &quot;john.doe@mail.com&quot;.

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-i
-d '{"email":"john.doe@mail.com"}'
```

Retorna o perfil recém-criado, com o endereço de email &quot;john.doe@mail.com&quot;.

```
{
    "PKey": "<PKEY>",
    "firstName": "John",
    "lastName":"Doe",
    "birthDate": "1980-10-24",
    "email": "john.doe@mail.com",
    ...
}
```
