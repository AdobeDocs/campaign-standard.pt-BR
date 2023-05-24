---
title: Sobre o gerenciamento de privacidade
description: Saiba mais sobre o gerenciamento de privacidade com APIs
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
source-git-commit: 210289d44f0ad0ebf0b2654f6e9795adad7dd458
workflow-type: tm+mt
source-wordcount: '107'
ht-degree: 0%

---


# Sobre o gerenciamento de privacidade {#about-privacy-management}

As APIs Campaign Standard fornecem recursos que permitem o processo automático de solicitações relacionadas a regulamentos de privacidade, como GDPR e CCPA.

As ações que você pode executar são as seguintes:

* Criar uma nova solicitação de privacidade,
* Monitorar uma solicitação de privacidade,
* Recuperar um arquivo de dados de privacidade,
* Gerencie o status de recusa da CCPA de um perfil.

O endpoint da API de privacidade é **/privacy/privacyTool**. A descrição de recursos da PrivacyTool e os filtros associados estão disponíveis nos metadados do recurso. Consulte [Mecanismo de metadados](../../api/using/metadata-mechanism.md).

A recusa da CCPA é gerenciada usando o **ccpaOptOut** atributo de perfil.

Para obter mais informações sobre o Adobe Campaign Standard e a conformidade com a privacidade, consulte [documentação dedicada](../../start/using/privacy-requests.md).
