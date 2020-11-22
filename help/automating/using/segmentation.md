---
solution: Campaign Standard
product: campaign
title: Segmentação
description: A atividade de segmentação permite criar um ou vários segmentos com base em uma população calculada pelas atividades incluídas anteriormente no fluxo de trabalho.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: segmentation,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '851'
ht-degree: 92%

---


# Segmentação{#segmentation}

## Descrição {#description}

![](assets/segmentation.png)

A atividade **[!UICONTROL Segmentation]** permite criar um ou vários segmentos com base em uma população calculada pelas atividades incluídas anteriormente no fluxo de trabalho. No final da atividade, eles podem ser processados em uma única transição ou em transições diferentes.

>[!NOTE]
>
>Por padrão, um membro da população de entrada só pode pertencer a um único segmento. Os filtros são aplicados de acordo com a ordem dos segmentos na atividade.

**Tópicos relacionados:**
* [Caso de uso: Segmentação no local](../../automating/using/workflow-segmentation-location.md)
* [Caso de uso: Segmentação de acordo com grupos etários](../../automating/using/segmentation-age-groups.md)

## Contexto de uso {#context-of-use}

A atividade **[!UICONTROL Segmentation]** geralmente é colocada após as atividades de direcionamento (query, intersecção, união, exclusão etc.) para definir a população padrão de base para a formação dos segmentos.

**Tópicos relacionados**

* [Caso de uso: Segmentação de perfis de acordo com seus grupos](../../automating/using/segmentation-age-groups.md)etários.

## Configuração {#configuration}

1. Arraste e solte uma atividade **[!UICONTROL Segmentation]** no seu fluxo de trabalho.
1. Selecione e abra a atividade usando o botão ![](assets/edit_darkgrey-24px.png) das ações rápidas exibidas.
1. In the **[!UICONTROL General]** tab, select the **[!UICONTROL Resource type]** on which the segmentation has to be carried out:

   * **[!UICONTROL Database resource]** se a segmentação for realizada nos dados existentes no banco de dados. Selecione a **[!UICONTROL Filtering dimension]** dependendo dos dados que você deseja segmentar. Por padrão, a segmentação é realizada nos **perfis**.
   * **[!UICONTROL Temporary resource]** se a segmentação for realizada nos dados temporários do fluxo de trabalho. Selecione o **[!UICONTROL Targeted set]** que contêm os dados a serem segmentados. Esse caso de uso poderá ser encontrado após a importação de um arquivo ou se os dados no banco de dados tiverem sido enriquecidos.

1. Selecione o tipo de transição de saída que deseja usar:

   * **[!UICONTROL Generate one transition per segment]**: uma transição de saída é adicionada para cada segmento configurado no final da atividade.
   * **[!UICONTROL Generate all segments in one transition]**: todos os segmentos configurados são reagrupados em uma única transição de saída. Especifique o rótulo da transição. Os membros de cada segmento mantêm o código de segmento que foi atribuído a eles.

1. Adicione um segmento usando o botão ![](assets/add_darkgrey-24px.png) ou **[!UICONTROL Add an element]** e especifique as propriedades padrão:

   * **[!UICONTROL Do not activate the transition if the population is empty]**: o segmento só será ativado se os dados forem recuperados.
   * **[!UICONTROL Filter initial population (query)]**: permite filtrar a população deste segmento.
   * **[!UICONTROL Limit segment population]**: permite limitar o tamanho do segmento.
   * **[!UICONTROL Filter and limit segment population]**: permite filtrar a população do segmento e limitar o tamanho.
   * **[!UICONTROL Label]**: rótulo do segmento.
   * **[!UICONTROL Segment code]**: código atribuído à população do segmento. O código de segmento pode ser personalizado usando uma expressão padrão e variáveis de eventos (consulte [esta página](../../automating/using/customizing-workflow-external-parameters.md)).
   * **[!UICONTROL Exclude segment from population]**: permite excluir o segmento especificado da população de saída da atividade. Essa opção só poderá ser usada se a opção **[!UICONTROL Generate all segments in the same transition]** estiver selecionada.

   ![](assets/wkf_segment_new_segment.png)

