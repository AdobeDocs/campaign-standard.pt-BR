---
title: Interação com recursos personalizados
description: Saiba mais sobre o gerenciamento de recursos personalizados com APIs/
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 19bfeecb-da60-479c-a929-0cfb72ef59e3
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 0%

---

# Interação com recursos personalizados {#interacting-with-custom-resources}

O ponto de extremidade **/customResources** permite expor os recursos personalizados do Campaign em REST. Com base nessa API, uma integração entre entidades personalizadas e endpoints externos está disponível.

O ponto de extremidade /customResources tem exatamente o mesmo comportamento que o ponto de extremidade /profileAndServices.

Os recursos personalizados expostos nessa API são:

* todas as entidades que não estão expostas em /profileAndServicesExt
* todas as entidades que não estão vinculadas ao perfil e, para essas entidades, seus filhos e netos.
* por padrão, todas as entidades que não estão vinculadas a nada, e seus filhos e netos.

>[!NOTE]
>Os recursos personalizados disponíveis em /profileAndServicesExt não são expostos na API /customResources.


Este é um exemplo para recuperar os metadados de um recurso personalizado:

```
GET /customResources/resourceType/<customResourceName>
```

Para executar uma criação, atualização ou exclusão, são usados o GET, POST, PATCH, DELETE.

```
POST /customResources/<customResourceName>
```

>[!NOTE]
>O ponto de extremidade da API de privacidade e os fluxos de trabalho (/privacy/privacyTool) não estão gerenciando os recursos personalizados que não estão vinculados à entidade do perfil.
>Você terá a responsabilidade de gerenciar e limpar qualquer PII desses recursos personalizados. Para obter mais informações sobre a ferramenta de privacidade, [clique aqui](../../api/using/creating-a-privacy-request.md).
