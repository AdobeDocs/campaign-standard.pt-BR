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
translation-type: tm+mt
source-git-commit: 68e825bc3b6b7f94f61875e7da2bc8f63f06d9cb

---


# Sobre mensagens transacionais{#about-transactional-messaging}

Você pode criar e gerenciar mensagens transacionais personalizados no Adobe Campaign.

Um mensagen transacional é uma comunicação individual e exclusiva enviada a um usuário por um provedor, como um site.

* Esse tipo de mensagem é especialmente esperado, pois contém informações que o recipient deseja verificar ou confirmar. Pode ser uma mensagem de boas-vindas após a criação de uma conta, por exemplo, ou uma confirmação de que um pedido foi entregue, uma lista ou uma mensagem confirmando uma alteração de senha.
* É uma mensagem importante que define a relação do cliente: o usuário espera que ele seja enviado em tempo real. O atraso entre o evento desencadeado e a mensagem que chega tem, por conseguinte, de ser muito curto.
* Mensagens transacionais geralmente têm altas taxas de abertura.

O Adobe Campaign permite integrar essa funcionalidade a um sistema de informações que envia eventos que serão transformados em mensagens transacionais personalizados.

>[!NOTE]
>
>Mensagens transacionais podem ser enviados por email, SMS ou notificação por push, dependendo de suas opções. Verifique o contrato de licença.

Dois tipos de mensagens transacionais estão disponíveis no Adobe Campaign:

* [mensagens transacionais](../../channels/using/event-transactional-messages.md) de Evento direcionados a um evento. Os dados contidos no próprio evento são usados para definir o público alvo do delivery.
* [mensagens transacionais](../../channels/using/profile-transactional-messages.md) Perfil que direcionam perfis do banco de dados de marketing do Adobe Campaign. Você pode usar as informações do banco de dados do Adobe Campaign para enviar um mensagen transacional com base em perfis de marketing do cliente.

O tipo de mensagem é definido ao configurar o evento que será transformado em um mensagen transacional. Consulte Configuração [de mensagens](../../administration/using/configuring-transactional-messaging.md)transacionais.

>[!NOTE]
>
>O Adobe Campaign prioriza o processamento dos mensagens transacionais em vez de qualquer outro delivery.

As mensagens transacionais também estão disponíveis na API Adobe Campaign Standard. For more on this, refer to the [dedicated documentation](../../api/using/managing-transactional-messages.md).

>[!NOTE]
>
>Todos os mensagens transacionais agora são enviados com o MTA aprimorado Adobe Campaign para oferecer mais capacidade de entrega, throughput e manuseio de rejeição. Todos os impactos são os mesmos das mensagens de marketing padrão. For more on this, see this [section](../../administration/using/configuring-email-channel.md).

## Princípio operacional do sistema de mensagens transacional {#transactional-messaging-operating-principle}

Vamos pegar o exemplo de uma empresa que tem um site e seus usuários podem comprar produtos nesse site.

O Adobe Campaign permite enviar um email de notificação para usuários do site que adicionaram produtos ao carrinho: quando um deles sai do site sem passar pelas compras, um e-mail de abandono do carrinho é automaticamente enviado a eles.

As etapas para colocar isso em prática são:

