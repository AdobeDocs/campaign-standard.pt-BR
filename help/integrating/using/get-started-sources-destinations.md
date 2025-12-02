---
title: Introdução a origens e destinos
description: Saiba mais sobre origens e destinos da Adobe Experience Platform.
audience: integrating
content-type: reference
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: ba6205fa-dbcf-497a-882f-f15c00f12e68
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 62%

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

* [Plataforma de dados do cliente em tempo real da Adobe](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=pt-BR)
* [Documentação de destinos](https://experienceleague.adobe.com/docs/experience-platform/destinations/home.html?lang=pt-BR)
* [Documentação de origens](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=pt-BR)

## Conectar o Campaign Standard com o Adobe Experience Platform

Para compartilhar dados entre o Adobe Experience Platform e a Campaign Standard, primeiro é necessário conectar o Adobe Campaign como um **Destino** e conectar seu local de armazenamento de blobs do AWS S3 ou do Azure como um **Source** na Adobe Experience Platform.

Após configurar os conectores, é possível configurar uma importação ou exportação de dados para o Campaign Standard usando workflows.

![](assets/rtcdp-schema.png)

Para obter mais detalhes sobre como configurar esses processos de importação e exportação, consulte estas seções:

* [Assimilar públicos-alvos da Adobe Experience Platform no Campaign](../../integrating/using/ingest-aep-data.md)
* [Exportar dados do Campaign para a Adobe Experience Platform](../../integrating/using/export-campaign-data.md)
