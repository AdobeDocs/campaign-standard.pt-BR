---
title: API externa
seo-title: API externa
description: API externa
seo-description: null
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizando
content-type: reference
topic-tags: atividades de definição de metas
context-tags: Externalapi, fluxo de trabalho, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1444a636f401ed9c34295aaca1a2b3271d6700a4

---


# External API {#external-api}

## Description {#description}

![](assets/wf_externalAPI.png)

The **[!UICONTROL External API]** activity brings data into the workflow from an **external system** via a **REST API** call.

The REST endpoints can be a Customer management system, an [Adobe I/O Runtime](https://www.adobe.io/apis/experienceplatform/runtime.html) or an Experience Cloud REST endpoints (Data Platform, Target, Analytics, Campaign, etc).

As principais características dessa atividade são:

* Limite de tamanho de dados de resposta HTTP de 5 MB
* Gerenciamento de falha com uma transição específica de saída
* O tempo limite da solicitação é de 60 segundos
* Redirecionamentos HTTP não são permitidos
* Os Urls não HTTPS são rejeitados
* " Accept: application/json "header and and" Content-Type: o cabeçalho de resposta do aplicativo/json é permitido

## Configuration {#configuration}

Drag and drop an **[!UICONTROL External API]** activity into your workflow and open the activity to start the configuration.

### Mapeamento de entrada

O mapeamento de entrada é uma tabela temporária gerada por uma atividade de entrada anterior que será exibida e enviada como JSON na interface do usuário.
Com base nesta tabela temporária, o usuário pode fazer modificações nos dados de entrada.

![](assets/externalAPI-inbound.png)

The **Inbound resource** dropdown lets you select the query activity that will create the temporary table.

The **Add count parameter** checkbox will a count value for each row coming from the temporary table. Observe que essa caixa de seleção está disponível somente se a atividade de entrada estiver gerando uma tabela temporária.

The **Inbound Columns** section allow the user to add any fields from the inbound transition table. As colunas selecionadas serão as chaves no objeto de dados. O objeto de dados no JSON será uma lista de matriz contendo dados das colunas selecionadas de cada linha da tabela de transição de entrada.

The **customize parameter** text box lets you add a valid JSON with additional data needed by the external API. Esses dados adicionais serão adicionados ao objeto params no JSON gerado.

### Mapeamento de saída

This tab lets you define the sample **JSON structure** returned by the API Call.

![](assets/externalAPI-outbound.png)

The JSON structure pattern is: **{“data”:[{“key”:“value”}, {“key”:“value”},...]}**

The sample JSON definition must have the **following characteristics**:

* **é** um nome de propriedade obrigatório no JSON, o conteúdo de "dados" é uma matriz JSON.
* **Os elementos** de matriz devem conter propriedades de primeiro nível (os níveis mais profundos não são suportados).
   **Nomes de propriedade** terminariam se tornassem nomes de colunas para o esquema de saída da tabela temporária de saída.
* **A definição do nome** da coluna baseia-se no primeiro elemento da matriz de "dados".
Columns definition (add/remove) and the type value of the property can be edited in the **Column definition** tab.

If the **parsing is validated** a message appears and invite you to customize the data mapping in the "Column definition" tab. Em outros casos, uma mensagem de erro é exibida.

### Execução

This tab lets you define the **HTTPS Endpoint** that will send data to ACS. If needed, you can enter authentication information in the fields below.
![](assets/externalAPI-execution.png)

### Propriedades

This tab lets you control **general properties** on the external API activity like the displayed label in the UI. A ID interna não é personalizável.

![](assets/externalAPI-properties.png)

### Definição de coluna

    &gt; [! OBSERVAÇÃO]
    &gt;
    &gt; Esta guia aparece quando o formato** de dados de resposta** é concluído e validado na guia Mapeamento de saída.

The **Column definition** tab allows you to precisely specify the data structure of each column in order to import data that does not contain any errors and make it match the types that are already present in the Adobe Campaign database for future operations.

![](assets/externalAPI-column.png)

Por exemplo, é possível alterar o rótulo de uma coluna, selecionar o tipo (sequência, número inteiro, data etc.)ou até mesmo especificar o processamento de erros.

For more information, refer to the [Load File](../../automating/using/load-file.md) section.

### Transição

This tab lets you activate the **outbound transition** and its label. This specific transition is useful in case of **timeout** or if the payload exceed the **data size limit**.

![](assets/externalAPI-transition.png)

### Opções de execução

Essa guia está disponível na maioria das atividades do fluxo de trabalho. For more information, consult the [Activity properties](../../automating/using/executing-a-workflow.md#activity-properties) section.

![](assets/externalAPI-options.png)

<!--
## Example: Managing coupons with External API Activity

This example illustrates how to **add coupon value** retrieving by a REST call to profiles and then sending an email containing these coupon values.

The workflow is presented as follows:

![](assets/externalAPI_activity_example1.png)

1. Drag and drop an **External API** activity
    1. Parse the JSON sample responsa as {"data":[{"code":"value"}]}.
    1. Add the **Rest endpoint URL** and define authentication setting if needed
    ![](assets/externalAPI_activity_example2.png)
    1. In the **column definition** tab, add a new column called **code** that will store the code value.
        ![](assets/externalAPI_activity_example3.png)
    1. Enabled an **outbound transition** to manage request failures.
1. Drag and drop a **Query** activity
    1. Configure the **Target** tab to query all the **@adobe.com** email. For different Query samples, refer to the [Query](../../automating/using/query.md) section.
    1. In the **additional data** tab, add a new column based on **rowId()** function. This additional column allows you to reconciliate coupon code with the profile ID..
        ![](assets/externalAPI_activity_example4.png)

        >[!NOTE]
        >
        >This reconciliation approach means that the profile query number is equal to the number of coupon values returned by the REST call.
1. Once this two activities are configured, drag and drop an **Enrichment** activity to associate coupon values with profiles.
    1. Select the previous Query activity in the **primarySet** field.
        ![](assets/externalAPI_activity_example5.png)
    1. Create a new relation in the **Advanced relations** tab, and add the following reconciliation criteria:
    1. **@expr1** coming grom the Query activity in the source expression field.
    1. **@lineNum** as an expression that returns the line number for each coupon value in the destination field.
        ![](assets/externalAPI_activity_example6.png)
        More information on the enrichment activity are available [here](../../automating/using/enrichment.md)

    1. The transition **Data Structure** will contain:
        ![](assets/externalAPI_activity_example7.png)
1. Finally drag and drop a **Send via Email** activity.
    You can modify your email template by adding the **code** personnalized field.

-->
