---
title: Sobre o serviço Destinos do Audience
description: Saiba mais sobre o serviço Destinos da Audiência.
page-status-flag: never-activated
uuid: b3996642-96ec-489e-b146-c8c2cb52aa32
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-audiences
discoiquuid: 750ecd8d-67a5-4180-bfec-2a8e3098c812
context-tags: audience,wizard;audience,overview;delivery,audience,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e1fa546313e8d543685ef30a072ae2d97c5bf236

---


# Sobre o serviço Destinos do Audience {#about-audiences}

>[!IMPORTANT]
>
>O serviço Destinos de Audiência está atualmente em beta, o que pode estar sujeito a atualizações frequentes sem aviso prévio. Os clientes precisam estar hospedados no Azure (atualmente em beta somente para a América do Norte) para acessar esses recursos. Entre em contato com o Atendimento ao cliente da Adobe se desejar acessar.

Capacite suas experiências de consumidores aproveitando a plataforma [](https://docs.adobe.com/content/help/en/experience-platform/landing/home.html) Adobe Experience para criar audiências altamente direcionadas com base em conjuntos de dados grandes e complexos. A plataforma Adobe Experience consolida dados de perfil, comportamento e várias entidades em fontes online e offline, incluindo o Adobe Analytics, para ajudá-lo a criar uma visualização de 360 graus do seu cliente, permitindo que você gerencie com eficácia suas experiências de cliente.

O Adobe Campaign Standard usará o serviço de Destinos **de** Audiência para recuperar uma coleção de perfis, conhecida como **Audiência**, da Adobe Experience Platform para programas de campanhas em várias etapas e/ou canais.

**As Audiências** são criadas pela primeira vez criando **segmentos**, que são essencialmente um conjunto de regras baseado em praticamente qualquer variável (por exemplo, dados de perfil, evento e várias entidades) dentro de um perfil de cliente da Adobe Experience Platform para criar um público alvo multidimensional. Os conceitos globais nos serviços de Perfil e segmentação unificados são referenciados nestes documentos dedicados:

* [Visão geral do Perfil do cliente em tempo real](https://docs.adobe.com/content/help/en/experience-platform/profile/home.html)
* [Visão geral do Serviço de segmentação](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html)

Depois que um segmento é criado, você pode ativá-lo como uma audiência para um delivery em workflows [](../../automating/using/aep-targeting-audiences.md)Campaign Standard. Além disso, você pode usar dados contextuais da Adobe Experience Platform para [personalizar](../../automating/using/aep-personalizing-campaigns.md) e adicionar conteúdo dinâmico às suas campanhas.

Os vídeos passo a passo também estão disponíveis [nesta seção](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html).

Termos usados nestas seções:

* **Perfil**: O Perfil é um modelo de dados padrão da plataforma Experience, usado para definir os atributos dos consumidores. Um perfil também pode ser uma agregação de dados e atributos do evento relacionados a uma pessoa e/ou dispositivo.

   Exemplo: &quot;John Doe é um homem de 55 anos.&quot;

* **Segmento**: Um conjunto de regras que define um subconjunto de perfis do banco de dados, usando atributos e dados de evento.

   Exemplo: &quot;Masculino > 50 anos.&quot;

* **Audiência**: Uma coleção de perfis que atendem às regras do segmento.

   Exemplo: Lista de perfis correspondentes a todos os machos > 50 anos em seu banco de dados.
