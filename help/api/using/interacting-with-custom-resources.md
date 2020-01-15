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
source-git-commit: 538739417c4ed28ff2991186dac5fb69d1af3afd

---


# Interagir com recursos personalizados {#interacting-with-custom-resources}

O endpoint **/customResources** permite que você exponha os recursos personalizados ACS em REST. Com base nessa API, está disponível uma integração entre entidades personalizadas e pontos de extremidade externos.

O endpoint /customResources tem exatamente o mesmo comportamento do endpoint /profileAndServices.

Os recursos personalizados expostos dentro desta API são:

* todas as entidades ligadas à entidade de perfil
* todas as entidades ligadas aos filhos da entidade de perfil
* todas as entidades que não estão vinculadas ao perfil e, para essas entidades, seus filhos e netos.

>[!NOTE]
>Os recursos personalizados disponíveis em /profileAndServicesExt não são expostos na API /customResources.

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
>Você terá a responsabilidade de gerenciar e limpar quaisquer PII para esses recursos personalizados. Para obter mais informações sobre a ferramenta de privacidade, [clique aqui](../../api/using/creating-a-privacy-request.md).