1. Abra a visualização detalhada do segmento para acessar as opções de configuração. Para fazer isso, marque a caixa relevante na lista de segmentos da atividade e selecione ![](assets/wkf_segment_parameters_24px.png).
1. Se a opção para filtrar a população inicial estiver marcada, abra a guia **[!UICONTROL Filter]** e especifique a população do segmento. Os filtros são baseados na dimensão do filtro selecionada na etapa 4. Consulte a seção [Edição de query](../../automating/using/editing-queries.md) para saber mais sobre a filtragem de população.

   Se a segmentação for realizada em um recurso temporário, a contagem e a pré-visualização da população não estarão disponíveis nessa guia.

1. Se a opção para limitar o tamanho do segmento estiver marcada, abra a guia **[!UICONTROL Limitation]**.

   Primeiro, selecione o **[!UICONTROL Type of limit]** que deseja usar:

   * **[!UICONTROL Random sampling]**: a população do segmento é selecionada aleatoriamente levando em conta a configuração da guia **[!UICONTROL Filter]**, se necessário. 
   * **[!UICONTROL Ordered sampling]**: a população do segmento é selecionada de maneira ordenada. Consequentemente, você deve especificar as colunas a serem consideradas e o tipo de classificação a ser aplicado. Por exemplo, se você selecionar o campo **Age** como a coluna de classificação ao aplicar uma **[!UICONTROL Descending sort]** e definir o limite 100, apenas os perfis das 100 pessoas mais velhas serão mantidos.

   Agora especifique o **[!UICONTROL Limit]** de tamanho do segmento:

   * **[!UICONTROL Size (as a % of the initial population)]**: especifique o tamanho do segmento usando uma porcentagem da população inicial da atividade.
   * **[!UICONTROL Maximum size]**: especifique um número máximo de membros para a população do segmento.
   * **[!UICONTROL By data grouping]**: é possível limitar a população do segmento de acordo com os valores de um campo específico da população de entrada. Selecione o campo para agrupamento e especifique os valores a serem usados.
   * **[!UICONTROL By data grouping (as a %)]**: é possível limitar a população do segmento de acordo com os valores de um campo de população de entrada específico usando uma porcentagem. Selecione o campo para aplicar o agrupamento e especifique os valores a serem usados.

      >[!NOTE]
      >
      >É possível usar diferentes limitações para cada valor. Por exemplo, você pode especificar um agrupamento para o campo **[!UICONTROL Gender]** e limitar a população com 10 membros **[!UICONTROL Male]** e 30 membros **[!UICONTROL Female]**. Se você usar vários campos de agrupamento de dados, todos os agrupamentos deverão ter o mesmo tamanho.
   ![](assets/wkf_segment_limit_by_grouping.png)

1. Confirme a configuração do seu segmento.
1. Adicione quantos segmentos forem necessários repetindo as etapas de 6 a 10 desse procedimento.
1. Se for necessário, edite os parâmetros na guia **[!UICONTROL Advanced options]**:

   * Marque a opção **[!UICONTROL Enable overlapping of outbound populations]** se desejar que um membro da população de entrada pertença a vários segmentos ao mesmo tempo. A população de saída da atividade pode exceder a população de entrada.
   * Marque a opção **[!UICONTROL Concatenate the code of each segment]** se a população de entrada já tiver recebido um código de segmento que você deseja manter. O código de segmento especificado na atividade será adicionado ao código de segmento inicial.
   * Marque a opção **[!UICONTROL Generate complement]** se desejar explorar a população restante. See [Use case: Creating deliveries with a complement](../../automating/using/workflow-created-query-with-complement.md).

1. Confirme a configuração da sua atividade e salve o fluxo de trabalho.
