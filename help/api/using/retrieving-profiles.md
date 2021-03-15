---
solution: Campaign Standard
product: campaign
title: Recuperação de perfis
description: Saiba mais sobre como recuperar perfis com APIs.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Engenheiro de dados
level: Experienciado
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 5%

---


# Recuperação de perfis {#retrieving-profiles}

A recuperação de perfis é realizada com uma solicitação **GET**.

Você pode refinar sua pesquisa usando filtros, pedidos e paginação. Para obter mais informações, consulte a seção [Additional operations](../../api/using/sorting.md).

Além disso, as APIs do Campaign Standard permitem pesquisar perfis com base em um desses campos: email, nome, sobrenome ou qualquer campo personalizado. Para obter mais informações, consulte [esta seção](#searching-field).

<br/>

***Solicitações de exemplo***

* Amostra de solicitação do GET para recuperar todos os perfis.

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

* Solicitação de exemplo do GET para recuperar os primeiros 10 valores de email.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_lineCount=10 \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

   Resposta à solicitação. O nó &quot;next&quot; retorna o URL que dá acesso aos 10 próximos valores de email.

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

## Armazenamento de perfis com base em um campo {#searching-field}

O parâmetro **[!UICONTROL filterType]** permite recuperar perfis com base em um desses campos: email, nome, sobrenome ou qualquer campo personalizado que tenha sido adicionado na Filtragem avançada ao estender o recurso de perfil.

>[!NOTE]
>
>As pesquisas fazem distinção entre maiúsculas e minúsculas e são executadas somente em prefixos. Por exemplo, você não poderá procurar um perfil usando as últimas letras do seu sobrenome.

***Solicitações de exemplo***

* Solicitação de exemplo para filtrar perfis com base no nome.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/byText?text=John&filterType=firstName \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

* Solicitação de exemplo para filtrar perfis com base no sobrenome.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/byText?text=Miller&filterType=lastName \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

* Solicitação de exemplo para filtrar perfis com base no email.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/byText?text=John%40gmail.com&filterType=email \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

* Solicitação de exemplo para filtrar perfis com base no campo personalizado &quot;Hobby&quot;.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/byText?cusHobby=Dancing&filterType=Hobby \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```
