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
source-wordcount: '198'
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
