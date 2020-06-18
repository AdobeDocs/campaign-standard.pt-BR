---
title: Mensagens transacionais de perfil
description: Saiba como criar e publicar um mensagen transacional de perfil.
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
source-git-commit: 012546e109b085b7ed968bcefa8f76482656ae0d
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 2%

---


# Mensagens transacionais de perfil{#profile-transactional-messages}

Você pode enviar mensagens transacionais com base em perfis de marketing do cliente, o que permite:

* Aplique regras de tipologia de marketing, como **[!UICONTROL Address on block list]** regras de [fadiga](../../sending/using/fatigue-rules.md).
* Inclua o link de unsubscription nas mensagens.
* Adicione os mensagens transacionais ao relatórios global do delivery.
* Aproveite os mensagens transacionais na jornada do cliente.

Depois que você criar e publicar um evento (o abandono do carrinho, conforme o [exemplo](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle) acima), o mensagen transacional correspondente será criado automaticamente.

As etapas de configuração são apresentadas na seção [Configuração de um evento para enviar um mensagen transacional](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) de perfil.

Para que o evento acione o envio de um mensagen transacional, é necessário personalizar a mensagem, testá-la e publicá-la.

>[!NOTE]
>
>Para acessar mensagens transacionais, você deve fazer parte do grupo de **[!UICONTROL Administrators (all units)]** segurança.
>
>As regras de fadiga são compatíveis com mensagens transacionais perfis. Consulte Regras de [fadiga](../../sending/using/fatigue-rules.md).

## Envio de um mensagen transacional de perfil {#sending-a-profile-transactional-message}

As etapas para criar, personalizar e publicar um mensagen transacional de perfil são as mesmas de um mensagen transacional de evento. See [Event transactional messages](../../channels/using/event-transactional-messages.md).

As diferenças estão listadas abaixo.

1. Vá para o mensagen transacional criado para editá-lo.
1. No mensagen transacional, clique na **[!UICONTROL Content]** seção. Além do modelo transacional, você também pode escolher qualquer direcionamento de modelo de email **[!UICONTROL Profile]**.

   ![](assets/message-center_marketing_templates.png)

1. Selecione o modelo de email padrão.

   Semelhante a todos os emails de marketing, ele inclui um link de unsubscription.

   ![](assets/message-center_marketing_perso_unsubscription.png)

   Além disso, ao contrário das configurações baseadas em eventos em tempo real, você tem acesso direto a todas as informações do perfil para personalizar sua mensagem. See [Inserting a personalization field](../../designing/using/personalization.md#inserting-a-personalization-field).

1. Salve as alterações e publique a mensagem. Consulte [Publicação de um mensagen transacional](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message).

## Monitoramento de um delivery de mensagen transacional de perfil {#monitoring-a-profile-transactional-message-delivery}

Quando a mensagem for publicada e a integração do site estiver concluída, você poderá monitorar o delivery.

1. Para visualização do registro de delivery de mensagens, clique no ícone na parte inferior direita do **[!UICONTROL Deployment]** bloco.

   Para obter mais informações sobre como acessar os registros, consulte [Monitoramento do delivery](../../sending/using/monitoring-a-delivery.md).

1. Select the **[!UICONTROL Sending logs]** tab. Na **[!UICONTROL Status]** coluna, **[!UICONTROL Sent]** indica que um perfil opt in.

   ![](assets/message-center_marketing_sending_logs.png)

1. Selecione a **[!UICONTROL Exclusions logs]** guia para visualização de recipient que foram excluídos do público alvo de mensagens, como endereços na lista de blocos.

   ![](assets/message-center_marketing_exclusion_logs.png)

Para qualquer perfil que tenha opt out, a **[!UICONTROL Address on block list]** regra de tipologia excluiu o recipient correspondente.

Essa regra faz parte de uma tipologia específica que se aplica a todos os mensagens transacionais baseados na **[!UICONTROL Profile]** tabela.

![](assets/message-center_marketing_typology.png)

**Tópicos relacionados**:

* [Integração do site](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)
* [Tipologias](../../sending/using/about-typology-rules.md)

