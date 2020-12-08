---
solution: Campaign Standard
product: campaign
title: Principais etapas para configurar um mensagen transacional
description: Descubra o que é mensagem transacional e aprenda as etapas principais para configurar um mensagen transacional no Adobe Campaign Standard.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
translation-type: tm+mt
source-git-commit: c276c468627208b584a0342414cdbe382e349f50
workflow-type: tm+mt
source-wordcount: '966'
ht-degree: 9%

---


# Introdução a mensagens transacionais {#getting-started-with-transactional-messaging}

## Visão geral {#overview}

<img src="assets/do-not-localize/icon_transactional.svg" width="60px">

Um mensagen transacional é uma comunicação individual e exclusiva, enviada em tempo real por um provedor, como um site. É particularmente esperado, pois contém informações importantes que o recipient deseja verificar ou confirmar.

* **Quando é o prazo?** Como essa mensagem contém informações importantes, o usuário espera que ela seja enviada em tempo real. Consequentemente, o atraso entre o evento desencadeado e a mensagem que chega tem de ser muito curto.

* **Por que é importante?** Geralmente, um mensagen transacional tem altas taxas de abertura. Por conseguinte, deve ser cuidadosamente concebido, uma vez que pode ter um forte impacto no comportamento dos clientes, na medida em que define a relação com os clientes.

* **Por exemplo?** Pode ser uma mensagem de boas-vindas depois de criar uma conta, uma confirmação de que um pedido foi entregue, uma fatura, uma mensagem confirmando uma alteração de senha ou uma notificação depois que um cliente navegou em seu site, etc.

A Adobe Campaign permite integrar essa funcionalidade a um sistema de informações que envia eventos que serão transformados em mensagens transacionais personalizados.

Mensagens transacionais podem ser enviados por email, SMS ou [notificação por push](../../channels/using/transactional-push-notifications.md), dependendo de suas opções. Verifique o contrato de licença.

>[!NOTE]
>
>A Adobe Campaign prioriza os mensagens transacionais de processamento em relação a qualquer outro delivery.

<!--Guidelines to implement transactional messaging capabilities in your website are detailed in [this section](../../api/using/managing-transactional-messages.md).-->

<!--All transactional messages are now sent with the Adobe Campaign Enhanced MTA for improved deliverability, throughput, and bounce handling. All impacts are the same as for standard marketing messages. For more on this, see [this section](../../administration/using/configuring-email-channel.md).-->

Antes de começar com mensagens transacionais, certifique-se de ler as [práticas recomendadas e limitações](../../channels/using/transactional-messaging-limitations.md) correspondentes.

## Princípio operacional das mensagens transacionais {#transactional-messaging-operating-principle}

O processo geral de mensagens transacionais pode ser descrito da seguinte forma:

![](assets/message-center-process.png)

Por exemplo, imagine que você é uma empresa com um site onde seus clientes podem comprar produtos.

A Adobe Campaign permite que você envie um email de notificação para clientes que adicionaram produtos ao carrinho. Quando um deles sai do seu site sem ter que fazer compras (evento externo que dispara uma evento Campanha), um email de abandono do carrinho é automaticamente enviado a ele (delivery do mensagen transacional).

