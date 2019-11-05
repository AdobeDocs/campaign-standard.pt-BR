---
title: Segmentação
description: A atividade de Segmentação permite criar um ou vários segmentos a partir de uma população calculada por atividades colocadas anteriormente no fluxo de trabalho.
page-status-flag: nunca ativado
uuid: 77796f18-cad5-4e7a-9d7b-4ed0dd8943bf
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: automatização
content-type: referência
topic-tags: atividades de definição de metas
discoiquuid: 0cd9d02-772e-406b-874a-5381dd0c8709
context-tags: segmentação,principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Segmentação{#segmentation}

## Descrição {#description}

![](assets/segmentation.png)

A **[!UICONTROL Segmentation]** atividade permite criar um ou vários segmentos a partir de uma população calculada por atividades colocadas anteriormente no fluxo de trabalho. No final da atividade, eles podem ser processados em uma única transição ou diferentes transições.

>[!NOTE]
>
>Por padrão, um membro da população de entrada só pode pertencer a um único segmento. Os filtros são aplicados de acordo com a ordem dos segmentos na atividade.

## Contexto de utilização {#context-of-use}

A **[!UICONTROL Segmentation]** atividade geralmente é colocada após as atividades de direcionamento (consulta, interseção, união, exclusão etc.) para definir a população padrão com base na qual os segmentos são formados.

## Configuração {#configuration}

1. Arraste e solte uma **[!UICONTROL Segmentation]** atividade em seu fluxo de trabalho.
1. Selecione a atividade e abra-a usando o ![](assets/edit_darkgrey-24px.png) botão das ações rápidas que aparecem.
1. Selecione o **[!UICONTROL Resource type]** local em que a segmentação deve ser realizada:

   * **[!UICONTROL Database resource]** se a segmentação for realizada em dados que já existem no banco de dados. Selecione os dados **[!UICONTROL Filtering dimension]** dependendo dos que deseja segmentar. Por padrão, a segmentação é realizada nos **perfis**.
   * **[!UICONTROL Temporary resource]** se a segmentação for realizada nos dados temporários do fluxo de trabalho: selecione os dados **[!UICONTROL Targeted set]** que contêm os dados a serem segmentados. Esse caso de uso pode ser encontrado após a importação de um arquivo ou se os dados no banco de dados foram enriquecidos.

1. Selecione o tipo de transição de saída que você deseja usar:

   * **[!UICONTROL Generate one transition per segment]**: uma transição de saída é adicionada para cada segmento configurado no final da atividade.
   * **[!UICONTROL Generate all segments in one transition]**: todos os segmentos configurados são agrupados em uma única transição de saída. Especifique o rótulo de transição. Os membros de cada segmento mantêm o código de segmento que foi atribuído a eles.

1. Adicione um segmento usando o botão ![](assets/add_darkgrey-24px.png) ou **[!UICONTROL Add an element]** e especifique as propriedades padrão:

   * **[!UICONTROL Do not activate the transition if the population is empty]**: o segmento só será ativado se os dados forem recuperados.
   * **[!UICONTROL Filter initial population (query)]**: permite filtrar a população desse segmento.
   * **[!UICONTROL Limit segment population]**: permite limitar o tamanho do segmento.
   * **[!UICONTROL Filter and limit segment population]**: permite filtrar a população do segmento e limitar seu tamanho.
   * **[!UICONTROL Label]**: rótulo do segmento.
   * **[!UICONTROL Segment code]**: código atribuído à população do segmento. O código do segmento pode ser personalizado usando uma expressão padrão e variáveis de eventos (consulte [Personalizar atividades com variáveis](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables)de eventos).
   * **[!UICONTROL Exclude segment from population]**: permite que você exclua o segmento especificado da população de saída da atividade. Essa opção só pode ser usada se a **[!UICONTROL Generate all segments in the same transition]** opção estiver selecionada.
   ![](assets/wkf_segment_new_segment.png)

1. Abra a exibição detalhada do segmento para acessar as opções de configuração do último. Para fazer isso, marque a caixa relevante na lista de segmentos da atividade e selecione ![](assets/wkf_segment_parameters_24px.png).
1. Se a opção para filtrar a população inicial estiver marcada, abra a **[!UICONTROL Filter]** guia e especifique a população do segmento. Os filtros são baseados na dimensão de filtragem selecionada na etapa 4. Consulte a seção de edição [](../../automating/using/editing-queries.md) Consulta para obter mais informações sobre a filtragem de população.

   Se a segmentação for realizada em um recurso temporário, a contagem e a visualização da população não estarão disponíveis nesta guia.

1. Se a opção para limitar o tamanho do segmento estiver marcada, abra a **[!UICONTROL Limitation]** guia.

   Primeiro, selecione o **[!UICONTROL Type of limit]** que deseja usar:

   * **[!UICONTROL Random sampling]**: a população do segmento é selecionada aleatoriamente levando em conta a configuração da guia, se necessário. **[!UICONTROL Filter]**
   * **[!UICONTROL Ordered sampling]**: a população do segmento é selecionada de forma ordenada. Consequentemente, você deve especificar as colunas a serem consideradas e o tipo de classificação a ser aplicado. Por exemplo, se você selecionar o campo **Idade** como a coluna de classificação ao aplicar um **[!UICONTROL Descending sort]** e definir um limite de 100, somente os perfis das 100 pessoas mais velhas serão mantidos.
   Agora especifique o tamanho **[!UICONTROL Limit]** do segmento:

   * **[!UICONTROL Size (as a % of the initial population)]**: especifique o tamanho do segmento usando uma porcentagem da população inicial da atividade.
   * **[!UICONTROL Maximum size]**: especifique um número máximo de membros para a população do segmento.
   * **[!UICONTROL By data grouping]**: é possível limitar a população do segmento de acordo com os valores de um campo específico da população de entrada. Selecione o campo para agrupamento e especifique os valores a serem usados.
   * **[!UICONTROL By data grouping (as a %)]**: é possível limitar a população do segmento de acordo com os valores de um campo de população de entrada específico usando uma porcentagem. Selecione o campo para aplicar o agrupamento e especifique os valores a serem usados.

      >[!NOTE]
      >
      >Podem ser usadas diferentes limitações para cada valor. Por exemplo, você pode especificar um agrupamento para o **[!UICONTROL Gender]** campo e limitar a população com **[!UICONTROL Male]** membros a 10 e a população com **[!UICONTROL Female]** membros a 30 pessoas. Se você usar vários campos de agrupamento de dados, todos os agrupamentos deverão ter o mesmo tamanho.
   ![](assets/wkf_segment_limit_by_grouping.png)

1. Confirme a configuração do seu segmento.
1. Adicione quantos segmentos forem necessários repetindo as etapas de 6 a 10 desse procedimento.
1. Se necessário, edite os parâmetros na **[!UICONTROL Advanced options]** guia:

   * Marque a **[!UICONTROL Enable overlapping of outbound populations]** opção se desejar que um membro da população de entrada pertença a vários segmentos ao mesmo tempo. A população de saída da atividade pode exceder a população de entrada.
   * Marque a **[!UICONTROL Concatenate the code of each segment]** opção se a população de entrada já tiver recebido um código de segmento que você deseja manter. O código do segmento especificado na atividade será adicionado ao código do segmento inicial.
   * Marque a **[!UICONTROL Generate complement]** opção se desejar explorar a população restante.

1. Confirme a configuração da atividade e salve o fluxo de trabalho.

## Exemplo {#example}

O exemplo a seguir mostra uma segmentação de perfis de banco de dados de acordo com sua faixa etária. O objetivo do fluxo de trabalho é enviar um email específico para cada faixa etária. Considerando o fato de que esse fluxo de trabalho é parte de uma campanha de teste, cada segmento só pode conter um máximo de 100 perfis que são selecionados aleatoriamente para usar públicos-alvo limitados e representativos ao mesmo tempo.

![](assets/wkf_segment_example_4.png)

O fluxo de trabalho é composto dos seguintes elementos:

* Uma **[!UICONTROL Scheduler]** atividade para especificar a data de execução do fluxo de trabalho. Refer to the [Scheduler](../../automating/using/scheduler.md) section.
* Uma **[!UICONTROL Query]** atividade para direcionar perfis de pessoas cujo endereço de aniversário e email foi inserido. Refer to the [Query](../../automating/using/query.md) section.
* Uma **[!UICONTROL Segmentation]** atividade para criar 3 segmentos divididos em diferentes transições de saída: 18-25 anos, 26-32 anos e perfis que têm mais de 32 anos. Os segmentos são definidos de acordo com os seguintes parâmetros:

   ![](assets/wkf_segment_example_3.png)

   * Um filtro na página para definir a faixa etária do segmento

      ![](assets/wkf_segment_new_segment.png)

   * Um limite **[!UICONTROL Random sampling]** de tipo vinculado a um **[!UICONTROL Maximum size]** limite de 100

      ![](assets/wkf_segment_example_1.png)

* Uma **[!UICONTROL Email delivery]** atividade por segmento. Consulte a seção Entrega [de](../../automating/using/email-delivery.md) email.

