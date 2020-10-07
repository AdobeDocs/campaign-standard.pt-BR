---
title: Personalização de mensagens do Campaign com dados de Ponto de interesse
description: Saiba como criar uma mensagem personalizada com base na localização de seus assinantes com a integração de dados do Ponto de interesse.
page-status-flag: never-activated
uuid: d74c3e55-f130-441b-bc2a-06ddcd5d9784
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
discoiquuid: a1736ba3-5121-4d01-bf04-ebb7e701e2e0
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 10%

---


# Personalização de mensagens do Campaign com dados de Ponto de interesse{#personalizing-campaign-messages-with-point-of-interest-data}

No Adobe Campaign, você pode usar os dados de Pontos de interesse coletados dos assinantes de seu aplicativo móvel para enviar mensagens de marketing personalizadas, como um email.

Você só pode reagir em dados de Ponto de interesse com delivery padrão. [Os mensagens transacionais](../../channels/using/getting-started-with-transactional-msg.md) não podem usar dados de localização.

A primeira coisa que você pode reagir é cerca de 10 minutos.

Neste caso, você decide enviar um email para todos os assinantes que visitaram sua loja de Boston nas últimas duas semanas.

1. Crie uma atividade de marketing por email.
1. Ao definir a audiência do delivery, arraste e solte o **[!UICONTROL Subscriptions to an application]** elemento na área de trabalho.

   ![](assets/poi_subscriptions_app.png)

   O gerenciamento de audiências é detalhado na seção [Definição de audiências](../../audiences/using/creating-audiences.md) .

1. In the **[!UICONTROL Add a rule - Profile/Subscriptions to an application]** window, drag and drop the **[!UICONTROL POI Location Subscription]** element into the workspace.

   ![](assets/poi_add_rule_profile_subscription.png)

1. Na **[!UICONTROL Add a rule - POI Location Subscription]** janela, informe o rótulo do Ponto de interesse que você deseja usar.

   ![](assets/poi_location_subscription.png)

1. No campo **[!UICONTROL Filter type]**, selecione **[!UICONTROL Relative]**.
1. Marque a **[!UICONTROL Preceding days]** opção e insira **[!UICONTROL 15]** no campo correspondente.
1. Defina o número de vezes que o usuário deve ter visitado o Ponto de interesse.
1. Click **[!UICONTROL Confirm]** to save your audience.

   ![](assets/poi_subscriptions_app_audience_defined.png)

1. Adicione conteúdo ao seu email.

   ![](assets/poi_email_content.png)

1. Confirme a criação da atividade para visualização do painel do email.
1. Envie sua mensagem.

O e-mail com a oferta de 10% de desconto será enviado aos assinantes que:

* Visitou sua loja de Boston pelo menos uma vez nas últimas duas semanas.
* Teve seu aplicativo móvel em primeiro plano pelo menos uma vez durante a visita.

**Tópicos relacionados:**

* [Criação de email](../../channels/using/creating-an-email.md)
* [Definição de conteúdo](../../designing/using/personalization.md#example-email-personalization)
* [Envio de mensagens](../../sending/using/confirming-the-send.md)

