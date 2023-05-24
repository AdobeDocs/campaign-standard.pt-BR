---
title: Promoção de um serviço
description: Use o Adobe Campaign para promover um serviço e envolver seus clientes por meio de páginas de aterrissagem dedicadas, emails ou diretamente no seu site.
audience: audiences
content-type: reference
topic-tags: managing-subscriptions
feature: Audiences
role: User
level: Intermediate
exl-id: c1f8770a-8b25-41db-aa52-828e181a563d
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 3%

---

# Promoção de um serviço{#promoting-a-service}

Você pode oferecer assinaturas de um serviço de várias maneiras e dar aos seus visitantes a capacidade de gerenciar suas assinaturas.

Você pode usar o Campaign para promover um serviço ao:

* [Inserção de um link de subscrição ou unsubscription de serviço em um email](../../designing/using/links.md#inserting-a-link).

* [Inserção de um link para uma landing page de subscrição ou unsubscription em um email](../../designing/using/links.md). Nesse caso, o serviço deve ser referenciado diretamente nas propriedades das landing pages relacionadas (consulte [Vinculação de uma landing page a um serviço](../../channels/using/configuring-landing-page.md#linking-a-landing-page-to-a-service)).

   >[!NOTE]
   >
   >Também é importante dar aos assinantes a possibilidade de cancelar a assinatura. Para fazer isso, insira um serviço <b>Link de cancelamento de subscrição</b> no email de confirmação (definido nas propriedades do serviço) enviado automaticamente aos novos assinantes, bem como nos emails de informativos futuros.

* Disponibilização de uma landing page de subscrição ou unsubscription em um site. Os URLs que dão acesso à landing page devem especificar parâmetros como o serviço associado, bem como a ID do perfil que está acessando-a. Essa ID pode ser definida nos parâmetros da landing page (consulte [Configuração de uma landing page](../../channels/using/configuring-landing-page.md)).
