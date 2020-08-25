---
title: Principais etapas para configurar um mensagen transacional
description: Descubra o que é mensagem transacional e aprenda as etapas principais para configurar um mensagen transacional no Adobe Campaign Standard.
page-status-flag: never-activated
uuid: b316bf47-7d98-46fa-ab4f-67ff50de8095
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: ca8d1698-6e8a-4f5a-b017-74a152e14286
context-tags: landingPage,wizard;landingPage,overview;landingPage,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 434be1d237e1ce5bd47552d371d2df4670e82f44
workflow-type: tm+mt
source-wordcount: '729'
ht-degree: 31%

---


# Introdução às mensagens transacionais {#getting-started-with-transactional-messaging}

## Visão geral


<img src="assets/do-not-localize/icon_transactional.svg" width="60px">

As mensagens transacionais permitem que você <b>envie mensagens</b> individuais e únicas para seus clientes em tempo real. Pode ser mensagens de boas-vindas, confirmações de envio de pedidos, modificação de senha etc.

A Adobe Campaign permite integrar essa funcionalidade a um sistema de informações que envia eventos que serão transformados em mensagens transacionais personalizados.

>[!NOTE]
>
>As mensagens transacionais podem ser enviadas por email, SMS ou notificação por push, dependendo das suas opções. Verifique o contrato de licença.

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

<!--[Event transactional messages](../../channels/using/event-transactional-messages.md) targeting an **event**. The data contained in the event itself is used to define the delivery target.-->

<table>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_event.svg" width="60px"><br><p><a href="../../channels/using/event-transactional-messages.md">Mensagens transacionais de evento</a><br><b> que direcionam um evento</b></p></td>
<td><p><ul><li>Elas não contêm informações sobre o perfil.</li><li>Não são compatíveis com regras <a href="../../sending/using/fatigue-rules.md">de</a> fadiga (mesmo no caso de um enriquecimento com perfis).</li><li>O público alvo do delivery é definido pelos dados contidos no próprio evento.</li></ul></p></td>
</tr>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_profile.svg" width="60px"><br><a href="../../channels/using/profile-transactional-messages.md"><p>Mensagens transacionais de perfil</a><br><b> que direcionam os perfis do banco de dados de marketing do Adobe Campaign</b></p></td>
<td><p>Mensagens transacionais de perfis permitem:<ul><li>Aplique regras de tipologia de marketing, como <b>Endereço na lista de bloqueios</b> ou regras <a href="../../sending/using/fatigue-rules.md">de</a>fadiga.</li><li>Incluir o link de unsubscription nas mensagens.</li><li>Adicionar as mensagens transacionais aos relatórios globais do delivery.</li><li>Usar as mensagens transacionais na jornada do cliente.</li></ul></p></td>
</tr>
</table>

<!--[Profile transactional messages](../../channels/using/profile-transactional-messages.md) targeting **profiles from the Adobe Campaign marketing database**. You can use information from the Adobe Campaign database to send a transactional message based on customer marketing profiles.-->

O tipo de mensagem é definido ao configurar o evento que será transformado em mensagem transacional. Consulte [Configuração de mensagens transacionais](../../administration/using/configuring-transactional-messaging.md).

>[!IMPORTANT]
>
>To access all transactional messages, you must be part of the **[!UICONTROL Administrators (all units)]** security group.

<!--Event transactional messages do not contain profile information, therefore they are not compatible with fatigue rules (even in the case of an enrichment with profiles). However, profile transactional messages are compatible. For more on fatigue rules, see [this section](../../sending/using/fatigue-rules.md#choosing-the-channel).-->

## Princípio operacional das mensagens transacionais {#transactional-messaging-operating-principle}

Vamos pegar o exemplo de uma empresa que tem um site e neste site seus clientes podem comprar produtos.

O Adobe Campaign permite enviar um email de notificação para os usuários do site que adicionaram produtos ao carrinho. Quando um deles sai do site sem concluir a compra, um email de abandono de carrinho é enviado automaticamente a eles.

As etapas para colocar isso em prática são as seguintes.

### Etapa 1 - Criar e publicar a configuração do evento {#create-event-configuration}

<img src="assets/do-not-localize/icon_config.svg" width="60px">

Configure um evento que será chamado de &quot;abandono do carrinho&quot; e publique essa configuração de evento.

A API que será usada pelo desenvolvedor do site é implantada e um mensagen transacional é criado automaticamente.

A criação e a publicação de um evento são apresentadas na seção [Configuração de um evento para enviar uma mensagem transacional de evento](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message).

### Etapa 2 - Editar e publicar o mensagen transacional {#create-transactional-message}

<img src="assets/do-not-localize/icon_transactional.svg" width="60px">

Edite e personalize o mensagen transacional, teste-o e publique-o.

For more on editing and publishing a transactional message, see [Event transactional messages](../../channels/using/event-transactional-messages.md).

### Etapa 3 - Integrar o acionamento do evento {#integrate-event-trigger}

<img src="assets/do-not-localize/icon_api.svg" width="60px">

Use a API Mensagens transacionais REST para integrar o evento ao seu site.

O evento será acionado quando um cliente abandonar seu carrinho.

Para obter mais informações sobre como integrar o evento ao seu site, consulte Integração [do](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)site.

### Etapa 4 - delivery de mensagens {#message-delivery}

<!--Once all of these steps have been carried out, the message can be delivered:-->

<img src="assets/do-not-localize/icon_notification.svg" width="40px">

Assim que um usuário sair do site sem solicitar os produtos em seu carrinho, ele receberá automaticamente um email de notificação.

## Principais etapas{#key-steps}

As etapas principais ao criar e gerenciar mensagens transacionais personalizados no Adobe Campaign são resumidas no gráfico abaixo.

![](assets/message-center-overview.png)

<!--## Transactional messaging publication process {#transactional-messaging-pub-process}

The chart below illustrates the whole transactional messaging publication process.

![](assets/message-center_pub-process.png)

For more on the event configuration steps, see [Transactional messaging configuration](../../administration/using/configuring-transactional-messaging.md).

Read more:

* [About transactional messaging](../../channels/using/about-transactional-messaging.md)
* [Event transactional messages](../../channels/using/event-transactional-messages.md)
* [Profile transactional messages](../../channels/using/profile-transactional-messages.md)
* [Transactional push notifications](../../channels/using/transactional-push-notifications.md)
* [Follow-up messages](../../channels/using/follow-up-messages.md)-->

**Tópicos relacionados:**

* [Etapas principais para enviar uma mensagem](../../channels/using/key-steps-to-send-a-message.md)
* [Introdução a canais de comunicação](../../channels/using/get-started-communication-channels.md)