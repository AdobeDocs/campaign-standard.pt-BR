---
solution: Campaign Standard
product: campaign
title: Limitações de mensagens transacionais
description: Saiba mais sobre as principais recomendações e limitações relacionadas aos mensagens transacionais no Adobe Campaign Standard.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
translation-type: tm+mt
source-git-commit: 0092ad11314fab232663f558ca6635b8fcc03133
workflow-type: tm+mt
source-wordcount: '742'
ht-degree: 67%

---


# Práticas recomendadas e limitações de mensagens transacionais {#transactional-messaging-limitations}

<img src="assets/do-not-localize/icon_concepts.svg" width="60px">

Esta seção lista as práticas recomendadas e limitações que você deve conhecer antes de começar a criar mensagens transacionais.

<!--For more on transactional messages, including on how to configure and create them, see [Getting started with transactional messaging](../../channels/using/getting-started-with-transactional-msg.md).-->

## Permissões {#permissions}

Somente os usuários com a função [Administration](../../administration/using/users-management.md#functional-administrators) podem configurar eventos transacionais e acessar mensagens transacionais.

## Configuração e publicação do evento {#design-and-publication}

Como você está configurando e publicando eventos transacionais, algumas das etapas que você precisa executar não podem ser revertidas. Você deve estar ciente das seguintes limitações:

* Os canais disponíveis para mensagens transacionais são: **[!UICONTROL Email]**, **[!UICONTROL Mobile (SMS)]** e **[!UICONTROL Push notification]**.
* Somente um canal pode ser usado para cada configuração de evento. Consulte [Criação de um evento](../../channels/using/configuring-transactional-event.md#creating-an-event).
* Depois que o evento é criado, não é possível alterar o canal. Portanto, se uma mensagem não for enviada, você precisará projetar o mecanismo para enviá-la de outro canal usando um fluxo de trabalho. Consulte [Dados e processos do fluxo de trabalho](../../automating/using/get-started-workflows.md).
* Você não poderá alterar o targeting dimension (**[!UICONTROL Real-time event]** ou **[!UICONTROL Profile]**) após a criação do evento. Consulte [Criação de um evento](../../channels/using/configuring-transactional-event.md#creating-an-event).
* Não é possível reverter uma publicação, mas você pode desfazer a publicação de um evento. Essa operação torna inacessíveis o evento e a mensagem transacional associada. Consulte [Desfazer a publicação de um evento](../../channels/using/publishing-transactional-event.md#unpublishing-an-event).
* A única mensagem transacional que pode ser associada a um evento é a criada automaticamente após a publicação do evento. Consulte [Pré-visualização e publicação do evento](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event).

## Número de mensagens transacionais {#transactional-message-number}

O número de mensagens transacionais publicados pode ter um impacto significativo na sua plataforma. Para obter o desempenho ideal, o número de mensagens transacionais publicados deve permanecer abaixo de 100. Para garantir isso, cancele a publicação ou exclua quaisquer mensagens transacionais não utilizados. Consulte [Cancelar a publicação de um mensagen transacional](../../channels/using/publishing-transactional-message.md#unpublishing-a-transactional-message) e [Excluindo um mensagen transacional](../../channels/using/publishing-transactional-message.md#deleting-a-transactional-message).

Para garantir o melhor desempenho, você também pode cancelar a publicação ou excluir eventos não utilizados. Na verdade, cancelar a publicação ou excluir um evento também cancelará a publicação ou excluirá os mensagens transacionais correspondentes e seu envio e logs de rastreamento, se houver. Consulte [Cancelar a publicação de um evento](../../channels/using/publishing-transactional-event.md#unpublishing-an-event) e [Excluindo um evento](../../channels/using/publishing-transactional-event.md#deleting-an-event).

## Personalização {#personalization}

O modo de personalização de um conteúdo de mensagem depende do tipo de mensagem transacional. As especificidades estão listadas abaixo.

### Mensagens transacionais baseadas em evento

* Os dados contidos no evento são a fonte das informações de personalização. Consulte [configuração de mensagen transacional baseada em Eventos](../../channels/using/configuring-transactional-event.md#event-based-transactional-messages).
* Você **não pode** usar **[!UICONTROL Unsubscription link]** blocos de conteúdo em um mensagen transacional de evento.
* As mensagens transacionais baseadas em evento só devem usar os dados contidos no evento enviado para definir o recipient e a personalização do conteúdo da mensagem. No entanto, você pode enriquecer o conteúdo da mensagem transacional usando informações do banco de dados do Adobe Campaign. Consulte [Enriquecendo um evento](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content) e [Personalizando um mensagen transacional](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message).
* Como as mensagens transacionais de evento não contêm informações sobre perfis, elas não são compatíveis com as regras de fadiga, até mesmo no caso de um enriquecimento com perfis.

### Mensagens transacionais baseadas em perfil

* Os dados contidos no evento ou do registro do perfil reconciliado podem ser a fonte das informações de personalização. Consulte [Configuração de mensagen transacional baseada em Perfis](../../channels/using/configuring-transactional-event.md#profile-based-transactional-messages) e [Especificações de mensagens transacionais baseadas em Perfis](../../channels/using/editing-transactional-message.md#profile-transactional-message-specificities).
* Você **pode** usar **[!UICONTROL Unsubscription link]** blocos de conteúdo em um mensagen transacional de perfil. Consulte [Adição de um bloco de conteúdo](../../designing/using/personalization.md#adding-a-content-block).
* As regras de fadiga são compatíveis com as mensagens transacionais de perfil. Consulte [Regras de fadiga](../../sending/using/fatigue-rules.md).

### Lista de produtos

Observe que as listas de produtos estão disponíveis somente em **mensagens de email transacionais**. Consulte [Uso das listagens de produtos em uma mensagem transacional](../../channels/using/editing-transactional-message.md#using-product-listings-in-a-transactional-message).

## Identidade visual {#permissions-and-branding}

No gerenciamento da [identidade visual](../../administration/using/branding.md), as mensagens transacionais são menos flexíveis do que as mensagens padrão. A Adobe recomenda vincular todas as marcas usadas nas mensagens transacionais à **[!UICONTROL All]** [unidade organizacional](../../administration/using/organizational-units.md). Para saber mais, leia a explicação detalhada abaixo.

Ao editar uma mensagem transacional, você pode vinculá-la a uma marca para aplicar automaticamente alguns parâmetros, como o nome ou o logotipo da marca. A opção **[!UICONTROL Default brand]** é selecionada por padrão nas propriedades da mensagem transacional.

![](assets/message-center_branding.png)

Todos os objetos (inclusive as marcas) usados em uma mensagem transacional devem estar visíveis na unidade organizacional **[!UICONTROL Message Center]**, o que significa que eles devem estar na **[!UICONTROL Message Center]** ou em unidades organizacionais **[!UICONTROL All]**.

No entanto, se a marca selecionada nas propriedades da mensagem estiver vinculada a uma unidade organizacional diferente de **[!UICONTROL Message Center]** ou **[!UICONTROL All]**, ocorrerá um erro e você não poderá enviar a mensagem transacional.

Portanto, se você quiser usar multimarcas no contexto de mensagens transacionais, vincule todas as marcas à unidade organizacional **[!UICONTROL Message Center]** ou **[!UICONTROL All]**.

## Exportação e importação de mensagens transacionais {#exporting-and-importing-transactional-messages}

* Para exportar uma mensagem transacional, é necessário incluir a configuração de evento correspondente ao [criar a exportação do pacote](../../automating/using/managing-packages.md#creating-a-package).
* Depois que a mensagem transacional for [importada em um pacote](../../automating/using/managing-packages.md#importing-a-package), ela não será exibida na lista de mensagens transacionais. Você precisará [publicar](../../channels/using/publishing-transactional-event.md) a configuração do evento para disponibilizar a mensagem transacional associada.
