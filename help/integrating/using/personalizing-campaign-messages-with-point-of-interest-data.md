---
title: Personalização de mensagens de campanha com dados de Ponto de interesse
seo-title: Personalização de mensagens de campanha com dados de Ponto de interesse
description: Personalização de mensagens de campanha com dados de Ponto de interesse
seo-description: Saiba como criar uma mensagem personalizada com base na localização dos assinantes com a integração de dados do Ponto de interesse.
page-status-flag: nunca ativado
uuid: d 74 c 3 e 55-f 130-441 b-bc 2 a -06 ddcd 5 d 9784
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
discoiquuid: a 1736 ba 3-5121-4 d 01-bf 04-ebb 7 e 701 e 2 e 0
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Personalizing Campaign messages with Point of Interest data{#personalizing-campaign-messages-with-point-of-interest-data}

No Adobe Campaign, você pode usar os dados de Pontos de interesse coletados dos assinantes do aplicativo móvel para enviá-los mensagens de marketing personalizadas, como um email.

Você só pode reagir aos dados do Ponto de interesse com entregas padrão. [As mensagens transacionais](../../channels/using/about-transactional-messaging.md) não podem usar dados de localização.

Quanto mais cedo você puder reagir, é aproximadamente 10 minutos.

Nesse caso, você decide enviar um email para todos os assinantes que visitaram sua loja de Boston nas últimas duas semanas.

1. Crie uma atividade de marketing por email.
1. When defining the delivery's audience, drag and drop the **[!UICONTROL Subscriptions to an application]** element into the workspace.

   ![](assets/poi_subscriptions_app.png)

   Managing audiences is detailed in the [Defining audiences](../../audiences/using/creating-audiences.md) section.

1. In the **[!UICONTROL Add a rule - Profile/Subscriptions to an application]** window, drag and drop the **[!UICONTROL POI Location Subscription]** element into the workspace.

   ![](assets/poi_add_rule_profile_subscription.png)

1. In the **[!UICONTROL Add a rule - POI Location Subscription]** window, enter the label of the Point of Interest that you want to use.

   ![](assets/poi_location_subscription.png)

1. In the **[!UICONTROL Filter type]** field, select **[!UICONTROL Relative]**.
1. Check the **[!UICONTROL Preceding days]** option and enter **[!UICONTROL 15]** in the corresponding field.
1. Defina o número de vezes que o usuário deve ter visitado o Ponto de interesse.
1. Click **[!UICONTROL Confirm]** to save your audience.

   ![](assets/poi_subscriptions_app_audience_defined.png)

1. Adicione conteúdo ao seu e-mail.

   ![](assets/poi_email_content.png)

1. Confirme a criação da atividade para exibir o painel do email.
1. Envie sua mensagem.

O email com a oferta de desconto de 10% será enviado para assinantes que:

* Visite sua loja de Boston pelo menos uma vez nas últimas duas semanas.
* Tinha seu aplicativo móvel em primeiro plano pelo menos uma vez durante a visita.

**Tópicos relacionados:**

* [Criação de um email](../../channels/using/creating-an-email.md)
* [Definição de conteúdo](../../designing/using/example--email-personalization.md)
* [Enviar mensagens](../../sending/using/confirming-the-send.md)

