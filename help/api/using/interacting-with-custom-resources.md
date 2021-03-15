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
source-wordcount: '187'
ht-degree: 3%

---


# Interação com recursos personalizados {#interacting-with-custom-resources}

O endpoint **/customResources** permite expor os recursos personalizados do Campaign no REST. Com base nessa API, uma integração entre entidades personalizadas e endpoints externos está disponível.

O endpoint /customResources tem exatamente o mesmo comportamento do endpoint /profileAndServices.

Os recursos personalizados expostos dentro dessa API são:

* todas as entidades vinculadas à entidade de perfil
* todas as entidades vinculadas aos filhos da entidade de perfil
* todas as entidades não vinculadas ao perfil e, para essas entidades, seus filhos e netos.

>[!NOTE]
>Os recursos personalizados disponíveis em /profileAndServicesExt não são expostos na API /customResources.

Este é um exemplo para recuperar os metadados de um recurso personalizado:

```
GET /customResources/resourceType/<customResourceName>
```

Para executar uma criação, atualização ou exclusão, são usados o GET, o POST, o DELETE.

```
POST /customResources/<customResourceName>
```

>[!NOTE]
>O endpoint da API de privacidade e os workflows (/privacy/privacyTool) não estão gerenciando os recursos personalizados que não estão vinculados à entidade de perfil.
>Você terá a responsabilidade de gerenciar e limpar qualquer PII para esses recursos personalizados. Para obter mais informações sobre a ferramenta de privacidade, [clique aqui](../../api/using/creating-a-privacy-request.md).

