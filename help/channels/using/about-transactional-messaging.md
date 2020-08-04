---
title: Sobre mensagens transacionais
description: Descubra os diferentes tipos de mensagens transacionais que você pode enviar e como eles são usados no Adobe Campaign.
page-status-flag: never-activated
uuid: 8470e9e2-ee17-456f-9e4c-460e69c78a2c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: transactional-messaging
discoiquuid: 71a4d5d5-fe2a-4ce5-b22b-a4736f7add83
internal: n
snippet: y
translation-type: ht
source-git-commit: 68e825bc3b6b7f94f61875e7da2bc8f63f06d9cb
workflow-type: ht
source-wordcount: '1147'
ht-degree: 100%

---


# Sobre mensagens transacionais{#about-transactional-messaging}

Você pode criar e gerenciar mensagens transacionais personalizadas no Adobe Campaign.

Uma mensagem transacional é uma comunicação individual e exclusiva enviada a um usuário por um provedor, como um site.

* Esse tipo de mensagem é esperado, pois contém informações que o recipient deseja verificar ou confirmar. Ela pode ser, por exemplo, uma mensagem de boas-vindas após a criação de uma conta, uma confirmação de entrega de pedido, uma fatura ou uma mensagem confirmando uma alteração de senha.
* Ela é uma mensagem importante que define a relação do cliente. O usuário espera que ela seja enviada em tempo real. Portanto, o atraso entre o evento acionado e a mensagem recebida deve ser muito curto.
* As mensagens transacionais geralmente têm altas taxas de abertura.

O Adobe Campaign permite integrar essa funcionalidade a um sistema de informações que envia eventos a ele e serão transformados em mensagens transacionais personalizadas.

>[!NOTE]
>
>As mensagens transacionais podem ser enviadas por email, SMS ou notificação por push, dependendo das suas opções. Verifique o contrato de licença.

Dois tipos de mensagens transacionais estão disponíveis no Adobe Campaign:

* [Mensagens transacionais de evento](../../channels/using/event-transactional-messages.md) que direcionam um evento. Os dados contidos no evento são usados para definir o público alvo do delivery.
* [Mensagens transacionais de perfil](../../channels/using/profile-transactional-messages.md) que direcionam os perfis do banco de dados de marketing do Adobe Campaign. Você pode usar as informações do banco de dados do Adobe Campaign para enviar uma mensagem transacional com base nos perfis de marketing do cliente.

O tipo de mensagem é definido ao configurar o evento que será transformado em mensagem transacional. Consulte [Configuração de mensagens transacionais](../../administration/using/configuring-transactional-messaging.md).

>[!NOTE]
>
>O Adobe Campaign prioriza o processamento das mensagens transacionais antes de qualquer outro delivery.

As mensagens transacionais também estão disponíveis na API do Adobe Campaign Standard. Para obter mais informações, consulte a [documentação dedicada](../../api/using/managing-transactional-messages.md).

>[!NOTE]
>
>Todas as mensagens transacionais agora são enviadas com o MTA aprimorado do Adobe Campaign para otimizar a capacidade de delivery, a taxa de transferência e o tratamento de rejeições. Todos os impactos são os mesmos das mensagens de marketing padrão. Para obter mais informações, consulte esta [seção](../../administration/using/configuring-email-channel.md).

## Princípio operacional das mensagens transacionais {#transactional-messaging-operating-principle}

Vamos usar o exemplo de uma empresa que tem um site de venda de produtos.

O Adobe Campaign permite enviar um email de notificação para os usuários do site que adicionaram produtos ao carrinho. Quando um deles sai do site sem concluir a compra, um email de abandono de carrinho é enviado automaticamente a eles.

Estas são as etapas para colocar o acionador em prática:

