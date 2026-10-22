---
title: Recursos personalizados
description: Saiba mais sobre o gerenciamento de recursos personalizados com APIs/
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
old-role: Data Architect
role: Developer
level: Experienced
exl-id: d7b2231d-46ff-4966-9ea7-27a775e5236b
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
    internal-label: APIs
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 3%
---
# Recursos personalizados {#custom-resources}

O Adobe Campaign vem com um modelo de dados predefinidos por meio de diferentes recursos. Você pode aprimorar o modelo de dados fornecido estendendo os recursos para adicionar seus próprios campos personalizados ou tabelas personalizadas, como tabelas de produtos ou de compras.

Os recursos personalizados podem ser acessados por meio de APIs usando o ponto de extremidade **/profileAndServicesExt** e o nome do recurso personalizado.

`https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/<resourceName>/`

>[!NOTE]
>
>Para recursos que não estão prontos para uso, sempre use o prefixo <b>&quot;cus&quot;</b> antes do nome do recurso.

Você pode executar qualquer operação com recursos personalizados, desde que eles estejam vinculados à tabela Perfil. Por exemplo, considere a estrutura das tabelas abaixo:

![alt texto](assets/cusresources.png)

Nesse caso, todos os recursos das tabelas **Transaction**, **TransactionDetails** e **Product** estarão disponíveis desde que estejam vinculados à tabela **Profile**.

<br/>

***Solicitação de exemplo***

Exemplo de solicitação GET para acessar o recurso profileAndServicesExt estendido.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/\
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
```

Retorna a lista de todos os recursos personalizados vinculados. Em seguida, você pode usar os URLs de recursos para executar qualquer tarefa de API descrita nesta documentação.

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
