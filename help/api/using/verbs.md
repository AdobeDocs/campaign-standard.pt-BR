---
title: GET / POST / PATCH / DELETE / verbos
description: Saiba mais sobre os verbos usados nas APIs do Campaign Standard.
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
source-wordcount: '129'
ht-degree: 0%

---


# GET / POST / PATCH / DELETE / verbos {#verbs}

Os verbos disponíveis para executar operações nos recursos são:

* `GET`: recupera um elemento ou uma coleção de elementos
* `POST`: cria um recurso com parâmetros.
* `PATCH`: atualiza um recurso com parâmetros.
* `DELETE`: exclui um recurso.

<!-- ajouter codes retour -->

<br/>

***Pedidos de amostra***

* Solicitação de amostra de GET na coleção de perfis.


   ```
   $curl  
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

   Ele retorna uma série de perfis.


   ```
   {
       "content": [
           {
               "PKey": "<PKEY>",
               "firstName": "Olivia",
               "lastName": "Varney",
               "birthDate": "1977-09-°4",
               "email": "o.varney@mail.com",
           },
           {
               "PKey": "<PKEY>",
               "firstName": "John",
               "lastName": "Doe",
               "birthDate": "1985-08-17",
               "email": "johndoe@mail.com",
           }
       ],
   }
   ```

* Solicitação de amostra de GET em um perfil específico.


   ```
   $curl  
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY> \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

   Ele retorna o perfil solicitado.


   ```
   {
       "PKey": "<PKEY>",
       "firstName": "John",
       "lastName": "Doe",
       "birthDate": "1985-08-17",
       "email": "johndoe@mail.com",
       ...
   }
   ```

* Amostra de solicitação de POST para criar um perfil.


   ```
   -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -d '{"lastName":"Doe"}'
   ```

   Ele retorna o perfil com os campos padrão.

   ```
   {
       "PKey": "<PKEY>",
       "firstName": "John",
       "lastName": "Doe",
       "birthDate": "1985-08-17",
       "email": "johndoe@mail.com",
   }
   ```

* Amostra de solicitação de PATCH para atualizar um perfil.

   ```
   -X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY> \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -d '{"firstName":"Mark"',"lastName":"Smith"}'
   ```

   Ele retorna a PKEY e o URL para recuperar o perfil atualizado.

   ```
   {
       "PKey": "<PKEY>",
       "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>"
   }
   ```

* Amostra de solicitação de DELETE para excluir um perfil.

   ```
   -X DELETE https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY> \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

   A solicitação retorna uma resposta 200, confirmando que o perfil foi excluído.