1. Configure um evento que será chamado de “Abandono do carrinho” e publique essa configuração, que cria automaticamente uma mensagem transacional. A criação e a publicação de um evento são apresentadas na seção [Configuração de um evento para enviar uma mensagem transacional de evento](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message).
1. A mensagem transacional precisa ser personalizada, testada e publicada. Consulte [Mensagens transacionais de evento](../../channels/using/event-transactional-messages.md).
1. Além disso, para acionar o evento quando um cliente abandonar o carrinho, ele deverá ser enviado do site da empresa usando a API REST do Adobe Campaign Standard. Consulte [Integração do site](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

Quando todas essas etapas forem executadas, assim que um usuário sair do site sem fazer o pedido dos produtos no carrinho, ele receberá automaticamente uma notificação por email.

## Processo de publicação de mensagens transacionais {#transactional-messaging-pub-process}

O gráfico abaixo ilustra o processo de publicação de mensagens transacionais.

![](assets/message-center_pub-process.png)

Para saber mais sobre as etapas de configuração do evento, consulte [Configuração de mensagens transacionais](../../administration/using/configuring-transactional-messaging.md).

## Limitações de mensagens transacionais {#transactional-messaging-limitations}

>[!NOTE]
>
>Para acessar as mensagens transacionais, você deve ter direitos administrativos.

### Design e publicação {#design-and-publication}

Quando você estiver projetando e publicando mensagens transacionais, algumas etapas necessárias não poderão ser revertidas. Você deve estar ciente das seguintes limitações:

* Somente um canal pode ser usado para cada configuração de evento. Consulte [Criação de um evento](../../administration/using/configuring-transactional-messaging.md#creating-an-event).
* Depois que o evento é criado, não é possível alterar o canal. Portanto, se uma mensagem não for enviada, você precisará projetar o mecanismo para enviá-la de outro canal usando um fluxo de trabalho. Consulte [Dados e processos do fluxo de trabalho](../../automating/using/get-started-workflows.md).
* Você não poderá alterar o targeting dimension (**[!UICONTROL Real-time event]** ou **[!UICONTROL Profile]**) após a criação do evento. Consulte [Criação de um evento](../../administration/using/configuring-transactional-messaging.md#creating-an-event).
* Não é possível reverter uma publicação, mas você pode desfazer a publicação de um evento. Essa operação torna inacessíveis o evento e a mensagem transacional associada. Consulte [Desfazer a publicação de um evento](../../administration/using/configuring-transactional-messaging.md#unpublishing-an-event).
* A única mensagem transacional que pode ser associada a um evento é a criada automaticamente após a publicação do evento. Consulte [Pré-visualização e publicação do evento](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event).

### Personalização {#personalization}

O modo de personalização de um conteúdo de mensagem depende do tipo de mensagem transacional. As especificidades são listadas abaixo.

**Mensagens transacionais baseadas em evento**:

* Os dados contidos no evento são a fonte das informações de personalização. Consulte [Mensagens transacionais de evento](../../channels/using/event-transactional-messages.md).
* Não é possível usar os blocos de conteúdo do **Link de unsubscription** em uma mensagem transacional de evento.
* As mensagens transacionais baseadas em evento só devem usar os dados contidos no evento enviado para definir o recipient e a personalização do conteúdo da mensagem. No entanto, você pode enriquecer o conteúdo da mensagem transacional usando informações do banco de dados do Adobe Campaign. Consulte [Enriquecimento de conteúdo de mensagens transacionais](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content).
* Como as mensagens transacionais de evento não contêm informações sobre perfis, elas não são compatíveis com as regras de fadiga, até mesmo no caso de um enriquecimento com perfis. Consulte [Regras de fadiga](../../sending/using/fatigue-rules.md).

**Mensagens transacionais baseadas em perfil**:

* Os dados contidos no evento ou do registro do perfil reconciliado podem ser a fonte das informações de personalização. Consulte [Mensagens transacionais de perfil](../../channels/using/profile-transactional-messages.md).
* É possível usar os blocos de conteúdo do **Link de unsubscription** em uma mensagem transacional de perfil. Consulte [Adição de um bloco de conteúdo](../../designing/using/personalization.md#adding-a-content-block).
* As regras de fadiga são compatíveis com as mensagens transacionais de perfil. Consulte [Regras de fadiga](../../sending/using/fatigue-rules.md).

Observe que as listagens de produtos só estão disponíveis nas mensagens de email transacionais. Consulte [Uso das listagens de produtos em uma mensagem transacional](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message).

### Permissões e identidade visual {#permissions-and-branding}

No gerenciamento da [identidade visual](../../administration/using/branding.md), as mensagens transacionais são menos flexíveis do que as mensagens padrão. A Adobe recomenda vincular todas as marcas usadas nas mensagens transacionais à **[!UICONTROL All]** [unidade organizacional](../../administration/using/organizational-units.md). Para saber mais, leia a explicação detalhada abaixo.

Ao editar uma mensagem transacional, você pode vinculá-la a uma marca para aplicar automaticamente alguns parâmetros, como o nome ou o logotipo da marca. A opção **[!UICONTROL Default brand]** é selecionada por padrão nas propriedades da mensagem transacional.

![](assets/message-center_branding.png)

Todos os objetos (inclusive as marcas) usados em uma mensagem transacional devem estar visíveis na unidade organizacional **[!UICONTROL Message Center]**, o que significa que eles devem estar na **[!UICONTROL Message Center]** ou em unidades organizacionais **[!UICONTROL All]**.

No entanto, se a marca selecionada nas propriedades da mensagem estiver vinculada a uma unidade organizacional diferente de **[!UICONTROL Message Center]** ou **[!UICONTROL All]**, ocorrerá um erro e você não poderá enviar a mensagem transacional.

Portanto, se você quiser usar multimarcas no contexto de mensagens transacionais, vincule todas as marcas à unidade organizacional **[!UICONTROL Message Center]** ou **[!UICONTROL All]**.

### Exportação e importação de mensagens transacionais {#exporting-and-importing-transactional-messages}

* Para exportar uma mensagem transacional, é necessário incluir a configuração de evento correspondente ao [criar a exportação do pacote](../../automating/using/managing-packages.md#creating-a-package).
* Depois que a mensagem transacional for [importada em um pacote](../../automating/using/managing-packages.md#importing-a-package), ela não será exibida na lista de mensagens transacionais. Você precisará [publicar](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event) a configuração do evento para disponibilizar a mensagem transacional associada.

