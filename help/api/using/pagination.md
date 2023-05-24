---
title: Paginação
description: Saiba como executar operações de paginação.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: d6ebce3c-1e84-4b3b-a68d-90df4680af64
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 1%

---

# Paginação

Por padrão, 25 recursos são carregados em uma lista.

A variável **_lineCount** permite limitar o número de recursos listados na resposta.  Em seguida, você pode usar o **próximo** para exibir os próximos resultados.

>[!NOTE]
>
>Sempre use o valor do URL retornado na variável **próximo** nó para executar uma solicitação de paginação.
>
>A variável **_lineStart** é calculada e sempre deve ser usada no URL retornado na variável **próximo** nó.

<br/>

***Exemplo de solicitação***

Exemplo de solicitação de GET para exibir 1 registro do recurso de perfil.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_lineCount=1 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Resposta à solicitação, com a **próximo** nó para executar a paginação.

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

Por padrão, a variável **próximo** O nó não está disponível ao interagir com tabelas com uma grande quantidade de dados. Para executar a paginação, é necessário adicionar o **_forcePagination=true** para o URL da chamada.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_forcePagination=true \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

>[!NOTE]
>
>O número de registros acima do qual uma tabela é considerada grande é definido em Campaign Standard **LimiteTabelaGrandeXtk** opção. O valor padrão é 100.000 registros.
