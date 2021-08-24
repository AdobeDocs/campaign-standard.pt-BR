---
solution: Campaign Standard
product: campaign
title: Introdução a origens e destinos
description: Saiba mais sobre origens e destinos da Adobe Experience Platform.
audience: integrating
content-type: reference
role: Data Architect
level: Intermediate
exl-id: ba6205fa-dbcf-497a-882f-f15c00f12e68
source-git-commit: ca8473f50b132b2d5ca58c6403d144fbf62741b0
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 64%

---

# Introdução a origens e destinos {#rtcdp}

## Sobre origens e destinos

Com o Adobe Experience Platform, você pode compartilhar dados entre o Campaign Standard e o Adobe Real-time Customer Data Platform (RTCDP). Isso permite direcionar os públicos da Adobe Experience Platform nos workflows do Campaign e enviar de volta para a Plataforma de dados do cliente em tempo real da Adobe relacionados a esses públicos, como envios, aberturas e cliques.

* Com **Destinos**, assimile públicos do Adobe Experience Platform ao Campaign Standard. Isso permite ativar os dados conhecidos e desconhecidos para suas campanhas de marketing.
* Com **Fontes**, exporte dados Campaign Standard (por exemplo, envia, abre, clica) para o Adobe Experience Platform. Isso permite centralizar os dados coletados de origens diferentes em um único local e usar os insights obtidos com eles para fazer mais.


>[!IMPORTANT]
>
>Lembre-se dos limites de armazenamento SFTP, armazenamento do banco de dados e perfil ativo conforme o contrato do Adobe Campaign ao fazer essa integração.

Para obter uma visão geral mais detalhada da Plataforma de dados do cliente em tempo real da Adobe, Origens e Fontes, consulte estas páginas:

* [Plataforma de dados do cliente em tempo real da Adobe](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=pt-BR)
* [Documentação de destinos](https://experienceleague.adobe.com/docs/experience-platform/destinations/home.html?lang=pt-BR)
* [Documentação de origens](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=pt-BR)

## Conecte o Campaign Standard ao Adobe Experience Platform

Para compartilhar dados entre o Adobe Experience Platform e o Campaign Standard, primeiro é necessário conectar o Adobe Campaign como um **Destino** e conectar seu local de armazenamento de blobs do AWS S3 ou Azure como um **Origem** na Adobe experience Platform.

Após configurar os conectores, é possível configurar uma importação de dados ou exportar para o Campaign Standard usando workflows.

![](assets/rtcdp-schema.png)

Para obter mais detalhes sobre como configurar esses processos de importação e exportação, consulte estas seções:

* [Assimilar públicos da Adobe Experience Platform no Campaign](../../integrating/using/ingest-aep-data.md)
* [Exportar dados do Campaign para a Adobe Experience Platform](../../integrating/using/export-campaign-data.md)
