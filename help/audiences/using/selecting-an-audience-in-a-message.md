---
title: Seleção de um público-alvo em uma mensagem
seo-title: Seleção de um público-alvo em uma mensagem
description: Seleção de um público-alvo em uma mensagem
seo-description: '«Procedimento passo a passo para escolher públicos de um email: principal público-alvo e perfis de teste. "'
page-status-flag: nunca ativado
uuid: 7 d 8 f 8446-f 2 e 0-49 c 1-83 f 6-9667 b 29 bc 228
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: públicos-alvo
content-type: reference
topic-tags: gerenciamento-público-alvo
discoiquuid: 158 da 6 ff -8899-4 e 7 b-b 925-8 a 42 c 3 de 46 a 1
context-tags: Deliverycreation, assistente; entrega, público-alvo, voltar
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c9e33f51ab497b8bd111dfc307670f2fde5d804f

---


# Selecting an audience in a message{#selecting-an-audience-in-a-message}

O Adobe Campaign permite que você configure vários tipos de perfil dentro do público-alvo de uma mensagem.

Os públicos-alvo podem ser definidos ao criar a mensagem através do assistente de criação ou do painel de mensagens, caso a mensagem já tenha sido criada.

>[!NOTE]
>
>Se o público-alvo foi criado dentro de um fluxo de trabalho e aprimorado com dados adicionais, você não poderá usar esses dados para personalizar uma entrega independente. Eles só podem ser usados a partir de uma entrega executada em um fluxo de trabalho.

1. No painel, acesse o bloco de público-alvo para iniciar.

   ![](assets/delivery_audience_definition_1.png)

   A tela para definir os públicos-alvo em seguida. Ele tem duas guias que permitem definir separadamente cada tipo de público que receberá a mensagem:

   * Target
   * Testar perfis
   ![](assets/delivery_audience_definition_2.png)

1. Define the main **[!UICONTROL Target]** of the email. Esse é o público-alvo de destino regular do email.

   The target is defined in the **[!UICONTROL Target]** tab and is made up of identified profiles from your database.

   You can establish your main target using the [query editor](../../automating/using/editing-queries.md#creating-queries) functionalities.

   In this tab, the **[!UICONTROL Shortcuts]** palette only contains predefined filters and the audiences that have been defined in the identified profiles. The **[!UICONTROL Explorer]** tab allows you to access additional configurations.

   Portanto, é possível reutilizar e combinar públicos existentes, aplicar filtros adicionais a eles, etc.

1. Define the **[!UICONTROL Test profiles]** you want to use for the email. Os perfis de teste receberão os testes que você pode enviar antes de testar o e-mail antes de enviá-lo para o destino principal.

   For more information on configuring test profiles, refer to the [Test profiles](../../sending/using/managing-test-profiles-and-sending-proofs.md) section.

O bloco de públicos-alvo é então atualizado e mostra que os perfis de destino e teste foram selecionados para o email em questão.

![](assets/delivery_audience_definition_3.png)

