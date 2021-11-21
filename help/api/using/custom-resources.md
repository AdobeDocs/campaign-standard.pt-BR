---
title: Recursos personalizados
description: Saiba mais sobre o gerenciamento de recursos personalizados com APIs/
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: d7b2231d-46ff-4966-9ea7-27a775e5236b
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 5%

---

# Recursos personalizados {#custom-resources}

O Adobe Campaign vem com um modelo de dados predefinido, onde os dados são definidos por meio de diferentes recursos. Você pode enriquecer o modelo de dados fornecido estendendo os recursos para adicionar seus próprios campos personalizados ou tabelas personalizadas, como tabelas de produtos ou de compras.

Os recursos personalizados podem ser acessados por meio de APIs usando o **/profileAndServicesExt** endpoint e o nome do recurso personalizado.

`https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/<resourceName>/`

>[!NOTE]
>
>Para recursos que não estão prontos, sempre use a variável <b>&quot;cus&quot;</b> antes do nome do recurso.

Você pode executar qualquer operação com recursos personalizados, desde que eles estejam vinculados à tabela Perfil. Por exemplo, vamos considerar a estrutura de tabelas abaixo:

![texto alternativo](assets/cusresources.png)

Nesse caso, todos os recursos do **Transação**, **Detalhes da transação** e **Produto** as tabelas estão disponíveis desde que estejam vinculadas à variável **Perfil** tabela.

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
