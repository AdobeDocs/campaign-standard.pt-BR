---
title: Gerenciamento de auto-exclusão do CCPA
description: Saiba como gerenciar a recusa de CCPA com APIs
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
source-wordcount: '153'
ht-degree: 3%

---


# Gerenciamento de auto-exclusão do CCPA {#managing-ccpa-optout}

Um status de recusa CCPA do perfil pode ser monitorado e gerenciado usando o atributo do perfil **cpaOptOut** e os valores &quot;true&quot; ou &quot;false&quot;:

`"ccpaOptOut": <value>`

* **true**:  proíbe a venda de informações pessoais.
* **false**: autoriza a venda de informações pessoais.

>[!CAUTION]
>
>O atributo &quot;CCPA Opt-Out&quot; só está disponível a partir de 19.4. Para ambientes 19.3, é necessário estender o recurso Perfis e adicionar um campo booleano. Esse campo será adicionado à API com o rótulo escolhido. Sugerimos que você use &quot;Recusar para CCPA&quot;.
>
>For more on this, refer to the [Privacy management documentation](https://helpx.adobe.com/campaign/kb/acs-privacy.html#ccpa).

<br/>

***Pedidos de amostra***

* Amostra de solicitação de GET para recuperar um status de recusa do CCPA do perfil.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profilesAndServices/profile/<PKEY> \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -H 'Content-Type: application/json;charset=utf-8'
   ```

   Resposta à solicitação de GET.

   ```
   {
   "PKey": "<PKEY>",
     "ccpaOptOut": false,
     "firstName": "John",
     "lastName": "Doe",
   ...
   }
   ```

* Solicitação de POST de amostra para marcar um perfil para recusa de CCPA.

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

   Resposta à solicitação de GET.

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

* Amostra de solicitação de PATCH para atualizar um perfil para cancelamento de CCPA.

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

   Resposta à solicitação de GET.

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
