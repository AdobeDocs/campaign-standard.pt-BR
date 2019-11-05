---
title: Definição do conteúdo de correio direto
description: Saiba como definir o conteúdo para a entrega de mala direta.
page-status-flag: nunca ativado
uuid: c1234c06-4d22-46d7-ad1b-3c88660f9b06
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: canais
content-type: referência
topic-tags: correio direto
discoiquuid: 9e73d6b5-41b4-474b-a880-a0cd5999c2d1
context-tags: entrega,directMailContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Definição do conteúdo de correio direto{#defining-the-direct-mail-content}

Você pode definir o conteúdo na última tela do assistente de criação ou clicando na seção **Conteúdo** do painel de entrega.

![](assets/direct_mail_6.png)

A tela de **[!UICONTROL Content]** definição é específica para o canal de mala direta. Ele é dividido em quatro guias: **[!UICONTROL Extraction]**, **[!UICONTROL File structure]**, **[!UICONTROL Header]** e **[!UICONTROL Footer]**.

![](assets/direct_mail_11.png)

## Definição da extração {#defining-the-extraction}

1. Comece definindo o nome do arquivo de extração. Clique no botão à direita do **[!UICONTROL Output file]** campo e insira o rótulo desejado. Você pode usar campos de personalização, blocos de conteúdo e texto dinâmico (consulte [Definição de conteúdo](../../designing/using/personalization.md#example-email-personalization)). Por exemplo, você pode preencher o rótulo com a ID de entrega ou a data de extração.

   ![](assets/direct_mail_12.png)

1. Clique no botão **[!UICONTROL +]** ou **[!UICONTROL Add an element]** para adicionar uma coluna de saída. O **[!UICONTROL Output columns]** permite que você defina as informações do perfil (colunas) a serem exportadas para o arquivo de saída.

   >[!CAUTION]
   >
   >Certifique-se de que seus perfis incluam um endereço postal, pois essas informações são essenciais para o provedor de mala direta. Verifique também se você marcou a **[!UICONTROL Address specified]** caixa nas informações de seus perfis. Consulte [Recomendações](../../channels/using/about-direct-mail.md#recommendations).

   ![](assets/direct_mail_13.png)

1. Crie quantas colunas forem necessárias. É possível editar colunas clicando em suas expressões e rótulos.

>[!NOTE]
>
>Para obter mais informações sobre a definição da coluna de saída, consulte a seção [Extrair atividade do fluxo de trabalho do arquivo](../../automating/using/extract-file.md) .

## Definição da estrutura do arquivo {#defining-the-file-structure}

A guia de estrutura **** Arquivo permite configurar os formatos de saída, data e número para o arquivo que será exportado.

![](assets/direct_mail_14.png)

>[!NOTE]
>
>As opções disponíveis são detalhadas nas seções de atividade do fluxo de trabalho [Extrair arquivo](../../automating/using/extract-file.md) .

## Definição do cabeçalho e rodapé {#defining-the-header-and-footer}

Às vezes, pode ser necessário adicionar informações no início ou no final do arquivo de extração. Para isso, use as guias **[!UICONTROL Header]** e **[!UICONTROL Footer]** a tela de **[!UICONTROL Content]** configuração.

![](assets/direct_mail_7.png)

Por exemplo, você pode querer incluir, para o provedor de mala direta, as informações do remetente no cabeçalho do arquivo. É possível personalizar o rodapé e o cabeçalho com as informações disponíveis no contexto da entrega. Consulte [Definição de conteúdo](../../designing/using/personalization.md#example-email-personalization).

O endereço do remetente é definido na **[!UICONTROL Send]** seção das propriedades de mala direta ou no nível do modelo.

![](assets/direct_mail_24.png)

