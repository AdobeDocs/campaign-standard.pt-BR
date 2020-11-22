---
solution: Campaign Standard
product: campaign
title: Sobre o gerenciamento de privacidade
description: Saiba mais sobre o gerenciamento de privacidade com APIs
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 4%

---


# Sobre o gerenciamento de privacidade {#about-privacy-management}

As APIs de Campaign Standard fornecem recursos que permitem o processo automático de solicitações relacionadas a regulamentos de privacidade, como o RGPD e o CCPA.

As ações que você pode executar são as seguintes:

* Criar uma nova solicitação de privacidade,
* Monitorar uma solicitação de privacidade,
* Recuperar um arquivo de dados de privacidade,
* Gerenciar um status de recusa do CCPA do perfil.

O endpoint da API de privacidade é **/privacy/privacyTool**. A descrição do recurso PrivacyTool e filtros associados estão disponíveis nos metadados do recurso. Consulte Mecanismo [de metadados](../../api/using/metadata-mechanism.md).

A opção de não participação CCPA é gerenciada usando o atributo de perfil **cpaOptOut** .

Para obter mais informações sobre a conformidade com a Adobe Campaign Standard e a privacidade, consulte a documentação [](https://helpx.adobe.com/br/campaign/kb/acs-privacy.html)dedicada.
