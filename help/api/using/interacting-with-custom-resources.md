---
solution: Campaign Standard
product: campaign
title: Recursos personalizados
description: Saiba mais sobre o gerenciamento de recursos personalizados com APIs/
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 19bfeecb-da60-479c-a929-0cfb72ef59e3
translation-type: tm+mt
source-git-commit: 01e4eb027b55815c3680b26691e61cbe5b63ee8c
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 3%

---

# Interação com recursos personalizados {#interacting-with-custom-resources}

O endpoint **/customResources** permite expor os recursos personalizados do Campaign no REST. Com base nessa API, uma integração entre entidades personalizadas e endpoints externos está disponível.

O endpoint /customResources tem exatamente o mesmo comportamento do endpoint /profileAndServices.

Os recursos personalizados expostos dentro dessa API são:

* todas as entidades não expostas em /profileAndServicesExt
* todas as entidades não vinculadas ao perfil e, para essas entidades, seus filhos e netos.
* por padrão, todas as entidades que não estão vinculadas a nada, e seus filhos e netos.

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