As etapas principais para colocar isso em prática são detalhadas abaixo em [nesta seção](#key-steps).

## tipos de mensagens transacionais {#transactional-message-types}

Dois tipos de mensagens transacionais estão disponíveis no Adobe Campaign.

**Dados de** segmentação de mensagens transacionais do evento contidos no próprio evento. Essas mensagens:
* Não contém informações sobre perfis e, portanto, não pode incluir links de unsubscription.
* Não são compatíveis com as regras de fadiga (mesmo no caso de um enriquecimento com perfis).
* Ter o público alvo do delivery definido pelos dados contidos no próprio evento.

Você pode desejar enviar um mensagen transacional de evento a um cliente que precise recuperar uma senha esquecida, por exemplo, ou confirmar um pedido. Na verdade, você não quer que seu recipient cancele a assinatura desse tipo de comunicação, e essa notificação não deve ser adicionada ao contador de mensagens de marketing como parte de uma regra de fadiga.

**Perfis de** meta de mensagens transacionais de perfil do banco de dados de marketing de Campanhas. Com este tipo de mensagens, você pode:
* Aproveite os dados contidos no banco de dados da Adobe Campaign.
* Personalize sua mensagem com as informações do perfil adicionando um [enriquecimento](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content) à configuração do evento.
* Aplique [regras de tipologia de marketing](../../sending/using/managing-typology-rules.md) ou [regras de fadiga](../../sending/using/fatigue-rules.md).
* Incluir o link de unsubscription nas mensagens.
* Adicionar as mensagens transacionais aos relatórios globais do delivery.
* Usar as mensagens transacionais na jornada do cliente.

Por exemplo, você pode usar esse tipo de mensagem ao entrar em contato com seus clientes depois que eles abandonarem o carrinho em seu site, para incentivá-los a continuar com a compra. Ao fazer isso, você pode personalizar mais facilmente sua mensagem com acesso direto a todas as informações do banco de dados do perfil, aplicar regras de marketing e incluir essa mensagem na jornada e relatórios global do cliente para obter uma melhor visualização sobre o comportamento do cliente.

O tipo de mensagem é definido ao configurar o evento que será transformado em mensagem transacional. Consulte as seções de configuração [mensagens transacionais baseados em Eventos](../../channels/using/configuring-transactional-event.md#event-based-transactional-messages) e [mensagens transacionais baseados em Perfis](../../channels/using/configuring-transactional-event.md#profile-based-transactional-messages).

## Principais etapas{#key-steps}

As etapas principais ao criar e gerenciar mensagens transacionais personalizados no Adobe Campaign são resumidas no schema abaixo.

![](assets/message-center-overview.png)

Cada uma dessas etapas é mais detalhada abaixo.

>[!IMPORTANT]
>
>Somente os usuários com a função [Administration](../../administration/using/users-management.md#functional-administrators) podem configurar eventos transacionais e acessar mensagens transacionais.

### Etapa 1 - Criar e publicar a configuração do evento {#create-event-configuration}

<img src="assets/do-not-localize/icon_config.svg" width="60px">

| Usuário | Ação | Resultado |
|--- |--- |--- |
| Esta etapa deve ser executada por um administrador com [direitos de administração](../../administration/using/users-management.md#functional-administrators). | Configure um evento que será chamado de &quot;abandono do carrinho&quot; e publique essa configuração de evento. | A API que será usada pelo desenvolvedor do site é implantada e um mensagen transacional é criado automaticamente. |

A criação e publicação de um evento são apresentadas nas seções [Configuração de um evento transacional](../../channels/using/configuring-transactional-event.md) e [Publicação de um evento transacional](../../channels/using/publishing-transactional-event.md).

### Etapa 2 - Editar e publicar o mensagen transacional {#create-transactional-message}

<img src="assets/do-not-localize/icon_notification.svg" width="40px">

| Usuário | Ação | Resultado |
|--- |--- |--- |
| Esta etapa pode ser executada por um usuário de marketing com [direitos de administração](../../administration/using/users-management.md#functional-administrators). | Edite e personalize o mensagen transacional, teste-o e publique-o. | O mensagen transacional estará pronto para ser enviado. |

Para obter mais informações sobre edição e publicação de um mensagen transacional, consulte [Edição de mensagens transacionais](../../channels/using/editing-transactional-message.md) e [ciclo de vida do Mensagen transacional](../../channels/using/publishing-transactional-message.md).

### Etapa 3 - Integrar o acionamento do evento {#integrate-event-trigger}

<img src="assets/do-not-localize/icon_api.svg" width="55px">

<!--**Event triggering integration**-->

| Usuário | Ação | Resultado |
|--- |--- |--- |
| Esta etapa é executada pelo desenvolvedor do seu site. | Use a API Mensagens transacionais REST para integrar o evento ao seu site. | O evento será acionado quando um cliente abandonar seu carrinho. |

Depois de criar um evento, é necessário integrar o acionamento desse evento ao seu site.<!--In this example, you want a "Cart abandonment" event to be triggered whenever one of your clients leaves your website before purchasing the products in their cart.--> Para fazer isso, o desenvolvedor da Web do site deve usar a API **REST da** Adobe Campaign Standard.

Para obter mais informações sobre como usar a API REST de Campanha para gerenciar mensagens transacionais, consulte a [documentação da API REST](../../api/using/managing-transactional-messages.md).

### Etapa 4 - delivery de mensagem {#message-delivery}

<img src="assets/do-not-localize/icon_channels.svg" width="60px">

Assim que todas essas etapas forem realizadas, a mensagem poderá ser entregue.

Assim que um usuário sair do site sem solicitar os produtos em seu carrinho, o evento de Campanha correspondente será acionado. O usuário recebe automaticamente um email de notificação.

## Tópicos relacionados

* [Etapas principais para enviar uma mensagem](../../channels/using/key-steps-to-send-a-message.md)
* [Introdução a canais de comunicação](../../channels/using/get-started-communication-channels.md)
* [Notificações por push transacionais](../../channels/using/transactional-push-notifications.md)
* [Mensagens de acompanhamento](../../channels/using/follow-up-messages.md)
