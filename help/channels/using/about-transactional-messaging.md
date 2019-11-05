---
title: Sobre mensagens transacionais
description: Descubra os diferentes tipos de mensagens transacionais que você pode enviar e como elas são usadas no Adobe Campaign.
page-status-flag: nunca ativado
uuid: 8470e9e2-ee17-456f-9e4c-460e69c78a2c
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: canais
content-type: referência
topic-tags: mensagens transacionais
discoiquuid: 71a4d5d5-fe2a-4ce5-b22b-a4736f7add83
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Sobre mensagens transacionais{#about-transactional-messaging}

Você pode criar e gerenciar mensagens transacionais personalizadas no Adobe Campaign.

Uma mensagem transacional é uma comunicação individual e exclusiva enviada a um usuário por um provedor, como um site.

* Esse tipo de mensagem é especialmente esperado, pois contém informações que o destinatário deseja verificar ou confirmar. Pode ser uma mensagem de boas-vindas após a criação de uma conta, por exemplo, ou uma confirmação de que um pedido foi entregue, uma lista ou uma mensagem confirmando uma alteração de senha.
* É uma mensagem importante que define a relação do cliente: o usuário espera que ele seja enviado em tempo real. Por conseguinte, o atraso entre o evento desencadeado e a mensagem que chega tem de ser muito curto.
* As mensagens transacionais geralmente têm altas taxas abertas.

O Adobe Campaign permite que você integre essa funcionalidade a um sistema de informações que envia eventos para serem transformados em mensagens transacionais personalizadas.

>[!NOTE]
>
>As mensagens transacionais podem ser enviadas por email, SMS ou notificação por push, dependendo de suas opções. Verifique o contrato de licença.

Dois tipos de mensagens transacionais estão disponíveis no Adobe Campaign:

* [Mensagens](../../channels/using/event-transactional-messages.md) transacionais de evento direcionadas a um evento. Os dados contidos no próprio evento são usados para definir a meta de entrega.
* [As mensagens](../../channels/using/profile-transactional-messages.md) transacionais de perfil direcionam perfis do banco de dados de marketing do Adobe Campaign. Você pode usar as informações do banco de dados do Adobe Campaign para enviar uma mensagem transacional com base nos perfis de marketing do cliente.

O tipo de mensagem é definido ao configurar o evento que será transformado em uma mensagem transacional. Consulte Configuração [de mensagens](../../administration/using/configuring-transactional-messaging.md)transacionais.

>[!NOTE]
>
>O Adobe Campaign prioriza o processamento das mensagens transacionais em vez de qualquer outra entrega.

As mensagens transacionais também estão disponíveis na API do Adobe Campaign Standard. For more on this, refer to the [dedicated documentation](https://final-docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#about-transactional-messaging).

## Princípio operacional do sistema de mensagens transacional {#transactional-messaging-operating-principle}

Vamos pegar o exemplo de uma empresa que tem um site e seus usuários podem comprar produtos nesse site.

O Adobe Campaign permite que você envie um email de notificação para usuários do site que adicionaram produtos ao carrinho: quando um deles sai do site sem passar pelas compras, um e-mail de abandono do carrinho é automaticamente enviado a eles.

As etapas para colocar isso em prática são:

1. Configure um evento que será chamado de "abandono do carrinho" e publique essa configuração de evento, o que cria automaticamente uma mensagem transacional. A criação e publicação de um evento são apresentadas na seção [Configuração de um evento para enviar uma mensagem](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) transacional de evento.
1. A mensagem transacional tem de ser personalizada, testada, depois publicada. See [Event transactional messages](../../channels/using/event-transactional-messages.md).
1. Além disso, para que o evento seja acionado quando um cliente abandona seu carrinho, esse evento deve ser enviado do site da empresa usando a API REST do Adobe Campaign Standard. Consulte Integração [do site](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

Assim que todas essas etapas forem executadas, assim que um usuário sair do site sem solicitar os produtos em seu carrinho, ele receberá automaticamente um email de notificação.

## Processo de publicação de mensagens transacionais {#transactional-messaging-pub-process}

O gráfico abaixo ilustra o processo de publicação de mensagens transacionais.

![](assets/message-center_pub-process.png)

Para obter mais informações sobre as etapas de configuração do evento, consulte Configuração [de mensagens](../../administration/using/configuring-transactional-messaging.md)transacionais.

## Limitações de mensagens transacionais {#transactional-messaging-limitations}

>[!NOTE]
>
>Para acessar mensagens transacionais, é necessário ter direitos administrativos.

### Design e publicação {#design-and-publication}

Como você está projetando e publicando mensagens transacionais, algumas das etapas que você precisa executar não podem ser revertidas. É necessário estar ciente das seguintes limitações:

* Somente um canal pode ser usado para cada configuração de evento. Consulte [Criação de um evento](../../administration/using/configuring-transactional-messaging.md#creating-an-event).
* Depois que o evento é criado, não é possível alterar o canal. Portanto, se uma mensagem não for enviada com êxito, será necessário projetar o mecanismo que permite enviá-la de outro canal usando um fluxo de trabalho. See [Workflow data and processes](../../automating/using/workflow-data-and-processes.md).
* Não é possível alterar a dimensão de definição de metas ( **[!UICONTROL Real-time event]** ou **[!UICONTROL Profile]** ) após a criação do evento. Consulte [Criação de um evento](../../administration/using/configuring-transactional-messaging.md#creating-an-event).
* Não é possível reverter uma publicação, mas você pode cancelar a publicação de um evento: esta operação torna o evento e a mensagem transacional associada inacessíveis. Consulte [Cancelar publicação de um evento](../../administration/using/configuring-transactional-messaging.md#unpublishing-an-event).
* A única mensagem transacional que pode ser associada a um evento é a mensagem que é criada automaticamente após a publicação desse evento. Consulte [Visualizar e publicar o evento](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event).

### Personalização {#personalization}

A maneira de personalizar um conteúdo de mensagem depende do tipo de mensagem transacional. As especificidades estão listadas abaixo:

**Mensagens** transacionais baseadas em eventos:

* As informações de personalização vêm dos dados contidos no próprio evento. See [Event transactional messages](../../channels/using/event-transactional-messages.md).
* Não é possível usar blocos de conteúdo de link **de** cancelamento de assinatura em uma mensagem transacional de evento.
* As mensagens transacionais baseadas em eventos devem usar somente os dados que estão no evento enviado para definir o destinatário e a personalização do conteúdo da mensagem. No entanto, você pode enriquecer o conteúdo de sua mensagem transacional usando informações do banco de dados do Adobe Campaign. Consulte [Enriquecendo o conteúdo](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)da mensagem transacional.
* Como as mensagens transacionais do evento não contêm informações de perfil, elas não são compatíveis com regras de fadiga, mesmo no caso de enriquecimento com perfis. Consulte Regras de [fadiga](../../administration/using/fatigue-rules.md).

**Mensagens** transacionais baseadas em perfil:

* As informações de personalização podem vir dos dados contidos no evento ou do registro de perfil reconciliado. See [Profile transactional messages](../../channels/using/profile-transactional-messages.md).
* Você pode usar blocos de conteúdo de link **de** cancelamento de assinatura em uma mensagem transacional de perfil. Consulte [Adicionar um bloco](../../designing/using/personalization.md#adding-a-content-block)de conteúdo.
* As regras de fadiga são compatíveis com mensagens transacionais de perfil. Consulte Regras de [fadiga](../../administration/using/fatigue-rules.md).

Observe que as listas de produtos estão disponíveis somente em mensagens de email transacionais. Consulte [Uso de listas de produtos em uma mensagem](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message)transacional.

### Permissões e marcas {#permissions-and-branding}

Quando se trata de gerenciamento de [marcas](../../administration/using/branding.md) , as mensagens transacionais permitem menos flexibilidade do que as mensagens padrão. A Adobe recomenda vincular todas as marcas usadas em mensagens transacionais à unidade **[!UICONTROL All]** [](../../administration/using/organizational-units.md)organizacional. Para mais informações, leia a explicação detalhada abaixo.

Ao editar uma mensagem transacional, você pode vinculá-la a uma marca para aplicar automaticamente alguns parâmetros, como o nome da marca ou o logotipo da marca. A opção **[!UICONTROL Default brand]** é selecionada por padrão nas propriedades da mensagem transacional.

![](assets/message-center_branding.png)

Todos os objetos (incluindo marcas) usados em uma mensagem transacional devem ser visíveis da unidade organizacional, o que significa que esses objetos devem estar nas unidades organizacionais **[!UICONTROL Message Center]** ou **[!UICONTROL Message Center]** **[!UICONTROL All]** .

Entretanto, se a marca selecionada nas propriedades da mensagem estiver vinculada a uma unidade organizacional diferente **[!UICONTROL Message Center]** ou **[!UICONTROL All]**, isso causará um erro e você não poderá enviar a mensagem transacional.

Portanto, se você quiser usar a multimarca no contexto de mensagens transacionais, vincule todas as marcas à unidade **[!UICONTROL Message Center]** organizacional ou à unidade **[!UICONTROL All]** organizacional.

### Exportação e importação de mensagens transacionais {#exporting-and-importing-transactional-messages}

* Para exportar uma mensagem transacional, é necessário incluir a configuração de evento correspondente ao [criar a exportação](../../automating/using/managing-packages.md#creating-a-package)do pacote.
* Quando a mensagem transacional é [importada por meio de um pacote](../../automating/using/managing-packages.md#importing-a-package), ela não é exibida na lista de mensagens transacionais. É necessário [publicar](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event) a configuração do evento para disponibilizar a mensagem transacional associada.

