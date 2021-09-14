---
title: Sobre o gerenciamento de privacidade
description: Saiba mais sobre o gerenciamento de privacidade com APIs
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 4%

---


# Sobre o gerenciamento de privacidade {#about-privacy-management}

As APIs do Campaign Standard fornecem recursos que permitem o processo automático de solicitações relacionadas a regulamentos de privacidade, como o GDPR e a CCPA.

As ações que você pode executar são as seguintes:

* Crie uma nova solicitação de acesso a dados pessoais,
* Monitorar uma solicitação de privacidade,
* Recuperar um arquivo de dados de privacidade,
* Gerencie o status de recusa do CCPA de um perfil.

O ponto de extremidade da API de privacidade é **/privacy/privacyTool**. A descrição do recurso PrivacyTool e os filtros associados estão disponíveis nos metadados do recurso. Consulte [Mecanismo de metadados](../../api/using/metadata-mechanism.md).

A recusa do CCPA é gerenciada usando o atributo de perfil **ccpaOptOut** .

Para obter mais informações sobre Adobe Campaign Standard e conformidade de privacidade, consulte a [documentação dedicada](https://helpx.adobe.com/br/campaign/kb/acs-privacy.html).
