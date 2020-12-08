---
title: Configuração de mensagens transacionais
description: Saiba como configurar mensagens transacionais.
page-status-flag: never-activated
uuid: 4caeadbe-f4a7-43ce-986d-e99fa9ca0d0d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 3f968556-e774-43dc-a0b8-7188d7665fbc
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: caa41d6c727385bd6e77f64750872f191a5ad040
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 3%

---


# Caso de uso de mensagens transacionais {#transactional-messaging-use-case}

Neste exemplo, você deseja usar a funcionalidade de mensagens transacionais da Adobe Campaign para enviar um e-mail de confirmação após cada compra em seu site, identificando seus clientes por meio da ID do CRM.

Os pré-requisitos são os seguintes:

* Verifique se o recurso **[!UICONTROL Profile]** foi estendido com um novo campo correspondente à ID do CRM.

* Crie e publique um recurso personalizado correspondente a compras e vincule-o ao recurso **[!UICONTROL Profile]**. Dessa forma, você poderá recuperar informações desse recurso para enriquecer o conteúdo da mensagem.

Para obter mais informações sobre como estender, criar e publicar recursos, consulte [esta seção](../../developing/using/key-steps-to-add-a-resource.md).

As principais etapas para implementar este caso de uso são apresentadas abaixo.

>[!NOTE]
>
>Para obter uma representação gráfica do processo geral de mensagens transacionais, consulte [este schema](../../channels/using/getting-started-with-transactional-msg.md#key-steps).

## Etapa 1 - Criar e publicar a configuração do evento {#create-event-configuration}

1. Crie um novo evento usando o canal **[!UICONTROL Email]**. Consulte [Criação de um evento](../../channels/using/configuring-transactional-event.md#creating-an-event).

1. Selecione o targeting dimension **[!UICONTROL Profile]** para criar um mensagen transacional [baseado em perfis](../../channels/using/configuring-transactional-event.md#profile-based-transactional-messages).

1. Defina os atributos que estarão disponíveis para personalizar o mensagen transacional. Neste exemplo, adicione os campos &quot;ID do CRM&quot; e &quot;Identificador do produto&quot;. Consulte [Definição dos atributos do evento](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes).

   ![](assets/message-center_usecase1.png)

1. Para enriquecer o conteúdo da mensagem com informações relacionadas às compras do cliente, crie um enriquecimento direcionado ao recurso **[!UICONTROL Purchase]**. Consulte [Enriquecendo o evento](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content).

   ![](assets/message-center_usecase2.png)

1. Crie uma condição de junção entre o campo &quot;Identificador do produto&quot; que foi adicionado anteriormente ao evento e o campo correspondente do recurso **[!UICONTROL Purchase]**.

   ![](assets/message-center_usecase3.png)

1. Como é obrigatório para eventos baseados em perfis, você também deve criar um enriquecimento direcionado para o recurso **[!UICONTROL Profile]**.

1. Crie uma condição de junção entre o campo &quot;ID do CRM&quot; que foi adicionado anteriormente à mensagem e o campo correspondente do recurso **[!UICONTROL Profile]** que você estendeu. <!--What's the purpose to have created a CRM ID for this event and to have the CRM ID as a join condition? could it be any other field provided you created it in the event?-->

   ![](assets/message-center_usecase4.png)

1. Na seção **[!UICONTROL Targeting enrichment]**, selecione o enriquecimento no recurso **[!UICONTROL Profile]**, que será usado como o público alvo de mensagens durante a execução do delivery.

   ![](assets/message-center_usecase5.png)

1. Pré-visualização e publique o evento. Consulte [Pré-visualização e publicação do evento](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event).

## Etapa 2 - Editar e publicar o mensagen transacional {#create-transactional-message}

1. Vá para o mensagen transacional que foi criado automaticamente após a publicação do evento. Consulte [Acesso a mensagens transacionais](../../channels/using/editing-transactional-message.md#accessing-transactional-messages).

1. Edite e personalize a mensagem. Consulte [Editar um mensagen transacional de perfil](../../channels/using/editing-transactional-message.md#editing-profile-transactional-message).

1. Por meio da reconciliação com o campo &quot;ID do CRM&quot; que você adicionou ao recurso **[!UICONTROL Profile]**, você tem acesso direto a todas as informações do perfil para [personalizar](../../designing/using/personalization.md#inserting-a-personalization-field) sua mensagem.

   ![](assets/message-center_usecase6.png)

1. Por meio da reconciliação com o campo &quot;Identificador do produto&quot;, é possível aprimorar o conteúdo da mensagem com informações relacionadas às compras do cliente, adicionando qualquer campo do recurso **[!UICONTROL Purchase]**.

   ![](assets/message-center_usecase7.png)

   Para fazer isso, selecione **[!UICONTROL Insert personalization field]** na barra de ferramentas contextual. No nó **[!UICONTROL Context]** > **[!UICONTROL Transactional event]** > **[!UICONTROL Event context]**, abra o nó correspondente ao recurso personalizado **[!UICONTROL Purchase]** e selecione qualquer campo.

1. Você pode testar sua mensagem usando um perfil de teste específico. Consulte [Testando um mensagen transacional](../../channels/using/testing-transactional-message.md#testing-a-transactional-message).

1. Quando o conteúdo estiver pronto, salve as alterações e publique a mensagem. Consulte [Publicação de uma mensagem transacional](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message).

## Etapa 3 - Integrar o acionamento do evento {#integrate-event-trigger}

Integre o evento ao seu site. Consulte [Integrar o evento que dispara](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger).

## Etapa 4 - delivery de mensagem {#message-delivery}

Assim que todas essas etapas forem executadas, assim que um cliente comprar produtos de seu site, ele receberá um email de confirmação personalizado, incluindo informações sobre sua compra.