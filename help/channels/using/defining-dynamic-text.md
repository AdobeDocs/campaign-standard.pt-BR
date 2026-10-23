---
title: Definição de texto dinâmico
description: Saiba como exibir textos diferentes dinamicamente para o usuário, de acordo com as condições definidas no Adobe Campaign.
audience: designing
content-type: reference
topic-tags: defining-conditional-content
feature: SMS
role: User
level: Beginner
exl-id: 649e3428-a3bf-470f-923c-04d9a57a208f
TQID: 'https://experienceleague.adobe.com/fgQySs0BUlvKT3CKMSaW-0fVe3W65qV1fDEZb1kDZ3w'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
subfeature_v2:
  - id: b1bd1421-1927-4c59-9bc6-ce292360e43b
    internal-label: SMS Messaging
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 3%
---
# Definição de texto dinâmico{#defining-dynamic-text}

O texto dinâmico é definido da mesma forma que o conteúdo dinâmico. Consulte a seção [Definição de conteúdo dinâmico](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).

>[!NOTE]
>
>Para SMS e push, você só pode definir texto dinâmico. Você pode definir conteúdo dinâmico e texto em uma página de aterrissagem. Se você quiser definir texto dinâmico com o [Designer de email](../../designing/using/designing-content-in-adobe-campaign.md), consulte [Definindo conteúdo dinâmico em um email](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).

Observe que pares substitutos, caracteres não incluídos no Plano Multilíngue Básico do conjunto de caracteres Unicode, não podem ser armazenados em 2 bytes (16 bits) e precisam ser codificados em 2 caracteres UTF-16. Esses personagens incluem alguns ideógrafos CJK, a maioria emojis e algumas línguas.
<br>Esses caracteres podem causar alguns problemas de incompatibilidade no texto dinâmico. Você precisa executar testes de segurança antes de enviar as mensagens.


O exemplo abaixo mostra como definir texto dinâmico em uma mensagem SMS.

1. Selecione o texto no corpo da mensagem ou landing page.
1. Clique em **[!UICONTROL Enable dynamic text]**.

   ![](assets/dynamic_text_sms_1.png)

   A opção **[!UICONTROL Dynamic text]** é exibida na paleta. Ela é configurada da mesma forma que o conteúdo dinâmico.

1. Selecione uma variante.

   ![](assets/dynamic_text_sms_2.png)

1. Defina uma condição para essa variante.

   ![](assets/dynamic_text_sms_4.png)

Depois que uma condição é definida para pelo menos uma variante, um quadro roxo é exibido ao redor do texto dinâmico.

![](assets/dynamic_text_sms_3.png)
