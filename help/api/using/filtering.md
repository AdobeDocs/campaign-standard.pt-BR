---
solution: Campaign Standard
product: campaign
title: Filtragem
description: Saiba como executar operações de filtragem.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: cdb050b7-d327-42f7-b534-d32d988c8ffb
source-git-commit: f946a7565c30a3e53b2bd6876e880100fa8a0be2
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 1%

---

# Filtragem {#filtering}

## Recuperar metadados de filtros

Os filtros estão disponíveis para cada recurso. Para identificar os filtros associados a um recurso, é necessário executar uma solicitação de GET nos metadados do recurso. Essa solicitação retorna o URL, onde todos os filtros são definidos para um determinado recurso. Para obter mais informações sobre metadados, consulte [esta seção](../../api/using/metadata-mechanism.md).

Para identificar os metadados de um filtro e determinar como usá-lo, é necessário executar uma solicitação de GET no URL retornado anteriormente.

<br/>

***Solicitação de exemplo***

As cargas de exemplo abaixo mostram como recuperar os metadados do filtro &quot;byText&quot; para o recurso &quot;perfil&quot;. Primeiro, execute uma solicitação GET na metada de recurso &quot;perfil&quot;.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Ele retorna o URL onde os filtros são descritos.

```
{
"filters": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/<PKEY>/filters/"
    }
  }
```

Execute uma solicitação GET no URL. Retorna a lista de filtros para o recurso de perfil, com os metadados associados a cada filtro.

```
{
"birthday": {
        "PKey": "@FL-CbDFXbnHbXcVpeCGWL46VXJLn1LqxLMPagt2vz8sCxQ52lvB15KiUaxXkxJYQw-tZXYrgUWG6K8QcB4gxVY9RKoba5bRFY3294YFshDmorRr8",
        "category": "0150_profile",
        "condition": ...,
        "data": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/birthday?type=$value&precision=$value&operator=$value&day=$value&month=$value&includeStart=$value&endDay=$value&endMonth=$value&includeEnd=$value&relativeValue=$value&nextUnitsValue=$value&previousUnitsValue=$value",
        "formType": "webPage",
        "fragmentName": "",
        "label": "Birthday",
}
```

## Filtrar estrutura de metadados

A mesma estrutura de metadados está disponível para cada filtro:

* Os campos **@formType** e **@webPage** são campos técnicos.
* O campo **data** fornece uma amostra sobre como usar o filtro.
* O nó **metadata** descreve os parâmetros de filtro.
* O nó **condition** descreve o que o filtro deve fazer. Os parâmetros de filtro descritos no nó de metadados são usados para criar condições de filtro. Para cada condição de filtro, se **enabledIf** for verdadeiro, o **expr** será aplicado.

<br/>

Amostra de estrutura de metadados de filtro:

```
"byText": {
        "PKey": "...",
        "category": "99_none",
        "condition": ...,
        "data": "/profileAndServices/profile/byText?text=$value",
        "formType": "none",
        "fragmentName": "",
        "label": "By name or email",
    }
```

## Uso de filtros

A filtragem é executada com a seguinte solicitação:

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/<resourceName>/by<filterName>?<filterParam>=<filterValue>`

É possível combinar vários filtros em uma única solicitação:

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/<resourceName>/<filter1name>/<filter2name>?<filter1param>=<filter1value>&<filter2param>=<filter2value>`

<br/>

***Solicitações de exemplo***

* Solicitação de exemplo do GET para recuperar os recursos do &quot;serviço&quot; com o tipo &quot;email&quot;.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/byChannel?channel=email \
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
               "created": "2019-09-25 23:20:35.000Z",
               "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/@I_FIiDush4OQPc0mbOVR9USoh36Tt5CsD35lATvQjdWlXrYc0lFkvle2XIwZUbD8GqTVvSp8AfWFUvjkGMe1fPe5nok",
               "label": "Marketing Newsletter",
               "lastModified": "2019-09-25 23:20:35.000Z",
               "limitedDuration": false,
               "messageType": "email",
               "mode": "newsletter",
               ...
           },
           ...
       ],
       ...
   }
   ```

* Solicitação de exemplo do GET para recuperar os recursos do &quot;perfil&quot; contendo &quot;Doe&quot; em
os campos email ou sobrenome (o filtro byText pesquisa nos campos email e sobrenome).

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/byText?text=Doe \
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
           }
           ...
       ],
       ...
   }
   ```

* Solicitação de exemplo do GET para recuperar os recursos dos serviços com o tipo &quot;email&quot; e o rótulo &quot;esporte&quot;.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/byChannel/byText?channel=email&text=sport \
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
               "created": "2019-09-26 09:36:01.014Z",
               "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>",
               "label": "sport",
               "lastModified": "2019-09-26 09:36:01.014Z",
               "limitedDuration": false,
               "messageType": "email",
               "mode": "newsletter",
               "name": "SVC13",
               ...
           }
       ],
       ...
   }
   ```

## Filtros personalizados

Se quiser usar um filtro personalizado, crie e personalize-o na interface do Adobe Campaign Standard. O filtro personalizado terá o mesmo comportamento dos filtros prontos para uso:

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/<resourceName>/by<customFilterName>?<customFilterparam>=<customFilterValue>`

Para obter mais informações, consulte a documentação do Campaign Standard:

* [Configuração da definição de filtro](https://helpx.adobe.com/campaign/standard/developing/using/configuring-filter-definition.html).
* [Caso de uso: Chamar um recurso usando uma chave](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/adding-or-extending-a-resource/uc-calling-resource-id-key.html) de identificação composta.

<br/>

***Solicitação de exemplo***

Solicitação de exemplo do GET para recuperar os recursos do &quot;perfil&quot; com valores de transação de 100$ ou mais. Observe que o filtro &quot;byAmount&quot; foi definido primeiro na interface do Adobe Campaign Standard e vinculado à tabela personalizada &quot;Transaction&quot;.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/byAmount?amount_parameter=100 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

<!--
Response to the request.

```

{
    "content": [
        {
            "PKey": "<PKEY>",
            "builtIn": false,
            "created": "2019-09-26 09:36:01.014Z",
            "desc": "",
            "end": "",
            "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>",
            ...
        }
    ],
}

```

-->

<!-- exemple à vérifier de bout en bout-->

<!--+category = query editor
privacy ?
displayFOrmat ?
pour faire un POST sur une enum, il faut lui passer le @name décrit dans le noeud values, chaque @name a une correspondance en format = au format définit par le resType
-->





<!--
 if link ou collection.* resName +
* resTarget tout ca, ca va ensemble : le système de lien, resTarget va donner la ressource targetée par le lien. type
resType = type technique (long..) resType = link alors unbound='false' ou 'true'
If type = enumeration alors champ "values" rajouté et les valeurs sont dans values
pour faire un POST sur une enum, il faut lui passer le @name décrit dans le noeud values, chaque @name a une correspondance en format = au format définit par le resType
ail faut que la valeur poster soit conforme ,elle doit valider la dataPolicy . La dataPolicy peut soit controler la valeur (email invalide), soit transformé (cas du smartCase par exemple)
type dans les metadata = type de haut-niveau (nombre, text)
-->
