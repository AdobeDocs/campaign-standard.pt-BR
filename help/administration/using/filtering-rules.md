---
title: Regras de filtragem
seo-title: Regras de filtragem
description: Regras de filtragem
seo-description: Use regras de filtragem para refinar o público-alvo de suas mensagens.
page-status-flag: nunca ativado
uuid: ed 3 eea 62-3 a 47-4318-ae 22-d 82 aa 857448 f
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: regras de trabalho com informações de typologia
discoiquuid: 7 ddaf 36 c -74 e 6-4501-b 3 eb -3 d 03 f 005 aaa 6
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Filtering rules{#filtering-rules}

As regras de filtragem permitem excluir uma parte da meta da mensagem de acordo com os critérios definidos em uma consulta, como perfis ou perfis cerados que já foram enviados um determinado número de emails.

Por exemplo, você pode filtrar os assinantes do boletim informativo para que os assinantes que tiverem mais de 18 anos nunca recebam comunicações.

## Creating a filtering rule {#creating-a-filtering-rule}

1. Create a **Filtering** typology rule, one that can be applied on all communication channels.

   ![](assets/typology_create-rule.png)

1. In the **[!UICONTROL Filtering criteria]** tab, select the subscriptions in the **[!UICONTROL Subscription]** category.

   ![](assets/typology_create-rule-subscription.png)

1. In the **[!UICONTROL Explorer]** tab of the query editor, drag and drop the **[!UICONTROL Subscriber]** node into the main part of the screen.

   ![](assets/typology_create-rule-subscriber.png)

1. Select the **[!UICONTROL Age]** field and define the filtering conditions so that the age of the subscribers is 18 or above.

   ![](assets/typology_create-rule-age.png)

1. In the **[!UICONTROL Typologies]** tab, link this rule to a typology.

   ![](assets/typology_create-rule-typology.png)

1. Certifique-se de que a tipologia em questão esteja selecionada no modelo de entrega que você deseja usar.

   ![](assets/typology_template.png)

   >[!NOTE]
   >
   >To access the delivery templates, select **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** in the navigation menu, which can be accessed via the Adobe Campaign logo.

Sempre que essa regra for usada em uma mensagem, os assinantes que forem considerados menores serão excluídos automaticamente.

## Restricting the applicability of a filtering rule {#restricting-the-applicability-of-a-filtering-rule}

É possível restringir a aplicabilidade de uma regra de filtragem de acordo com a mensagem a ser enviada.

1. In the typology rule's **[!UICONTROL Application criteria]** tab, uncheck the **[!UICONTROL Apply the rule on all deliveries]** option, which is enabled by default.

   ![](assets/typology_limit.png)

1. Use o editor de consultas para definir um filtro. Por exemplo, você pode aplicar a regra somente em mensagens cuja etiqueta começa com uma determinada palavra ou cuja ID contém certas letras.

   ![](assets/typology_limit-rule.png)

Nesse caso, a regra é aplicada somente às mensagens que correspondem aos critérios definidos.

## Default deliverability exclusion rules {#default-deliverability-exclusion-rules}

Two filtering rules are available by default: **[!UICONTROL Exclusion of addresses]** ( **[!UICONTROL addressExclusions]** ) and **[!UICONTROL Exclusion of domains]** ( **[!UICONTROL domainExclusions]** ). Durante a análise de email, essas regras comparam os endereços de email do destinatário com os endereços proibidos ou os nomes de domínio contidos em uma lista de exclusão global criptografada gerenciada na instância de entrega. Se houver correspondência, a mensagem não será enviada para esse destinatário.

Isso deve ser evitado devido à atividade maliciosa, especialmente ao uso de um Spamapping. Por exemplo, se um Spamapping é usado para assinar por meio de um dos formulários da Web, um e-mail de confirmação é automaticamente enviado para esse Espaçamento e isso resulta na lista negra automaticamente.

>[!NOTE]
>
>Os endereços e os nomes de domínio contidos na lista de exclusão global estão ocultos. Somente o número de destinatários excluídos é indicado nos logs de análise de entrega.

