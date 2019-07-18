---
title: Consulta incremental
seo-title: Consulta incremental
description: Consulta incremental
seo-description: A atividade de consulta incremental permite filtrar e extrair uma população de elementos do banco de dados do Adobe Campaign.
page-status-flag: nunca ativado
uuid: 73 b 42422-e 815-43 ef -84 c 0-97 c 4433 ccc 98
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizando
content-type: reference
topic-tags: atividades de definição de metas
discoiquuid: 80961 e 73-42 ec -463 a -8496-cff 69 fab 0475
context-tags: incremental, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Incremental query{#incremental-query}

## Description {#description}

![](assets/incremental.png)

The **[!UICONTROL Incremental query]** activity allows you to filter and extract a population of elements from the Adobe Campaign database. Cada vez que essa atividade é executada, os resultados das execuções anteriores são excluídos. Isso permite direcionar apenas novos elementos.

You can define **[!UICONTROL Additional data]** for the targeted population via a dedicated tab. Esses dados são armazenados em colunas adicionais e podem ser usados apenas para o fluxo de trabalho em andamento.

A atividade usa a ferramenta do editor de consulta. This tool is detailed in a [dedicated section](../../automating/using/editing-queries.md#about-query-editor).

## Context of use {#context-of-use}

An **[!UICONTROL Incremental query]** has to be linked to a **[!UICONTROL Scheduler]** in order to define the execution frequency of the workflow, and therefore the query.

The **[!UICONTROL Processed data]** tab, which is specific to this activity, allows you to view any results of the activity's previous executions, if required.

**[!UICONTROL Incremental query]** A atividade pode ser usada para vários tipos de uso:

* Segmentação de indivíduos para definir a meta de uma mensagem, público-alvo, etc.
* Exportação de dados.

## Configuration {#configuration}

1. Drag and drop an **[!UICONTROL Incremental query]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. If you would like to run a query on a resource other than the profile resource, go to the activity's **[!UICONTROL Properties]** tab and select a **[!UICONTROL Resource]** and a **[!UICONTROL Targeting dimension]**.

   The **[!UICONTROL Resource]** allows you to refine the filters displayed in the palette whereas the **[!UICONTROL Targeting dimension]**, contextual with regard to the resource selected, corresponds to the type of population that you would like to obtain (identified profiles, deliveries, data linked to the selected resource, etc.).

1. In the **[!UICONTROL Target]** tab, run your query by defining and combining rules.
1. In the **[!UICONTROL Processed data]** tab, choose the incremental mode you want to use for the next executions of the workflow:

   * **[!UICONTROL Use the exclusion of the results of previous executions]**: os resultados das execuções anteriores para cada nova execução são excluídos.
   * **[!UICONTROL Use a date field]**: as próximas execuções levam em consideração os resultados que têm o campo de datas selecionado maior ou igual à última data de execução da **[!UICONTROL Incremental query]** atividade. You can select any date field pertaining to the resource selected in the **[!UICONTROL Properties]** tab. Esse modo tem melhor desempenho ao consultar recursos grandes, como dados de log.

      Após a primeira execução do fluxo de trabalho, você pode ver nesta guia a última data de execução que será usada para a próxima execução. É automaticamente atualizado toda vez que o fluxo de trabalho é executado. Você ainda tem a possibilidade de substituir esse valor inserindo manualmente um novo para que ele se ajuste às suas necessidades.
   >[!NOTE]
   >
   >The **[!UICONTROL Use a date field]** mode allows more flexibility depending on the date field that is selected. Por exemplo, se o campo selecionado corresponde a uma data de modificação, o modo de campo de data permitirá recuperar os dados que foram atualizados recentemente, enquanto o outro modo simplesmente excluirá as gravações que já foram direcionadas em uma execução anterior, mesmo que tenham sido modificadas desde a última execução do fluxo de trabalho.

   ![](assets/incremental_query_usedatefield.png)

1. You can define **[!UICONTROL Additional data]** for the targeted population via a dedicated tab. Esses dados são armazenados em colunas adicionais e podem ser usados apenas para o fluxo de trabalho em andamento. Especificamente, você pode adicionar dados das tabelas de banco de dados do Adobe Campaign relacionadas à dimensão de direcionamento da consulta. Consult the [Enriching data](../../automating/using/query.md#enriching-data) section.
1. Confirme a configuração da atividade e salve seu fluxo de trabalho.

## Enriching data {#enriching-data}

Just as for a query, you can enrich the data from an **[!UICONTROL Incremental query]**. Consult the [Enriching data](../../automating/using/query.md#enriching-data) section.

## Example: incremental query on subscribers to a service {#example--incremental-query-on-subscribers-to-a-service}

The following example shows the configuration of an **[!UICONTROL Incremental query]** activity which filters the profiles in the Adobe Campaign database that are subscribed to the **Running Newsletter** service, to send them a welcome email containing a promo code.

O fluxo de trabalho é composto pelos seguintes elementos:

![](assets/incremental_query_example1.png)

* A **[!UICONTROL Scheduler]** activity, to execute the workflow every Monday at 6 am.

   ![](assets/incremental_query_example2.png)

* An **[!UICONTROL Incremental query]** activity, which targets all of the current subscribers during the first execution, then only the new subscribers of that week during the following executions.

   ![](assets/incremental_query_example3.png)

* An **[!UICONTROL Email delivery]** activity. O fluxo de trabalho é executado uma vez por semana, mas é possível agregar os e-mails enviados e os resultados por mês, por exemplo, para gerar relatórios ao longo de um período de um mês inteiro e não apenas uma semana.

   To do this, choose to create a **[!UICONTROL Recurring email]** here regrouping the emails and the results **[!UICONTROL By month]**.

   Defina o conteúdo de seu email e insira o código promocional de boas-vindas.

   For more on this, refer to the [Email delivery](../../automating/using/email-delivery.md) and [Defining email content](../../designing/using/about-personalization.md) sections.

Em seguida, inicie a execução do fluxo de trabalho. Cada semana os novos assinantes receberão o email de boas-vindas com o código promocional.

## Example: incremental query on delivery logs {#example--incremental-query-on-delivery-logs}

You can use an **[!UICONTROL Incremental query]** activity to regularly export new logs in files. Isso pode ser útil por exemplo se você quiser usar seus dados de log em relatórios externos ou em ferramentas BI.

A complete example is available in the [Exporting logs](../../automating/using/exporting-logs.md) section.
