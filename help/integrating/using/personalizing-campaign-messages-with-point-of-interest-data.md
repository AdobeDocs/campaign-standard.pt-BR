---
solution: Campaign Standard
product: campaign
title: Personalização de mensagens do Campaign com dados de Ponto de interesse
description: Saiba como criar uma mensagem personalizada com base na localização dos assinantes com a integração de dados do Ponto de interesse.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
feature: Audiences
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 10%

---


# Personalização de mensagens do Campaign com dados de Ponto de interesse{#personalizing-campaign-messages-with-point-of-interest-data}

No Adobe Campaign, você pode usar os dados de Pontos de interesse coletados dos assinantes do aplicativo móvel para enviar mensagens de marketing personalizadas a eles, como um email.

Você só pode reagir em dados de Ponto de interesse com deliveries padrão. [As ](../../channels/using/getting-started-with-transactional-msg.md) mensagens transacionais não podem usar dados de localização.

O mais antigo que você pode reagir é cerca de 10 minutos.

Nesse caso, você decide enviar um email para todos os assinantes que visitaram sua loja de Boston nas últimas duas semanas.

1. Crie uma atividade de marketing por email.
1. Ao definir o público do delivery, arraste e solte o elemento **[!UICONTROL Subscriptions to an application]** no espaço de trabalho.

   ![](assets/poi_subscriptions_app.png)

   O gerenciamento de públicos-alvo é detalhado na seção [Definição de públicos-alvo](../../audiences/using/creating-audiences.md) .

1. Na janela **[!UICONTROL Add a rule - Profile/Subscriptions to an application]**, arraste e solte o elemento **[!UICONTROL POI Location Subscription]** no espaço de trabalho.

   ![](assets/poi_add_rule_profile_subscription.png)

1. Na janela **[!UICONTROL Add a rule - POI Location Subscription]**, insira o rótulo do Ponto de interesse que deseja usar.

   ![](assets/poi_location_subscription.png)

1. No campo **[!UICONTROL Filter type]**, selecione **[!UICONTROL Relative]**.
1. Marque a opção **[!UICONTROL Preceding days]** e insira **[!UICONTROL 15]** no campo correspondente.
1. Defina o número de vezes que o usuário deve ter visitado o Ponto de interesse.
1. Clique em **[!UICONTROL Confirm]** para salvar o público-alvo.

   ![](assets/poi_subscriptions_app_audience_defined.png)

1. Adicione conteúdo ao seu email.

   ![](assets/poi_email_content.png)

1. Confirme a criação da atividade para exibir o painel do email.
1. Envie sua mensagem.

O email com a oferta de desconto de 10% será enviado para assinantes que:

* Visitou sua loja de Boston pelo menos uma vez nas últimas duas semanas.
* Teve seu aplicativo móvel em primeiro plano pelo menos uma vez durante a visita.

**Tópicos relacionados:**

* [Criar email](../../channels/using/creating-an-email.md)
* [Definição do conteúdo](../../designing/using/personalization.md#example-email-personalization)
* [Envio de mensagens](../../sending/using/confirming-the-send.md)

