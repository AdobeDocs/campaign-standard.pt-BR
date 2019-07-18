---
title: Desduplicação
seo-title: Desduplicação
description: Desduplicação
seo-description: A atividade de desduplicação permite que você exclua duplicatas nos resultados das atividades de entrada.
page-status-flag: nunca ativado
uuid: 11 a 22 a 9 c -3 bfe -4953-8 a 52-2 f 4 e 93 c 128 fb
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizando
content-type: reference
topic-tags: atividades de definição de metas
discoiquuid: e 7 a 5 e 1 e 7-4680-46 c 7-98 b 8-0 a 47 bb 7 be 2 b 8
context-tags: dedup, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Deduplication{#deduplication}

## Description {#description}

![](assets/deduplication.png)

The **[!UICONTROL Deduplication]** activity allows you to delete duplicates in the result(s) of the inbound activities.

## Context of use {#context-of-use}

The **[!UICONTROL Deduplication]** activity is generally used following targeting activities or after importing a file and before activities that allow the use of targeted data.

Durante a desduplicação, as transições de entrada são processadas separadamente. Por exemplo, se o perfil "A" estiver presente em resultado de consulta 1 e também no resultado da consulta 2, ele não será desduplicado.

Portanto, é recomendável que uma desduplicação tenha apenas uma transição de entrada. Para fazer isso, você pode combinar consultas diferentes usando atividades que correspondem às necessidades de direcionamento, como atividade da união, atividade de interseção etc. Por exemplo:

![](assets/dedup_bonnepratique.png)

## Configuration {#configuration}

Para configurar uma atividade de desduplicação, você deve inserir um rótulo, o método e os critérios de desduplicação, bem como as opções relacionadas ao resultado.

1. Drag and drop a **[!UICONTROL Deduplication]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.

   ![](assets/deduplication_1.png)

1. Select the **[!UICONTROL Resource type]** on which the deduplication has to be carried out:

   * **[!UICONTROL Database resource]** se a deduplicação for realizada em dados que já existem no banco de dados. Select the **[!UICONTROL Filtering dimension]** and the **[!UICONTROL Targeting dimension]**, depending on the data that you want to deduplicate. By default, deduplication is carried out on the **profiles**.
   * **[!UICONTROL Temporary resource]** se a deduplicação for realizada nos dados temporários do fluxo de trabalho: selecione os **[!UICONTROL Targeted set]** dados a serem desduplicados. Esse caso de uso pode ser encontrado após a importação de um arquivo ou se os dados no banco de dados tiverem sido aprimorados (com um código de segmento, por exemplo).

1. Select the **[!UICONTROL Number of unique records to keep]**. O valor padrão desse campo é 1. O valor 0 permite manter todas as duplicatas.

   Por exemplo, se os registros A e B forem considerados duplicatas de registro Y, e um registro C for considerado como uma duplicata de registro Z:

   * Se o valor do campo for 1: somente os registros Y e Z são mantidos.
   * Se o valor do campo for 0: todos os registros são mantidos.
   * Se o valor do campo for 2: registros C e Z são mantidos e dois registros de A, B e Y são mantidos por acaso ou dependendo do método de desduplicação selecionado depois.

1. Define the **[!UICONTROL Duplicate identification]** criteria by adding conditions in the list provided. Especifique os campos e/ou expressões para os quais os valores idênticos permitem identificar as duplicatas: endereço de e-mail, nome, sobrenome etc. A ordem das condições permite que você especifique os que serão processados primeiro.
1. In the drop-down list, select the **[!UICONTROL Deduplication method]** to use:

   * **[!UICONTROL Choose for me]**: seleciona aleatoriamente o registro a ser mantido fora das duplicatas.
   * **[!UICONTROL Following a list of values]**: permite definir uma prioridade de valor para um ou mais campos. Para definir os valores, selecione um campo ou crie uma expressão e adicione os valores à tabela apropriada. To define a new field, click the **[!UICONTROL Add]** button located above the list of values.

      ![](assets/deduplication_2.png)

   * **[!UICONTROL Non-empty value]**: isso permite manter registros para os quais o valor da expressão selecionada não está vazio como uma prioridade.

      ![](assets/deduplication_3.png)

   * **[!UICONTROL Using an expression]**: isso permite manter os registros nos quais o valor da expressão inserida é o menor ou o maior.

      ![](assets/deduplication_4.png)

1. If needed, manage the activity's [Transitions](../../automating/using/executing-a-workflow.md#managing-an-activity-s-outbound-transitions) to access the advanced options for the outbound population.
1. Confirme a configuração da atividade e salve seu fluxo de trabalho.

## Example 1: Identifying duplicates before a delivery {#example-1--identifying-duplicates-before-a-delivery}

O exemplo a seguir ilustra uma desduplicação que permite excluir as duplicatas de uma meta antes de enviar um e-mail. Isso significa que você evita enviar uma comunicação várias vezes para o mesmo perfil.

O fluxo de trabalho é composto por:

![](assets/deduplication_example_workflow.png)

* A **[!UICONTROL Query]** which allows you to define the target of the email. Aqui, o fluxo de trabalho direciona todos os perfis entre 18 e 25 que estiveram no banco de dados cliente por mais de um ano.

   ![](assets/deduplication_example_query.png)

* **[!UICONTROL Deduplication]** Uma atividade, que permite identificar as duplicatas provenientes da consulta anterior. Neste exemplo, apenas um registro é salvo para cada duplicada. As duplicatas são identificadas usando o endereço de email. Isso significa que a entrega por email só pode ser enviada uma vez para cada endereço de email estar presente na definição de metas.

   The deduplication method selected is **[!UICONTROL Non-empty value]**. This allows you to ensure that amongst the records kept in case of duplicates, priority is given to those in which the **First name** has been provided. Isso tornará isso mais consistente se o primeiro nome for usado nos campos de personalização do conteúdo de email.

   Além disso, uma transição extra é adicionada para manter as duplicatas e poder listá-las.

   ![](assets/deduplication_example_dedup.png)

* An **[!UICONTROL Email delivery]** placed after the main outbound transition of the deduplication. The configuration for email deliveries is detailed in the [Email delivery](../../automating/using/email-delivery.md) section.
* A **[!UICONTROL Save audience]** activity placed after the additional transition of the deduplication to save the duplicates in a **Duplicates** audience. Esse público pode ser reutilizado para excluir diretamente seus membros de cada entrega de email.

## Example 2: Deduplicating the data from an imported file {#example-2--deduplicating-the-data-from-an-imported-file}

Este exemplo mostra como desduplicar dados de um arquivo importado antes de carregar os dados no banco de dados. Esse procedimento melhora a qualidade dos dados carregados no banco de dados.

O fluxo de trabalho é composto por:

![](assets/deduplication_example2_workflow.png)

* A file that contains a list of profiles is imported using a **[!UICONTROL Load file]** activity. Neste exemplo, o arquivo importado está no formato. csv e contém 10 perfis:

   ```
   lastname;firstname;dateofbirth;email
   Smith;Hayden;23/05/1989;hayden.smith@example.com
   Mars;Daniel;17/11/1987;dannymars@example.com
   Smith;Clara;08/02/1989;hayden.smith@example.com
   Durance;Allison;15/12/1978;allison.durance@example.com
   Lucassen;Jody;28/03/1988;jody.lucassen@example.com
   Binder;Tom;19/01/1982;tombinder@example.com
   Binder;Tommy;19/01/1915;tombinder@example.com
   Connor;Jade;10/10/1979;connor.jade@example.com
   Mack;Clarke;02/03/1985;clarke.mack@example.com
   Ross;Timothy;04/07/1986;timross@example.com
   ```

   Esse arquivo também pode ser usado como um arquivo de amostra para detectar e definir o formato das colunas. From the **[!UICONTROL Column definition]** tab, make sure that each column of the imported file is configured correctly.

   ![](assets/deduplication_example2_fileloading.png)

* A **[!UICONTROL Deduplication]** activity. A desduplicação é realizada diretamente após a importação do arquivo e antes de inserir os dados no banco de dados. It should therefore be based on the **[!UICONTROL Temporary resource]** from the **[!UICONTROL Load file]** activity.

   Para esse exemplo, queremos manter uma única entrada por endereço de email exclusivo contido no arquivo. Duplicate identification is therefore carried out on the **email** column of the temporary resource. No entanto, dois endereços de email aparecem duas vezes no arquivo. Duas linhas serão consideradas como duplicatas.

   ![](assets/deduplication_example2_dedup.png)

* An **[!UICONTROL Update data]** activity allows you to insert the data kept from the deduplication process into the database. Somente quando os dados são atualizados, os dados importados são identificados como pertencendo à dimensão do perfil.

   Here, we would like to **[!UICONTROL Insert only]** the profiles that do not already exist in the database. We are going to do this by using the file's email column and the email field from the **Profile** dimension as the reconciliation key.

   ![](assets/deduplication_example2_writer1.png)

   Specify the mappings between the file's columns from which you want to insert the data and the database fields from the **[!UICONTROL Fields to update]** tab.

   ![](assets/deduplication_example2_writer2.png)

Em seguida, inicie o fluxo de trabalho. Os registros salvos do processo de desduplicação são então adicionados aos perfis no banco de dados.
