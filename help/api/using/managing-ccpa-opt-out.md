---
solution: Campaign Standard
product: campaign
title: Gerenciamento de auto-exclusão do CCPA
description: Saiba como gerenciar a recusa do CCPA com APIs
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 4%

---


# Gerenciamento de auto-exclusão do CCPA {#managing-ccpa-optout}

O status de recusa da CCPA de um perfil pode ser monitorado e gerenciado usando o atributo de perfil **ccpaOptOut** e os valores &quot;true&quot; ou &quot;false&quot;:

`"ccpaOptOut": <value>`

* **true**: Proíbe a venda de informações pessoais.
* **false**: autoriza a venda de informações pessoais.

>[!CAUTION]
>
>O atributo &quot;Não participação na CCPA&quot; só está disponível a partir da versão 19.4. Para ambientes 19.3, é necessário estender o recurso Perfis e adicionar um campo booleano. Esse campo será adicionado à API com o rótulo escolhido. Sugerimos que você use a opção &quot;Não participação na CCPA&quot;.
>
>Para obter mais informações, consulte a [documentação sobre gerenciamento de solicitações de privacidade](../../start/using/privacy-requests.md#sale-of-personal-information-ccpa).

<br/>

***Solicitações de exemplo***

* Exemplo de solicitação do GET para recuperar o status de recusa do CCPA do perfil.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profilesAndServices/profile/<PKEY> \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -H 'Content-Type: application/json;charset=utf-8'
   ```

   Resposta à solicitação do GET.

   ```
   {
   "PKey": "<PKEY>",
     "ccpaOptOut": false,
     "firstName": "John",
     "lastName": "Doe",
   ...
   }
   ```

* Exemplo de solicitação do POST para marcar um perfil para não participação no CCPA.

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

   Resposta à solicitação do GET.

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

* Exemplo de solicitação do PATCH para atualizar um perfil para não participação no CCPA.

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

   Resposta à solicitação do GET.

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
