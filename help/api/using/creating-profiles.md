---
title: Criar perfis
description: Saiba mais sobre como criar perfis com APIs.
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
source-git-commit: aee0e0437cbfe578cb2f715a2433099c79dd1748

---


# Criar perfis {#creating-profiles}

A criação de perfis é realizada com uma solicitação **POST** no recurso de perfil.

>[!CAUTION]
>
>Se você quiser associar uma <b>orgUnit</b> ao perfil criado, é necessário estender o recurso de perfil a esse campo e, após a publicação da extensão, executar uma solicitação POST no terminal <b>ProfileAndServicesExt</b> .
>
>Para obter mais informações sobre a extensão de recursos do perfil, consulte a documentação da <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles">Campanha</a>.

<br/>

***Solicitação de amostra***

Amostra de solicitação POST para criar um perfil com o email "john.doe@mail.com".

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-i
-d '{"email":"john.doe@mail.com"}'
```

Ele retorna o perfil recém-criado, com o endereço de email "john.doe@mail.com".

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
