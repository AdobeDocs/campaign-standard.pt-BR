---
title: Enriquecimento
seo-title: Enriquecimento
description: Enriquecimento
seo-description: A atividade de Enriquecimento é uma atividade avançada que permite que você defina dados adicionais para processar no seu fluxo de trabalho.
page-status-flag: nunca ativado
uuid: 8 c 1693 ef -1312-422 c-b 05 d -263553113 f 8 f
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizando
content-type: reference
topic-tags: atividades de definição de metas
discoiquuid: f 67 c 1 caf -3284-4 c 34-a 5 b 0-8654 a 95640 ae
context-tags: enriquecimento, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 782a5f89b0361f1cbe59c9b353ca90dec90c3906

---


# Enriquecimento{#enrichment}

## Descrição {#description}

![](assets/enrichment.png)

**[!UICONTROL Enrichment]** A atividade é uma atividade avançada que permite que você defina dados adicionais para processar no seu fluxo de trabalho.

## Contexto de uso {#context-of-use}

A **[!UICONTROL Enrichment]** atividade é geralmente usada após as atividades de definição de metas ou após a importação de um arquivo e antes das atividades que permitem o uso de dados direcionados.

Essa atividade contém funções de enriquecimento mais avançadas do que a **[!UICONTROL Query]** atividade. Alguns casos simples de enriquecimento podem ser executados diretamente na atividade [de consulta](../../automating/using/query.md#enriching-data).

Com **[!UICONTROL Enrichment]** a atividade, você pode aproveitar a transição de entrada e configurar a atividade para concluir a transição de saída com dados adicionais. Ela permite combinar dados provenientes de vários conjuntos ou criar links para um recurso temporário.

## Configuração {#configuration}

Para configurar uma **[!UICONTROL Enrichment]** atividade:

1. Arraste e solte uma **[!UICONTROL Enrichment]** atividade no seu fluxo de trabalho.
1. Selecione a atividade e abra-a usando o ![](assets/edit_darkgrey-24px.png) botão das ações rápidas que aparecem.
1. Se a atividade tiver várias transições de entrada, selecione-a **[!UICONTROL Primary set]**. Os dados adicionais configurados nesta atividade serão adicionados a esse conjunto principal na transição de saída.

   Se o conjunto principal já contiver dados adicionais, você poderá optar por mantê-los ou removê-los. Se você desmarcar a **[!UICONTROL Keep all additional data from the main set]** opção, apenas os dados adicionais configurados nos **[!UICONTROL Enrichment]** são mantidos na transição de saída.

1. Se houver várias transições de entrada, defina as relações entre o conjunto principal e os outros dados de entrada na **[!UICONTROL Advanced Relations]** guia da atividade. Você pode adicionar várias relações usando o **[!UICONTROL Add element]** botão.

   Ao definir uma nova relação, selecione o conjunto de dados de entrada que deseja vincular ao conjunto principal. Em seguida, defina o tipo de relação. Vários tipos de relações estão disponíveis, dependendo dos dados de entrada e do modelo de dados:

   * **[!UICONTROL 1 cardinality simple link]**: cada registro dos dados de entrada está associado a um e apenas um registro do conjunto principal. Cada registro do conjunto principal tem um registro associado nos dados vinculados.
   * **[!UICONTROL N cardinality collection link]**: 0, 1 ou mais (N) registros de dados vinculados podem ser associados a 1 registro do conjunto principal.
   * **[!UICONTROL 0 or 1 cardinality simple link]**: os registros do conjunto principal podem ser associados a 0 ou 1 registros a partir dos dados vinculados, mas não mais do que um.
   Uma vez **[!UICONTROL Cardinality]** definido, defina a **[!UICONTROL Reconciliation criteria]**. O **[!UICONTROL Source expression]** dos critérios de reconciliação pode ser um campo do recurso de destino, uma [expressão](../../automating/using/advanced-expression-editing.md) ou diretamente um valor especificado entre aspas.

   Defina um **[!UICONTROL Label]** e um **[!UICONTROL ID]** que será fácil de identificar mais tarde no fluxo de trabalho.

   >[!NOTE]
   >
   >Apenas é possível definir relações entre o conjunto principal e as outras transições de entrada conectadas à **[!UICONTROL Enrichment]** atividade. Para casos mais simples com o objetivo de definir relações com recursos de banco de dados, use uma [atividade de Reconciliação](../../automating/using/reconciliation.md) .

1. Defina os dados adicionais da **[!UICONTROL Additional data]** guia da atividade. É possível definir dados adicionais (campos simples, agregados e coleções) relacionados à dimensão de definição de metas do conjunto principal ou com base nos links criados na **[!UICONTROL Advanced relations]** guia da **[!UICONTROL Enrichment]** atividade.

   Consulte a seção [de dados](../../automating/using/query.md#enriching-data) Enriquecimento.

1. Confirme a configuração da atividade e salve seu fluxo de trabalho.

Os dados agora estão disponíveis para uso nas atividades conectadas depois do **[!UICONTROL Enrichment]**. Por exemplo, é possível encontrá-lo sob o **[!UICONTROL Additional data (targetData)]** link dos campos de personalização explorer em um conteúdo de email.

## Exemplo: Enriquecer dados de perfil com dados contidos em um arquivo {#example--enriching-profile-data-with-data-contained-in-a-file}

Este exemplo mostra como encher dados de perfil com dados de compra contidos em um arquivo. Consideramos que os dados de compra são armazenados em um sistema de terceiros. Cada perfil pode ter várias compras armazenadas no arquivo. A meta final do fluxo de trabalho é enviar um email para os perfis de destino que compraram pelo menos dois itens para agradecer pela fidelidade.

O fluxo de trabalho é configurado da seguinte maneira:

![](assets/enrichment_example_workflow.png)

* Uma **[!UICONTROL Query]** atividade direcionada aos perfis que receberão a mensagem.
* Uma **[!UICONTROL Load file]** atividade que carrega os dados de compra. Por exemplo:

   ```
   tcode;tdate;customer;product;tamount
   aze123;21/05/2017;dannymars@example.com;TV;799
   aze124;28/05/2017;dannymars@example.com;Headphones;8
   aze125;31/07/2017;john.smith@example.com;Headphones;8
   aze126;14/12/2017;john.smith@example.com;Plastic Cover;4
   aze127;02/01/2018;dannymars@example.com;Case Cover;79
   aze128;04/03/2017;clara.smith@example.com;Phone;149
   ```

   Com esse arquivo de exemplo, nós usaremos o endereço de email para reconciliar os dados com os perfis de banco de dados. Você também pode ativar IDs exclusivas conforme descrito [neste documento](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources).

* **[!UICONTROL Enrichment]** Uma atividade que cria um vínculo entre os dados de transação carregados do arquivo e os perfis selecionados no **[!UICONTROL Query]**. O link é definido na **[!UICONTROL Advanced relations]** guia da atividade. O link se baseia na transição proveniente da **[!UICONTROL Load file]** atividade. Ele usa o campo "email" do recurso de perfil e a coluna "cliente" do arquivo importado como critério de reconciliação.

   ![](assets/enrichment_example_workflow2.png)

   Depois que o link é criado, dois conjuntos de **[!UICONTROL Additional data]** são adicionados:

   * Uma coleção de duas linhas correspondendo às duas últimas transações de cada perfil. Para essa coleção, o nome do produto, a data da transação e o preço do produto são adicionados como dados adicionais. Uma classificação decrescente é aplicada nos dados. Para criar a coleção, na **[!UICONTROL Additional data]** guia:

      Selecione o link definido anteriormente na **[!UICONTROL Advanced relations]** guia da atividade.

      ![](assets/enrichment_example_workflow3.png)

      Verifique **[!UICONTROL Collection]** e especifique o número de linhas a serem recuperadas (2 neste exemplo). Nessa tela, você pode personalizar o **[!UICONTROL Alias]** e o **[!UICONTROL Label]** da coleção. Esses valores estarão visíveis nas seguintes atividades do fluxo de trabalho ao se referir a essa coleção.

      ![](assets/enrichment_example_workflow4.png)

      Para **[!UICONTROL Data]** manter a coleção, selecione as colunas que serão usadas na entrega final.

      ![](assets/enrichment_example_workflow6.png)

      Aplique uma classificação decrescente na data da transação para recuperar as transações mais recentes.

      ![](assets/enrichment_example_workflow7.png)

   * Uma contagem agregada do número total de transações para cada perfil. Esse agregado será usado posteriormente para filtrar perfis com pelo menos duas transações gravadas. Para criar o agregado, na **[!UICONTROL Additional data]** guia:

      Selecione o link definido anteriormente na **[!UICONTROL Advanced relations]** guia da atividade.

      ![](assets/enrichment_example_workflow3.png)

      Selecione **[!UICONTROL Aggregate]**.

      ![](assets/enrichment_example_workflow8.png)

      Como **[!UICONTROL Data]** manter, defina uma **contagem de Contagem total** . Se for necessário, especifique um alias personalizado para encontrá-lo mais rápido nas seguintes atividades.

      ![](assets/enrichment_example_workflow9.png)

* Uma **[!UICONTROL Segmentation]** atividade com apenas um segmento, que recupera perfis do destino inicial com pelo menos duas transações gravadas. Perfis com apenas uma transação são excluídos. Para fazer isso, a consulta da segmentação é feita previamente no agregado definido anteriormente.

   ![](assets/enrichment_example_workflow5.png)

* Uma **[!UICONTROL Email delivery]** atividade que usa os dados adicionais definidos para **[!UICONTROL Enrichment]** recuperar dinamicamente as duas últimas compras feitas pelo perfil. Os dados adicionais podem ser encontrados no nó Dados **adicionais (targetdata)** ao adicionar um campo de personalização.

   ![](assets/enrichment_example_workflow10.png)

**Tópico relacionado:**

* [Enriquecer perfis de clientes com dados externos](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Managedatatofuelengagingexperiences)

