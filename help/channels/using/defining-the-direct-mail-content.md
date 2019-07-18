---
title: Definição do conteúdo de mala direta
seo-title: Definição do conteúdo de mala direta
description: Definição do conteúdo de mala direta
seo-description: Saiba como definir o conteúdo da entrega de mala direta.
page-status-flag: nunca ativado
uuid: c 1234 c 06-4 d 22-46 d 7-ad 1 b -3 c 88660 f 9 b 06
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canais
content-type: reference
topic-tags: direta
discoiquuid: 9 e 73 d 6 b 5-41 b 4-474 b-a 880-a 0 cd 5999 c 2 d 1
context-tags: entrega, directmailcontent, back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b0cf437ec97153b53bd4502171b24286abb25731

---


# Defining the direct mail content{#defining-the-direct-mail-content}

You can either define the content in the last screen of the creation wizard or by clicking on the **Content** section of the delivery dashboard.

![](assets/direct_mail_6.png)

The **[!UICONTROL Content]** definition screen is specific to the direct mail channel. It is divided into four tabs: **[!UICONTROL Extraction]**, **[!UICONTROL File structure]**, **[!UICONTROL Header]** and **[!UICONTROL Footer]**.

![](assets/direct_mail_11.png)

## Defining the extraction {#defining-the-extraction}

1. Comece definindo o nome do arquivo de extração. Click on the button to the right of the **[!UICONTROL Output file]** field and enter the desired label. You can use personalization fields, content blocks and dynamic text (see [Defining content](../../designing/using/example--email-personalization.md)). Por exemplo, você pode concluir o rótulo com a ID de entrega ou a data de extração.

   ![](assets/direct_mail_12.png)

1. Click the **[!UICONTROL +]** or **[!UICONTROL Add an element]** button to add an output column. The **[!UICONTROL Output columns]** let you define the profile information (columns) to be exported into the output file.

   >[!CAUTION]
   >
   >Verifique se os perfis incluem um endereço postal, pois essas informações são essenciais para o provedor de mala direta. Also make sure you have checked the **[!UICONTROL Address specified]** box in your profiles' information. See [Recommendations](../../channels/using/about-direct-mail.md#recommendations).

   ![](assets/direct_mail_13.png)

1. Crie quantas colunas forem necessárias. É possível editar colunas clicando em suas expressões e etiquetas.

>[!NOTE]
>
>For more information on output column definition, refer to the [Extract file](../../automating/using/extract-file.md) workflow activity section.

## Defining the file structure {#defining-the-file-structure}

The **File structure** tab allows you to configure the output, date, and number formats for the file that will be exported.

![](assets/direct_mail_14.png)

>[!NOTE]
>
>The available options are detailed in the [Extract file](../../automating/using/extract-file.md) workflow activity sections.

## Defining the header and footer {#defining-the-header-and-footer}

Às vezes, pode ser necessário adicionar informações no início ou no final do arquivo de extração. For this, use the **[!UICONTROL Header]** and **[!UICONTROL Footer]** tabs of the **[!UICONTROL Content]** configuration screen.

![](assets/direct_mail_7.png)

Por exemplo, você pode querer incluir, para o provedor de mala direta, as informações do remetente no cabeçalho do arquivo. É possível personalizar o rodapé e o cabeçalho com as informações disponíveis no contexto da entrega. See [Defining content](../../designing/using/example--email-personalization.md).

The sender address is defined in the **[!UICONTROL Send]** section of the direct mail properties or at the template level.

![](assets/direct_mail_24.png)

