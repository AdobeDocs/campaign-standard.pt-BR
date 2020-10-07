---
title: Sobre o gerenciamento de privacidade
description: Saiba mais sobre o gerenciamento de privacidade com APIs
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
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
