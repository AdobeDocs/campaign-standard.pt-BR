---
solution: Campaign Standard
product: campaign
title: Seleção de um público-alvo em uma mensagem
description: '“Passo a passo para a escolha dos públicos-alvo de um email: população principal de direcionamento e perfis de teste.”'
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: deliveryCreation,wizard;delivery,audience,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 83%

---


# Seleção de um público-alvo em uma mensagem{#selecting-an-audience-in-a-message}

O Adobe Campaign permite configurar vários tipos de perfil no público-alvo de uma mensagem.

Os públicos-alvo podem ser definidos ao criar a mensagem com o assistente de criação ou no painel de mensagens se a mensagem já tiver sido criada.

>[!NOTE]
>
>Se o público-alvo tiver sido criado em um fluxo de trabalho e enriquecido com dados adicionais, você não poderá usar esses dados para personalizar um delivery independente. Eles só poderão ser usados de um delivery executado em um fluxo de trabalho.

1. No painel, acesse o bloco de públicos-alvo para iniciar.

   ![](assets/delivery_audience_definition_1.png)

   A tela para definir os públicos-alvo é aberta. Ela tem duas guias que permitem definir separadamente cada tipo de público-alvo que receberá a mensagem:

   * Target
   * Testar perfis

   ![](assets/delivery_audience_definition_2.png)

1. Defina o **[!UICONTROL Target]** principal do email. Ele é o público-alvo normal do email.

   O target é definido na guia **[!UICONTROL Target]** e é composto de perfis identificados do banco de dados.

   Você pode estabelecer seu público-alvo principal usando as funcionalidades do [Editor de consultas](../../automating/using/editing-queries.md#creating-queries).

   Nessa guia, a paleta **[!UICONTROL Shortcuts]** contém apenas os filtros predefinidos e os públicos-alvo que foram definidas nos perfis identificados. A guia **[!UICONTROL Explorer]** permite acessar configurações adicionais.

   Portanto, é possível reutilizar e combinar os públicos-alvo, aplicar filtros adicionais a eles etc.

1. Defina os **[!UICONTROL Test profiles]** que deseja usar para o email. Os perfis de teste receberão as provas que você enviar para testar o email antes que ele seja enviado ao público-alvo principal.

   Para saber mais sobre como configurar perfis de teste, consulte a seção [Perfis de teste](../../audiences/using/managing-test-profiles.md).

1. Se necessário, é possível definir um grupo de controle usando a guia correspondente. Isso permitirá que você retire alguns perfis do seu público alvo para que eles não recebam a mensagem. For more on this, see [Adding a control group](../../sending/using/control-group.md).

1. Você também pode usar endereços de substituição para obter uma representação exata da mensagem que o perfil receberá.  Para mais informações, consulte [Testar mensagens de email usando perfis segmentados](../../sending/using/testing-messages-using-target.md).

O bloco de públicos-alvo é atualizado e mostra que um público-alvo e perfis de teste foram selecionados para o email específico.

![](assets/delivery_audience_definition_3.png)

