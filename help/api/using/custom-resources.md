---
solution: Campaign Standard
product: campaign
title: Recursos personalizados
description: Saiba mais sobre o gerenciamento de recursos personalizados com APIs/
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 5%

---


# Recursos personalizados {#custom-resources}

A Adobe Campaign vem com um modelo de dados predefinido, onde os dados são definidos por meio de diferentes recursos. Você pode aprimorar o modelo de dados fornecido estendendo os recursos para adicionar seus próprios campos personalizados ou tabelas personalizadas, como tabelas de produtos ou de compras.

Os recursos personalizados são acessíveis por meio de APIs usando o terminal **/profileAndServicesExt** e o nome do recurso personalizado.

`https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/<resourceName>/`

>[!NOTE]
>
>Para recursos que não estão prontos para uso, use sempre o prefixo <b>&quot;cus&quot;</b> antes do nome do recurso.

É possível executar qualquer operação com recursos personalizados, desde que estejam vinculados à tabela de Perfis. Por exemplo, vamos considerar a estrutura de tabelas abaixo:

![texto alternativo](assets/cusresources.png)

Nesse caso, todos os recursos das tabelas **Transaction**, **TransactionDetails** e **Product** estão disponíveis desde que estejam vinculados à tabela **Perfil**.

<br/>

***Solicitação de amostra***

Amostra de solicitação de GET para acessar o recurso profileAndServicesExt estendido.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/\
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
```

Ele retorna a lista de todos os recursos personalizados vinculados. Você pode usar os URLs de recursos para executar qualquer tarefa de API descrita nesta documentação.

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

Para obter mais informações sobre a extensão do modelo de dados, consulte a documentação da Campanha:

* [Conceitos do modelo de dados](../../developing/using/data-model-concepts.md)
* [Extensão da API](../../developing/using/about-extending-the-api.md)
* [Definição de links com outros recursos](https://helpx.adobe.com/campaign/standard/developing/using/configuring-the-resource-s-data-structure.html#defining-links-with-other-resources)
