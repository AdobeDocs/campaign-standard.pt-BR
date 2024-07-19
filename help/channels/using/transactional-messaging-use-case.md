---
title: Caso de uso de mensagem transacional
description: Descubra um exemplo completo da funcionalidade de mensagens transacionais do Adobe Campaign.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: ee1a9705-4c21-4d46-a178-fde2e059f443
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 4%

---

# Caso de uso de mensagem transacional {#transactional-messaging-use-case}

Neste exemplo, você deseja usar a funcionalidade de mensagens transacionais do Adobe Campaign para enviar um email de confirmação após cada compra em seu site, identificando os clientes por meio da ID do CRM.

Os pré-requisitos são os seguintes:

* Verifique se o recurso **[!UICONTROL Profile]** foi estendido com um novo campo correspondente à ID do CRM.

* Crie e publique um recurso personalizado correspondente a compras e vincule-o ao recurso **[!UICONTROL Profile]**. Dessa forma, você poderá recuperar informações desse recurso para enriquecer o conteúdo da mensagem.

Para obter mais informações sobre extensão, criação e publicação de recursos, consulte [esta seção](../../developing/using/key-steps-to-add-a-resource.md).

As principais etapas para implementar esse caso de uso são apresentadas abaixo.

>[!NOTE]
>
>Para obter uma representação gráfica do processo geral de mensagens transacionais, consulte [este esquema](../../channels/using/getting-started-with-transactional-msg.md#key-steps).

## Etapa 1 - Criar e publicar a configuração do evento {#create-event-configuration}

1. Crie um novo evento usando o canal **[!UICONTROL Email]**. Consulte [Criação de um evento](../../channels/using/configuring-transactional-event.md#creating-an-event).

1. Selecione a **[!UICONTROL Profile]** targeting dimension para criar uma [mensagem transacional baseada em perfil](../../channels/using/configuring-transactional-event.md#profile-based-transactional-messages).

1. Defina os atributos que estarão disponíveis para personalizar a mensagem transacional. Neste exemplo, adicione os campos &quot;ID do CRM&quot; e &quot;Identificador de produto&quot;. Consulte [Definindo os atributos do evento](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes).

   ![](assets/message-center_usecase1.png)

1. Para enriquecer o conteúdo da mensagem com informações sobre as compras do cliente, crie um enriquecimento direcionado ao recurso **[!UICONTROL Purchase]**. Consulte [Enriquecimento do evento](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content).

   ![](assets/message-center_usecase2.png)

1. Crie uma condição de associação entre o campo &quot;Identificador de produto&quot; que foi adicionado anteriormente ao evento e o campo correspondente do recurso **[!UICONTROL Purchase]**.

   ![](assets/message-center_usecase3.png)

1. Como é obrigatório para eventos baseados em perfil, você também deve criar um enriquecimento direcionado ao recurso **[!UICONTROL Profile]**.

1. Crie uma condição de associação entre o campo &quot;ID do CRM&quot; que foi adicionado anteriormente à mensagem e o campo correspondente do recurso **[!UICONTROL Profile]** que você estendeu. <!--What's the purpose to have created a CRM ID for this event and to have the CRM ID as a join condition? could it be any other field provided you created it in the event?-->

   ![](assets/message-center_usecase4.png)

1. Na seção **[!UICONTROL Targeting enrichment]**, selecione o enriquecimento no recurso **[!UICONTROL Profile]**, que será usado como destino da mensagem durante a execução da entrega.

   ![](assets/message-center_usecase5.png)

1. Visualize e publique o evento. Consulte [Pré-visualização e publicação do evento](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event).

## Etapa 2 — edição e publicação da mensagem transacional {#create-transactional-message}

1. Vá para a mensagem transacional que foi criada automaticamente após a publicação do evento. Consulte [Acessando mensagens transacionais](../../channels/using/editing-transactional-message.md#accessing-transactional-messages).

1. Edite e personalize a mensagem. Consulte [Editar uma mensagem transacional de perfil](../../channels/using/editing-transactional-message.md#editing-profile-transactional-message).

1. Por meio da reconciliação com o campo &quot;ID do CRM&quot; que você adicionou ao recurso **[!UICONTROL Profile]**, você tem acesso direto a todas as informações do perfil para [personalizar](../../designing/using/personalization.md#inserting-a-personalization-field) sua mensagem.

   ![](assets/message-center_usecase6.png)

1. Por meio da reconciliação com o campo &quot;Identificador de produto&quot;, você pode enriquecer o conteúdo da mensagem com informações sobre as compras do cliente adicionando qualquer campo do recurso **[!UICONTROL Purchase]**.

   ![](assets/message-center_usecase7.png)

   Para fazer isso, selecione **[!UICONTROL Insert personalization field]** na barra de ferramentas contextual. No nó **[!UICONTROL Context]** > **[!UICONTROL Transactional event]** > **[!UICONTROL Event context]**, abra o nó correspondente ao recurso personalizado **[!UICONTROL Purchase]** e selecione qualquer campo.

1. Você pode testar sua mensagem usando um perfil de teste específico. Consulte [Teste de mensagem transacional](../../channels/using/testing-transactional-message.md#testing-a-transactional-message).

1. Quando o conteúdo estiver pronto, salve as alterações e publique a mensagem. Consulte [Publicação de uma mensagem transacional](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message).

## Etapa 3 - Integrar o acionamento de evento {#integrate-event-trigger}

Integre o evento ao seu site. Consulte [Integrar o acionador de evento](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger).

## Etapa 4 - Entrega de mensagem {#message-delivery}

Depois que todas essas etapas forem executadas, assim que um cliente comprar os produtos do seu site, ele receberá um email de confirmação personalizado, incluindo informações sobre a compra.
