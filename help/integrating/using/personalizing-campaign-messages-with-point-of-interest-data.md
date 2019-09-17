---
title: Personalização de mensagens da campanha com dados de Ponto de interesse
seo-title: Personalização de mensagens da campanha com dados de Ponto de interesse
description: Personalização de mensagens da campanha com dados de Ponto de interesse
seo-description: Saiba como criar uma mensagem personalizada com base na localização de seus assinantes com a integração de dados do Ponto de interesse.
page-status-flag: nunca ativado
uuid: d74c3e55-f130-441b-bc2a-06dcd5d9784
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: integrando
content-type: referência
topic-tags: trabalhar com campanha e análise para dispositivos móveis
discoiquuid: a1736ba3-5121-4d01-bf04-ebb7e701e2e0
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 781904d58f520987e978ad5d1cdc9e34871ca876

---


# Personalização de mensagens da campanha com dados de Ponto de interesse{#personalizing-campaign-messages-with-point-of-interest-data}

No Adobe Campaign, você pode usar os dados de Pontos de interesse coletados dos assinantes do aplicativo móvel para enviar mensagens de marketing personalizadas, como um email.

Você só pode reagir em dados de Ponto de interesse com entregas padrão. [Mensagens](../../channels/using/about-transactional-messaging.md) transacionais não podem usar dados de localização.

A primeira coisa que você pode reagir é cerca de 10 minutos.

Neste caso, você decide enviar um email para todos os assinantes que visitaram sua loja de Boston nas últimas duas semanas.

1. Crie uma atividade de marketing por email.
1. Ao definir o público-alvo da entrega, arraste e solte o **[!UICONTROL Subscriptions to an application]** elemento no espaço de trabalho.

   ![](assets/poi_subscriptions_app.png)

   O gerenciamento de públicos-alvo é detalhado na seção [Definição de públicos-alvo](../../audiences/using/creating-audiences.md) .

1. Na **[!UICONTROL Add a rule - Profile/Subscriptions to an application]** janela, arraste e solte o **[!UICONTROL POI Location Subscription]** elemento no espaço de trabalho.

   ![](assets/poi_add_rule_profile_subscription.png)

1. Na **[!UICONTROL Add a rule - POI Location Subscription]** janela, informe o rótulo do Ponto de interesse que deseja usar.

   ![](assets/poi_location_subscription.png)

1. No **[!UICONTROL Filter type]** campo, selecione **[!UICONTROL Relative]**.
1. Marque a **[!UICONTROL Preceding days]** opção e insira **[!UICONTROL 15]** no campo correspondente.
1. Defina o número de vezes que o usuário deve ter visitado o Ponto de interesse.
1. Clique **[!UICONTROL Confirm]** para salvar seu público-alvo.

   ![](assets/poi_subscriptions_app_audience_defined.png)

1. Adicione conteúdo ao seu email.

   ![](assets/poi_email_content.png)

1. Confirme a criação da atividade para exibir o painel do email.
1. Envie sua mensagem.

O e-mail com a oferta de desconto de 10% será enviado aos assinantes que:

* Visitou sua loja de Boston pelo menos uma vez nas últimas duas semanas.
* Teve seu aplicativo móvel em primeiro plano pelo menos uma vez durante a visita.

**Tópicos relacionados:**

* [Criação de um email](../../channels/using/creating-an-email.md)
* [Definição de conteúdo](../../designing/using/personalization.md#example-email-personalization)
* [Enviando mensagens](../../sending/using/confirming-the-send.md)

