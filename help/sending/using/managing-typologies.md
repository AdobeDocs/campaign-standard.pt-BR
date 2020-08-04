---
title: Gerenciamento de tipologias
description: Saiba como usar tipologias.
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
translation-type: ht
source-git-commit: ba1fcca02ce9582d85e57bde815ccf3f551ac7a3
workflow-type: ht
source-wordcount: '308'
ht-degree: 100%

---


# Gerenciamento de tipologias {#managing-typologies}

## Sobre tipologias {#about-typologies}

As tipologias são conjuntos de regras que permitem verificar a validade da mensagem antes de ela ser enviada. Por exemplo, o conteúdo da mensagem não está vazio, uma unsubscription está presente, exclusão de duplicados etc.

As tipologias podem ser acessadas pelo menu **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]**. Por padrão, uma tipologia padrão está disponível no aplicativo. Você pode criar suas próprias tipologias ou modificar as existentes, conforme suas necessidades.

![](assets/typologies-list.png)

Para cada tipologia, a seção **[!UICONTROL Typology rules]** lista o conjunto de regras que são executadas ao usar a tipologia com uma mensagem.

![](assets/typology_typo-rule-list.png)

>[!NOTE]
>
>Para obter mais detalhes sobre uma das regras de tipologia, clique duas vezes nela. A regra será exibida no modo somente leitura.

## Criação de uma tipologia {#creating-a-typology}

Para criar uma nova tipologia, siga estas etapas:

1. Acesse o menu **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]**.

1. A lista de tipologias é exibida. Clique no botão **[!UICONTROL Create]**.

   ![](assets/typologies-create.png)

1. Defina a tipologia **[!UICONTROL Label]** e clique no botão **[!UICONTROL Add an element]** para selecionar as regras de tipologia que deseja incluir. Para saber mais sobre as regras de tipologia, consulte [esta seção](../../sending/using/managing-typology-rules.md).

   ![](assets/typology_addrules.png)

   >[!NOTE]
   >
   >O campo **[!UICONTROL IP affinity]** permite gerenciar as afinidades de acordo com a configuração. Elas são definidas no arquivo de configuração da instância. Se quiser usar as afinidades, entre em contato com o administrador.

1. Clique em **[!UICONTROL Create]** para confirmar a seleção. Sua tipologia agora está pronta para ser usada nas mensagens.

## Aplicação de tipologias a mensagens {#applying-typologies-to-messages}

Ao associar uma tipologia a uma mensagem ou a um template de mensagem, as regras de tipologia incluídas na tipologia serão executadas para verificar a validade da mensagem.

>[!NOTE]
>
>Cada mensagem ou template de mensagem só pode ter uma única tipologia.

Para vincular uma tipologia a uma mensagem, siga estas etapas:

1. Acesse as propriedades da mensagem. Os templates de mensagem podem ser acessados no menu de navegação **[!UICONTROL Resources]** > **[!UICONTROL Templates]**.

1. Na seção **[!UICONTROL Advanced parameters]** > **[!UICONTROL Prearation]**, selecione a tipologia a ser vinculada à mensagem.

   ![](assets/typology_message.png)

1. Clique em **[!UICONTROL Confirm]**.

   A tipologia selecionada agora está vinculada à mensagem. Todas as regras de tipologia associadas serão executadas para verificar a validade da mensagem.