1. Configure um evento que será chamado de &quot;abandono do carrinho&quot; e publique essa configuração de evento, que cria automaticamente um mensagen transacional. A criação e publicação de um evento são apresentadas na seção [Configuração de um evento para enviar um mensagen transacional](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) de evento.
1. O mensagen transacional tem de ser personalizado, testado, depois publicado. See [Event transactional messages](../../channels/using/event-transactional-messages.md).
1. Além disso, para que o evento seja acionado quando um cliente abandona seu carrinho, esse evento deve ser enviado do site da empresa usando a API REST do Adobe Campaign Standard. Consulte Integração [do site](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

Assim que todas essas etapas forem executadas, assim que um usuário sair do site sem solicitar os produtos em seu carrinho, ele receberá automaticamente um email de notificação.

## Processo de publicação de mensagens transacionais {#transactional-messaging-pub-process}

O gráfico abaixo ilustra o processo de publicação de mensagens transacionais.

![](assets/message-center_pub-process.png)

Para obter mais informações sobre as etapas de configuração do evento, consulte Configuração [de mensagens](../../administration/using/configuring-transactional-messaging.md)transacionais.

## Limitações de mensagens transacionais {#transactional-messaging-limitations}

>[!NOTE]
>
>Para acessar mensagens transacionais, você deve ter direitos administrativos.

### Design e publicação {#design-and-publication}

À medida que você está projetando e publicando mensagens transacionais, algumas das etapas necessárias não podem ser revertidas. É necessário estar ciente das seguintes limitações:

* Somente um canal pode ser usado para cada configuração de evento. Consulte [Criação de um evento](../../administration/using/configuring-transactional-messaging.md#creating-an-event).
* Depois que o evento é criado, não é possível alterar o canal. Portanto, se uma mensagem não for enviada com êxito, será necessário projetar o mecanismo que permite enviá-la de outro canal usando um fluxo de trabalho. See [Workflow data and processes](../../automating/using/get-started-workflows.md).
* Não é possível alterar o targeting dimension ( **[!UICONTROL Real-time event]** ou **[!UICONTROL Profile]** ) após a criação do evento. Consulte [Criação de um evento](../../administration/using/configuring-transactional-messaging.md#creating-an-event).
* Não é possível reverter uma publicação, mas você pode cancelar a publicação de um evento: essa operação torna o evento e o mensagen transacional associado inacessíveis. Consulte [Desfazer publicação de um evento](../../administration/using/configuring-transactional-messaging.md#unpublishing-an-event).
* O único mensagen transacional que pode ser associado a um evento é a mensagem que é criada automaticamente após a publicação desse evento. Consulte [Visualizar e publicar o evento](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event).

### Personalização {#personalization}

A maneira de personalizar um conteúdo de mensagem depende do tipo de mensagen transacional. As especificidades estão listadas abaixo:

**mensagens transacionais** baseados em Eventos:

* As informações de personalização vêm dos dados contidos no próprio evento. See [Event transactional messages](../../channels/using/event-transactional-messages.md).
* Não é possível usar blocos de conteúdo de link **de** Unsubscription em um mensagen transacional de evento.
* As mensagens transacionais baseadas em Eventos devem usar somente os dados que estão no evento enviado para definir o recipient e a personalização do conteúdo da mensagem. No entanto, você pode enriquecer o conteúdo do seu mensagen transacional usando informações do banco de dados do Adobe Campaign. Consulte [Enriquecendo o conteúdo](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)do mensagen transacional.
* Como os mensagens transacionais eventos não contêm informações sobre perfis, eles não são compatíveis com regras de fadiga, mesmo no caso de um enriquecimento com perfis. Consulte Regras de [fadiga](../../sending/using/fatigue-rules.md).

**mensagens transacionais** baseados em Perfis:

* As informações de personalização podem vir dos dados contidos no evento ou do registro do perfil reconciliado. See [Profile transactional messages](../../channels/using/profile-transactional-messages.md).
* Você pode usar blocos de conteúdo de link **de** Unsubscription em um mensagen transacional de perfil. Consulte [Adicionar um bloco](../../designing/using/personalization.md#adding-a-content-block)de conteúdo.
* As regras de fadiga são compatíveis com mensagens transacionais perfis. Consulte Regras de [fadiga](../../sending/using/fatigue-rules.md).

Observe que as listas de produtos estão disponíveis somente em mensagens de email transacionais. Consulte [Uso das listas de produtos em um mensagen transacional](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message).

### Permissões e marcas {#permissions-and-branding}

Quando se trata de gerenciamento de [marcas](../../administration/using/branding.md) , as mensagens transacionais permitem menos flexibilidade do que as mensagens padrão. A Adobe recomenda vincular todas as marcas usadas em mensagens transacionais à unidade **[!UICONTROL All]** [](../../administration/using/organizational-units.md)organizacional. Para mais informações, leia a explicação detalhada abaixo.

Ao editar um mensagen transacional, você pode vinculá-lo a uma marca para aplicar automaticamente alguns parâmetros, como o nome da marca ou o logotipo da marca. A opção **[!UICONTROL Default brand]** é selecionada por padrão nas propriedades do mensagen transacional.

![](assets/message-center_branding.png)

Todos os objetos (incluindo marcas) usados em um mensagen transacional devem ser visíveis da unidade organizacional, o que significa que esses objetos devem estar nas unidades organizacionais **[!UICONTROL Message Center]** ou **[!UICONTROL Message Center]** **[!UICONTROL All]** .

No entanto, se a marca selecionada nas propriedades da mensagem estiver vinculada a uma unidade organizacional diferente **[!UICONTROL Message Center]** ou **[!UICONTROL All]**, isso causará um erro e você não poderá enviar o mensagen transacional.

Portanto, se você quiser usar a multimarca no contexto de mensagens transacionais, vincule todas as marcas à unidade **[!UICONTROL Message Center]** organizacional ou à unidade **[!UICONTROL All]** organizacional.

### Exportação e importação de mensagens transacionais {#exporting-and-importing-transactional-messages}

* Para exportar um mensagen transacional, é necessário incluir a configuração de evento correspondente ao [criar a exportação](../../automating/using/managing-packages.md#creating-a-package)do pacote.
* Depois que o mensagen transacional é [importado por meio de um pacote](../../automating/using/managing-packages.md#importing-a-package), ele não é exibido na lista do mensagen transacional. É necessário [publicar](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event) a configuração do evento para disponibilizar o mensagen transacional associado.

