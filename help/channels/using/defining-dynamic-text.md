---
title: Definição de texto dinâmico
description: Saiba como exibir textos diferentes dinamicamente para o usuário, de acordo com as condições definidas no Adobe Campaign.
page-status-flag: never-activated
uuid: bbcd200c-4fb4-467b-ba39-09b8bee9bcaa
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: defining-conditional-content
discoiquuid: 6bb6cee3-5674-4113-8073-5a9572b3e830
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 564613ecc2879be87d1f85f9f15e675697690139
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 3%

---


# Definição de texto dinâmico{#defining-dynamic-text}

O texto dinâmico é definido da mesma forma que o conteúdo dinâmico. Consulte a seção [Definição de conteúdo](../../designing/using/personalization.md#defining-dynamic-content-in-an-email) dinâmico.

>[!NOTE]
>
>Para SMS e push, você só pode definir texto dinâmico. É possível definir o conteúdo dinâmico e o texto em uma landing page. Se desejar definir um texto dinâmico com o [Email Designer](../../designing/using/designing-content-in-adobe-campaign.md), consulte [Definição de conteúdo dinâmico em um email](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).

Observe que pares substitutos, caracteres não incluídos no Plano Multilingue Básico do conjunto de caracteres Unicode, não podem ser armazenados em 2 bytes (16 bits) e precisam ser codificados em 2 caracteres UTF-16. Esses caracteres incluem algumas ideografias CJK, a maioria dos emojis e alguns idiomas.
<br>Esses caracteres podem causar alguns problemas de incompatibilidade no texto dinâmico. É necessário realizar testes fortes antes de enviar suas mensagens.


O exemplo abaixo mostra como definir um texto dinâmico em uma mensagem SMS.

1. Selecione o texto no corpo da sua mensagem ou landing page.
1. Clique em **[!UICONTROL Enable dynamic text]**.

   ![](assets/dynamic_text_sms_1.png)

   A **[!UICONTROL Dynamic text]** opção é exibida na paleta. É configurado da mesma forma que o conteúdo dinâmico.

1. Selecione uma variante.

   ![](assets/dynamic_text_sms_2.png)

1. Defina uma condição para essa variante.

   ![](assets/dynamic_text_sms_4.png)

Depois que uma condição é definida para pelo menos uma variante, um quadro violeta é exibido ao redor do texto dinâmico.

![](assets/dynamic_text_sms_3.png)

