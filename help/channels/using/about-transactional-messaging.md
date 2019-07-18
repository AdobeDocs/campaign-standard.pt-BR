---
title: Sobre mensagens transacionais
seo-title: Sobre mensagens transacionais
description: Sobre mensagens transacionais
seo-description: Descubra os diferentes tipos de mensagens transacionais que podem ser enviadas e como são usadas no Adobe Campaign.
page-status-flag: nunca ativado
uuid: 8470 e 9 e 2-ee 17-456 f -9 e 4 c -460 e 69 c 78 a 2 c
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canais
content-type: reference
topic-tags: transacionais-messaging
discoiquuid: 71 a 4 d 5 d 5-fe 2 a -4 ce 5-b 22 b-a 4736 f 7 add 83
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d93c2600299a8d2ec3672b3d82222f423878034c

---


# About transactional messaging{#about-transactional-messaging}

Você pode criar e gerenciar mensagens transacionais personalizadas no Adobe Campaign.

Uma mensagem transacional é uma comunicação individual e exclusiva enviada a um usuário por um provedor, como um site.

* Esse tipo de mensagem é especificamente esperado, pois contém informações que o destinatário deseja verificar ou confirmar. Pode ser uma mensagem de boas-vindas após criar uma conta, por exemplo, ou uma confirmação de que um pedido foi enviado, uma fatura ou uma mensagem confirmando uma alteração de senha.
* É uma mensagem importante que define a relação do cliente: o usuário espera que ele seja enviado em tempo real. O atraso entre o evento sendo acionado e a mensagem chegando, portanto, deve ser muito curto.
* As mensagens transacionais geralmente têm altas taxas abertas.

O Adobe Campaign permite integrar essa funcionalidade com um sistema de informações que a envia para transformar em mensagens transacionais personalizadas.

>[!NOTE]
>
>As mensagens transacionais podem ser enviadas por email, SMS ou notificação por push, dependendo das suas opções. Verifique seu contrato de licença.

Dois tipos de mensagens transacionais estão disponíveis no Adobe Campaign:

* [Mensagens transacionais de evento](../../channels/using/event-transactional-messages.md) direcionadas a um evento. Os dados contidos no próprio evento são usados para definir o destino da entrega.
* [Mensagens transacionais de perfil](../../channels/using/profile-transactional-messages.md) de direcionamento de perfis do banco de dados de marketing do Adobe Campaign. Você pode usar informações do banco de dados do Adobe Campaign para enviar uma mensagem transacional com base em perfis de marketing do cliente.

O tipo de mensagem é definido ao configurar o evento que será transformado em uma mensagem transacional. See [Transactional messaging configuration](../../administration/using/configuring-transactional-messaging.md).

>[!NOTE]
>
>O Adobe Campaign prioriza o processamento das mensagens transacionais em qualquer outro fornecimento.

