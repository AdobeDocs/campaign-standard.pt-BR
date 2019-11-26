---
title: Recursos personalizados
description: Saiba mais sobre o gerenciamento de recursos personalizados com APIs/
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 206bb19acfd4c1bcbc7e8839cdf2d13a6279642f

---


# Interagir com recursos personalizados {#interacting-with-custom-resources}


O endpoint **/customResources** permite que você exponha as entidades personalizadas ACS em REST. Com base nessa API, está disponível uma integração entre entidades personalizadas e pontos de extremidade externos.

O /customResources tem exatamente o mesmo comportamento que o endpoint /profileAndServices.

As entidades personalizadas expostas dentro desta API são:

* todas as entidades ligadas à entidade de perfil
* todas as entidades ligadas aos filhos da entidade de perfil
* todas as entidades que não estão vinculadas ao perfil e, para essas entidades, seus filhos e netos.

>[!NOTE]
>As entidades personalizadas que estão disponíveis em /profileAndServicesExt não são expostas na API /customResources.

Este é um exemplo para recuperar os metadados de um recurso personalizado:

```
GET /customResources/resourceType/<customResourceName>
```

Para executar uma criação, atualização ou exclusão, são usados GET, POST, PATCH, DELETE.

```
POST /customResources/<customResourceName>
```

>[!NOTE]
>O endpoint e os fluxos de trabalho da API de privacidade (/privacy/privacyTool) não estão gerenciando os recursos personalizados que não estão vinculados à entidade de perfil.
>Você terá a responsabilidade de gerenciar e limpar quaisquer PII para esses recursos personalizados. Para obter mais informações sobre a ferramenta de privacidade, [clique aqui](../../api/using/privacy-management.md).
