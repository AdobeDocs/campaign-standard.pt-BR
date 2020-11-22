---
solution: Campaign Standard
product: campaign
title: Criar um relatório com base em segmentos de workflow
description: Saiba como verificar o sucesso de seu delivery dependendo dos segmentos de seus workflows em seus relatórios.
audience: reporting
content-type: reference
topic-tags: customizing-reports
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '617'
ht-degree: 2%

---


# Criar um relatório com base em segmentos de workflow{#creating-a-report-workflow-segment}

Depois de criar um fluxo de trabalho e filtrar sua população em diferentes audiências direcionadas, você pode medir a eficiência de suas campanhas de marketing com base nos segmentos definidos neste fluxo de trabalho de definição de metas.
Para público alvo desses segmentos em seus relatórios:

* [Etapa 1: Atualizar recurso personalizado de Perfis com segmentos](#step-1--update-profiles-custom-resource-segments)
* [Etapa 2: Criar um fluxo de trabalho com segmentos](#step-2--create-a-workflow-segments)
* [Etapa 3: Criar um relatório dinâmico para filtrar segmentos](#step-3--create-a-dynamic-report-filter-segments)

>[!CAUTION]
>O contrato de uso do relatórios dinâmico deve ser aceito para o start coletar esses dados.
>For more on this agreement, refer to this [page](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

## Etapa 1: Atualizar recurso personalizado de Perfis com segmentos{#step-1--update-profiles-custom-resource-segments}

Antes do relatórios do código de segmento, é necessário atualizar o recurso **[!UICONTROL Profiles]** personalizado para que os códigos de segmento sejam armazenados.

1. From the advanced menu, via the Adobe Campaign logo, select **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]**, then select the **[!UICONTROL Profile (profile)]** resource.
1. No **[!UICONTROL Sending logs extension]** menu da **[!UICONTROL Data structure]** guia, marque **[!UICONTROL Add segment code]** para permitir que o armazenamento de seus códigos de segmento seja direcionado para workflows de definição de metas e para enviá-lo para o relatórios dinâmico.

   O **[!UICONTROL Segment code]** estará disponível na seção de **[!UICONTROL Profile]** dimensão do seu relatório.

   ![](assets/report_segment_4.png)

1. Salve o recurso personalizado.

1. Agora você precisa publicar seu recurso personalizado.
No menu avançado, selecione **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publishing]**.

   ![](assets/custom_profile_7.png)

1. Clique em **[!UICONTROL Prepare publication]** e, quando a preparação estiver concluída, clique no **[!UICONTROL Publish]** botão. For more information on custom resource, refer to this [page](../../developing/using/updating-the-database-structure.md).

Agora você pode criar seu fluxo de trabalho com start.

Observe que os códigos de segmento serão coletados assim que você ativar o código de segmento no **[!UICONTROL Sending logs extension]**.

## Etapa 2: Criar um fluxo de trabalho com segmentos {#step-2--create-a-workflow-segments}

>[!NOTE]
>Se a transição de entrada do delivery de email estiver vazia, o Código de segmento da transição anterior será adicionado por padrão.

Primeiro, é necessário criar um fluxo de trabalho com população direcionada diferente. Aqui, queremos enviar um email que será personalizado dependendo da idade da nossa audiência: um delivery para perfis de 20 a 30 anos e outro para perfis de 30 a 40 anos.

1. Crie seu fluxo de trabalho. For more details on how to create your workflow, refer to this [page](../../automating/using/building-a-workflow.md).

1. Add a **[!UICONTROL Query]** activity by dragging it from the palette and dropping it in the workspace.

1. Perfis públicos alvos de 20 a 40 anos para depois segmentá-los em populações mais direcionadas.

   ![](assets/report_segment_1.png)

1. Adicione uma **[!UICONTROL Segmentation]** atividade para dividir os resultados do query em duas populações direcionadas. For more on segmentation, refer to this [page](../../automating/using/segmentation.md).

1. Duplo clique na **[!UICONTROL Segmentation]** atividade para configurá-la. Edite o primeiro segmento clicando em **[!UICONTROL Edit properties]**.

   ![](assets/report_segment_7.png)

1. Perfis de query entre 20 e 30 anos e clique **[!UICONTROL Confirm]** quando concluído.

   ![](assets/report_segment_8.png)

1. Clique **[!UICONTROL Add an element]** para criar seu segundo segmento e configurá-lo conforme descrito nas etapas acima para perfis de público alvo entre 30 e 40 anos.

1. Edite o **[!UICONTROL Segment code]** para que cada população seja transmitida pelo relatórios dinâmico.

   >[!NOTE]
   >Essa etapa é obrigatória ou você não poderá entender em quais segmentos relatar.

   ![](assets/report_segment_9.png)

1. Drag and drop an **[!UICONTROL Email delivery]** activity after your segments.

   ![](assets/report_segment_3.png)

1. Personalize seus delivery dependendo das diferentes populações-alvo. For more on email creation, refer to this [page](../../designing/using/designing-content-in-adobe-campaign.md).

1. Salve o workflow.

1. Clique **[!UICONTROL Start]** quando seu fluxo de trabalho estiver pronto.

Agora você pode acessar seus relatórios para rastrear seus códigos de segmento.

## Etapa 3: Criar um relatório dinâmico para filtrar segmentos {#step-3--create-a-dynamic-report-filter-segments}

Depois de enviar delivery com seu fluxo de trabalho, você pode detalhar os relatórios usando seus códigos de segmento do fluxo de trabalho.

1. Na **[!UICONTROL Reports]** guia, selecione um relatório predefinido ou clique no botão **[!UICONTROL Create new project]** para start um do zero.

   ![](assets/custom_profile_18.png)
1. Arraste e solte a **[!UICONTROL Delivery]** dimensão em sua tabela de forma livre.

   ![](assets/report_segment_5.png)

1. Arraste e solte métricas diferentes em sua tabela, como as métricas **[!UICONTROL Open]** e **[!UICONTROL Click]** , para filtrar seus dados por start.
1. Na **[!UICONTROL Dimensions]** categoria, clique na **[!UICONTROL Profile]** dimensão e arraste e solte a **[!UICONTROL Segment code]** dimensão no delivery do seu fluxo de trabalho para medir o sucesso do seu delivery de email, dependendo das populações direcionadas.

   ![](assets/report_segment_6.png)

1. Arraste e solte uma visualização no seu espaço de trabalho, se necessário.

   ![](assets/report_segment_10.png)
