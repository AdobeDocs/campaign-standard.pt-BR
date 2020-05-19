---
title: Atualizar dados
description: A atividade Atualizar dados permite executar uma atualização em massa nos campos do banco de dados.
page-status-flag: never-activated
uuid: 1dc55db5-affd-4688-b673-adfb8c1338b5
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: 4db83c95-4b75-4a16-8dbf-bd8940431fa9
context-tags: writer,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 21faea89b3b38f3e667ed6c4de0be6d07f0b7197
workflow-type: tm+mt
source-wordcount: '517'
ht-degree: 1%

---


# Atualizar dados{#update-data}

## Descrição {#description}

![](assets/data_update.png)

A **[!UICONTROL Update data]** atividade permite executar uma atualização em massa nos campos no banco de dados.

## Contexto de utilização {#context-of-use}

A atividade de dados **** Update pode ser usada após a importação de um arquivo para inserir os dados recuperados no banco de dados Adobe Campaign. Várias opções permitem que você personalize a atualização dos dados.

## Configuração {#configuration}

1. Arraste e solte uma **[!UICONTROL Update data]** atividade no seu fluxo de trabalho.
1. Selecione a atividade e abra-a usando o ![](assets/edit_darkgrey-24px.png) botão das ações rápidas que aparecem.
1. Especificar as modalidades **[!UICONTROL Operation type]** de execução:

   * **[!UICONTROL Insert or update]**: insira os dados ou atualize-os se já existirem registros no banco de dados.
   * **[!UICONTROL Insert only]**: inserir apenas dados. Os registros que já existem não são atualizados. Se os critérios de reconciliação forem definidos, somente os registros não reconciliados serão adicionados.

      Marque a **[!UICONTROL Generate an outbound transition for rejects]** caixa se os dados importados contêm determinados registros que já existem no banco de dados para evitar possíveis erros.

   * **[!UICONTROL Update]**: atualize os dados dos registros que já existem somente no banco de dados.
   * **[!UICONTROL Delete]**: excluir dados.
   >[!NOTE]
   >
   >O **[!UICONTROL Batch size]** campo permite definir o tamanho máximo do lote para os dados a serem carregados.

1. Na **[!UICONTROL Identification]** guia, especifique como identificar os registros no banco de dados:

   * **[!UICONTROL Using the targeting dimension]**: selecione o **[!UICONTROL Dimension to update]** e especifique o **[!UICONTROL Keys for finding records]**. Para obter mais informações, consulte [Targeting dimension e recursos](../../automating/using/query.md#targeting-dimensions-and-resources).
   * Se os dados digitados corresponderem a um targeting dimension existente, selecione a **[!UICONTROL Using one or more links]** opção. Em seguida, selecione o **[!UICONTROL Dimension to update]**.
   Se o tipo de operação selecionado exigir uma atualização, você deverá usar o chave de reconciliação.

1. Na **[!UICONTROL Fields to update]** guia, especifique os campos nos quais a atualização será aplicada e, se necessário, adicione condições para que essa atualização seja realizada. To do this, use the **[!UICONTROL Taken into account if]** column. As condições são aplicadas uma após a outra em ordem de lista. Use as setas à direita para alterar a ordem das atualizações. Você pode usar o mesmo campo de destino várias vezes.

   É possível vincular campos automaticamente usando o ![](assets/wkf_magic_wand-24px.png) botão. A vinculação automática detecta campos com o mesmo nome.

   Durante uma operação de **[!UICONTROL Insert or update]** tipo, você pode selecionar individualmente a operação a ser aplicada para cada campo. Para fazer isso, selecione o valor desejado na **[!UICONTROL Operation]** coluna.

   >[!NOTE]
   >
   >**Gerenciando atualizações** Os campos **[!UICONTROL lastModified]**, **[!UICONTROL modifiedBy]** e **[!UICONTROL created]** **[!UICONTROL createdBy]** são automaticamente atualizados quando uma atividade de dados de atualização é executada, a menos que sua configuração seja explicitamente executada na tabela de atualização de campo. A atualização só é efetuada nos registros em que tenha sido detectada pelo menos uma diferença. Se os valores forem os mesmos, nenhuma atualização será realizada.

1. Se necessário, gerencie as [Transições](../../automating/using/activity-properties.md) de atividade para acessar as opções avançadas para a população de saída.

   Se você selecionou **[!UICONTROL Insert only]** e os dados importados podem conter registros que já estão presentes no banco de dados, marque a **[!UICONTROL Generate an outbound transition for the rejects]** caixa para evitar possíveis erros.

1. Confirme a configuração da atividade e salve o fluxo de trabalho.

## Exemplo {#example}

A atividade a seguir mostra a configuração de uma **[!UICONTROL Update data]** atividade após uma **[!UICONTROL Load file]** atividade. O objetivo desse fluxo de trabalho é adicionar ou atualizar perfis ao banco de dados do Adobe Campaign com os dados recuperados do arquivo. A chave de reconciliação usada é o endereço de email.

O arquivo carregado é um arquivo de formato **.txt** que contém os seguintes dados de exemplo:

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

A **[!UICONTROL Update data]** atividade é configurada da seguinte maneira:

![](assets/deduplication_example2_writer1.png)

![](assets/deduplication_example2_writer2.png)

