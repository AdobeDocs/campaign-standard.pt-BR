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

As APIs do Campaign Standard fornecem recursos que permitem o processo automático de solicitações relacionadas a regulamentos de privacidade, como o GDPR e a CCPA.

As ações que você pode executar são as seguintes:

* Crie uma nova solicitação de acesso a dados pessoais,
* Monitorar uma solicitação de privacidade,
* Recuperar um arquivo de dados de privacidade,
* Gerencie o status de recusa do CCPA de um perfil.

O endpoint da API de privacidade é **/privacy/privacyTool**. A descrição do recurso PrivacyTool e os filtros associados estão disponíveis nos metadados do recurso. Consulte [Mecanismo de metadados](../../api/using/metadata-mechanism.md).

A recusa do CCPA é gerenciada usando o **ccpaOptOut** atributo de perfil.

Para obter mais informações sobre a Adobe Campaign Standard e a conformidade da privacidade, consulte [documentação dedicada](../../start/using/privacy-requests.md).
