---
title: Personalização de mensagens do Campaign com dados de Ponto de interesse
description: Saiba como criar uma mensagem personalizada com base na localização dos assinantes com a integração de dados do Ponto de interesse.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
feature: Audiences
role: Data Architect
level: Intermediate
exl-id: fcc79829-902d-4547-87c5-8a213e1257b7
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 10%

---

# Personalização de mensagens do Campaign com dados de Ponto de interesse{#personalizing-campaign-messages-with-point-of-interest-data}

No Adobe Campaign, você pode usar os dados de Pontos de interesse coletados dos assinantes do aplicativo móvel para enviar mensagens de marketing personalizadas a eles, como um email.

Você só pode reagir em dados de Ponto de interesse com deliveries padrão. [Mensagens transacionais](../../channels/using/getting-started-with-transactional-msg.md) O não pode usar dados de localização.

O mais antigo que você pode reagir é cerca de 10 minutos.

Nesse caso, você decide enviar um email para todos os assinantes que visitaram sua loja de Boston nas últimas duas semanas.

1. Crie uma atividade de marketing por email.
1. Ao definir o público do delivery, arraste e solte a variável **[!UICONTROL Subscriptions to an application]** no espaço de trabalho.

   ![](assets/poi_subscriptions_app.png)

   O gerenciamento de públicos-alvo é detalhado na seção [Definição de públicos-alvo](../../audiences/using/creating-audiences.md) seção.

1. No **[!UICONTROL Add a rule - Profile/Subscriptions to an application]** , arraste e solte a **[!UICONTROL POI Location Subscription]** no espaço de trabalho.

   ![](assets/poi_add_rule_profile_subscription.png)

1. No **[!UICONTROL Add a rule - POI Location Subscription]** , insira o rótulo do Ponto de interesse que deseja usar.

   ![](assets/poi_location_subscription.png)

1. No campo **[!UICONTROL Filter type]**, selecione **[!UICONTROL Relative]**.
1. Verifique a **[!UICONTROL Preceding days]** e insira **[!UICONTROL 15]** no campo correspondente.
1. Defina o número de vezes que o usuário deve ter visitado o Ponto de interesse.
1. Clique em **[!UICONTROL Confirm]** para salvar seu público-alvo.

   ![](assets/poi_subscriptions_app_audience_defined.png)

1. Adicione conteúdo ao seu email.

   ![](assets/poi_email_content.png)

1. Confirme a criação da atividade para exibir o painel do email.
1. Envie sua mensagem.

O email com a oferta de desconto de 10% será enviado para assinantes que:

* Visitou sua loja de Boston pelo menos uma vez nas últimas duas semanas.
* Teve seu aplicativo móvel em primeiro plano pelo menos uma vez durante a visita.

**Tópicos relacionados:**

* [Criação de um email](../../channels/using/creating-an-email.md)
* [Definição do conteúdo](../../designing/using/personalization.md#example-email-personalization)
* [Envio de mensagens](../../sending/using/confirming-the-send.md)
