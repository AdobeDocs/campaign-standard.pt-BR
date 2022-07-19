---
title: Sobre o serviço de destinos de público
description: Saiba mais sobre o serviço Destinos do público-alvo.
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: 34235749-d056-4d4c-9939-7dc52f980a76
hide: true
hidefromtoc: true
source-git-commit: 26394f3f6fd9b67996c30924c376533380e8f4d6
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 2%

---

# Sobre o serviço de destinos de público {#about-audiences}

>[!IMPORTANT]
>
>O serviço Audience Destinations está atualmente em beta, o que pode estar sujeito a atualizações frequentes sem aviso prévio. Os clientes precisam ser hospedados no Azure (atualmente em beta somente para a América do Norte) para acessar esses recursos. Entre em contato com o Atendimento ao cliente do Adobe se desejar acesso.

Capacite suas experiências de consumidores aproveitando a [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/home.html) para criar públicos-alvo altamente direcionados com base em conjuntos de dados grandes e complexos. A Adobe Experience Platform consolida dados de perfil, comportamento e várias entidades em fontes online e offline, incluindo o Adobe Analytics, para ajudá-lo a criar uma visualização de 360 graus do cliente, permitindo que você gerencie com eficiência as experiências do cliente.

A Adobe Campaign Standard usará a variável **Destinos do público-alvo** para recuperar uma coleção de perfis, conhecida como **Públicos-alvo**, do Adobe Experience Platform para programas de campanha de várias etapas e/ou entre canais.

**Públicos-alvo** são criados pela primeira criação **segmentos**, que são essencialmente um conjunto de regras baseado em praticamente qualquer variável (por exemplo, perfil, evento, dados de várias entidades) em um perfil de cliente do Adobe Experience Platform para criar um target multidimensional. Os conceitos globais sobre o Perfil do cliente em tempo real e os Serviços de segmentação são mencionados nestes documentos dedicados:

* [Visão geral do perfil do cliente em tempo real](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html)
* [Visão geral do serviço de segmentação](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html)

Depois que um segmento é criado, você pode ativá-lo como um público-alvo para um delivery em [Fluxos de trabalho Campaign Standard](../../integrating/using/aep-targeting-audiences.md). Além disso, você pode usar dados contextuais da Adobe Experience Platform para [personalizar](../../integrating/using/aep-personalizing-campaigns.md) e adicionar conteúdo dinâmico às suas campanhas.

![](assets/do-not-localize/how-to-video.png) Vídeos explicativos também estão disponíveis em [esta seção](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html).

Termos usados nestas seções:

* **Perfil**: Perfil é um modelo de dados padrão do Experience Platform usado para definir atributos dos consumidores. Um perfil também pode ser um agregado de dados e atributos do evento relacionados a uma pessoa e um dispositivo.

   Exemplo: &quot;John Doe é um homem de 55 anos.&quot;

* **Segmento**: Um conjunto de regras que define um subconjunto de perfis do banco de dados, usando atributos e dados de evento.

   Exemplo: &quot;Masculino > 50 anos.&quot;

* **Público**: Uma coleção de perfis que atendem às regras de segmentos.

   Exemplo: Lista de perfis correspondentes a todos os homens > 50 anos no banco de dados.
