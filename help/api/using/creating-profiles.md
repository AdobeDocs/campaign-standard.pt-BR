---
title: Criação de perfis
description: Saiba mais sobre como criar perfis com APIs.
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 3%

---


# Criação de perfis {#creating-profiles}

A criação de perfil é realizada com uma solicitação de **POST** no recurso perfil.

>[!CAUTION]
>
>Se você quiser associar um <b>orgUnit</b> ao perfil criado, é necessário estender o recurso do perfil a esse campo e, após a publicação da extensão, executar uma solicitação POST no terminal <b>ProfileAndServicesExt</b> .
>
>Para obter mais informações sobre a extensão de recursos do perfil, consulte a documentação <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles">da</a>Campanha.

<br/>

***Solicitação de amostra***

Amostra de solicitação de POST para criar um perfil com o email &quot;john.doe@mail.com&quot;.

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-i
-d '{"email":"john.doe@mail.com"}'
```

Ele retorna o perfil recém-criado, com o endereço de email &quot;john.doe@mail.com&quot;.

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
