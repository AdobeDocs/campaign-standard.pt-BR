---
title: Definição de uma condição de visibilidade
seo-title: Definição de uma condição de visibilidade
description: Definição de uma condição de visibilidade
seo-description: Torne um elemento de página da Web visível somente se uma determinada condição for respeitada.
page-status-flag: nunca ativado
uuid: 224005 ba-ef 09-4790-b 2 f 0-30 ed 74 cfa 32 d
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: definindo-conteúdo condicional
discoiquuid: c 12125 a 7-a 1 cf -4 bc 1-a 13ff 74ff 74024 4024
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Defining a visibility condition{#defining-a-visibility-condition}

Você pode especificar uma condição de visibilidade em qualquer elemento. Só estará visível se a condição for respeitada.

To add a visibility condition, select a block and enter the condition to be respected in the **[!UICONTROL Visibility condition]** field of its settings.

![](assets/delivery_content_5.png)

Essa opção está disponível apenas para os seguintes elementos: ADDRESS, BLOCKQUOTE, CENTER, DIR, DIV, DL, FIELDSET, FORM, H 1, H 2, H 2, H 4, H 4, NOSCRIPT, OL, P, PRE, UL, P, PRE, UL, TD.

The expression editor is presented in the [Advanced expression editing](../../automating/using/editing-queries.md#about-query-editor) section.

These conditions adopt the XTK expression syntax (e.g. **context.profile.email !=''** or **context.profile.status='0'**). Por padrão, todos os campos ficam visíveis.

>[!NOTE]
>
>Uma condição não pode ser definida para um bloco que já contém um subelemento com um conteúdo dinâmico ou um bloco que já compõem um conteúdo dinâmico. Blocos dinâmicos não visíveis, como listas suspensas, não podem ser editados.

