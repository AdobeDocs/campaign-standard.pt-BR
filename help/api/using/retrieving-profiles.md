---
solution: Campaign Standard
product: campaign
title: Recuperação de perfis
description: Saiba mais sobre como recuperar perfis com APIs.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: da0aa6c111f3e44bb502c1e5c4ad7feff9108d81
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 5%

---


# Recuperação de perfis {#retrieving-profiles}

A recuperação de perfis é realizada com uma solicitação **GET**.

Você pode refinar sua pesquisa usando filtros, pedidos e paginação. Para obter mais informações, consulte a seção [Operações adicionais](../../api/using/sorting.md).

Além disso, as APIs de Campaign Standard permitem pesquisar perfis com base em um desses campos: email, nome, sobrenome ou qualquer campo personalizado. Para obter mais informações, consulte [esta seção](#searching-field).

<br/>

***Pedidos de amostra***

* Amostra de solicitação de GET para recuperar todos os perfis.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
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
               "firstName": "John",
               "lastName":"Doe",
               "birthDate": "1980-10-24",
               ...
           },
           ...
   }
   ```

* Amostra de solicitação de GET para recuperar os primeiros 10 valores de email.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_lineCount=10 \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

   Resposta à solicitação. O nó &quot;próximo&quot; retorna o URL que fornece acesso aos 10 valores de e-mail seguintes.

   ```
   {
   "content": [
       "amy.dakota@mail.com",
       "kristen.smith@mail.com",
       "omalley@mail.com",
       "xander.harrys@mail.com",
       "jane.summer@mail.com",
       "gloria.boston@mail.com",
       "edward.snow@mail.com",
       "dorian.simons@mail.com",
       "peter.paolini@mail.com",
       "mingam+test08@adobe.com"
   ],
   "next": {
       "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_lineCount=10&_
       lineStart=@Qy2MRJCS67PFf8soTf4BzF7BXsq1Gbkp_e5lLj1TbE7HJKqc"
   }
   }
   ```

## Procurando perfis com base em um campo {#searching-field}

O parâmetro **[!UICONTROL filterType]** permite recuperar perfis com base em um destes campos: email, nome, sobrenome ou qualquer campo personalizado que tenha sido adicionado na filtragem Avançada ao estender o recurso de perfil.

>[!NOTE]
>
>As pesquisas fazem distinção entre maiúsculas e minúsculas e são executadas somente em prefixos. Por exemplo, você não poderá procurar por um perfil usando as últimas letras do seu sobrenome.

***Pedidos de amostra***

* Solicitação de amostra para filtrar perfis com base no nome.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/byText?text=John&filterType=firstName \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

* Solicitação de amostra para filtrar perfis com base no sobrenome.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/byText?text=Miller&filterType=lastName \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

* Solicitação de amostra para filtrar perfis com base em email.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/byText?text=John%40gmail.com&filterType=email \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

* Solicitação de amostra para filtrar perfis com base no campo personalizado &quot;Hobby&quot;.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/byText?cusHobby=Dancing&filterType=Hobby \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```
