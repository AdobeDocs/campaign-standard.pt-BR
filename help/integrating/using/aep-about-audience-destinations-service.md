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
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 2%

---

# Sobre o serviço de destinos de público {#about-audiences}

>[!IMPORTANT]
>
>O serviço Audience Destinations está atualmente em beta, o que pode estar sujeito a atualizações frequentes sem aviso prévio. Os clientes precisam ser hospedados no Azure (atualmente em beta somente para a América do Norte) para acessar esses recursos. Entre em contato com o Atendimento ao cliente do Adobe se desejar acesso.

Capacite suas experiências de consumidores aproveitando o [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/home.html) para criar públicos altamente direcionados com base em conjuntos de dados grandes e complexos. A Adobe Experience Platform consolida dados de perfil, comportamento e várias entidades em fontes online e offline, incluindo o Adobe Analytics, para ajudá-lo a criar uma visualização de 360 graus do cliente, permitindo que você gerencie com eficiência as experiências do cliente.

O Adobe Campaign Standard usará o serviço **Audience Destinations** para recuperar uma coleção de perfis, conhecida como **Audiences**, do Adobe Experience Platform para programas de campanha de várias etapas e/ou entre canais.

**** Os públicos-alvo são criados pela primeira vez em  **segmentos**, que são essencialmente um conjunto de regras baseado em praticamente qualquer variável (por exemplo, perfil, evento, dados de várias entidades) em um perfil de cliente do Adobe Experience Platform para criar um público-alvo multidimensional. Os conceitos globais sobre o Perfil do cliente em tempo real e os Serviços de segmentação são mencionados nestes documentos dedicados:

* [Visão geral do perfil do cliente em tempo real](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html)
* [Visão geral do serviço de segmentação](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html)

Depois que um segmento é criado, você pode ativá-lo como um público-alvo para um delivery em [Campaign Standard workflows](../../integrating/using/aep-targeting-audiences.md). Além disso, você pode usar dados contextuais da Adobe Experience Platform para [personalizar](../../integrating/using/aep-personalizing-campaigns.md) e adicionar conteúdo dinâmico às suas campanhas.

![](assets/do-not-localize/how-to-video.png) Vídeos explicativos também estão disponíveis  [nesta seção](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html).

Termos usados nestas seções:

* **Perfil**: Perfil é um modelo de dados padrão do Experience Platform usado para definir atributos dos consumidores. Um perfil também pode ser um agregado de dados e atributos do evento relacionados a uma pessoa e um dispositivo.

   Exemplo: &quot;John Doe é um homem de 55 anos.&quot;

* **Segmento**: Um conjunto de regras que define um subconjunto de perfis do banco de dados, usando atributos e dados de evento.

   Exemplo: &quot;Masculino > 50 anos.&quot;

* **Público-alvo**: Uma coleção de perfis que atendem às regras de segmentos.

   Exemplo: Lista de perfis correspondentes a todos os homens > 50 anos no banco de dados.
