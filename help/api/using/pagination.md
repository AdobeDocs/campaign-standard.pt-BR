---
solution: Campaign Standard
product: campaign
title: Paginação
description: Saiba como executar operações de paginação.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 1%

---


# Paginação

Por padrão, 25 recursos são carregados em uma lista.

O parâmetro **_lineCount** permite limitar o número de recursos listados na resposta.  Em seguida, você pode usar o **próximo** nó para exibir os resultados seguintes.

>[!NOTE]
>
>Sempre use o valor de URL retornado no nó **seguinte** para executar uma solicitação de paginação.
>
>A solicitação **_lineStart** é calculada e deve ser sempre usada dentro do URL retornado no **próximo** nó.

<br/>

***Solicitação de amostra***

Amostra de solicitação de GET para exibir 1 registro do recurso de perfil.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_lineCount=1 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Resposta à solicitação, com o **próximo** nó para executar a paginação.

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
    ],
    "next": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_lineCount=10&_
        lineStart=@Qy2MRJCS67PFf8soTf4BzF7BXsq1Gbkp_e5lLj1TbE7HJKqc"
    }
    ...
}
```

Por padrão, o nó **seguinte** não está disponível ao interagir com tabelas com grande quantidade de dados. Para poder executar a paginação, você deve adicionar o parâmetro **_forcePagination=true** ao URL da chamada.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_forcePagination=true \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

>[!NOTE]
>
>O número de registros acima dos quais uma tabela é considerada grande é definido na opção Campaign Standard **XtkBigTableThreshold** . O valor padrão é 100.000 registros.
