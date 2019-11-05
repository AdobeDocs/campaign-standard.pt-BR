---
title: Criar um relatório com base em segmentos de fluxo de trabalho
description: Saiba como verificar o sucesso de sua entrega dependendo dos segmentos dos fluxos de trabalho em seus relatórios.
page-status-flag: nunca ativado
uuid: f75e005b-5328-4c98-9e78-51d54fd0e246
contentOwner: comida
products: SG_CAMPAIGN/STANDARD
audience: relatório
content-type: referência
topic-tags: personalização de relatórios
discoiquuid: b6d3de63-3add-4881-8917-04a6f8b6be4d
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Criar um relatório com base em segmentos de fluxo de trabalho{#creating-a-report-workflow-segment}

Depois de criar um fluxo de trabalho e filtrar sua população em públicos-alvo diferentes, você pode medir a eficiência de suas campanhas de marketing com base nos segmentos definidos neste fluxo de trabalho de definição de metas.
Para direcionar esses segmentos em seus relatórios:

* [Etapa 1: Atualizar recurso personalizado Perfis com segmentos](#step-1--update-profiles-custom-resource-segments)
* [Etapa 2: Criar um fluxo de trabalho com segmentos](#step-2--create-a-workflow-segments)
* [Etapa 3: Criar um relatório dinâmico para filtrar segmentos](#step-3--create-a-dynamic-report-filter-segments)

>[!CAUTION]
>O contrato de uso de relatório dinâmico deve ser aceito para começar a coletar esses dados.
>For more on this agreement, refer to this [page](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

## Etapa 1: Atualizar recurso personalizado Perfis com segmentos{#step-1--update-profiles-custom-resource-segments}

Antes de criar relatórios sobre seu código de segmento, é necessário atualizar seu recurso **[!UICONTROL Profiles]** personalizado para que seus códigos de segmento sejam armazenados.

1. No menu avançado, pelo logotipo do Adobe Campaign, selecione **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Custom resources]** e selecione o **[!UICONTROL Profile (profile)]** recurso.
1. No **[!UICONTROL Sending logs extension]** menu da **[!UICONTROL Data structure]** guia, marque **[!UICONTROL Add segment code]** para permitir o armazenamento de seus códigos de segmento a partir de fluxos de trabalho de definição de metas e para enviá-los para relatórios dinâmicos.

   O **[!UICONTROL Segment code]** estará disponível na seção de **[!UICONTROL Profile]** dimensão do seu relatório.

   ![](assets/report_segment_4.png)

1. Salve o recurso personalizado.

1. Agora você precisa publicar seu recurso personalizado.
No menu avançado, selecione **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Publishing]**.

   ![](assets/custom_profile_7.png)

1. Clique **[!UICONTROL Prepare publication]** e, quando a preparação estiver concluída, clique no **[!UICONTROL Publish]** botão. For more information on custom resource, refer to this [page](../../developing/using/updating-the-database-structure.md).

Agora você pode começar a criar seu fluxo de trabalho com códigos de segmento.

Observe que os códigos de segmento serão coletados assim que você ativar o código de segmento no **[!UICONTROL Sending logs extension]**.

## Etapa 2: Criar um fluxo de trabalho com segmentos {#step-2--create-a-workflow-segments}

>[!NOTE]
>Se a transição de entrada da entrega de email estiver vazia, o código do segmento da transição anterior será adicionado por padrão.

Primeiro, é necessário criar um fluxo de trabalho com população direcionada diferente. Aqui, queremos enviar um email que será personalizado dependendo da idade do nosso público: uma entrega para perfis de 20 a 30 anos e outra para perfis de 30 a 40 anos.

1. Crie seu fluxo de trabalho. Para obter mais detalhes sobre como criar seu fluxo de trabalho, consulte esta [página](../../automating/using/building-a-workflow.md).

1. Adicione uma **[!UICONTROL Query]** atividade arrastando-a da paleta e soltando-a no espaço de trabalho.

1. Direcione perfis de 20 a 40 anos para segmentar posteriormente em populações mais direcionadas.

   ![](assets/report_segment_1.png)

1. Adicione uma **[!UICONTROL Segmentation]** atividade para dividir os resultados da consulta em duas populações direcionadas. For more on segmentation, refer to this [page](../../automating/using/targeting-data.md#segmenting-data).

1. Clique duas vezes na **[!UICONTROL Segmentation]** atividade para configurá-la. Edite o primeiro segmento clicando em **[!UICONTROL Edit properties]**.

   ![](assets/report_segment_7.png)

1. Consulte os perfis entre 20 e 30 anos e clique **[!UICONTROL Confirm]** quando terminar.

   ![](assets/report_segment_8.png)

1. Clique **[!UICONTROL Add an element]** para criar seu segundo segmento e configurá-lo conforme descrito nas etapas acima para direcionar perfis entre 30 e 40 anos.

1. Edite o **[!UICONTROL Segment code]** para que cada população seja transmitida por meio de relatórios dinâmicos.

   >[!NOTE]
   >Essa etapa é obrigatória ou você não poderá entender em quais segmentos relatar.

   ![](assets/report_segment_9.png)

1. Arraste e solte uma **[!UICONTROL Email delivery]** atividade após seus segmentos.

   ![](assets/report_segment_3.png)

1. Personalize suas entregas dependendo das diferentes populações-alvo. For more on email creation, refer to this [page](../../designing/using/overview.md).

1. Salve o workflow.

1. Clique **[!UICONTROL Start]** quando seu fluxo de trabalho estiver pronto.

Agora você pode acessar seus relatórios para rastrear seus códigos de segmento.

## Etapa 3: Criar um relatório dinâmico para filtrar segmentos {#step-3--create-a-dynamic-report-filter-segments}

Depois de enviar entregas com seu fluxo de trabalho, você pode detalhar relatórios usando seus códigos de segmento do fluxo de trabalho.

1. Na **[!UICONTROL Reports]** guia, selecione um relatório predefinido ou clique no **[!UICONTROL Create new project]** botão para iniciar um do zero.

   ![](assets/custom_profile_18.png)
1. Arraste e solte a **[!UICONTROL Delivery]** dimensão em sua tabela de forma livre.

   ![](assets/report_segment_5.png)

1. Arraste e solte métricas diferentes em sua tabela, como as **[!UICONTROL Open]** e **[!UICONTROL Click]** métricas, para começar a filtrar seus dados.
1. Na **[!UICONTROL Dimensions]** categoria, clique na **[!UICONTROL Profile]** dimensão e arraste e solte a **[!UICONTROL Segment code]** dimensão na entrega do seu fluxo de trabalho para medir o sucesso da entrega de email, dependendo das populações direcionadas.

   ![](assets/report_segment_6.png)

1. Arraste e solte uma visualização no seu espaço de trabalho, se necessário.

   ![](assets/report_segment_10.png)
