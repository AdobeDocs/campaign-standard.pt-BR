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
source-wordcount: '183'
ht-degree: 3%

---


# Interação com recursos personalizados {#interacting-with-custom-resources}

O endpoint **/customResources** permite que você exponha os recursos personalizados ACS em REST. Com base nessa API, está disponível uma integração entre entidades personalizadas e pontos de extremidade externos.

O endpoint /customResources tem exatamente o mesmo comportamento do endpoint /profileAndServices.

Os recursos personalizados expostos dentro desta API são:

* todas as entidades ligadas à entidade perfil
* todas as entidades ligadas aos filhos da entidade perfil
* todas as entidades que não estão ligadas ao perfil e, para essas entidades, seus filhos e netos.

>[!NOTE]
>Os recursos personalizados disponíveis em /profileAndServicesExt não são expostos na API /customResources.

Este é um exemplo para recuperar os metadados de um recurso personalizado:

```
GET /customResources/resourceType/<customResourceName>
```

Para executar uma criação, atualização ou exclusão, são usados o GET, o POST, o PATCH, o DELETE.

```
POST /customResources/<customResourceName>
```

>[!NOTE]
>O terminal e os workflows da API de privacidade (/privacy/privacyTool) não estão gerenciando os recursos personalizados que não estão vinculados à entidade do perfil.
>Você terá a responsabilidade de gerenciar e limpar quaisquer PII para esses recursos personalizados. Para obter mais informações sobre a ferramenta de privacidade, [clique aqui](../../api/using/creating-a-privacy-request.md).

