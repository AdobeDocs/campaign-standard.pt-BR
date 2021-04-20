---
solution: Campaign Standard
product: campaign
title: Introdução a mensagens transacionais
description: Descubra que mensagens transacionais são e saiba mais sobre as principais etapas para configurar uma mensagem transacional no Adobe Campaign Standard.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: Business Practitioner
level: Beginner
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '968'
ht-degree: 10%

---


# Introdução a mensagens transacionais {#getting-started-with-transactional-messaging}

## Visão geral {#overview}

<img src="assets/do-not-localize/icon_transactional.svg" width="60px">

Uma mensagem transacional é uma comunicação individual e exclusiva, enviada em tempo real por um provedor, como um site. É particularmente esperado, pois contém informações importantes que o recipient deseja verificar ou confirmar.

* **Quando é devido?** Como essa mensagem contém informações importantes, o usuário espera que ela seja enviada em tempo real. Consequentemente, o atraso entre o evento acionado e a mensagem recebida deve ser muito curto.

* **Por que é importante?** Geralmente, uma mensagem transacional tem altas taxas de abertura. Por conseguinte, deve ser cuidadosamente concebido, uma vez que pode ter um forte impacto no comportamento dos clientes, na medida em que define a relação com o cliente.

* **Por exemplo?** Pode ser uma mensagem de boas-vindas após criar uma conta, uma confirmação de que um pedido foi enviado, uma fatura, uma mensagem confirmando uma alteração de senha ou uma notificação depois que um cliente navegou em seu site, etc.

O Adobe Campaign permite integrar essa funcionalidade a um sistema de informações que envia eventos que serão transformados em mensagens transacionais personalizadas.

As mensagens transacionais podem ser enviadas por email, SMS ou [notificação por push](../../channels/using/transactional-push-notifications.md), dependendo de suas opções. Verifique o contrato de licença.

>[!NOTE]
>
>O Adobe Campaign prioriza o processamento de mensagens transacionais antes de qualquer outro delivery.

<!--Guidelines to implement transactional messaging capabilities in your website are detailed in [this section](../../api/using/managing-transactional-messages.md).-->

Antes de começar com mensagens transacionais, leia as [práticas recomendadas e limitações](../../channels/using/transactional-messaging-limitations.md) correspondentes.

## Princípio operacional das mensagens transacionais {#transactional-messaging-operating-principle}

O processo geral de mensagens transacionais pode ser descrito da seguinte maneira:

![](assets/message-center-process.png)

Por exemplo, imagine que você é uma empresa com um site em que seus clientes podem comprar produtos.

O Adobe Campaign permite enviar um email de notificação para clientes que adicionaram produtos ao carrinho. Quando um deles sai do site sem passar pelas compras (evento externo que aciona um evento de Campanha), um email de abandono de carrinho é enviado automaticamente a eles (delivery de mensagem transacional).

