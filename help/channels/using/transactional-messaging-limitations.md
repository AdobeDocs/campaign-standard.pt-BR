---
title: Limitações de mensagens transacionais
description: Saiba mais sobre as principais limitações e recomendações relacionadas aos mensagens transacionais no Adobe Campaign Standard.
page-status-flag: never-activated
uuid: b316bf47-7d98-46fa-ab4f-67ff50de8095
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: ca8d1698-6e8a-4f5a-b017-74a152e14286
context-tags: landingPage,wizard;landingPage,overview;landingPage,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 88%

---


# Limitações de mensagens transacionais {#transactional-messaging-limitations}

<img src="assets/do-not-localize/icon_concepts.svg" width="60px">

A seção abaixo lista as limitações que você deve estar ciente antes de começar a criar mensagens transacionais.

Para obter mais informações sobre mensagens transacionais, incluindo sobre como configurá-los e criá-los, consulte [Introdução às mensagens](../../channels/using/getting-started-with-transactional-msg.md)transacionais.

>[!IMPORTANT]
>
>Para acessar as mensagens transacionais, você deve ter direitos administrativos.

## Design e publicação {#design-and-publication}

Quando você estiver projetando e publicando mensagens transacionais, algumas etapas necessárias não poderão ser revertidas. Você deve estar ciente das seguintes limitações:

* Somente um canal pode ser usado para cada configuração de evento. Consulte [Criação de um evento](../../administration/using/configuring-transactional-messaging.md#creating-an-event).
* Depois que o evento é criado, não é possível alterar o canal. Portanto, se uma mensagem não for enviada, você precisará projetar o mecanismo para enviá-la de outro canal usando um fluxo de trabalho. Consulte [Dados e processos do fluxo de trabalho](../../automating/using/get-started-workflows.md).
* Você não poderá alterar o targeting dimension (**[!UICONTROL Real-time event]** ou **[!UICONTROL Profile]**) após a criação do evento. Consulte [Criação de um evento](../../administration/using/configuring-transactional-messaging.md#creating-an-event).
* Não é possível reverter uma publicação, mas você pode desfazer a publicação de um evento. Essa operação torna inacessíveis o evento e a mensagem transacional associada. Consulte [Desfazer a publicação de um evento](../../administration/using/configuring-transactional-messaging.md#unpublishing-an-event).
* A única mensagem transacional que pode ser associada a um evento é a criada automaticamente após a publicação do evento. Consulte [Pré-visualização e publicação do evento](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event).

## Personalização {#personalization}

O modo de personalização de um conteúdo de mensagem depende do tipo de mensagem transacional. As especificidades estão listadas abaixo.

### Mensagens transacionais baseadas em evento

* Os dados contidos no evento são a fonte das informações de personalização. Consulte [Mensagens transacionais de evento](../../channels/using/event-transactional-messages.md).
* You **cannot** use **[!UICONTROL Unsubscription link]** content blocks in an event transactional message.
* As mensagens transacionais baseadas em evento só devem usar os dados contidos no evento enviado para definir o recipient e a personalização do conteúdo da mensagem. No entanto, você pode enriquecer o conteúdo da mensagem transacional usando informações do banco de dados do Adobe Campaign. Consulte [Enriquecimento de conteúdo de mensagens transacionais](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content).
* Como as mensagens transacionais de evento não contêm informações sobre perfis, elas não são compatíveis com as regras de fadiga, até mesmo no caso de um enriquecimento com perfis. Consulte [Regras de fadiga](../../sending/using/fatigue-rules.md).

### Mensagens transacionais baseadas em perfil

* Os dados contidos no evento ou do registro do perfil reconciliado podem ser a fonte das informações de personalização. Consulte [Mensagens transacionais de perfil](../../channels/using/profile-transactional-messages.md).
* You **can** use **[!UICONTROL Unsubscription link]** content blocks in a profile transactional message. Consulte [Adição de um bloco de conteúdo](../../designing/using/personalization.md#adding-a-content-block).
* As regras de fadiga são compatíveis com as mensagens transacionais de perfil. Consulte [Regras de fadiga](../../sending/using/fatigue-rules.md).

Observe que as listagens de produtos só estão disponíveis nas mensagens de email transacionais. Consulte [Uso das listagens de produtos em uma mensagem transacional](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message).

## Permissões e identidade visual {#permissions-and-branding}

No gerenciamento da [identidade visual](../../administration/using/branding.md), as mensagens transacionais são menos flexíveis do que as mensagens padrão. A Adobe recomenda vincular todas as marcas usadas nas mensagens transacionais à **[!UICONTROL All]** [unidade organizacional](../../administration/using/organizational-units.md). Para saber mais, leia a explicação detalhada abaixo.

Ao editar uma mensagem transacional, você pode vinculá-la a uma marca para aplicar automaticamente alguns parâmetros, como o nome ou o logotipo da marca. A opção **[!UICONTROL Default brand]** é selecionada por padrão nas propriedades da mensagem transacional.

![](assets/message-center_branding.png)

Todos os objetos (inclusive as marcas) usados em uma mensagem transacional devem estar visíveis na unidade organizacional **[!UICONTROL Message Center]**, o que significa que eles devem estar na **[!UICONTROL Message Center]** ou em unidades organizacionais **[!UICONTROL All]**.

No entanto, se a marca selecionada nas propriedades da mensagem estiver vinculada a uma unidade organizacional diferente de **[!UICONTROL Message Center]** ou **[!UICONTROL All]**, ocorrerá um erro e você não poderá enviar a mensagem transacional.

Portanto, se você quiser usar multimarcas no contexto de mensagens transacionais, vincule todas as marcas à unidade organizacional **[!UICONTROL Message Center]** ou **[!UICONTROL All]**.

## Exportação e importação de mensagens transacionais {#exporting-and-importing-transactional-messages}

* Para exportar uma mensagem transacional, é necessário incluir a configuração de evento correspondente ao [criar a exportação do pacote](../../automating/using/managing-packages.md#creating-a-package).
* Depois que a mensagem transacional for [importada em um pacote](../../automating/using/managing-packages.md#importing-a-package), ela não será exibida na lista de mensagens transacionais. Você precisará [publicar](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event) a configuração do evento para disponibilizar a mensagem transacional associada.
