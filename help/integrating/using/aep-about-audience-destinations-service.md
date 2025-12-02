---
title: Sobre o serviço de destinos de público
description: Saiba mais sobre o serviço Destinos do Audience.
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 34235749-d056-4d4c-9939-7dc52f980a76
hide: true
hidefromtoc: true
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 2%

---

# Sobre o serviço de destinos de público {#about-audiences}

>[!IMPORTANT]
>
>O serviço Audience Destinations foi descontinuado. Embora os recursos obsoletos ainda estejam disponíveis, eles não serão aprimorados nem terão suporte. Saiba mais [nesta página](../../rn/using/deprecated-features.md)

Capacite suas experiências de consumidor aproveitando o [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/home.html) para criar públicos-alvo altamente direcionados com base em conjuntos de dados grandes e complexos. O Adobe Experience Platform consolida dados de perfil, comportamentais e de várias entidades em fontes online e offline, incluindo o Adobe Analytics, para ajudar você a criar uma visualização de 360 graus do seu cliente, permitindo que você gerencie com eficiência as experiências dele.

O Adobe Campaign Standard usará o serviço **Destinos do público-alvo** para recuperar uma coleção de perfis, conhecidos como **Públicos-alvo**, do Adobe Experience Platform para programas de campanha em várias etapas e/ou entre canais.

**Públicos-alvo** são criados pela primeira vez, criando **segmentos**, que são essencialmente um conjunto de regras baseadas em praticamente qualquer variável (por exemplo, perfil, evento, dados de várias entidades) dentro de um perfil de cliente do Adobe Experience Platform para criar um destino multidimensional. Os conceitos globais sobre o Perfil do cliente em tempo real e os Serviços de segmentação são referenciados nestes documentos dedicados:

* [Visão geral do Perfil do cliente em tempo real](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html)
* [Visão geral do Serviço de segmentação](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html)

Depois que um segmento é criado, você pode ativá-lo como um público-alvo para uma entrega em [fluxos de trabalho do Campaign Standard](../../integrating/using/aep-targeting-audiences.md). Além disso, você pode usar dados contextuais da Adobe Experience Platform para [personalizar](../../integrating/using/aep-personalizing-campaigns.md) e adicionar conteúdo dinâmico às suas campanhas.

Os vídeos de instrução ![](assets/do-not-localize/how-to-video.png) também estão disponíveis em [esta seção](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html).

Termos usados nestas seções:

* **Perfil**: o perfil é um modelo de dados padrão da Experience Platform usado para definir atributos de consumidores. Um perfil também pode ser um agregado de dados e atributos de eventos relacionados a uma pessoa e/ou dispositivo.

  Exemplo: &quot;John Doe é um homem de 55 anos.&quot;

* **Segmento**: um conjunto de regras que define um subconjunto de perfis do seu banco de dados, usando atributos e dados de evento.

  Exemplo: &quot;Machos > 50 anos&quot;.

* **Público-alvo**: uma coleção de perfis que atendem às regras de segmento.

  Exemplo: lista de perfis que correspondem a todos os homens > 50 anos no banco de dados.
