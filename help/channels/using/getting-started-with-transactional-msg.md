---
solution: Campaign Standard
product: campaign
title: Principais etapas para configurar um mensagen transacional
description: Descubra o que é mensagem transacional e aprenda as etapas principais para configurar um mensagen transacional no Adobe Campaign Standard.
audience: channels
content-type: reference
topic-tags: landing-pages
context-tags: landingPage,wizard;landingPage,overview;landingPage,main
translation-type: tm+mt
source-git-commit: a0ad969c86a5047f3f967a21fdc2d6040d7d939f
workflow-type: tm+mt
source-wordcount: '814'
ht-degree: 28%

---


# Introdução a mensagens transacionais {#getting-started-with-transactional-messaging}

## Visão geral

<img src="assets/do-not-localize/icon_transactional.svg" width="60px">

Introduzindo o conceito de **mensagens transacionais**

As mensagens transacionais permitem que você envie mensagens individuais e únicas para seus clientes em tempo real.

Elas podem ser mensagens de boas-vindas, confirmações de envio de pedidos, atualizações de senha etc.
A Adobe Campaign permite integrar essa funcionalidade a um sistema de informações que envia eventos que serão transformados em mensagens transacionais personalizados.

As mensagens transacionais podem ser enviadas por email, SMS ou notificação por push, dependendo das suas opções. Verifique o contrato de licença.

A Adobe Campaign prioriza os mensagens transacionais de processamento em relação a qualquer outro delivery.

As mensagens transacionais também estão disponíveis na API do Adobe Campaign Standard. Para obter mais informações, consulte a [documentação dedicada](../../api/using/managing-transactional-messages.md).

>[!NOTE]
>
>Todas as mensagens transacionais agora são enviadas com o MTA aprimorado do Adobe Campaign para otimizar a capacidade de delivery, a taxa de transferência e o tratamento de rejeições. Todos os impactos são os mesmos das mensagens de marketing padrão. Para obter mais informações, consulte esta [seção](../../administration/using/configuring-email-channel.md).

## Definição de mensagem transacional {#transactional-messaging-definition}

<table>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_concepts.svg" width="60px"><br><p><b>O que é um mensagen transacional?</b></p></td>
<td><p>É uma comunicação individual e exclusiva, enviada por um provedor, como um site.</p></td>
<td><p>É particularmente esperado, pois contém informações importantes que o recipient deseja verificar ou confirmar.</p></td>
</tr>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_channels.svg" width="60px"><br><p><b>Quando é o prazo?</b></p></td>
<td><p> Como essa mensagem contém informações importantes, o usuário espera que ela seja enviada em tempo real.</p></td>
<td><p>Consequentemente, o atraso entre o evento desencadeado e a mensagem que chega tem de ser muito curto.</p></td>
</tr>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_important.svg" width="60px"><br><p><b>Por que é importante?</b></p></td>
<td><p>Geralmente, um mensagen transacional tem altas taxas de abertura. Por conseguinte, deve ser cuidadosamente concebido.</p></td>
<td><p>Com efeito, pode ter um forte impacto no comportamento dos clientes, na medida em que define a relação com os clientes.</p></td>
</tr>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_example.svg" width="60px"><br><p><b>Por exemplo?</b></p></td>
<td><p>Pode ser uma mensagem de boas-vindas depois de criar uma conta, uma confirmação de que um pedido foi entregue, uma fatura...</p></td>
<td><p>Também pode ser uma mensagem confirmando uma alteração de senha ou uma notificação depois que um cliente navegou em seu site...</p></td>
</tr>
</table>

## Tipos de mensagens transacionais

Dois tipos de mensagens transacionais estão disponíveis no Adobe Campaign:

<img src="assets/do-not-localize/icon_event.svg" width="60px">

[Mensagens transacionais de evento](../../channels/using/event-transactional-messages.md) que direcionam um evento.

* Mensagens transacionais de evento não contêm informações sobre perfis.

* Eles não são compatíveis com [regras de fadiga](../../sending/using/fatigue-rules.md) (mesmo no caso de um enriquecimento com perfis).

* O público alvo do delivery é definido pelos dados contidos no próprio evento.


<img src="assets/do-not-localize/icon_profile.svg" width="60px">

[Mensagens transacionais de perfil](../../channels/using/profile-transactional-messages.md) que direcionam os perfis do banco de dados de marketing do Campaign.

Com mensagens transacionais de perfis, você pode:

