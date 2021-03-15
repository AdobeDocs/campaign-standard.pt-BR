---
solution: Campaign Standard
product: campaign
title: Recursos personalizados
description: Saiba mais sobre o gerenciamento de recursos personalizados com APIs/
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Engenheiro de dados
level: Experienciado
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 6%

---


# Recursos personalizados {#custom-resources}

O Adobe Campaign vem com um modelo de dados predefinido, onde os dados são definidos por meio de diferentes recursos. Você pode enriquecer o modelo de dados fornecido estendendo os recursos para adicionar seus próprios campos personalizados ou tabelas personalizadas, como tabelas de produtos ou de compras.

Os recursos personalizados podem ser acessados por meio de APIs usando o endpoint **/profileAndServicesExt** e o nome do recurso personalizado.

`https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/<resourceName>/`

>[!NOTE]
>
>Para recursos que não estão prontos, sempre use o prefixo <b>&quot;cus&quot;</b> antes do nome do recurso.

Você pode executar qualquer operação com recursos personalizados, desde que eles estejam vinculados à tabela Perfil. Por exemplo, vamos considerar a estrutura de tabelas abaixo:

![texto alternativo](assets/cusresources.png)

Nesse caso, todos os recursos das tabelas **Transaction**, **TransactionDetails** e **Product** estão disponíveis, desde que estejam vinculadas à tabela **Profile**.

<br/>

***Solicitação de exemplo***

Solicitação de exemplo do GET para acessar o recurso profileAndServicesExt estendido.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/\
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
```

Retorna a lista de todos os recursos personalizados vinculados. Você pode usar os URLs de recursos para executar qualquer tarefa de API descrita nesta documentação.

```
{
"apiName": "resourceType",
"cusProduct": {
        "content": ...,
        "data": "/profileAndServicesExt/cusProduct/",
        "help": "Product",
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/cusProduct/metadata",
        "name": "cusProduct",
        "type": "collection"
    },
"cusTransaction": {
        "content": ...,
        "data": "/profileAndServicesExt/cusTransaction/",
        "help": "Product",
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/cusTransaction/metadata",
        "name": "cusProduct",
        "type": "collection"
    },
    ...
}
```

Para obter mais informações sobre a extensão do modelo de dados, consulte a documentação do Campaign:

* [Conceitos do modelo de dados](../../developing/using/data-model-concepts.md)
* [Extensão da API](../../developing/using/about-extending-the-api.md)
* [Definição de links com outros recursos](https://helpx.adobe.com/campaign/standard/developing/using/configuring-the-resource-s-data-structure.html#defining-links-with-other-resources)
