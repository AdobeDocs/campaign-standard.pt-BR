---
solution: Campaign Standard
product: campaign
title: Introdução a fontes e destinos
description: Saiba mais sobre Fontes e Destinos do Adobe Experience Platform.
audience: integrating
content-type: reference
feature: Sources and Destinations
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: ebbdea387a547cd95c96681faed0a20b37edaf0f
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 1%

---


# Introdução às Fontes e Destinos {#rtcdp}

## Sobre fontes e destinos

Com o Adobe Experience Platform, você pode compartilhar dados entre o Campaign Standard e o Adobe Real-time Customer Data Platform (RTCDP). Isso permite direcionar os públicos-alvo da Adobe Experience Platform nos fluxos de trabalho do Campaign e enviar de volta para o Adobe Real-time Customer Data Platform relacionados a esses públicos-alvo, como envios, aberturas e cliques.

* Com **Destinos**, assimile públicos do Adobe Experience Platform ao Campaign Standard. Isso permite ativar seus dados conhecidos e desconhecidos para suas campanhas de marketing.
* Com **Fontes**, exporte dados Campaign Standard (por exemplo, envia, abre, clica) para o Adobe Experience Platform. Isso permite centralizar os dados coletados de fontes diferentes em um único local e usar os insights obtidos com eles para fazer mais.


>[!IMPORTANT]
>
>Lembre-se dos limites de armazenamento SFTP, limites de armazenamento de banco de dados e limites de perfil ativos de acordo com seu contrato da Adobe Campaign ao executar essa integração.

Para obter uma visão geral mais detalhada do Adobe Real-time Customer Data Platform, Destinos e Fontes, consulte estas páginas:

* [Plataforma de dados do cliente em tempo real da Adobe](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html)
* [Documentação de destinos](https://experienceleague.adobe.com/docs/experience-platform/destinations/home.html)
* [Documentação de fontes](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html)

## Conecte o Campaign Standard ao Adobe Experience Platform

Para compartilhar dados entre o Adobe Experience Platform e o Campaign Standard, primeiro é necessário conectar o Adobe Campaign como um **Destino** e conectar seu local de armazenamento de blobs do AWS S3 ou Azure como um **Origem** na Adobe experience Platform.

Após configurar os conectores, é possível configurar uma importação de dados ou exportar para o Campaign Standard usando workflows.

![](assets/rtcdp-schema.png)

Para obter mais detalhes sobre como configurar esses processos de importação e exportação, consulte estas seções:

* [Assimilar públicos da Adobe Experience Platform no Campaign](../../integrating/using/ingest-aep-data.md)
* [Exportar dados do Campaign para o Adobe Experience Platform](../../integrating/using/export-campaign-data.md)
