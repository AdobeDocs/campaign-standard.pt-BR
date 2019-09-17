---
title: Sobre páginas de aterrissagem
seo-title: Sobre páginas de aterrissagem
description: Sobre páginas de aterrissagem
seo-description: Descubra as páginas iniciais da Campanha e seu ciclo de vida.
page-status-flag: nunca ativado
uuid: b316bf47-7d98-46fa-ab4f-67ff50de8095
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: canais
content-type: referência
topic-tags: páginas de aterrissagem
discoiquuid: ca8d1698-6e8a-4f5a-b017-74a152e14286
context-tags: landingPage,assistente;landingPage,overview;landingPage,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4084346b537bb483c5519c26d71880d3c57a7e44

---


# Sobre páginas de aterrissagem{#about-landing-pages}

A campanha vem com páginas de aterrissagem que são formulários da Web que podem ser usados para capturar informações em seus públicos-alvo, oferecer assinaturas para um serviço, exibir dados e aumentar seu banco de dados. As páginas iniciais também podem ser usadas para adquirir ou atualizar perfis existentes.

>[!CAUTION]
>
>As páginas iniciais só podem ser usadas para atualizar perfis.

A campanha vem com um conjunto de modelos incorporados de página de aterrissagem:

* **[!UICONTROL Acquisition]**: este é o modelo padrão para páginas iniciais, que permite capturar e atualizar dados no banco de dados do Campaign.
* **[!UICONTROL Subscription]**: este modelo deve ser usado para oferecer assinaturas para um serviço.
* **[!UICONTROL Unsubscription]**: este modelo pode ser vinculado a partir de um email enviado aos assinantes para um serviço, para permitir que eles cancelem a assinatura deste serviço.
* **[!UICONTROL Blacklist]**: este modelo deve ser usado quando um perfil não quiser mais ser contatado pelo Campaign. Para obter mais informações sobre a lista negra, consulte [Sobre aceitação e não participação no Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

Esses modelos são propostos por padrão ao criar uma nova página inicial.

![](assets/lp_creation_1.png)

A Adobe recomenda criar seus próprios modelos duplicando um modelo incorporado. Alguns parâmetros só podem ser definidos em modelos de página inicial e não podem ser modificados diretamente em páginas iniciais.

>[!NOTE]
>
>Para acessar modelos de página inicial, clique no logotipo do Adobe Campaign no canto superior esquerdo e selecione **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Landing page templates]**.

O ciclo de vida completo de uma página de aterrissagem é o seguinte:

1. Criação: crie e defina o conteúdo da página de aterrissagem.
1. Teste: simule a execução da página inicial em um perfil de teste.
1. Publicação: publique a página de aterrissagem para colocá-la ao vivo.
1. Expiração ou publicação: cancele a publicação manualmente ou aguarde até que a página de aterrissagem expire e então ela não estará mais disponível.

![](assets/lp_livecycle.png)

Depois de criada e publicada, você pode tornar a página de aterrissagem acessível por meio de um site ou [inserindo um link direto para a página de aterrissagem em um email](../../designing/using/links.md#inserting-a-link).

**Tópicos relacionados:**

* [Criação de um vídeo de página](https://helpx.adobe.com/campaign/kt/acs/using/acs-create-edit-landing-page-feature-video-use.html) de aterrissagem
* [Usar uma página de aterrissagem para assinar um serviço](../../audiences/using/creating-a-service.md)