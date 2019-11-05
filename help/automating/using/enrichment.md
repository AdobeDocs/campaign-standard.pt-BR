---
title: Enriquecimento
description: A atividade Enriquecimento é uma atividade avançada que permite definir dados adicionais para serem processados no fluxo de trabalho.
page-status-flag: nunca ativado
uuid: 8c1693ef-1312-422c-b05d-263553113f8f
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: automatização
content-type: referência
topic-tags: atividades de definição de metas
discoiquuid: f67c1caf-3284-4c34-a5b0-8654a95640ae
context-tags: enriquecimento,principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Enriquecimento{#enrichment}

## Descrição {#description}

![](assets/enrichment.png)

A **[!UICONTROL Enrichment]** atividade é uma atividade avançada que permite definir dados adicionais para serem processados no fluxo de trabalho.

## Contexto de utilização {#context-of-use}

A **[!UICONTROL Enrichment]** atividade é geralmente usada após atividades de definição de metas ou após a importação de um arquivo e antes de atividades que permitem o uso de dados direcionados.

Esta atividade contém funções de enriquecimento mais avançadas do que a **[!UICONTROL Query]** atividade. Alguns casos simples de enriquecimento podem ser executados diretamente na atividade [Query](../../automating/using/query.md#enriching-data).

Com a **[!UICONTROL Enrichment]** atividade, você pode aproveitar a transição de entrada e configurar a atividade para concluir a transição de saída com dados adicionais. Permite combinar dados provenientes de vários conjuntos ou criar links para um recurso temporário.

## Configuração {#configuration}

Para configurar uma **[!UICONTROL Enrichment]** atividade:

1. Arraste e solte uma **[!UICONTROL Enrichment]** atividade em seu fluxo de trabalho.
1. Selecione a atividade e abra-a usando o ![](assets/edit_darkgrey-24px.png) botão das ações rápidas que aparecem.
1. Se a atividade tiver várias transições de entrada, selecione a **[!UICONTROL Primary set]**. Os dados adicionais configurados nesta atividade serão adicionados a este conjunto principal na transição de saída.

   Se o conjunto principal já contiver dados adicionais, você poderá optar por mantê-los ou removê-los. Se você desmarcar a **[!UICONTROL Keep all additional data from the main set]** opção, somente os dados adicionais configurados na transição **[!UICONTROL Enrichment]** serão mantidos.

1. Se houver várias transições de entrada, defina as relações entre o conjunto principal e os outros dados de entrada na **[!UICONTROL Advanced Relations]** guia da atividade. É possível adicionar várias relações usando o **[!UICONTROL Add element]** botão.

   Ao definir uma nova relação, selecione o conjunto de dados de entrada que você deseja vincular ao conjunto principal. Em seguida, defina o tipo de relação. Vários tipos de relações estão disponíveis, dependendo dos dados de entrada e do modelo de dados:

   * **[!UICONTROL 1 cardinality simple link]**: cada registro dos dados recebidos está associado a um e somente a um registro do conjunto principal. Cada registro do conjunto principal tem um registro associado nos dados vinculados.
   * **[!UICONTROL N cardinality collection link]**: 0, 1 ou mais registros (N) dos dados vinculados podem ser associados a 1 registro do conjunto principal.
   * **[!UICONTROL 0 or 1 cardinality simple link]**: os registros do conjunto principal podem ser associados a 0 ou 1 registro dos dados vinculados, mas não a mais de um.
   Uma vez que o **[!UICONTROL Cardinality]** for definido, defina um **[!UICONTROL Reconciliation criteria]**. O **[!UICONTROL Source expression]** dos critérios de reconciliação pode ser um campo do recurso de destino, uma [expressão](../../automating/using/advanced-expression-editing.md) ou um valor especificado diretamente entre aspas.

   Defina um **[!UICONTROL Label]** e um **[!UICONTROL ID]** que será fácil de identificar posteriormente no fluxo de trabalho.

   >[!NOTE]
   >
   >Você só pode definir relações entre o conjunto principal e as outras transições de entrada conectadas à **[!UICONTROL Enrichment]** atividade. Para casos mais simples que visem definir relações com recursos de banco de dados, use uma atividade de [Reconciliação](../../automating/using/reconciliation.md) .

1. Defina os dados adicionais na **[!UICONTROL Additional data]** guia da atividade. É possível definir dados adicionais (campos simples, agregados e coleções) relacionados à dimensão de definição de metas do conjunto principal ou com base nos links criados na **[!UICONTROL Advanced relations]** guia da **[!UICONTROL Enrichment]** atividade.

   Consulte a seção Dados [](../../automating/using/query.md#enriching-data) enriquecedores.

1. Confirme a configuração da atividade e salve o fluxo de trabalho.

Os dados agora estão disponíveis para uso nas atividades conectadas depois do **[!UICONTROL Enrichment]**. Por exemplo, você pode encontrá-lo sob o **[!UICONTROL Additional data (targetData)]** link do explorador de campos de personalização em um conteúdo de email.

## Exemplo: Enriquecendo dados de perfil com dados contidos em um arquivo {#example--enriching-profile-data-with-data-contained-in-a-file}

Este exemplo mostra como aprimorar dados de perfil com dados de compra contidos em um arquivo. Consideramos aqui que os dados de compra são armazenados em um sistema de terceiros. Cada perfil pode ter várias compras armazenadas no arquivo. O objetivo final do fluxo de trabalho é enviar um email para os perfis de destino que compraram pelo menos dois itens para agradecer sua lealdade.

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

   Com este arquivo de exemplo, usaremos o endereço de email para reconciliar os dados com os perfis do banco de dados. Também é possível ativar IDs exclusivas conforme descrito em [este documento](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources).

* Uma **[!UICONTROL Enrichment]** atividade que cria um link entre os dados da transação carregados do arquivo e os perfis selecionados no **[!UICONTROL Query]**. O link é definido na **[!UICONTROL Advanced relations]** guia da atividade. O link se baseia na transição proveniente da **[!UICONTROL Load file]** atividade. Ele usa o campo "email" do recurso de perfil e a coluna "cliente" do arquivo importado como critérios de reconciliação.

   ![](assets/enrichment_example_workflow2.png)

   Depois que o link é criado, dois conjuntos de **[!UICONTROL Additional data]** são adicionados:

   * Uma coleção de duas linhas correspondentes às duas últimas transações de cada perfil. Para essa coleção, o nome do produto, a data da transação e o preço do produto são adicionados como dados adicionais. Uma classificação decrescente é aplicada aos dados. Para criar a coleção, na **[!UICONTROL Additional data]** guia:

      Selecione o link definido anteriormente na **[!UICONTROL Advanced relations]** guia da atividade.

      ![](assets/enrichment_example_workflow3.png)

      Verifique **[!UICONTROL Collection]** e especifique o número de linhas a serem recuperadas (2 neste exemplo). Nessa tela, você pode personalizar o **[!UICONTROL Alias]** e o da coleção **[!UICONTROL Label]** . Esses valores estarão visíveis nas seguintes atividades do fluxo de trabalho ao fazer referência a essa coleção.

      ![](assets/enrichment_example_workflow4.png)

      Quanto **[!UICONTROL Data]** manter para a coleção, selecione as colunas que serão usadas na entrega final.

      ![](assets/enrichment_example_workflow6.png)

      Aplique uma classificação decrescente na data da transação para garantir a recuperação das transações mais recentes.

      ![](assets/enrichment_example_workflow7.png)

   * Uma contagem agregada do número total de transações para cada perfil. Esse agregado será usado posteriormente para filtrar perfis que tenham pelo menos duas transações registradas. Para criar a agregação, na **[!UICONTROL Additional data]** guia:

      Selecione o link definido anteriormente na **[!UICONTROL Advanced relations]** guia da atividade.

      ![](assets/enrichment_example_workflow3.png)

      Select **[!UICONTROL Aggregate]**.

      ![](assets/enrichment_example_workflow8.png)

      Como **[!UICONTROL Data]** manter, defina um agregado **Contar todos** . Se necessário, especifique um alias personalizado para encontrá-lo mais rapidamente nas seguintes atividades.

      ![](assets/enrichment_example_workflow9.png)

* Uma **[!UICONTROL Segmentation]** atividade com apenas um segmento, que recupera perfis do destino inicial que têm pelo menos duas transações registradas. Os perfis com apenas uma transação são excluídos. Para fazer isso, a consulta da segmentação é feita no agregado definido anteriormente.

   ![](assets/enrichment_example_workflow5.png)

* Uma **[!UICONTROL Email delivery]** atividade que usa os dados adicionais definidos no **[!UICONTROL Enrichment]** para recuperar dinamicamente as duas últimas compras feitas pelo perfil. Os dados adicionais podem ser encontrados no nó Dados **adicionais (TargetData)** ao adicionar um campo de personalização.

   ![](assets/enrichment_example_workflow10.png)

**Tópico relacionado:**

* [Enriquecer perfis de clientes com dados externos](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Managedatatofuelengagingexperiences)

