---
title: Introdução a origens e destinos
description: Saiba mais sobre origens e destinos da Adobe Experience Platform.
audience: integrating
content-type: reference
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: ba6205fa-dbcf-497a-882f-f15c00f12e68
TQID: https://experienceleague.adobe.com/r1rASYXuo-xeKH80eZVYG-jUhxy93GuTa8CIDyouSNY
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 314
ht-degree: 64%

---

# Introdução a origens e destinos {#rtcdp}

## Sobre origens e destinos

Com a Adobe Experience Platform, você pode compartilhar dados entre a Campaign Standard e a Plataforma de dados do cliente em tempo real (RTCDP) da Adobe. Isso permite direcionar os públicos-alvos da Adobe Experience Platform nos workflows do Campaign e enviar de volta para a Plataforma de dados do cliente em tempo real da Adobe relacionados a esses públicos-alvos, como envios, aberturas e cliques.

* Com **Destinos**, assimile públicos do Adobe Experience Platform na Campaign Standard. Isso permite ativar os dados conhecidos e desconhecidos para suas campanhas de marketing.
* Com **Fontes**, exporte dados do Campaign Standard (por exemplo, envios, aberturas e cliques) para o Adobe Experience Platform. Isso permite centralizar os dados coletados de origens diferentes em um único local e usar os insights obtidos com eles para fazer mais.


>[!IMPORTANT]
>
>Lembre-se dos limites de armazenamento SFTP, armazenamento do banco de dados e perfil ativo conforme o contrato do Adobe Campaign ao fazer essa integração.

Para obter uma visão geral mais detalhada da Plataforma de dados do cliente em tempo real da Adobe, Origens e Fontes, consulte estas páginas:

* [Adobe Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=pt-BR)
* [Documentação de destinos](https://experienceleague.adobe.com/docs/experience-platform/destinations/home.html?lang=pt-BR)
* [Documentação de origens](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=pt-BR)

## Conectar o Campaign Standard com o Adobe Experience Platform

Para compartilhar dados entre o Adobe Experience Platform e o Campaign Standard, primeiro é necessário conectar o Adobe Campaign como um **Destino** e conectar seu local de armazenamento de blobs do AWS S3 ou do Azure como um **Source** na Adobe Experience Platform.

Após configurar os conectores, é possível configurar uma importação ou exportação de dados para o Campaign Standard usando workflows.

![](assets/rtcdp-schema.png)

Para obter mais detalhes sobre como configurar esses processos de importação e exportação, consulte estas seções:

* [Assimilar públicos-alvos da Adobe Experience Platform no Campaign](../../integrating/using/ingest-aep-data.md)
* [Exportar dados do Campaign para a Adobe Experience Platform](../../integrating/using/export-campaign-data.md)
