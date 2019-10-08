---
title: Mensagens transacionais de perfil
seo-title: Mensagens transacionais de perfil
description: Mensagens transacionais de perfil
seo-description: Saiba como criar e publicar uma mensagem transacional de perfil.
page-status-flag: nunca ativado
uuid: a8efe979-74ae-46ff-a305-b86a90679581
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: canais
content-type: referência
topic-tags: mensagens transacionais
discoiquuid: dcb90afc-42c3-419e-8345-79cdf969e41
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: fad149d30d06f285a89f13e4c8bff20932297695

---


# Mensagens transacionais de perfil{#profile-transactional-messages}

Você pode enviar mensagens transacionais com base nos perfis de marketing do cliente, o que permite:

* Aplique regras de tipologia de marketing, como **[!UICONTROL Blacklisted address]** regras de [fadiga](../../administration/using/fatigue-rules.md).
* Inclua o link de cancelamento de assinatura nas mensagens.
* Adicione as mensagens transacionais ao relatório de entrega global.
* Aproveite as mensagens transacionais na jornada do cliente.

Depois que você criar e publicar um evento (o abandono do carrinho de acordo com o [exemplo](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle) acima), a mensagem transacional correspondente será criada automaticamente.

As etapas de configuração são apresentadas na seção [Configuração de um evento para enviar uma mensagem](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) transacional de perfil.

Para que o evento dispare o envio de uma mensagem transacional, é necessário personalizar a mensagem, testá-la e publicá-la.

>[!NOTE]
>
>Para acessar mensagens transacionais, você deve fazer parte do grupo de **[!UICONTROL Administrators (all units)]** segurança.
>
>As regras de fadiga são compatíveis com mensagens transacionais de perfil. Consulte Regras de [fadiga](../../administration/using/fatigue-rules.md).

## Envio de uma mensagem transacional de perfil {#sending-a-profile-transactional-message}

As etapas para criar, personalizar e publicar uma mensagem transacional de perfil são as mesmas de uma mensagem transacional de evento. Consulte Mensagens [transacionais de](../../channels/using/event-transactional-messages.md)evento.

As diferenças estão listadas abaixo.

1. Vá para a mensagem transacional criada para editá-la.
1. Na mensagem transacional, clique na **[!UICONTROL Content]** seção. Além do modelo transacional, você também pode escolher qualquer direcionamento de modelo de email **[!UICONTROL Profile]**.

   ![](assets/message-center_marketing_templates.png)

1. Selecione o modelo de email padrão.

   Semelhante a todos os emails de marketing, ele inclui um link para cancelar a assinatura.

   ![](assets/message-center_marketing_perso_unsubscription.png)

   Além disso, ao contrário das configurações baseadas em eventos em tempo real, você tem acesso direto a todas as informações do perfil para personalizar sua mensagem. See [Inserting a personalization field](../../designing/using/personalization.md#inserting-a-personalization-field).

1. Salve as alterações e publique a mensagem. Consulte [Publicar uma mensagem](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message)transacional.

## Monitorando a entrega de mensagens transacionais de perfil {#monitoring-a-profile-transactional-message-delivery}

Quando a mensagem for publicada e a integração do site estiver concluída, você poderá monitorar a entrega.

1. Para exibir o log de entrega da mensagem, clique no ícone na parte inferior direita do **[!UICONTROL Deployment]** bloco.

   Para obter mais informações sobre como acessar os registros, consulte [Monitoramento da entrega](../../sending/using/monitoring-a-delivery.md).

1. Select the **[!UICONTROL Sending logs]** tab. Na **[!UICONTROL Status]** coluna, **[!UICONTROL Sent]** indica que um perfil optou por participar.

   ![](assets/message-center_marketing_sending_logs.png)

1. Selecione a **[!UICONTROL Exclusions logs]** guia para exibir destinatários que foram excluídos do destino da mensagem, como endereços da lista negra.

   ![](assets/message-center_marketing_exclusion_logs.png)

Para qualquer perfil que tenha rejeitado, a regra de **[!UICONTROL Blacklisted address]** tipologia excluiu o destinatário correspondente.

Essa regra faz parte de uma tipologia específica que se aplica a todas as mensagens transacionais com base na **[!UICONTROL Profile]** tabela.

![](assets/message-center_marketing_typology.png)

**Tópicos relacionados**:

* [Integração do site](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)
* [Tipologias](../../administration/using/about-typology-rules.md)

