---
solution: Campaign Standard
product: campaign
title: Gerenciamento de regras de tipologia
description: Saiba como usar regras de tipologia.
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
context-tags: typology,overview;typologyRule,main;typologyRule,overview
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 96%

---


# Gerenciamento de regras de tipologia {#managing-typology-rules}

## Sobre regras de tipologia {#about-typology-rules}

Regras de tipologia são regras de negócios que permitem executar verificações e filtrar a mensagem antes de enviá-la. Os tipos disponíveis de regras de tipologia são:

* Regras de **Filtragem**: nesse tipo de regra você pode excluir uma parte do público-alvo da mensagem de acordo com os critérios definidos em uma consulta. Podem ser perfis em quarentena ou perfis que já receberam um determinado número de emails. Para obter mais informações, consulte [esta seção](../../sending/using/filtering-rules.md).

* Regras de **Fadiga**: nesse tipo de regra você pode definir um número máximo de mensagens por perfil para evitar que elas sejam solicitadas em excesso. Para obter mais informações, consulte [esta seção](../../sending/using/fatigue-rules.md).

* Regras de **Controle**: nesse tipo de regra o usuário pode verificar a validade e a qualidade das mensagens antes de serem enviadas. É possível verificar, por exemplo, a exibição de caracteres, o tamanho da mensagem SMS, o formato de endereço etc. Para obter mais informações, consulte [esta seção](../../sending/using/control-rules.md).

As Regras de tipologia estão disponíveis no menu **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]** > **[!UICONTROL Typology rules]**.

Por padrão, várias regras de tipologia de **Filtragem** e **Controle** estão disponíveis prontas para uso. Elas estão detalhadas nas seções [Regras de filtragem](../../sending/using/fatigue-rules.md) e [Regras de controle](../../sending/using/control-rules.md).

De acordo com suas necessidades, você pode modificar as regras de tipologia existentes ou criar novas, com exceção das regras de **[!UICONTROL Control]**, que são somente leitura e não podem ser modificadas.

## Criação de uma regra de tipologia {#creating-a-typology-rule}

As principais etapas para criar uma regra de tipologia são as seguintes:

1. Acesse o menu **[!UICONTROL Administration]** / **[!UICONTROL Channels]** / **[!UICONTROL Typologies]** / **[!UICONTROL Typology rules]**, e clique em **[!UICONTROL Create]**.

   ![](assets/typology_create-rule.png)

1. Insira a tipologia **[!UICONTROL Label]**, e especifique o **[!UICONTROL Channel]** ao qual a regra deve se aplicar.

   ![](assets/typology-rule-label.png)

1. Especifique a regra de tipologia **[!UICONTROL Type]** e configure-a de acordo com suas necessidades. Observe que a configuração da regra de tipologia varia dependendo do tipo. Para obter mais informações, consulte as seções **[Regras de filtragem](../../sending/using/filtering-rules.md)** e **[Regras de fadiga](../../sending/using/fatigue-rules.md)**.

1. Selecione as tipologias nas quais deseja incluir a nova regra. Para fazer isso, selecione a guia **[!UICONTROL Typologies]** e clique no botão **[!UICONTROL Create element]**.

   ![](assets/typology-typologies-tab.png)

1. Selecione a tipologia desejada e clique em **[!UICONTROL Confirm]**.

   ![](assets/typology-link.png)

1. Depois que todas as tipologias forem selecionadas, clique em **[!UICONTROL Create]** para confirmar a criação da regra de tipologia.

## Ordem de execução das regras de tipologia {#typology-rules-execution-order}

As regras de tipologia são executadas em uma ordem especificada durante as fases de direcionamento, análise e personalização de mensagens.

No modo de operação padrão, as regras são aplicadas na seguinte sequência:

1. Regras de controle, se elas forem aplicadas no início do direcionamento.
1. Regras de filtragem:

   * Regras nativas para a qualificação de endereço: endereço definido / endereço não verificado / endereço em lista de bloqueios / endereço em quarentena / qualidade do endereço.
   * Filtrar regras definidas pelo usuário.

1. Regras de controle, se elas forem aplicadas no final do direcionamento.
1. Regras de controle, se elas forem aplicadas no início da personalização.
1. Regras de controle, se elas forem aplicadas no final da personalização.

No entanto, você pode adaptar a ordem de execução do mesmo tipo de regras em cada tipologia. Na verdade, quando várias regras são executadas durante a mesma fase de processamento de mensagens, você pode escolher a ordem de aplicação.

Por exemplo, uma regra de filtragem cuja ordem de execução está posicionada no número 20 será executada antes de uma regra de filtragem cuja ordem de execução está posicionada no número 30.

Nas **[!UICONTROL Properties]** de uma regra de tipologia, é possível definir sua ordem de execução. Quando várias regras têm de ser aplicadas, a ordem de execução de cada regra determina as que devem ser processadas primeiro. Para obter mais informações, consulte a seção [Ordem de execução das regras de tipologia](#typology-rules-execution-order).

![](assets/typology_rule-active.png)

Uma regra de tipologia pode ser desativada por meio de suas **[!UICONTROL Properties]** se você não quiser que a regra seja aplicada no momento em que as mensagens afetadas pela regra forem analisadas.

![](assets/typology_rule-order.png)