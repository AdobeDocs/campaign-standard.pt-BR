---
solution: Campaign Standard
product: campaign
title: Sobre o serviço Destinos do Audience
description: Saiba mais sobre o serviço Destinos do público-alvo.
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
translation-type: tm+mt
source-git-commit: 35d61efce8d752ea30b7eaad55e6c23d4debd853
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 7%

---


# Sobre o serviço Destinos do Audience {#about-audiences}

>[!IMPORTANT]
>
>O serviço Audience Destinations está atualmente em beta, o que pode estar sujeito a atualizações frequentes sem aviso prévio. Os clientes precisam ser hospedados no Azure (atualmente em beta somente para a América do Norte) para acessar esses recursos. Entre em contato com o Atendimento ao cliente da Adobe se desejar acesso.

Capacite suas experiências de consumidor aproveitando a [Adobe Experience Platform](https://docs.adobe.com/content/help/en/experience-platform/landing/home.html) para criar públicos altamente direcionados com base em conjuntos de dados grandes e complexos. A Adobe Experience Platform consolida dados de perfil, comportamento e várias entidades em fontes online e offline, incluindo o Adobe Analytics, para ajudá-lo a criar uma visualização de 360 graus do cliente, permitindo que você gerencie com eficiência as experiências dele.

O Adobe Campaign Standard usará o serviço **Audience Destinations** para recuperar uma coleção de perfis, conhecida como **Audiences**, da Adobe Experience Platform para programas de campanha de várias etapas e/ou entre canais.

**** Os públicos-alvo são criados pela primeira vez em  **segmentos**, que são essencialmente um conjunto de regras baseado em praticamente qualquer variável (por exemplo, perfil, evento, dados de várias entidades) em um perfil de cliente da Adobe Experience Platform para criar um público-alvo multidimensional. Os conceitos globais sobre o Perfil do cliente em tempo real e os Serviços de segmentação são mencionados nestes documentos dedicados:

* [Visão geral do perfil do cliente em tempo real](https://docs.adobe.com/content/help/en/experience-platform/profile/home.html)
* [Visão geral do serviço de segmentação](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html)

Depois que um segmento é criado, você pode ativá-lo como um público-alvo para um delivery em [Workflows do Campaign Standard](../../integrating/using/aep-targeting-audiences.md). Além disso, você pode usar dados contextuais da Adobe Experience Platform para [personalizar](../../integrating/using/aep-personalizing-campaigns.md) e adicionar conteúdo dinâmico às campanhas.

![](assets/do-not-localize/how-to-video.png) Vídeos explicativos também estão disponíveis  [nesta seção](https://docs.adobe.com/content/help/pt-BR/campaign-standard-learn/tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.translate.html).

Termos usados nestas seções:

* **Perfil**: Perfil é um modelo de dados padrão da Experience Platform usado para definir atributos dos consumidores. Um perfil também pode ser um agregado de dados e atributos do evento relacionados a uma pessoa e um dispositivo.

   Exemplo: &quot;John Doe é um homem de 55 anos.&quot;

* **Segmento**: Um conjunto de regras que define um subconjunto de perfis do banco de dados, usando atributos e dados de evento.

   Exemplo: &quot;Masculino > 50 anos.&quot;

* **Público-alvo**: Uma coleção de perfis que atendem às regras de segmentos.

   Exemplo: Lista de perfis correspondentes a todos os homens > 50 anos no banco de dados.
