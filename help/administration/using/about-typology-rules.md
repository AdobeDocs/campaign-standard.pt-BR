---
title: Sobre regras de tipologia
seo-title: Sobre regras de tipologia
description: Sobre regras de tipologia
seo-description: Descubra como as regras de tipologia funcionam no Adobe Campaign.
page-status-flag: nunca ativado
uuid: a 98 ebc 36-172 d -4 f 46-b 6 ee-b 2636 a 1007 c 9
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: regras de trabalho com informações de typologia
discoiquuid: 2590 d 94 c -51 ef -4 c 0 f-b 1 ec-c 2837 e 94 da 40
context-tags: tipologia, visão geral; Typologyrule, main; Typologyrule, visão geral
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# About typology rules{#about-typology-rules}

Uma tipologia é um conjunto de regras, executadas durante a fase de análise da mensagem, que permite o destino, o conteúdo e a configuração dos seguintes elementos a serem validados: o assunto, URL, imagens, link para cancelamento de assinatura, tamanho da prova etc.

No Adobe Campaign, cada mensagem contém um link para uma tipologia. This link is defined in the advanced parameters of the delivery template's properties (for more on this, refer to the [Preparation](../../administration/using/configuring-email-channel.md#preparation) section).

>[!NOTE]
>
>Cada mensagem só pode receber uma única typologia.

For each typology, the **[!UICONTROL Typology rules]** section lists the set of rules for this typology.

![](assets/typology_typo-rule-list.png)

## Managing typologies {#managing-typologies}

Várias tipologias estão presentes por padrão no aplicativo. Com base em suas necessidades, você pode criar suas próprias tipologias ou modificar as existentes.

1. Access the **[!UICONTROL List of typologies]** from the **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Typologies]** menu.
1. Selecione uma tipologia para modificar seu conteúdo e propriedades ou criar uma nova.

   ![](assets/typology_list.png)

1. Defina o tipo da tipologia. As tipologias podem ser padrão ou filtrar tipologias.
1. Add the typology rules you need using the **[!UICONTROL Add an element]** button or remove the ones you do not want to use.

   É possível modificar a ordem em que as regras são aplicadas em uma determinada tipologia. Para fazer isso, mova os elementos para modificar a ordem em que eles aparecem na tela. Os números correspondentes à ordem de execução são recalculados automaticamente. The rule application mode is presented in the [Typology rules execution order](../../administration/using/about-typology-rules.md#typology-rules-execution-order) section.

   As regras exibidas nessa tela podem ser acessadas no modo somente leitura.

Sua tipologia está pronta para ser usada. Você pode selecioná-lo nas propriedades da mensagem ou nas propriedades do modelo de mensagem.

>[!NOTE]
>
>The **[!UICONTROL IP affinity]** field allows you to manage the affinities according to your configuration. Eles são definidos no arquivo de configuração da instância. Se quiser usar as afinidades, entre em contato com o administrador.

## Typology rules {#typology-rules}

As regras de tipologia são regras comerciais aplicadas durante a preparação da mensagem. Eles são usados para verificar se uma mensagem é válida e atender aos critérios de qualidade. Eles também verificam se cada membro do público-alvo está qualificado para receber a mensagem.

Typology rules are available under the **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Typologies]** &gt; **[!UICONTROL Typology rules]** menu.

Há dois tipos de regras:

* **Regras de filtragem** : permite excluir uma parte da meta da mensagem de acordo com os critérios definidos em uma consulta, como perfis ou perfis cerados que já foram enviados um determinado número de emails. See [Filtering rules](../../administration/using/filtering-rules.md).
* **Regras de esgotamento** : permite definir um número máximo de mensagens por perfil para evitar o recebimento excessivo dessas mensagens. See [Fatigue rules](../../administration/using/fatigue-rules.md).
* **Regras de controle** : permite que o usuário verifique a validade e a qualidade das mensagens antes de serem enviadas, como a exibição de caracteres, tamanho de mensagem SMS, formato de endereço etc. See [Control rules](../../administration/using/control-rules.md).

Uma regra de tipologia pode ser aplicada somente a um canal ou a todos os canais.

![](assets/typology_channel.png)

In the **[!UICONTROL Properties]** of a typology rule, you can set its execution order. Quando várias regras precisam ser aplicadas, a ordem de execução de cada regra determina que os processos devem ser processados primeiro. For more on this, refer to the [Typology rules execution order](../../administration/using/about-typology-rules.md#typology-rules-execution-order) section.

![](assets/typology_rule-active.png)

A typology rule can be deactivated through its **[!UICONTROL Properties]** if you do not want the rule to be applied at the moment that the messages concerned by the rule are analyzed.

![](assets/typology_rule-order.png)

In the **[!UICONTROL Targeting context]** category, you can select the **Targeting dimension** and **Filtering dimension** depending on the data that you want to target.

By default, filtering is carried out on the **[!UICONTROL Profiles]**. For example, if the rule is aimed at a mobile application, the **[!UICONTROL Filtering dimension]** can be changed to **[!UICONTROL Subscriptions to an application]**.

![](assets/typology_rule-order_2.png)

>[!NOTE]
>
>Como o conteúdo das regras de controle não pode ser modificado, essas são essencialmente as regras usadas.

## Typology rules execution order {#typology-rules-execution-order}

As regras de tipologia são executadas em uma ordem especificada durante as fases de definição, análise e personalização de mensagens.

No modo de operação padrão, as regras são aplicadas na seguinte sequência:

1. Controle as regras, se elas forem aplicadas no início da definição de metas.
1. Regras de filtragem:

   * Regras de aplicativo nativas para qualificação de endereços: endereço/endereço não verificado/endereço não verificado/endereço de quarant/quarentena programada.
   * Regras de filtragem definidas pelo usuário.

1. Controle as regras, se elas forem aplicadas ao fim da definição de metas.
1. Regras de controle, se aplicadas no início da personalização.
1. Regras de controle, se aplicadas ao fim da personalização.

No entanto, você pode adaptar a ordem de execução do mesmo tipo de regras em cada tipologia. Na verdade, quando várias regras são executadas durante a mesma fase de processamento de mensagem, você pode escolher a ordem em que são aplicadas.

Por exemplo, uma regra de filtragem cuja ordem de execução é posicionada no número 20 será executada antes de uma regra de filtragem cuja ordem de execução esteja posicionada em número 30.
