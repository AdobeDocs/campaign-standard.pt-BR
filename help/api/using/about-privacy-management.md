---
title: Sobre o gerenciamento de privacidade
description: Saiba mais sobre o gerenciamento de privacidade com APIs
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 0%
---

# Sobre o gerenciamento de privacidade {#about-privacy-management}

As APIs do Campaign Standard fornecem recursos que permitem o processo automático de solicitações relacionadas a regulamentos de privacidade, como GDPR e CCPA.

As ações que você pode executar são as seguintes:

* Criar uma nova solicitação de privacidade,
* Monitorar uma solicitação de privacidade,
* Recuperar um arquivo de dados de privacidade,
* Gerencie o status de recusa da CCPA de um perfil.

O ponto de extremidade da API de privacidade é **/privacy/privacyTool**. A descrição de recursos da PrivacyTool e os filtros associados estão disponíveis nos metadados do recurso. Consulte [Mecanismo de metadados](../../api/using/metadata-mechanism.md).

A recusa da CCPA é gerenciada com o uso do atributo de perfil **ccpaOptOut**.

Para obter mais informações sobre o Adobe Campaign Standard e a conformidade com a privacidade, consulte a [documentação dedicada](../../start/using/privacy-requests.md).
