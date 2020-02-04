---
title: Sobre o serviço Destinos de público-alvo
description: Saiba mais sobre o serviço de Destinos de público-alvo.
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
source-git-commit: ff3b41589f47e7697a69bb68824aefd4d9036793

---


# Sobre o serviço Destinos de público-alvo {#about-audiences}

>[!IMPORTANT]
>
>O serviço de Destinos de público-alvo está atualmente em beta, o que pode estar sujeito a atualizações frequentes sem aviso prévio. Os clientes precisam estar hospedados no Azure (atualmente em beta somente para a América do Norte) para acessar esses recursos. Entre em contato com o Atendimento ao cliente da Adobe se desejar acessar.

Capacite suas experiências de consumidores aproveitando a [Adobe Experience Platform](https://www.adobe.io/apis/experienceplatform/home.html) (AEP) para criar públicos-alvo altamente direcionados com base em conjuntos de dados grandes e complexos. A plataforma Adobe Experience consolida dados de perfil, comportamento e multientidade em fontes online e offline, incluindo o Adobe Analytics, para ajudá-lo a criar uma visão de 360 graus do seu cliente, permitindo que você gerencie com eficácia suas experiências de cliente.

O Adobe Campaign Standard usará o serviço Destinos **de** público-alvo para recuperar uma coleção de perfis, conhecidos como **Públicos-alvo**, da AEP para programas de campanha de várias etapas e/ou entre canais.

**Os públicos** são criados pela primeira vez criando **segmentos**, que são essencialmente um conjunto de regras baseado em praticamente qualquer variável (por exemplo, perfil, evento, dados de várias entidades) dentro de um perfil de cliente da AEP para criar uma meta multidimensional. Os conceitos globais nos Serviços de perfil e segmentação unificados podem ser referenciados [nesses documentos](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation.html)dedicados.

Depois que um segmento é criado, você pode ativá-lo como um público-alvo para uma entrega nos fluxos de trabalho [do](../../automating/using/aep-targeting-audiences.md)Campaign Standard. Além disso, você pode usar dados contextuais da Adobe Experience Platform para [personalizar](../../automating/using/aep-personalizing-campaigns.md) e adicionar conteúdo dinâmico às suas campanhas, se desejar.

Os vídeos de demonstração também estão disponíveis [nesta seção](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html).

Termos usados nestas seções:

* **Perfil**: Perfil é um modelo de dados padrão da Plataforma de experiência usado para definir atributos dos consumidores. Um perfil também pode ser um agregado de dados e atributos do evento relacionados a uma pessoa e/ou dispositivo.

   Exemplo: &quot;John Doe é um homem de 55 anos.&quot;

* **Segmento**: Um conjunto de regras que define um subconjunto de perfis do banco de dados, usando atributos e dados de eventos.

   Exemplo: &quot;Masculino > 50 anos.&quot;

* **Público-alvo**: Uma coleção de perfis que atendem às regras do segmento.

   Exemplo: Lista de perfis que correspondem a todos os homens > 50 anos no banco de dados.
