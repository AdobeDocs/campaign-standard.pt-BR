---
solution: Campaign Standard
product: campaign
title: Criação de perfis
description: Saiba mais sobre como criar perfis com APIs.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 3%

---


# Criação de perfis {#creating-profiles}

A criação de perfis é realizada com uma solicitação **POST** no recurso de perfil.

>[!CAUTION]
>
>Se você quiser associar uma <b>orgUnit</b> ao perfil criado, é necessário estender o recurso do perfil a esse campo e, após a publicação da extensão, executar uma solicitação POST no terminal <b>ProfileAndServicesExt</b>.
>
>Para obter mais informações sobre a extensão de recursos do perfil, consulte a <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles">documentação da Campanha</a>.

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
