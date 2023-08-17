---
title: Sobre o serviço de destinos de público
description: Saiba mais sobre o serviço Destinos do Audience.
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
>O serviço Audience Destinations está atualmente em versão beta, que pode estar sujeita a atualizações frequentes sem aviso prévio. Os clientes precisam ser hospedados no Azure (atualmente na versão beta somente para a América do Norte) para acessar esses recursos. Entre em contato com o Atendimento ao cliente do Adobe se desejar obter acesso.

Capacite as experiências do seu consumidor aproveitando o [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/home.html) criar públicos-alvo altamente direcionados com base em conjuntos de dados grandes e complexos. O Adobe Experience Platform consolida dados de perfil, comportamentais e de várias entidades em fontes online e offline, incluindo o Adobe Analytics, para ajudar você a criar uma visualização de 360 graus do seu cliente, permitindo que você gerencie com eficiência as experiências dele.

A Adobe Campaign Standard usará o **Audience Destinations** serviço para recuperar uma coleção de perfis, conhecido como **Públicos-alvo**, da Adobe Experience Platform para programas de campanha em várias etapas e/ou entre canais.

**Públicos-alvo** são criados pela primeira criação **segmentos**, que são essencialmente um conjunto de regras baseadas em praticamente qualquer variável (por exemplo, perfil, evento, dados de várias entidades) em um perfil de cliente do Adobe Experience Platform para criar um público-alvo multidimensional. Os conceitos globais sobre o Perfil do cliente em tempo real e os Serviços de segmentação são referenciados nestes documentos dedicados:

* [Visão geral do Perfil do cliente em tempo real](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html)
* [Visão geral do serviço de segmentação](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html)

Depois que um segmento é criado, você pode ativá-lo como um público-alvo para um delivery no [workflows do Campaign Standard](../../integrating/using/aep-targeting-audiences.md). Além disso, é possível usar dados contextuais da Adobe Experience Platform para [personalizar](../../integrating/using/aep-personalizing-campaigns.md) e adicionar conteúdo dinâmico às suas campanhas.

![](assets/do-not-localize/how-to-video.png) Vídeos explicativos também estão disponíveis no [nesta seção](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html).

Termos usados nestas seções:

* **Perfil**: Perfil é um modelo de dados padrão Experience Platform usado para definir atributos de consumidores. Um perfil também pode ser um agregado de dados e atributos de eventos relacionados a uma pessoa e/ou dispositivo.

  Exemplo: &quot;John Doe é um homem de 55 anos.&quot;

* **Segmento**: um conjunto de regras que define um subconjunto de perfis do banco de dados, usando atributos e dados de evento.

  Exemplo: &quot;Machos > 50 anos&quot;.

* **Público**: uma coleção de perfis que atendem às regras de segmento.

  Exemplo: lista de perfis que correspondem a todos os homens > 50 anos no banco de dados.
