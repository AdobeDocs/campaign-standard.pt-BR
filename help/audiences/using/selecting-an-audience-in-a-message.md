---
title: Selecionar um público-alvo em uma mensagem
description: '"Passo a passo do procedimento para escolher públicos de um email: população-alvo principal e perfis de teste."'
page-status-flag: nunca ativado
uuid: 7d8f8446-f2e0-49c1-83f6-9667b29bc228
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: referência
topic-tags: gerenciar públicos-alvo
discoiquuid: 158da6ff-8899-4e7b-b925-8a42c3de46a1
context-tags: delivery,assistente;entrega,público,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Selecionar um público-alvo em uma mensagem{#selecting-an-audience-in-a-message}

O Adobe Campaign permite que você configure vários tipos de perfil no público-alvo de uma mensagem.

Os públicos-alvo podem ser definidos ao criar a mensagem por meio do assistente de criação ou do painel de mensagens se a mensagem já tiver sido criada.

>[!NOTE]
>
>Se o público-alvo foi criado dentro de um fluxo de trabalho e enriquecido com dados adicionais, você não poderá usar esses dados para personalizar uma entrega independente. Eles só podem ser usados a partir de uma entrega executada em um fluxo de trabalho.

1. No painel, vá para o bloco de público-alvo para iniciar.

   ![](assets/delivery_audience_definition_1.png)

   A tela para definir os públicos-alvo é aberta. Ele tem duas guias que permitem definir separadamente cada tipo de público-alvo que receberá a mensagem:

   * Target
   * Testar perfis
   ![](assets/delivery_audience_definition_2.png)

1. Defina o principal **[!UICONTROL Target]** do email. Este é o público-alvo regular do email.

   O destino é definido na **[!UICONTROL Target]** guia e é composto de perfis identificados do banco de dados.

   Você pode estabelecer sua meta principal usando as funcionalidades do editor [de](../../automating/using/editing-queries.md#creating-queries) consulta.

   Nessa guia, a **[!UICONTROL Shortcuts]** paleta contém apenas filtros predefinidos e os públicos-alvo que foram definidos nos perfis identificados. A **[!UICONTROL Explorer]** guia permite acessar configurações adicionais.

   Portanto, você pode reutilizar e combinar públicos existentes, aplicar filtros adicionais a eles etc.

1. Defina o **[!UICONTROL Test profiles]** que deseja usar para o email. Os perfis de teste receberão as provas que você pode enviar antes para testar o email antes de enviá-lo para o destino principal.

   Para obter mais informações sobre como configurar perfis de teste, consulte a seção Perfis [de](../../sending/using/managing-test-profiles-and-sending-proofs.md) teste.

O bloco de públicos-alvo é atualizado e mostra que os perfis de destino e teste foram selecionados para o email em questão.

![](assets/delivery_audience_definition_3.png)

