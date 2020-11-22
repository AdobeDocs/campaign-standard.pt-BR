---
solution: Campaign Standard
product: campaign
title: Gerenciamento de auto-exclusão do CCPA
description: Saiba como gerenciar a recusa de CCPA com APIs
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 4%

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
>Para obter mais informações, consulte a documentação [Solicitações de](../../start/using/privacy-requests.md#sale-of-personal-information-ccpa)gerenciamento de privacidade.

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
