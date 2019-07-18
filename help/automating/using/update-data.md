---
title: Atualizar dados
seo-title: Atualizar dados
description: Atualizar dados
seo-description: A atividade de dados Atualizar permite executar uma atualização em massa nos campos do banco de dados.
page-status-flag: nunca ativado
uuid: 1 dc 55 db 5-affd -4688-b 673-adfb 8 c 1338 b 5
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizando
content-type: reference
topic-tags: gerenciamento de dados-atividades
discoiquuid: 4 db 83 c 95-4 b 75-4 a 16-8 dbf-bd 8940431 fa 9
context-tags: writer, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Update data{#update-data}

## Description {#description}

![](assets/data_update.png)

The **[!UICONTROL Update data]** activity allows you to perform a mass update on fields in the database.

## Context of use {#context-of-use}

The **Update data** activity can be used after importing a file in order to insert the data recovered into the Adobe Campaign database. Várias opções permitem personalizar a atualização dos dados.

## Configuration {#configuration}

1. Drag and drop an **[!UICONTROL Update data]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Specify the **[!UICONTROL Operation type]** to be carried out:

   * **[!UICONTROL Insert or update]**: inserir dados ou atualizá-los se eles já existirem no banco de dados.
   * **[!UICONTROL Insert only]**: inserir somente dados. Os registros que já existem não são atualizados. Se os critérios de reconciliação forem definidos, apenas os registros não sincronizados serão adicionados.

      Check the **[!UICONTROL Generate an outbound transition for rejects]** box if the data imported contains certain records that already exist in the database to avoid any possible errors.

   * **[!UICONTROL Update]**: atualizar dados dos registros que já existem no banco de dados.
   * **[!UICONTROL Delete]**: excluir dados.
   >[!NOTE]
   >
   >**[!UICONTROL Batch size]** O campo permite que você defina o tamanho máximo do lote para os dados serem carregados.

1. In the **[!UICONTROL Identification]** tab, specify how to identify the records in the database:

   * **[!UICONTROL Using the targeting dimension]**: selecione o **[!UICONTROL Dimension to update]** em seguida especificar o **[!UICONTROL Keys for finding records]**. For more this, refer to [Targeting dimensions and resources](../../automating/using/query.md#targeting-dimensions-and-resources).
   * If the data entered matches an existing targeting dimension, select the **[!UICONTROL Using one or more links]** option. Then select the **[!UICONTROL Dimension to update]**.
   Se o tipo de operação selecionado exigir uma atualização, use as teclas de reconciliação.

1. In the **[!UICONTROL Fields to update]** tab, specify the fields on which the update will be applied and, if necessary, add conditions so that this update is carried out. To do this, use the **[!UICONTROL Taken into account if]** column. As condições são aplicadas uma após a outra na ordem de lista. Use as setas à direita para alterar a ordem das atualizações. É possível usar o mesmo campo de destino várias vezes.

   You can automatically link fields using the ![](assets/wkf_magic_wand-24px.png) button. A vinculação automática detecta campos com o mesmo nome.

   During an **[!UICONTROL Insert or update]** type operation, you can individually select the operation to apply for each field. To do this, select the value you would like in the **[!UICONTROL Operation]** column.

   >[!NOTE]
   >
   >**Gerenciando atualizações** O **[!UICONTROL lastModified]**, **[!UICONTROL modifiedBy]** e **[!UICONTROL created]****[!UICONTROL createdBy]** os campos são atualizados automaticamente quando uma atividade de dados de atualização é executada, a menos que a configuração seja executada explicitamente na tabela de atualização de campo. A atualização só é realizada nos registros onde pelo menos uma diferença foi detectada. Se os valores forem iguais, nenhuma atualização será realizada.

1. If needed, manage the activity's [Transitions](../../automating/using/executing-a-workflow.md#managing-an-activity-s-outbound-transitions) to access the advanced options for the outbound population.

   If you have selected **[!UICONTROL Insert only]** and the data imported may contain records that are already present in the database, check the **[!UICONTROL Generate an outbound transition for the rejects]** box to avoid any possible errors.

1. Confirme a configuração da atividade e salve seu fluxo de trabalho.

## Example {#example}

The following activity shows the configuration of an **[!UICONTROL Update data]** activity following a **[!UICONTROL Load file]** activity. O objetivo deste fluxo de trabalho é adicionar ou atualizar perfis no banco de dados do Adobe Campaign com os dados recuperados do arquivo. A chave de reconciliação usada é o endereço de email.

The file loaded is a **.txt** format file containing the following example data:

```
lastname;firstname;email;birthdate
jackman;megan;megan.jackman@testmail.com;07/08/1975
phillips;edward;phillips@testmail.com;09/03/1986
weaver;justin;justin_w@testmail.com;11/15/1990
martin;babeth;babeth_martin@testmail.net;11/25/1964
reese;richard;rreese@testmail.com;02/08/1987
cage;nathalie;cage.nathalie227@testmail.com;07/03/1989
xiuxiu;andrea;andrea.xiuxiu@testmail.com;09/12/1992
grimes;daryl;daryl_890@testmail.com;12/06/1979
tycoon;tyreese;tyreese_t@testmail.net;10/08/1971
```

**[!UICONTROL Update data]** A atividade é configurada da seguinte maneira:

![](assets/deduplication_example2_writer1.png)

![](assets/deduplication_example2_writer2.png)

