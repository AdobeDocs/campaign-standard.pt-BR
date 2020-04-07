---
title: Gerenciamento de tipologias
description: Descubra como usar tipologias.
page-status-flag: never-activated
uuid: a98ebc36-172d-4f46-b6ee-b2636a1007c9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
discoiquuid: 2590d94c-51ef-4c0f-b1ec-c2837e94da40
context-tags: typology,overview;typologyRule,main;typologyRule,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ec0af8c06e36f51ddaf6e3d4190fa6acd56d2da6

---


# Gerenciamento de tipologias {#managing-typologies}

## Sobre tipologias {#about-typologies}

As tipologias são conjuntos de regras que permitem verificar a validade de sua mensagem antes de enviá-la. Por exemplo: O conteúdo da mensagem não está vazio, uma unsubscription está presente, exclusão de duplicados etc.

As tipologias podem ser acessadas pelo menu **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]** . Por padrão, uma tipologia padrão está disponível no aplicativo. Com base em suas necessidades, você pode criar suas próprias tipologias ou modificar as existentes.

![](assets/typologies-list.png)

Para cada tipologia, a **[!UICONTROL Typology rules]** seção lista o conjunto de regras que são executadas ao usar a tipologia com uma mensagem.

![](assets/typology_typo-rule-list.png)

>[!NOTE]
>
>Para obter mais detalhes sobre uma das regras de tipologia, clique nele com o duplo. A regra será exibida no modo somente leitura.

## Creating a typology {#creating-a-typology}

Para criar uma nova tipologia, siga estas etapas:

1. Acesse o menu **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]** .

1. A lista de tipologias é exibida. Clique no botão **[!UICONTROL Create]**.

   ![](assets/typologies-list.png)

1. Defina a tipologia **[!UICONTROL Label]**, em seguida, clique no **[!UICONTROL Add an element]** botão para selecionar as regras de tipologia que deseja incluir nela. For more on typology rules, refer to [this section](../../sending/using/managing-typology-rules.md).

   ![](assets/typology_addrules.png)

   >[!NOTE]
   >
   >O **[!UICONTROL IP affinity]** campo permite gerenciar as afinidades de acordo com sua configuração. Eles são definidos no arquivo de configuração da instância. Se quiser usar o afinidade, entre em contato com o administrador.

1. Clique em **[!UICONTROL Create]** para confirmar a seleção. Sua tipologia agora está pronta para ser usada em mensagens.

## Aplicação de tipologias a mensagens {#applying-typologies-to-messages}

Ao associar uma tipologia a uma mensagem ou modelo de mensagem, as regras de tipologia incluídas na tipologia serão executadas para verificar a validade da mensagem.

>[!NOTE]
>
>A cada mensagem ou modelo de mensagem só pode ser atribuída uma única tipologia.

Para vincular uma tipologia a uma mensagem, siga estas etapas:

1. Acesse as propriedades da mensagem. Observe que os modelos de mensagem podem ser acessados no menu de navegação **[!UICONTROL Resources]** > **[!UICONTROL Templates]** .

1. Na seção **[!UICONTROL Advanced parameters]** > **[!UICONTROL Prearation]** , selecione a tipologia a ser vinculada à mensagem.

   ![](assets/typology_message.png)

1. Clique em **[!UICONTROL Confirm]**.

   A tipologia selecionada agora está vinculada à mensagem. Todas as regras de tipologia associadas serão executadas para verificar a validade da mensagem.
