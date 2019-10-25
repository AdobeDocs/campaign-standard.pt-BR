---
title: Sobre regras de tipologia
seo-title: Sobre regras de tipologia
description: Sobre regras de tipologia
seo-description: Descubra como as regras de tipologia funcionam no Adobe Campaign.
page-status-flag: nunca ativado
uuid: a98ebc36-172d-4f46-b6ee-b2636a1007c9
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: administração
content-type: referência
topic-tags: regras de trabalho com tipologia
discoiquuid: 2590d94c-51ef-4c0f-b1ec-c2837e94da40
context-tags: tipologia,visão geral;typologyRule,main;typologyRule,visão geral
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 51d80fc9c683e39b9d08ba7d36b76b71a9dd1e8c

---


# Sobre regras de tipologia{#about-typology-rules}

Uma tipologia é um conjunto de regras, executadas durante a fase de análise da mensagem, que permitem que o destino, o conteúdo e a configuração dos seguintes elementos sejam validados: assunto, URL, imagens, link de cancelamento de assinatura, tamanho da prova etc.

No Adobe Campaign, cada mensagem contém um link para uma tipologia. Esse link é definido nos parâmetros avançados das propriedades do modelo de entrega (para obter mais informações, consulte a seção [Preparação](../../administration/using/configuring-email-channel.md#preparation) ).

>[!NOTE]
>
>Cada mensagem só pode receber uma única tipologia.

Para cada tipologia, a **[!UICONTROL Typology rules]** seção lista o conjunto de regras para essa tipologia.

![](assets/typology_typo-rule-list.png)

## Gerenciamento de tipologias {#managing-typologies}

Várias tipologias estão presentes por padrão no aplicativo. Com base em suas necessidades, você pode criar suas próprias tipologias ou modificar as existentes.

1. Acesse o **[!UICONTROL List of typologies]** no menu **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Typologies]** .
1. Selecione uma tipologia para modificar seu conteúdo e propriedades ou criar uma nova.

   ![](assets/typology_list.png)

1. Defina o tipo da tipologia. As tipologias podem ser tipologias padrão ou de filtragem.
1. Adicione as regras de tipologia necessárias usando o **[!UICONTROL Add an element]** botão ou remova aquelas que você não deseja usar.

   É possível modificar a ordem na qual as regras são aplicadas para uma determinada tipologia. Para fazer isso, mova os elementos para modificar a ordem em que aparecem na tela. Os números correspondentes à ordem de execução são recalculados automaticamente. O modo de aplicação de regra é apresentado na seção Ordem [de execução das regras de](#typology-rules-execution-order) Tipologia.

   As regras exibidas nessa tela podem ser acessadas no modo somente leitura.

Sua tipologia está pronta para ser usada. É possível selecioná-la nas propriedades da mensagem ou nas propriedades do modelo de mensagem.

>[!NOTE]
>
>O **[!UICONTROL IP affinity]** campo permite gerenciar as afinidades de acordo com sua configuração. Eles são definidos no arquivo de configuração da instância. Se quiser usar as afinidades, entre em contato com o administrador.

## Regras de tipologia {#typology-rules}

As regras de tipologia são regras de negócios aplicadas durante a preparação da mensagem. Eles são usados para verificar se uma mensagem é válida e atende aos seus critérios de qualidade. Eles também verificam se cada membro do público-alvo está qualificado para receber a mensagem.

As regras de tipologia estão disponíveis no menu **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Typologies]** &gt; **[!UICONTROL Typology rules]** .

Há dois tipos de regras:

* **Regras de filtragem** : permite que você exclua uma parte do destino da mensagem de acordo com critérios definidos em uma consulta, como perfis em quarentena ou perfis que já foram enviados para um determinado número de emails. Consulte Regras [de](../../administration/using/filtering-rules.md)filtragem.
* **Regras de fadiga** : permite que você defina um número máximo de mensagens por perfil para evitar solicitar demais. Consulte Regras de [fadiga](../../administration/using/fatigue-rules.md).
* **Regras de controle** : permitir que o usuário verifique a validade e a qualidade das mensagens antes de serem enviadas, como exibição de caracteres, tamanho da mensagem SMS, formato de endereço, etc. Consulte Regras [de controle](../../administration/using/control-rules.md).

Uma regra de tipologia pode ser aplicada a apenas um canal ou a todos os canais.

![](assets/typology_channel.png)

No caso **[!UICONTROL Properties]** de uma regra de tipologia, é possível definir sua ordem de execução. Quando várias regras têm de ser aplicadas, a ordem de execução de cada regra determina as que devem ser processadas primeiro. Para obter mais informações, consulte a seção Ordem [de execução das regras de](#typology-rules-execution-order) Tipologia.

![](assets/typology_rule-active.png)

Uma regra de tipologia pode ser desativada por meio de sua regra **[!UICONTROL Properties]** se você não quiser que ela seja aplicada no momento em que as mensagens afetadas pela regra forem analisadas.

![](assets/typology_rule-order.png)

Na **[!UICONTROL Targeting context]** categoria, você pode selecionar a dimensão **** Definição de metas e a dimensão **** Filtragem dependendo dos dados que deseja definir como meta.

Por padrão, a filtragem é realizada no **[!UICONTROL Profiles]**. Por exemplo, se a regra for direcionada para um aplicativo móvel, a regra **[!UICONTROL Filtering dimension]** pode ser alterada para **[!UICONTROL Subscriptions to an application]**.

![](assets/typology_rule-order_2.png)

## Ordem de execução das regras de tipologia {#typology-rules-execution-order}

As regras de tipologia são executadas em uma ordem especificada durante as fases de definição de metas, análise e personalização de mensagens.

No modo de operação padrão, as regras são aplicadas na seguinte sequência:

1. Regras de controle, se elas forem aplicadas no início do direcionamento.
1. Regras de filtragem:

   * Regras de aplicações nativas para qualificação de endereço: endereço definido / endereço não verificado / endereço incluído na blacklist / endereço em quarentena / qualidade do endereço.
   * Filtrar regras definidas pelo usuário.

1. Regras de controle, se elas forem aplicadas no final do direcionamento.
1. Regras de controle, se elas forem aplicadas ao início da personalização.
1. Regras de controle, se forem aplicadas no final da personalização.

No entanto, você pode adaptar a ordem de execução do mesmo tipo de regras em cada tipologia. Na verdade, quando várias regras são executadas durante a mesma fase de processamento de mensagens, você pode escolher a ordem em que são aplicadas.

Por exemplo, uma regra de filtragem cuja ordem de execução está posicionada no número 20 será executada antes de uma regra de filtragem cuja ordem de execução está posicionada no número 30.
