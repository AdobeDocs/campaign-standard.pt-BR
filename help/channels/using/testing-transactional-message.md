---
title: Teste de mensagem transacional
description: Saiba como testar uma mensagem transacional no Adobe Campaign.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags:
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: 5138826d-ae08-403b-91ef-91027ef6e78e
TQID: 'https://experienceleague.adobe.com/13JYxn86ZNf9mBAnNCLGCW4M80IvRvkYvnEWmkqGnAU'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
subfeature_v2:
  - id: d3b34fea-a110-482f-adb2-aae8d686bac8
    internal-label: Transactional messaging
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 31%
---
# Teste de mensagem transacional {#testing-a-transactional-message}

Antes de publicar a mensagem transacional, você pode criar um perfil de teste específico que permitirá verificar a mensagem corretamente.

## Definição de um perfil de teste específico {#defining-specific-test-profile}

Defina um perfil de teste que será vinculado ao evento, o que permitirá pré-visualizar a mensagem e enviar uma prova relevante.

1. No [painel de mensagens transacionais](../../channels/using/editing-transactional-message.md#accessing-transactional-messages), clique no botão **[!UICONTROL Create test profile]**.

   ![](assets/message-center_test-profile.png)

1. Especifique as informações para enviar no formato JSON, na seção **[!UICONTROL Event data used for personalization]**. Esse é o conteúdo que será usado ao visualizar a mensagem e quando o perfil de teste receber a prova.

   ![](assets/message-center_event-data.png)

   >[!NOTE]
   >
   >Se você enriqueceu sua mensagem, também pode inserir informações relacionadas a outra tabela, como **[!UICONTROL Profile]**. Consulte [Enriquecimento do evento](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content) e [Personalização de uma mensagem transacional](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message).

1. Depois de criado, o perfil de teste será pré-especificado na mensagem transacional. Clique no bloco **[!UICONTROL Test profiles]** da mensagem para verificar o público-alvo da prova.

   ![](assets/message-center_5.png)

Você também pode criar um novo perfil de teste ou usar um que já existe no menu **[!UICONTROL Test profiles]**. Para isso:

1. Clique no logotipo **Adobe**, no canto superior esquerdo, e selecione **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Test profiles]**.
1. Na seção **[!UICONTROL Event]**, selecione o evento que acabou de criar. Neste exemplo, selecione &quot;Abandono de carrinho (EVTcartAbandonment)&quot;.
1. Especifique as informações para enviar no formato JSON na caixa de texto **[!UICONTROL Event data]**.

   ![](assets/message-center_3.png)

1. Salve as alterações.
1. [Acesse a mensagem](../../channels/using/editing-transactional-message.md#accessing-transactional-messages) que você criou e selecione o perfil de teste atualizado.

**Tópicos relacionados:**

* [Gerenciamento de perfis de teste](../../audiences/using/managing-test-profiles.md)
* [Criação de públicos-alvo](../../audiences/using/creating-audiences.md)

## Envio de uma prova {#sending-proof}

Depois de criar um ou mais perfis de teste específicos e salvar a mensagem transacional, você pode enviar uma prova para testá-la.

![](assets/message-center_10.png)

As etapas para enviar uma prova estão detalhadas na seção [Enviar provas](../../sending/using/sending-proofs.md).