As principais etapas para colocar isso em prática são detalhadas abaixo em [this section](#key-steps).

## Tipos de mensagem transacional {#transactional-message-types}

Dois tipos de mensagens transacionais estão disponíveis no Adobe Campaign.

**Dados de** segmentação de mensagens transacionais de evento contidos no próprio evento. Essas mensagens:
* Não contém informações de perfil e, portanto, não pode incluir links de unsubscription.
* Não são compatíveis com as regras de fadiga (mesmo no caso de um enriquecimento com perfis).
* Ter o target de delivery definido pelos dados contidos no próprio evento.

Você pode enviar uma mensagem transacional de evento para um cliente que precisa recuperar uma senha esquecida, por exemplo, ou para confirmar um pedido. Na verdade, você não deseja que o recipient cancele a assinatura desse tipo de comunicação e essa notificação não deve ser adicionada ao contador de mensagens de marketing como parte de uma regra de fadiga.

**Perfil de perfis de** segmentação de mensagens transacionais do banco de dados de marketing do Campaign. Com esse tipo de mensagem, você pode:
* Aproveite os dados contidos no banco de dados do Adobe Campaign.
* Personalize sua mensagem com informações de perfil adicionando um [enriquecimento](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content) à configuração do evento.
* Aplique [regras de tipologia de marketing](../../sending/using/managing-typology-rules.md) ou [regras de fadiga](../../sending/using/fatigue-rules.md).
* Incluir o link de unsubscription nas mensagens.
* Adicionar as mensagens transacionais aos relatórios globais do delivery.
* Usar as mensagens transacionais na jornada do cliente.

Por exemplo, você pode usar esse tipo de mensagem ao entrar em contato com seus clientes depois que eles abandonarem o carrinho em seu site, para incentivá-los a prosseguir com a compra. Ao fazer isso, você pode personalizar mais facilmente sua mensagem com acesso direto a todas as informações do banco de dados de perfis, aplicar regras de marketing e incluir essa mensagem na jornada global do cliente e gerar relatórios para obter uma melhor visão do comportamento do cliente.

O tipo de mensagem é definido ao configurar o evento que será transformado em mensagem transacional. Consulte as seções de configuração [Mensagens transacionais baseadas em eventos](../../channels/using/configuring-transactional-event.md#event-based-transactional-messages) e [Mensagens transacionais baseadas em perfil](../../channels/using/configuring-transactional-event.md#profile-based-transactional-messages) .

## Principais etapas{#key-steps}

As principais etapas ao criar e gerenciar mensagens transacionais personalizadas no Adobe Campaign são resumidas no schema abaixo.

![](assets/message-center-overview.png)

Cada uma dessas etapas é detalhada abaixo.

>[!IMPORTANT]
>
>Somente os usuários com a função [Administration](../../administration/using/users-management.md#functional-administrators) podem configurar eventos transacionais e acessar mensagens transacionais.

### Etapa 1 - Criar e publicar a configuração do evento {#create-event-configuration}

<img src="assets/do-not-localize/icon_config.svg" width="60px">

| Usuário | Ação | Resultado |
|--- |--- |--- |
| Esta etapa deve ser executada por um administrador com [direitos de administração](../../administration/using/users-management.md#functional-administrators). | Configure um evento que será chamado de &quot;Abandono do carrinho&quot; e publique essa configuração. | A API que será usada pelo desenvolvedor do site é implantada e uma mensagem transacional é criada automaticamente. |

A criação e a publicação de um evento são apresentadas nas seções [Configuração de um evento transacional](../../channels/using/configuring-transactional-event.md) e [Publicação de um evento transacional](../../channels/using/publishing-transactional-event.md) .

### Etapa 2 - Editar e publicar a mensagem transacional {#create-transactional-message}

<img src="assets/do-not-localize/icon_notification.svg" width="40px">

| Usuário | Ação | Resultado |
|--- |--- |--- |
| Essa etapa pode ser executada por um usuário de marketing com [direitos de administração](../../administration/using/users-management.md#functional-administrators). | Edite e personalize a mensagem transacional, teste-a e publique-a. | A mensagem transacional estará pronta para ser enviada. |

Para obter mais informações sobre como editar e publicar uma mensagem transacional, consulte [Edição de mensagens transacionais](../../channels/using/editing-transactional-message.md) e [Ciclo de vida da mensagem transacional](../../channels/using/publishing-transactional-message.md).

### Etapa 3 - Integrar o evento que aciona {#integrate-event-trigger}

<img src="assets/do-not-localize/icon_api.svg" width="55px">

<!--**Event triggering integration**-->

| Usuário | Ação | Resultado |
|--- |--- |--- |
| Esta etapa é executada pelo desenvolvedor do seu site. | Use a REST Transactional Messages API para integrar o evento ao seu site. | O evento será acionado quando um cliente abandonar o carrinho. |

Depois de criar um evento, é necessário integrar o acionamento desse evento no site.<!--In this example, you want a "Cart abandonment" event to be triggered whenever one of your clients leaves your website before purchasing the products in their cart.--> Para fazer isso, o desenvolvedor da Web do site deve usar a API REST do  **Adobe Campaign Standard**.

Para obter mais informações sobre como usar a API REST do Campaign para gerenciar mensagens transacionais, consulte a [documentação da API REST](../../api/using/managing-transactional-messages.md).

### Etapa 4 - Delivery de mensagem {#message-delivery}

<img src="assets/do-not-localize/icon_channels.svg" width="60px">

Depois que todas essas etapas forem executadas, a mensagem poderá ser entregue.

Assim que um usuário sair do site sem solicitar os produtos no carrinho, o evento correspondente do Campaign é acionado. O usuário recebe automaticamente um email de notificação.

## Tópicos relacionados

* [Etapas principais para enviar uma mensagem](../../channels/using/key-steps-to-send-a-message.md)
* [Introdução a canais de comunicação](../../channels/using/get-started-communication-channels.md)
* [Notificações por push transacionais](../../channels/using/transactional-push-notifications.md)
* [Mensagens de acompanhamento](../../channels/using/follow-up-messages.md)
