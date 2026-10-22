---
title: Adicionar painéis
description: O relatório dinâmico permite que você adicione um painel para filtrar melhor os dados, dependendo do período escolhido.
audience: reporting
content-type: reference
topic-tags: customizing-reports
feature: Reporting
role: Leader
level: Intermediate
exl-id: e48b9630-c5ce-4d5d-90e6-97b77fbe3d50
TQID: 'https://experienceleague.adobe.com/jQtNVS-IFlOGMS5RAfKfOU610fZGzLB2GjEWwOPJE84'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: c309ee4e-82e4-4f7e-b608-ef345678c34e
    internal-label: Dynamic reporting
subfeature_v2:
  - id: b3a4149f-2b3a-44d1-894e-e3ac4c77fb47
    internal-label: Reporting interface
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 2%
---
# Adicionar painéis{#adding-panels}

## Adição de um painel em branco {#adding-a-blank-panel}

Para iniciar seu relatório, você pode adicionar um conjunto de painéis a um relatório pronto para uso ou personalizado. Cada painel contém diferentes conjuntos de dados e é composto por tabelas e visualizações de forma livre.

Esse painel permite criar relatórios conforme necessário. Você pode adicionar quantos painéis desejar em seus relatórios para filtrar seus dados com diferentes períodos de tempo.

1. Clique no ícone **Painéis**. Você também pode adicionar um painel clicando na **guia Inserir** e selecionando **Novo Painel em Branco**.

   ![](assets/dynamic_report_panel_1.png)

1. Arraste e solte o **Painel em Branco** no painel.

   ![](assets/dynamic_report_panel.png)

Agora é possível adicionar uma tabela de forma livre ao painel para começar a direcionar dados.

## Adição de uma tabela de forma livre {#adding-a-freeform-table}

As tabelas de forma livre permitem criar uma tabela para analisar seus dados usando as diferentes métricas e dimensões disponíveis na tabela **Componente**.

Cada tabela e visualização é redimensionável e pode ser movida para personalizar melhor seu relatório.

1. Clique no ícone **[!UICONTROL Panels]**.

   ![](assets/dynamic_report_panel_1.png)

1. Arraste e solte o item **[!UICONTROL Freeform]** no seu painel.

   Você também pode adicionar uma tabela clicando na guia **[!UICONTROL Insert]** e selecionando **[!UICONTROL New Freeform]** ou clicando em **[!UICONTROL Add a freeform table]** em um painel vazio.

   ![](assets/dynamic_report_panel_2.png)

1. No campo **[!UICONTROL Drop a segment here]**, adicione um **[!UICONTROL Segment]** da guia **[!UICONTROL Components]** na barra superior.

   ![](assets/dynamic_report_panel_3.png)

1. Arraste e solte itens da guia **[!UICONTROL Components]** nas colunas e linhas para criar sua tabela.

   ![](assets/dynamic_report_freeform_3.png)

1. Clique no ícone **[!UICONTROL Settings]** para alterar como os dados são exibidos em suas colunas.

   ![](assets/dynamic_report_freeform_4.png)

   O **[!UICONTROL Column settings]** é composto de:

   * **[!UICONTROL Number]**: permite mostrar ou ocultar números de resumo na coluna.
   * **[!UICONTROL Percent]**: permite mostrar ou ocultar a porcentagem na coluna.
   * **[!UICONTROL Interpret zero as no value]**: permite mostrar ou ocultar quando o valor é igual a zero.
   * **[!UICONTROL Background]**: permite mostrar ou ocultar a barra de progresso horizontal nas células.
   * **[!UICONTROL Include retries]**: permite incluir tentativas no resultado. Isto só está disponível para **[!UICONTROL Sent]** e **[!UICONTROL Bounces + Errors]**.

1. Selecione uma ou várias linhas e clique no ícone **[!UICONTROL Visualize]**. Uma visualização é adicionada para refletir as linhas selecionadas.

   ![](assets/dynamic_report_freeform_5.png)

Agora é possível adicionar quantos componentes forem necessários e também adicionar visualizações para fornecer representações gráficas de seus dados.
