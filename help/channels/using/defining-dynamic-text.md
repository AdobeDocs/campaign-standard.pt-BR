---
solution: Campaign Standard
product: campaign
title: Definição de texto dinâmico
description: Saiba como exibir textos diferentes dinamicamente para o usuário de acordo com as condições definidas no Adobe Campaign.
audience: designing
content-type: reference
topic-tags: defining-conditional-content
feature: SMS
role: Business Practitioner
level: Beginner
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 3%

---


# Definição de texto dinâmico{#defining-dynamic-text}

O texto dinâmico é definido da mesma forma que o conteúdo dinâmico. Consulte a seção [Definição de conteúdo dinâmico](../../designing/using/personalization.md#defining-dynamic-content-in-an-email) .

>[!NOTE]
>
>Para SMS e push, você só pode definir texto dinâmico. Você pode definir conteúdo dinâmico e texto em uma página de aterrissagem. Se desejar definir um texto dinâmico com o [Email Designer](../../designing/using/designing-content-in-adobe-campaign.md), consulte [Definição de conteúdo dinâmico em um email](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).

Observe que os pares substitutos, caracteres não incluídos no Plano Multilingue Básico do conjunto de caracteres Unicode, não podem ser armazenados em 2 bytes (16 bits) e precisam ser codificados em 2 caracteres UTF-16. Esses caracteres incluem alguns ideogramas CJK, a maioria dos emojis e alguns idiomas.
<br>Esses caracteres podem causar alguns problemas de incompatibilidade no texto dinâmico. Você precisa realizar testes fortes antes de enviar suas mensagens.


O exemplo abaixo mostra como definir texto dinâmico em uma mensagem SMS.

1. Selecione o texto no corpo da mensagem ou na landing page.
1. Clique em **[!UICONTROL Enable dynamic text]**.

   ![](assets/dynamic_text_sms_1.png)

   A opção **[!UICONTROL Dynamic text]** é exibida na paleta. Ele é configurado da mesma forma que o conteúdo dinâmico.

1. Selecione uma variante.

   ![](assets/dynamic_text_sms_2.png)

1. Defina uma condição para essa variante.

   ![](assets/dynamic_text_sms_4.png)

Depois que uma condição é definida para pelo menos uma variante, um quadro violeta é exibido ao redor do texto dinâmico.

![](assets/dynamic_text_sms_3.png)