As mensagens transacionais também estão disponíveis na API do Adobe Campaign Standard. For more on this, refer to the [dedicated documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#about-transactional-messaging).

## Transactional messaging operating principle {#transactional-messaging-operating-principle}

Vejamos o exemplo de uma empresa que tem um site e, nesse site, seus usuários podem comprar produtos.

O Adobe Campaign permite enviar um email de notificação para usuários do site que adicionaram produtos ao carrinho: quando um deles deixar o site sem passar com suas compras, um e-mail de abandono de carrinho será enviado automaticamente para eles.

As etapas para colocar isso em vigor são:

1. Configure um evento que se chamará «Abandono do carrinho» e publique essa configuração de evento, que cria automaticamente uma mensagem transacional. Creating and publishing an event are presented in the [Configuring an event to send an event transactional message](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) section.
1. A mensagem transacional deve ser personalizada, testada e publicada. See [Event transactional messages](../../channels/using/event-transactional-messages.md).
1. Além disso, para que o evento seja acionado quando um cliente abandona o carrinho, esse evento deve ser enviado do site da empresa usando a API REST do Adobe Campaign Standard. See [Site integration](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

Assim que todas essas etapas tiverem sido executadas, assim que um usuário deixar o site sem ordenar os produtos no carrinho, ele receberá automaticamente um email de notificação.

## Transactional messaging limitations {#transactional-messaging-limitations}

### Design and publication {#design-and-publication}

À medida que você está criando e publicando mensagens transacionais, algumas das etapas que você precisa executar não podem ser revertidas. Você deve estar ciente das seguintes limitações:

* Apenas um canal pode ser usado para cada configuração de evento. See [Creating an event](../../administration/using/configuring-transactional-messaging.md#creating-an-event).
* Depois que o evento é criado, não é possível alterar o canal. Portanto, se uma mensagem não for enviada com sucesso, é necessário projetar o mecanismo que permite o envio de outro canal usando um fluxo de trabalho. See [Workflow data and processes](../../automating/using/workflow-data-and-processes.md).
* You cannot change the targeting dimension ( **[!UICONTROL Real-time event]** or **[!UICONTROL Profile]** ) after the event is created. See [Creating an event](../../administration/using/configuring-transactional-messaging.md#creating-an-event).
* Não é possível reverter uma publicação, mas você pode cancelar a publicação de um evento: esta operação torna o evento e a mensagem transacionais associados inacessíveis. See [Unpublishing an event](../../administration/using/configuring-transactional-messaging.md#unpublishing-an-event).
* A única mensagem transacional que pode ser associada a um evento é a mensagem que é criada automaticamente após a publicação desse evento. See [Previewing and publishing the event](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event).

### Personalization {#personalization}

A maneira como você pode personalizar um conteúdo de mensagem depende do tipo de mensagem transacional. As especificidades estão listadas abaixo:

**Mensagens transacionais baseadas em eventos**:

* As informações de personalização vêm dos dados contidos no próprio evento. See [Event transactional messages](../../channels/using/event-transactional-messages.md).
* You cannot use **Unsubscription link** content blocks in an event transactional message.
* As mensagens transacionais baseadas em eventos devem usar apenas os dados que estão no evento enviado para definir o destinatário e a personalização do conteúdo da mensagem. No entanto, você pode aprimorar o conteúdo da sua mensagem transacional usando informações do banco de dados do Adobe Campaign. See [Enriching the transactional message content](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content).
* Como as mensagens transacionais de evento não contêm informações de perfil, elas não são compatíveis com regras de fadiga, mesmo no caso de um enriquecimento com perfis. See [Fatigue rules](../../administration/using/fatigue-rules.md).

**Mensagens transacionais baseadas em perfil**:

* As informações de personalização podem ser provenientes dos dados contidos no evento ou do registro de perfil reconciliado. See [Profile transactional messages](../../channels/using/profile-transactional-messages.md).
* You can use **Unsubscription link** content blocks in a profile transactional message. See [Adding a content block](../../designing/using/adding-a-content-block.md).
* As regras de esgotamento são compatíveis com as mensagens transacionais do perfil. See [Fatigue rules](../../administration/using/fatigue-rules.md).

Observe que as listagens de produto estão disponíveis apenas em mensagens de email transacionais. See [Using product listings in a transactional message](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message).

### Permissions and branding {#permissions-and-branding}

When it comes to [branding](../../administration/using/branding.md) management, transactional messaging enables less flexibility than standard messaging. Adobe recommends linking all brands used in transactional messages to the **[!UICONTROL All]** organizational unit. Para saber mais sobre isso, leia a explicação detalhada abaixo.

Ao editar uma mensagem transacional, você pode vinculá-la a uma marca para aplicar automaticamente alguns parâmetros, como o nome da marca ou o logotipo da marca. The **[!UICONTROL Default brand]** is selected by default in the transactional message properties.

![](assets/message-center_branding.png)

To access the transactional messages, you must be part of the **[!UICONTROL Message Center agents]** (mcExec) security group, which is linked to the **[!UICONTROL Message Center]** [organizational unit](../../administration/using/organizational-units.md). Therefore, all objects (including branding) used in a transactional message must be visible from the **[!UICONTROL Message Center]** organizational unit, meaning that these objects must be in the **[!UICONTROL Message Center]** or **[!UICONTROL All]** organizational units.

However, if the brand selected in the message properties is linked to an organizational unit which is different from **[!UICONTROL Message Center]** or **[!UICONTROL All]**, this will cause an error and you will not be able to send the transactional message.

Therefore, if you want to use multi-branding in the context of transactional messaging, you should link all brands either to the **[!UICONTROL Message Center]** organizational unit or to the **[!UICONTROL All]** organizational unit.

### Exporting and importing transactional messages {#exporting-and-importing-transactional-messages}

* To export a transactional message, you need to include the corresponding event configuration when [creating the package export](../../automating/using/managing-packages.md#creating-a-package).
* Once the transactional message is [imported through a package](../../automating/using/managing-packages.md#importing-a-package), it is not displayed in the transactional message list. You need to [publish](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event) the event configuration in order to make the associated transactional message available.

