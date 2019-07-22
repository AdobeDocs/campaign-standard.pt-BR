---
title: Criação de um relatório com base em segmentos de fluxo de trabalho
seo-title: Criação de um relatório com base em segmentos de fluxo de trabalho
description: Criação de um relatório com base em segmentos de fluxo de trabalho
seo-description: Saiba como verificar o sucesso da entrega, dependendo dos segmentos dos seus fluxos de trabalho em seus relatórios.
page-status-flag: nunca ativado
uuid: f 75 e 005 b -5328-4 c 98-9 e 78-51 d 54 fd 0 e 246
contentOwner: beneat
products: SG_ CAMPAIGN/STANDARD
audience: relatórios
content-type: reference
topic-tags: personalização-relatórios
discoiquuid: b 6 d 3 de 63-3 add -4881-8917-04 a 6 f 8 b 6 be 4 d
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 36e04227f300d28d2c48da440ddab3ccf9281168

---


# Creating a report based on workflow segments{#creating-a-report-workflow-segment}

Depois de criar um fluxo de trabalho e filtrar sua população em diferentes público-alvo, você pode medir a eficiência de suas campanhas de marketing com base em segmentos definidos neste fluxo de trabalho de direcionamento.
Para direcionar esses segmentos em seus relatórios:

* [Etapa 1: Atualizar recursos personalizados de perfis com segmentos](#step-1--update-profiles-custom-resource-segments)
* [Etapa 2: Criar um fluxo de trabalho com segmentos](#step-2--create-a-workflow-segments)
* [Etapa 3: Criar um relatório dinâmico para filtrar segmentos](#step-3--create-a-dynamic-report-filter-segments)

>[!CAUTION]
>O contrato de uso de relatório dinâmico deve ser aceito para começar a coletar esses dados.
>For more on this agreement, refer to this [page](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

## Step 1: Update Profiles custom resource with segments{#step-1--update-profiles-custom-resource-segments}

Before reporting on your segment code, you need to update your **[!UICONTROL Profiles]** custom resource for your segment codes to be stored.

1. From the advanced menu, via the Adobe Campaign logo, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Custom resources]**, then select the **[!UICONTROL Profile (profile)]** resource.
1. In the **[!UICONTROL Sending logs extension]** menu from the **[!UICONTROL Data structure]** tab, check **[!UICONTROL Add segment code]** to allow storage of your segment codes from targeting workflows and to send it to dynamic reporting.

   The **[!UICONTROL Segment code]** will then be available in the **[!UICONTROL Profile]** dimension section of your report.

   ![](assets/report_segment_4.png)

1. Salve o recurso personalizado.

1. Agora você precisa publicar seu recurso personalizado.
From the advanced menu, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Publishing]**.

   ![](assets/custom_profile_7.png)

1. Click **[!UICONTROL Prepare publication]** then when the preparation is done, click the **[!UICONTROL Publish]** button. For more information on custom resource, refer to this [page](../../developing/using/updating-the-database-structure.md).

Agora você pode começar a criar seu fluxo de trabalho com códigos de segmento.

Note that segment codes will be collected as soon as you enable the segment code in the **[!UICONTROL Sending logs extension]**.

## Step 2: Create a workflow with segments {#step-2--create-a-workflow-segments}

[!NOTE]
>Se a transição de entrada da entrega de email estiver vazia, o código do Segmento da transição anterior será adicionado por padrão.

Primeiro, você precisa criar um fluxo de trabalho com uma população direcionada diferente. Aqui, queremos enviar um email que será personalizado dependendo da idade de nosso público-alvo: uma entrega por 20 a 30 anos e outra para perfis entre 30 a 40 anos.

1. Crie seu fluxo de trabalho. For more details on how to create your workflow, refer to this [page](../../automating/using/building-a-workflow.md).

1. Add a **[!UICONTROL Query]** activity by dragging it from the palette and dropping it in the workspace.

1. Direcione perfis de 20 a 40 anos para segmentar os segmentos mais tarde em populações mais direcionadas.

   ![](assets/report_segment_1.png)

1. Add a **[!UICONTROL Segmentation]** activity to split your query results into two targeted populations. For more on segmentation, refer to this [page](../../automating/using/targeting-data.md#segmenting-data).

1. Double click the **[!UICONTROL Segmentation]** activity to configure it. Edit the first segment by clicking **[!UICONTROL Edit properties]**.

   ![](assets/report_segment_7.png)

1. Query profiles between the age of 20 to 30 and click **[!UICONTROL Confirm]** when done.

   ![](assets/report_segment_8.png)

1. Click **[!UICONTROL Add an element]** to create your second segment and configure it as described in the steps above to target profiles between the age of 30 to 40.

1. Edit the **[!UICONTROL Segment code]** for each population to be passed on through dynamic reporting.

   >[!NOTE]
   >Essa etapa é obrigatória ou você não poderá compreender quais segmentos serão relatados.

   ![](assets/report_segment_9.png)

1. Drag and drop an **[!UICONTROL Email delivery]** activity after your segments.

   ![](assets/report_segment_3.png)

1. Personalize suas entregas dependendo das diferentes populações direcionadas. For more on email creation, refer to this [page](../../designing/using/about-email-content-design.md).

1. Salve o fluxo de trabalho.

1. Click **[!UICONTROL Start]** when your workflow is ready.

Agora você pode acessar seus relatórios para rastrear seus códigos de segmento.

## Step 3: Create a dynamic report to filter segments {#step-3--create-a-dynamic-report-filter-segments}

Depois de enviar entregas com seu fluxo de trabalho, você pode detalhar os relatórios usando seus códigos de segmento do seu fluxo de trabalho.

1. From the **[!UICONTROL Reports]** tab, select an out-of-the-box report or click the **[!UICONTROL Create new project]** button to start one from scratch.

   ![](assets/custom_profile_18.png)
1. Drag and drop the **[!UICONTROL Delivery]** dimension to your freeform table.

   ![](assets/report_segment_5.png)

1. Drag and drop different metrics to your table such as the **[!UICONTROL Open]** and **[!UICONTROL Click]** metrics to start filtering your data.
1. In the **[!UICONTROL Dimensions]** category, click the **[!UICONTROL Profile]** dimension then drag and drop the **[!UICONTROL Segment code]** dimension on your workflow's delivery to measure the success of your email delivery depending on the targeted populations.

   ![](assets/report_segment_6.png)

1. Arraste e solte uma visualização na área de trabalho, se necessário.

   ![](assets/report_segment_10.png)
