---
title: Criação de um serviço com APIs
description: Saiba como criar um serviço com APIs
feature: API
role: Data Engineer
level: Experienced
exl-id: 91bbce9e-a618-4be2-840b-c7d021271f4e
source-git-commit: 02f1ef1f960cf98b5277b2db960e61ae20e22209
workflow-type: tm+mt
source-wordcount: '77'
ht-degree: 0%

---

# Criação de um serviço com APIs{#creating-a-service-api}

A criação de serviços é executada com uma solicitação **POST** no recurso de serviço.

Se quiser criar o serviço com atributos específicos, adicione-os à carga. Caso contrário, o novo serviço será criado com os padrões.

<br/>

***Solicitação de exemplo***

Exemplo de solicitação POST para criar um serviço com atributos específicos.

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/ \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
-i
-d {
-d "label": "My newsletter",
-d "messageType": "email",
-d "name": "email_newsletter",
-d "start": "2019-10-06"
-d }
```

Ele retorna o serviço recém-criado com os atributos atualizados.

```
{
    "PKey": "<PKEY>",
    "builtIn": false,
    "created": "2019-09-26 12:00:37.005Z",
    "href": "https://mc.adobe.io/<ORGANIZATION>/profileAndServices/service/@NLscZuVHxdVu9rPftvrMWFfR1zRIxQGswSOmGLrK09JTF_iWhB0JCUHEndA_vvy__k9mzOYa5NVkcWDcrK8qGh0wygahX9kRcD44kiWWSEceShn3",
    "label": "My newsletter",
    ...
}
```
