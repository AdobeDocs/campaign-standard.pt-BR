---
title: Definição do conteúdo da correspondência direta
description: Saiba como definir o conteúdo do delivery de correspondência direta.
page-status-flag: never-activated
uuid: c1234c06-4d22-46d7-ad1b-3c88660f9b06
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: direct-mail
discoiquuid: 9e73d6b5-41b4-474b-a880-a0cd5999c2d1
context-tags: delivery,directMailContent,back
internal: n
snippet: y
translation-type: ht
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e
workflow-type: ht
source-wordcount: '337'
ht-degree: 100%

---


# Definição do conteúdo da correspondência direta{#defining-the-direct-mail-content}

Você pode definir o conteúdo na última tela do assistente de criação ou clicando na seção **Content** do painel do delivery.

![](assets/direct_mail_6.png)

A tela de definição **[!UICONTROL Content]** é específica do canal de correspondência direta. Ela é dividido em quatro guias: **[!UICONTROL Extraction]**, **[!UICONTROL File structure]**, **[!UICONTROL Header]** e **[!UICONTROL Footer]**.

![](assets/direct_mail_11.png)

## Definição da extração {#defining-the-extraction}

1. Comece definindo o nome do arquivo de extração. Clique no botão à direita do campo **[!UICONTROL Output file]** e insira o rótulo desejado. Você pode usar campos de personalização, blocos de conteúdo e texto dinâmico (consulte [Definição de conteúdo](../../designing/using/personalization.md#example-email-personalization)). Por exemplo, você pode preencher o rótulo com a ID do delivery ou a data da extração.

   ![](assets/direct_mail_12.png)

1. Clique no botão **[!UICONTROL +]** ou **[!UICONTROL Add an element]** para adicionar uma coluna de saída. As **[!UICONTROL Output columns]** permitem que você defina as informações (colunas) do perfil a serem exportadas para o arquivo de saída.

   >[!CAUTION]
   >
   >Verifique se os perfis incluem o CEP, pois essa informação é essencial para o provedor de correspondência direta. Verifique também se você marcou a caixa **[!UICONTROL Address specified]** nas informações dos perfis. Consulte [Recomendações](../../channels/using/about-direct-mail.md#recommendations).

   ![](assets/direct_mail_13.png)

1. Crie quantas colunas forem necessárias. Você pode editar as colunas clicando nas expressões e nos rótulos.

>[!NOTE]
>
>Para saber mais sobre a definição da coluna de saída, consulte a seção da atividade [Extract file](../../automating/using/extract-file.md) do fluxo de trabalho.

## Definição da estrutura de arquivo {#defining-the-file-structure}

A guia **File structure** permite configurar os formatos de saída, data e número do arquivo que será exportado.

![](assets/direct_mail_14.png)

>[!NOTE]
>
>As opções disponíveis são detalhadas nas seções da atividade [Extract file](../../automating/using/extract-file.md) do fluxo de trabalho.

## Definição do cabeçalho e rodapé {#defining-the-header-and-footer}

Às vezes, pode ser necessário adicionar informações ao início ou final do arquivo de extração. Para isso, use as guias **[!UICONTROL Header]** e **[!UICONTROL Footer]** da tela de configuração **[!UICONTROL Content]**.

![](assets/direct_mail_7.png)

Por exemplo, você talvez queira incluir as informações do remetente no cabeçalho do arquivo para o provedor de correspondência direta. É possível personalizar o rodapé e o cabeçalho com as informações disponíveis no contexto do delivery. Consulte [Definição de conteúdo](../../designing/using/personalization.md#example-email-personalization).

O endereço do remetente é definido na seção **[!UICONTROL Send]** das propriedades de correspondência direta ou no nível do template.

![](assets/direct_mail_24.png)

