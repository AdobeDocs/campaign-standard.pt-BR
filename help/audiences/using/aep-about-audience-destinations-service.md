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
source-git-commit: 1059b840d9a2d0c89a6cbd1808b645862747a76c

---


# Sobre o serviço Destinos de público-alvo {#about-audiences}

>[!IMPORTANT]
>
>O serviço de Destinos de público-alvo está atualmente em beta, o que pode estar sujeito a atualizações frequentes sem aviso prévio. Os clientes precisam estar hospedados no Azure (atualmente em beta somente para a América do Norte) para acessar esses recursos. Entre em contato com o Atendimento ao cliente da Adobe se desejar acessar.

O serviço **Destinos de** público-alvo permite criar públicos altamente direcionados com base em conjuntos de dados grandes e complexos e compartilhar esses segmentos em tempo real com outras soluções da Adobe Experience Cloud.

A plataforma [](https://www.adobe.io/apis/experienceplatform/home.html) Adobe Experience consolida dados de perfil, comportamento e várias entidades para ajudá-lo a criar uma visualização 360 do seu cliente, permitindo que você gerencie com eficácia suas experiências do cliente.

O Campaign Standard permite que você trabalhe com a Adobe Experience Platform para identificar coleções de perfis, conhecidas como **Públicos**. Eles são criados por meio da criação de **segmentos**, que são regras que incluem atributos de perfil e dados de evento provenientes da plataforma Adobe Experience. Os conceitos globais nos Serviços de perfil e segmentação unificados podem ser referenciados [nesses documentos](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation.html)dedicados.

Depois que um público-alvo é criado, você pode ativá-lo para uma entrega nos fluxos de trabalho [do](../../automating/using/aep-targeting-audiences.md)Campaign Standard. Além disso, você pode usar dados contextuais da Adobe Experience Platform para [personalizar](../../automating/using/aep-personalizing-campaigns.md) e adicionar conteúdo dinâmico às suas campanhas, se desejar.

Vídeos de demonstração também estão disponíveis [nesta página](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/leveraging-aep-audiences-overview.html)

Termos usados nestas seções:

* **Perfil**: Perfil é um modelo de dados padrão da Plataforma de experiência usado para definir atributos dos consumidores. Um perfil também pode ser um agregado de dados e atributos do evento relacionados a uma pessoa e/ou dispositivo.

   Exemplo: &quot;John Doe é um homem de 55 anos.&quot;

* **Segmento**: Um conjunto de regras que define um subconjunto de perfis do banco de dados, usando atributos e dados de eventos.

   Exemplo: &quot;Masculino > 50 anos.&quot;

* **Público-alvo**: Uma coleção de perfis que atendem às regras do segmento.

   Exemplo: Lista de perfis que correspondem a todos os homens > 50 anos no banco de dados.
