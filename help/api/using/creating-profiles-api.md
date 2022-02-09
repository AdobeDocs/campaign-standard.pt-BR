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
source-git-commit: 64f24fb692754973331b4fb2f7b95e9a6f31cd0d
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 1%

---

# Criação de perfis com APIs {#creating-profiles-api}

A criação de perfis é realizada com uma **POST** no recurso de perfil.

>[!CAUTION]
>
>Se quiser associar um <b>orgUnit</b> para o perfil criado, é necessário estender o recurso de perfil com esse campo e, após a publicação da extensão, executar uma solicitação POST no <b>ProfileAndServicesExt</b> endpoint .
>
>Para obter mais informações sobre a extensão de recurso do perfil, consulte <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles">Documentação da campanha</a>.

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
