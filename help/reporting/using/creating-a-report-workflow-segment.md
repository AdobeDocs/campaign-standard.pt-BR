---
title: Criar relatório com base em segmentos de fluxo de trabalho
description: Saiba como verificar o sucesso do delivery dependendo dos segmentos dos workflows em seus relatórios.
audience: reporting
content-type: reference
topic-tags: customizing-reports
feature: Reporting
role: Leader
level: Intermediate
exl-id: 514bffa0-2413-4212-b1b9-e070031c462f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '624'
ht-degree: 2%

---

# Criar relatório com base em segmentos de fluxo de trabalho{#creating-a-report-workflow-segment}

>[!CAUTION]
> **[!UICONTROL Segment code]**O só pode direcionar deliveries de email e SMS.

Depois de criar um workflow e filtrar sua população em diferentes públicos-alvo, você pode medir a eficiência de suas campanhas de marketing com base nos segmentos definidos nesse workflow de direcionamento.
Para direcionar esses segmentos em seus relatórios:

* [Etapa 1: Atualizar recurso personalizado Perfis com segmentos](#step-1--update-profiles-custom-resource-segments)
* [Etapa 2: Criar um fluxo de trabalho com segmentos](#step-2--create-a-workflow-segments)
* [Etapa 3: Criar um relatório dinâmico para filtrar segmentos](#step-3--create-a-dynamic-report-filter-segments)

>[!CAUTION]
>O contrato de uso do Dynamic Reporting deve ser aceito para começar a coletar esses dados.
>
>Para obter mais informações sobre esse contrato, consulte esta seção [página](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

## Etapa 1: Atualizar recurso personalizado Perfis com segmentos{#step-1--update-profiles-custom-resource-segments}

Antes de criar relatórios sobre o código do segmento, é necessário atualizar **[!UICONTROL Profiles]** recurso personalizado para os códigos de segmento a serem armazenados.

1. No menu avançado, selecione pelo logotipo do Adobe Campaign **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]**, em seguida, selecione o **[!UICONTROL Profile (profile)]** recurso.
1. No **[!UICONTROL Sending logs extension]** no menu **[!UICONTROL Data structure]** guia , verifique **[!UICONTROL Add segment code]** para permitir o armazenamento dos códigos de seu segmento em workflows para construção do target e enviá-lo para relatórios dinâmicos.

   O **[!UICONTROL Segment code]** estará disponível no **[!UICONTROL Profile]** seção de dimensão do relatório.

   ![](assets/report_segment_4.png)

1. Salve o recurso personalizado.

1. Agora, é necessário publicar o recurso personalizado.
No menu avançado, selecione **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publishing]**.

   ![](assets/custom_profile_7.png)

1. Clique em **[!UICONTROL Prepare publication]** quando a preparação estiver concluída, clique no botão **[!UICONTROL Publish]** botão. Para obter mais informações sobre recursos personalizados, consulte esta seção [página](../../developing/using/updating-the-database-structure.md).

Agora é possível começar a criar seu fluxo de trabalho com códigos de segmento.

Observe que os códigos de segmento serão coletados assim que você ativar o código do segmento na **[!UICONTROL Sending logs extension]**.

## Etapa 2: Criar um fluxo de trabalho com segmentos {#step-2--create-a-workflow-segments}

>[!NOTE]
>Se a transição de entrada do delivery de email estiver vazia, o código do Segment da transição anterior será adicionado por padrão.

Primeiro, é necessário criar um workflow com uma população direcionada diferente. Aqui, queremos enviar um email que será personalizado dependendo da idade do público-alvo: uma delivery para perfis com idade entre 20 e 30 anos e outra para perfis entre 30 e 40 anos.

1. Crie seu workflow. Para obter mais detalhes sobre como criar o workflow, consulte esta seção [página](../../automating/using/building-a-workflow.md).

1. Adicione um **[!UICONTROL Query]** arrastando-a da paleta e soltando-a no espaço de trabalho.

1. Direcione perfis de 20 a 40 anos para segmentá-los posteriormente em populações mais direcionadas.

   ![](assets/report_segment_1.png)

1. Adicione um **[!UICONTROL Segmentation]** atividade para dividir os resultados da consulta em duas populações direcionadas. Para obter mais informações sobre segmentação, consulte esta seção [página](../../automating/using/segmentation.md).

1. Clique duas vezes na **[!UICONTROL Segmentation]** para configurá-la. Edite o primeiro segmento clicando em **[!UICONTROL Edit properties]**.

   ![](assets/report_segment_7.png)

1. Consultar perfis entre 20 e 30 anos e clicar em **[!UICONTROL Confirm]** quando concluído.

   ![](assets/report_segment_8.png)

1. Clique em **[!UICONTROL Add an element]** para criar seu segundo segmento e configurá-lo conforme descrito nas etapas acima para direcionar perfis entre 30 e 40 anos.

1. Edite o **[!UICONTROL Segment code]** para cada população a ser transmitida por meio de relatórios dinâmicos.

   >[!NOTE]
   >Essa etapa é obrigatória ou você não poderá entender em quais segmentos relatar.

   ![](assets/report_segment_9.png)

1. Arraste e solte um **[!UICONTROL Email delivery]** atividade após seus segmentos.

   ![](assets/report_segment_3.png)

1. Personalize seus deliveries dependendo das diferentes populações direcionadas. Para obter mais informações sobre criação de email, consulte esta seção. [página](../../designing/using/designing-content-in-adobe-campaign.md).

1. Salve o workflow.

1. Clique em **[!UICONTROL Start]** quando o fluxo de trabalho estiver pronto.

Agora é possível acessar seus relatórios para rastrear os códigos do segmento.

## Etapa 3: Criar um relatório dinâmico para filtrar segmentos {#step-3--create-a-dynamic-report-filter-segments}

Após enviar os deliveries com o workflow, é possível detalhar os relatórios usando os códigos de segmento do workflow.

1. No **[!UICONTROL Reports]** selecione um relatório pronto para uso ou clique no link **[!UICONTROL Create new project]** botão para iniciar um do zero.

   ![](assets/custom_profile_18.png)
1. Arraste e solte a **[!UICONTROL Delivery]** à tabela de forma livre.

   ![](assets/report_segment_5.png)

1. Arraste e solte métricas diferentes na tabela, como a variável **[!UICONTROL Open]** e **[!UICONTROL Click]** para começar a filtrar seus dados.
1. No **[!UICONTROL Dimensions]** , clique no botão **[!UICONTROL Profile]** em seguida, arraste e solte a **[!UICONTROL Segment code]** na entrega do seu fluxo de trabalho para medir o sucesso da sua entrega de email, dependendo das populações direcionadas.

   ![](assets/report_segment_6.png)

1. Arraste e solte uma visualização em seu espaço de trabalho, se necessário.

   ![](assets/report_segment_10.png)
