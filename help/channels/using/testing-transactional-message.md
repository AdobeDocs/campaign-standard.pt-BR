---
solution: Campaign Standard
product: campaign
title: Teste de mensagem transacional
description: Saiba como testar uma mensagem transacional no Adobe Campaign.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 40%

---


# Teste de mensagem transacional {#testing-a-transactional-message}

Antes de publicar a mensagem transacional, você pode criar um perfil de teste específico que permitirá verificar a mensagem corretamente.

## Definição de um perfil de teste específico {#defining-specific-test-profile}

Defina um perfil de teste que será vinculado ao evento, que permitirá pré-visualizar a mensagem e enviar uma prova relevante.

1. No [painel de mensagens transacionais](../../channels/using/editing-transactional-message.md#accessing-transactional-messages), clique no botão **[!UICONTROL Create test profile]**.

   ![](assets/message-center_test-profile.png)

1. Especifique as informações para enviar no formato JSON, na seção **[!UICONTROL Event data used for personalization]**. Esse é o conteúdo que será usado ao visualizar a mensagem e quando o perfil de teste receber a prova.

   ![](assets/message-center_event-data.png)

   >[!NOTE]
   >
   >Se você enriqueceu sua mensagem, também pode inserir informações relacionadas a outra tabela, como **[!UICONTROL Profile]**. Consulte [Enriquecendo o evento](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content) e [Personalizando uma mensagem transacional](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message).

1. Depois de criado, o perfil de teste será pré-especificado na mensagem transacional. Clique no bloco **[!UICONTROL Test profiles]** da mensagem para verificar o público-alvo da prova.

   ![](assets/message-center_5.png)

Você também pode criar um novo perfil de teste ou usar um que já existe no menu **[!UICONTROL Test profiles]**. Para fazer isso:

1. Clique no logotipo **[!UICONTROL Adobe Campaign]**, no canto superior esquerdo, em seguida, selecione **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Test profiles]**.
1. Na seção **[!UICONTROL Event]**, selecione o evento que acabou de criar. Neste exemplo, selecione &quot;Abandono de carrinho (EVTcartAbandonment)&quot;.
1. Especifique as informações para enviar no formato JSON na caixa de texto **[!UICONTROL Event data]**.

   ![](assets/message-center_3.png)

1. Salve as alterações.
1. [Acesse a ](../../channels/using/editing-transactional-message.md#accessing-transactional-messages) mensagem criada e selecione o perfil de teste atualizado.

**Tópicos relacionados:**

* [Gerenciamento de perfis de teste](../../audiences/using/managing-test-profiles.md)
* [Criação de públicos-alvo](../../audiences/using/creating-audiences.md)

## Envio de uma prova {#sending-proof}

Depois de criar um ou mais perfis de teste específicos e salvar a mensagem transacional, você pode enviar uma prova para testá-la.

![](assets/message-center_10.png)

As etapas para enviar uma prova são detalhadas na seção [Envio de provas](../../sending/using/sending-proofs.md) .
