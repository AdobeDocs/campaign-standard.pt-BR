---
title: Atualização de perfis
description: Saiba como atualizar perfis com APIs
feature: API
role: Data Engineer
level: Experienced
exl-id: fa3796ee-a00c-4d70-bf3d-e8d2099f1116
source-git-commit: 64f24fb692754973331b4fb2f7b95e9a6f31cd0d
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 2%

---

# Atualização de perfis com APIs{#updating-profiles-api}

A atualização de perfis é executada com uma solicitação **PATCH**.

`https://mc.adobe.io/<ORGANIZATION>/campaign/<apiName>/<resourceName>/<PKEY>`

1. A primeira etapa é **recuperar o perfil**.

1. Em uma segunda solicitação, execute uma **solicitação de PATCH** no perfil com as informações concluídas na carga.

1. Para verificar se a solicitação PATCH atualizou o perfil, podemos executar uma solicitação GET final.

<br/>

***Solicitação de exemplo***

Exemplo de solicitação do GET para recuperar um perfil.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>\
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Resposta à solicitação.

```
{
    "content": [
        {
            "PKey": "<PKEY>",
            "firstName": "Amy",
            "lastName":"Dakota",
            "birthDate": "1980-10-24",
            ...
        }
    ]
}
```

Solicitação PATCH para atualizar o atributo &quot;phone&quot;.

```
-X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-d '{"phone":"3301020304"}'
```

Ele retorna a PKEY e o URL para recuperar o perfil atualizado.

```
{
    "PKey": "<PKEY>",
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/@2v1dr3ZKJveMDhAdh0MPnh9hNQQ93qb7AW6BNVVKknjwXvTZRBAgUqz1SNcB4ZndgjqOofx3BwBZYBftlmObISoM3rs"
}
```