* Aplicar [regras de tipologia de marketing](../../sending/using/managing-typology-rules.md) ou [regras de fadiga](../../sending/using/fatigue-rules.md)

* Incluir o link de unsubscription nas mensagens.

* Adicionar as mensagens transacionais aos relatórios globais do delivery.

* Usar as mensagens transacionais na jornada do cliente.

O tipo de mensagem é definido ao configurar o evento que será transformado em mensagem transacional. Consulte [Configuração de mensagens transacionais](../../administration/using/configuring-transactional-messaging.md).

>[!IMPORTANT]
>
>Para acessar todos os mensagens transacionais, você deve fazer parte do grupo de segurança **[!UICONTROL Administrators (all units)]**.

## Princípio operacional das mensagens transacionais {#transactional-messaging-operating-principle}

Vamos pegar o exemplo de uma empresa que tem um site e neste site seus clientes podem comprar produtos.

O Adobe Campaign permite enviar um email de notificação para os usuários do site que adicionaram produtos ao carrinho. Quando um deles sai do site sem concluir a compra, um email de abandono de carrinho é enviado automaticamente a eles.

As etapas para a implementação são as seguintes:

### Etapa 1 - Criar e publicar a configuração do evento {#create-event-configuration}

<img src="assets/do-not-localize/icon_config.svg" width="60px">

**Configuração** do evento transacional:

* Configure um evento que será chamado de &quot;abandono do carrinho&quot; e publique essa configuração de evento.

* A API que será usada pelo desenvolvedor do site é implantada e um mensagen transacional é criado automaticamente.

* Observe que essa etapa deve ser executada por um usuário com [direitos de administração](../../administration/using/users-management.md#functional-administrators).

A criação e a publicação de um evento são apresentadas na seção [Configuração de um evento para enviar uma mensagem transacional de evento](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message).

### Etapa 2 - Editar e publicar o mensagen transacional {#create-transactional-message}

<img src="assets/do-not-localize/icon_notification.svg" width="40px">

**Edição de mensagen transacional**

* Edite e personalize o mensagen transacional, teste-o e publique-o.

* O mensagen transacional estará pronto para ser enviado.

* Esta etapa pode ser executada por qualquer usuário de marketing com [direitos padrão de acesso do usuário](../../administration/using/users-management.md#basic-users).

Para obter mais informações sobre edição e publicação de um mensagen transacional, consulte [mensagens transacionais de Evento](../../channels/using/event-transactional-messages.md).

### Etapa 3 - Integrar o acionamento do evento {#integrate-event-trigger}

<img src="assets/do-not-localize/icon_api.svg" width="55px">

**Evento acionando a integração**

* Use a API Mensagens transacionais REST para integrar o evento ao seu site.&lt;

* O evento será acionado quando um cliente abandonar seu carrinho.

* Esta etapa é executada pelo desenvolvedor do seu site.

Para obter mais informações sobre como integrar o evento ao seu site, consulte [Integração do site](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

### Etapa 4 - delivery de mensagem {#message-delivery}

<img src="assets/do-not-localize/icon_channels.svg" width="60px">

**Evento externo proveniente do seu site**

* Assim que todas essas etapas forem realizadas, a mensagem poderá ser entregue.

* Assim que um usuário sair do site sem solicitar os produtos em seu carrinho, o evento de Campanha correspondente será acionado.

* O usuário recebe automaticamente um email de notificação.

## Principais etapas{#key-steps}

As etapas principais ao criar e gerenciar mensagens transacionais personalizados no Adobe Campaign são resumidas no gráfico abaixo.

![](assets/message-center-overview.png)

## Tópicos relacionados

* [Etapas principais para enviar uma mensagem](../../channels/using/key-steps-to-send-a-message.md)
* [Introdução a canais de comunicação](../../channels/using/get-started-communication-channels.md)

<!--## Transactional messaging publication process {#transactional-messaging-pub-process}

The chart below illustrates the whole transactional messaging publication process.

![](assets/message-center_pub-process.png)

For more on the event configuration steps, see [Transactional messaging configuration](../../administration/using/configuring-transactional-messaging.md).

Read more:

* [Event transactional messages](../../channels/using/event-transactional-messages.md)
* [Profile transactional messages](../../channels/using/profile-transactional-messages.md)
* [Transactional push notifications](../../channels/using/transactional-push-notifications.md)
* [Follow-up messages](../../channels/using/follow-up-messages.md)-->