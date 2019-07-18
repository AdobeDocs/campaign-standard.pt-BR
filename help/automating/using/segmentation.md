---
title: Segmentação
seo-title: Segmentação
description: Segmentação
seo-description: A atividade de Segmentação permite criar um ou vários segmentos a partir de uma população calculada pelas atividades realizadas anteriormente no fluxo de trabalho.
page-status-flag: nunca ativado
uuid: 77796 f 18-cad 5-4 e 7 a -9 d 7 b -4 ed 0 dd 8943 bf
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizando
content-type: reference
topic-tags: atividades de definição de metas
discoiquuid: 0 ccd 9 d 02-772 e -406 b -874 a -5381 dd 0 c 8709
context-tags: segmentação, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Segmentation{#segmentation}

## Description {#description}

![](assets/segmentation.png)

The **[!UICONTROL Segmentation]** activity lets you create one or several segments from a population calculated by activities placed earlier in the workflow. No fim da atividade, eles podem ser processados em uma única transição ou transições diferentes.

>[!NOTE]
>
>Por padrão, um membro da população de entrada pode pertencer apenas a um único segmento. Os filtros são aplicados de acordo com a ordem dos segmentos na atividade.

## Context of use {#context-of-use}

The **[!UICONTROL Segmentation]** activity is generally placed after targeting activities (query, intersection, union, exclusion, etc.) para definir a população padrão com base na qual os segmentos são formados.

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Segmentation]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Select the **[!UICONTROL Resource type]** on which the segmentation has to be carried out:

   * **[!UICONTROL Database resource]** se a segmentação for realizada em dados que já existam no banco de dados. Select the **[!UICONTROL Filtering dimension]** depending on the data that you want to segment. By default, segmentation is carried out on the **profiles**.
   * **[!UICONTROL Temporary resource]** se a segmentação for realizada nos dados temporários do fluxo de trabalho: selecione os **[!UICONTROL Targeted set]** dados a serem segmentados. Esse caso de uso pode ser encontrado após a importação de um arquivo ou se os dados no banco de dados tiverem sido aprimorados.

1. Selecione o tipo de transição de saída que deseja usar:

   * **[!UICONTROL Generate one transition per segment]**: uma transição de saída é adicionada para cada segmento configurado no final da atividade.
   * **[!UICONTROL Generate all segments in one transition]**: todos os segmentos configurados são reunidos em uma única transição de saída. Especifique o rótulo da transição. Os membros de cada segmento mantêm o código do segmento atribuído a eles.

1. Add a segment by using the ![](assets/add_darkgrey-24px.png) or **[!UICONTROL Add an element]** button and specify the standard properties:

   * **[!UICONTROL Do not activate the transition if the population is empty]**: o segmento só será ativado se os dados forem recuperados.
   * **[!UICONTROL Filter initial population (query)]**: permite filtrar a população do segmento.
   * **[!UICONTROL Limit segment population]**: permite limitar o tamanho do segmento.
   * **[!UICONTROL Filter and limit segment population]**: permite filtrar o preenchimento do segmento e limitar seu tamanho.
   * **[!UICONTROL Label]**: rótulo do segmento.
   * **[!UICONTROL Segment code]**: código atribuído à população do segmento. O código do segmento pode ser personalizado usando uma expressão padrão e variáveis de eventos (consulte [Personalizar atividades com variáveis de eventos](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables)).
   * **[!UICONTROL Exclude segment from population]**: permite excluir o segmento especificado da população de saída da atividade. This option can only be used if the **[!UICONTROL Generate all segments in the same transition]** option is selected.
   ![](assets/wkf_segment_new_segment.png)

1. Abra a exibição detalhada do segmento para acessar as opções de configuração do último. To do this, check the relevant box in the activity's segment list, then select ![](assets/wkf_segment_parameters_24px.png).
1. If the option to filter the initial population is checked, open the **[!UICONTROL Filter]** tab and specify your segment's population. Os filtros são baseados na dimensão de filtragem selecionada na etapa 4. Consult the [Query editing](../../automating/using/editing-queries.md) section for further information on population filtering.

   Se a segmentação for executada em um recurso temporário, a contagem e a visualização da população não estarão disponíveis nesta guia.

