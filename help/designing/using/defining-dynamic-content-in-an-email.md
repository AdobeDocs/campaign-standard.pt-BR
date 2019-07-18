---
title: Definição de conteúdo dinâmico em um email
seo-title: Definição de conteúdo dinâmico em um email
description: Definição de conteúdo dinâmico em um email
seo-description: Siga estas etapas para exibir dinamicamente conteúdos diferentes em um e-mail de acordo com as condições definidas pelo editor de expressões do Adobe Campaign.
page-status-flag: nunca ativado
uuid: b 1 c 5013 f -3201-4239-8202-511 a 6902 d 604
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: definindo-conteúdo condicional
discoiquuid: d 0 d 009 a 5-6022-433 e-acdf -2 b 51 a 243 a 5 c 9
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Defining dynamic content in an email{#defining-dynamic-content-in-an-email}

Em um email, você pode definir conteúdos diferentes que serão exibidos dinamicamente para os destinatários, de acordo com as condições definidas pelo editor de expressão. Por exemplo, a partir do mesmo email, é possível garantir que cada perfil receba uma mensagem diferente de acordo com sua faixa etária.

Defining dynamic content is different from [defining visibility conditions](../../designing/using/defining-a-visibility-condition.md).

1. Selecione um fragmento, um componente ou um elemento. Neste exemplo, selecione uma imagem.
1. Click the **[!UICONTROL Dynamic content]** icon from the contextual toolbar.

   ![](assets/dynamic_content_2.png)

   The **[!UICONTROL Dynamic content]** section appears in the palette on the left.

   ![](assets/dynamic_content_3.png)

   Por padrão, esta seção contém dois elementos: variante padrão e uma nova variante.

   >[!NOTE]
   >
   >O conteúdo deve ter sempre uma variante padrão. Não é possível excluí-lo.

1. Click the **[!UICONTROL Edit]** button to define the display conditions for the first alternative variant.

   ![](assets/dynamic_content_4.png)

1. Especifique um rótulo e selecione os campos que deseja definir como condições. For example, from the **[!UICONTROL General]** node, select the **[!UICONTROL Age]** field

   ![](assets/dynamic_content_5.png)

1. Defina as condições de filtragem. Por exemplo, você deseja que um conteúdo diferente seja exibido para pessoas com idades entre 18 e 25 anos.

   ![](assets/dynamic_content_6.png)

1. Após definir todas as condições, defina a ordem de prioridade na qual a condição será aplicada e salve suas alterações.

   ![](assets/dynamic_content_7.png)

   O conteúdo será exibido na paleta em ordem de prioridade, de cima para baixo. For more on priorities, refer to [this section](../../designing/using/defining-dynamic-content-in-an-email.md#order-of-priority).

1. Carregue uma nova imagem para a variante que você acabou de definir.

   ![](assets/dynamic_content_8.png)

   Os destinatários que permaneceram entre 18 e 25 anos visualizarão a nova imagem.

   ![](assets/dynamic_content_10.png)

1. Click **[!UICONTROL Add a condition]** to add a new content and its linked rule.

   ![](assets/dynamic_content_9.png)

   Por exemplo, você pode adicionar uma imagem diferente a ser exibida para pessoas com idades entre 26 e 35 anos.

1. Prossiga de forma semelhante para qualquer outro elemento do seu email que você deseja exibir dinamicamente. Pode ser texto, botão, fragmento etc. Salve as alterações.

>[!CAUTION]
>
>Após preparar a mensagem e antes de enviá-la, teste-a usando uma prova. Caso não faça isso, alguns erros podem não ser detectados e o email pode não ser enviado.

**Tópicos relacionados:**

* [Envio de testes](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs)
* [Edição de expressões avançadas](../../automating/using/editing-queries.md#about-query-editor)

## Order of priority {#order-of-priority}

No editor de expressões, ao definir um conteúdo dinâmico, a ordem de prioridade é a seguinte.

1. You define two different dynamic contents with **two different conditions**, for example:

   **Condição 1:** o gênero do perfil é masculino,

   **Condição 2:** o perfil tem entre 20 e 30 anos.

   ![](assets/delivery_content_61.png)

   Alguns perfis no banco de dados correspondem a duas condições, mas apenas um email com um conteúdo dinâmico pode ser enviado.

1. Portanto, você precisa definir a prioridade para o conteúdo dinâmico. A condition with an order of priority of **1** (and therefore the corresponding dynamic content) will be sent to a profile even if another condition whose priority order is **2** or **3** is also met by this profile.

   ![](assets/delivery_content_62.png)

Você só pode definir uma ordem de prioridade por conteúdo dinâmico.
