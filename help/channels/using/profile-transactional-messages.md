---
title: Mensagens transacionais de perfil
description: Saiba como criar e publicar uma mensagem transacional de perfil.
page-status-flag: never-activated
uuid: a8efe979-74ae-46ff-a305-b86a90679581
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: transactional-messaging
discoiquuid: dcb90afc-42c3-419e-8345-79cddf969e41
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 9c812b0b622b82ba7aa382f04edb7a2a3f717cd4
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 95%

---


# Mensagens transacionais de perfil{#profile-transactional-messages}

Você pode enviar mensagens transacionais com base nos perfis de marketing do cliente, o que permite:

* Aplicar regras de tipologia de marketing, como **[!UICONTROL Address on denylist]** ou [regras de fadiga](../../sending/using/fatigue-rules.md).
* Incluir o link de unsubscription nas mensagens.
* Adicionar as mensagens transacionais aos relatórios globais do delivery.
* Usar as mensagens transacionais na jornada do cliente.

Depois de criar e publicar um evento (o abandono do carrinho, conforme o [exemplo](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle) acima), a mensagem transacional correspondente será criada automaticamente.

As etapas de configuração são apresentadas na seção [Configuração de um evento para enviar uma mensagem transacional de perfil](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message).

Para que o evento acione o envio de uma mensagem transacional, é necessário personalizar a mensagem, testá-la e publicá-la.

>[!NOTE]
>
>Para acessar mensagens transacionais, você deve fazer parte do grupo de segurança **[!UICONTROL Administrators (all units)]**.
>
>As regras de fadiga são compatíveis com as mensagens transacionais de perfil. Consulte [Regras de fadiga](../../sending/using/fatigue-rules.md).

## Envio de uma mensagem transacional de perfil {#sending-a-profile-transactional-message}

As etapas para criar, personalizar e publicar uma mensagem transacional de perfil são as mesmas de uma mensagem transacional de evento. Consulte [Mensagens transacionais de evento](../../channels/using/event-transactional-messages.md).

As diferenças são listadas abaixo.

1. Acesse a mensagem transacional criada para editá-la.
1. Na mensagem transacional, clique na seção **[!UICONTROL Content]**. Além do template transacional, você também pode escolher qualquer direcionamento de template de email **[!UICONTROL Profile]**.

   ![](assets/message-center_marketing_templates.png)

1. Selecione o template de email padrão.

   Assim como todos os emails de marketing, ele inclui um link de unsubscription.

   ![](assets/message-center_marketing_perso_unsubscription.png)

   Além disso, ao contrário das configurações baseadas em eventos em tempo real, você tem acesso direto a todas as informações do perfil para personalizar a mensagem. Consulte [Inserção de um campo de personalização](../../designing/using/personalization.md#inserting-a-personalization-field).

1. Salve as alterações e publique a mensagem. Consulte [Publicação de uma mensagem transacional](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message).

## Monitoramento de um delivery de mensagem transacional de perfil {#monitoring-a-profile-transactional-message-delivery}

Quando a mensagem for publicada e a integração do site estiver concluída, você poderá monitorar o delivery.

1. Para exibir o log de delivery da mensagem, clique no ícone na parte inferior direita do bloco **[!UICONTROL Deployment]**.

   Para saber mais sobre como acessar os logs, consulte [Monitoramento do delivery](../../sending/using/monitoring-a-delivery.md).

1. Selecione a guia **[!UICONTROL Sending logs]**. Na coluna **[!UICONTROL Status]**, **[!UICONTROL Sent]** indica que um perfil foi aceito.

   ![](assets/message-center_marketing_sending_logs.png)

1. Select the **[!UICONTROL Exclusions logs]** tab to view recipients who have been excluded from the message target, such as addresses on denylist.

   ![](assets/message-center_marketing_exclusion_logs.png)

Para os perfis recusados, a regra de tipologia **[!UICONTROL Address on denylist]** exclui o recipient correspondente.

Essa regra faz parte de uma tipologia específica aplicável a todas as mensagens transacionais baseadas na tabela **[!UICONTROL Profile]**.

![](assets/message-center_marketing_typology.png)

**Tópicos relacionados**:

* [Integração do site](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)
* [Tipologias](../../sending/using/about-typology-rules.md)