1. If the option to limit the segment size is checked, open the **[!UICONTROL Limitation]** tab.

   First, select the **[!UICONTROL Type of limit]** that you would like to use:

   * **[!UICONTROL Random sampling]**: a população do segmento é selecionada aleatoriamente levando em conta a configuração da **[!UICONTROL Filter]** guia, se necessário.
   * **[!UICONTROL Ordered sampling]**: a população do segmento é selecionada de forma ordenada. Consequentemente, você deve especificar as colunas a serem levadas em consideração e o tipo de classificação a ser aplicado. For example, if you select the **Age** field as the sort column while applying a **[!UICONTROL Descending sort]** and setting a limit of 100, only the profiles of the top 100 oldest people will be kept.
   Now specify the size **[!UICONTROL Limit]** of the segment:

   * **[!UICONTROL Size (as a % of the initial population)]**: especifique o tamanho do segmento usando uma porcentagem da população inicial da atividade.
   * **[!UICONTROL Maximum size]**: especificar um número máximo de membros para a população do segmento.
   * **[!UICONTROL By data grouping]**: você pode limitar a população de segmentos de acordo com os valores de um campo específico da população de entrada. Selecione o campo para agrupar e especifique os valores a serem usados.
   * **[!UICONTROL By data grouping (as a %)]**: você pode limitar a população do segmento de acordo com os valores de um campo de população de entrada específico usando uma porcentagem. Selecione o campo para aplicar o agrupamento e especifique os valores a serem usados.

      >[!NOTE]
      >
      >Diferentes limitações para cada valor podem ser usadas. For example, you can specify a grouping for the **[!UICONTROL Gender]** field and limit the population with **[!UICONTROL Male]** members to 10 and the population with **[!UICONTROL Female]** members to 30 people. Se você usar vários campos de agrupamento de dados, todos os agrupamentos precisarão ter o mesmo tamanho.
   ![](assets/wkf_segment_limit_by_grouping.png)

1. Confirme a configuração do segmento.
1. Adicione quantos segmentos forem necessários ao repetir as etapas de 6 a 10 desse procedimento.
1. If necessary, edit the parameters in the **[!UICONTROL Advanced options]** tab:

   * Check the **[!UICONTROL Enable overlapping of outbound populations]** option if you want a member of the inbound population to belong to several segments at the same time. A população de saída da atividade pode exceder a população de entrada.
   * Check the **[!UICONTROL Concatenate the code of each segment]** option if the inbound population has already been assigned a segment code that you want to keep. O código do segmento especificado na atividade será adicionado ao código do segmento inicial.
   * Check the **[!UICONTROL Generate complement]** option if you would like to exploit the remaining population.

1. Confirme a configuração da atividade e salve seu fluxo de trabalho.

## Example {#example}

O exemplo a seguir mostra uma segmentação de perfis de banco de dados de acordo com seu grupo etário. O objetivo do fluxo de trabalho é enviar um email específico para cada faixa etária. Considerando o fato de que esse fluxo de trabalho faz parte de uma campanha de teste, cada segmento pode conter apenas 100 perfis selecionados aleatoriamente para usar públicos-alvo limitados e representativos ao mesmo tempo.

![](assets/wkf_segment_example_4.png)

O fluxo de trabalho é composto pelos seguintes elementos:

* A **[!UICONTROL Scheduler]** activity to specify the workflow's execution date. Refer to the [Scheduler](../../automating/using/scheduler.md) section.
* A **[!UICONTROL Query]** activity to target profiles of people whose birthday and email address have been entered. Refer to the [Query](../../automating/using/query.md) section.
* A **[!UICONTROL Segmentation]** activity to create 3 segments divided into different outbound transitions: 18-25-year old, 26-32-year old and profiles that are over 32 years old. Os segmentos são definidos de acordo com os seguintes parâmetros:

   ![](assets/wkf_segment_example_3.png)

   * Um filtro da idade para definir o grupo etária do segmento

      ![](assets/wkf_segment_new_segment.png)

   * A **[!UICONTROL Random sampling]** type limit that is linked to a **[!UICONTROL Maximum size]** limit of 100

      ![](assets/wkf_segment_example_1.png)

* An **[!UICONTROL Email delivery]** activity per segment. Refer to the [Email delivery](../../automating/using/email-delivery.md) section.

