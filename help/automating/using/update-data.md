---
solution: Campaign Standard
product: campaign
title: Atualização de dados
description: A atividade Update data permite executar uma atualização em massa nos campos no banco de dados.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: writer,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 98%

---


# Atualização de dados{#update-data}

## Descrição {#description}

![](assets/data_update.png)

A atividade **[!UICONTROL Update data]** permite executar uma atualização em massa nos campos no banco de dados.

## Contexto de uso {#context-of-use}

A atividade **Update data** pode ser usada após a importação de um arquivo para inserir os dados recuperados no banco de dados do Adobe Campaign. Várias opções permitem que você personalize a atualização dos dados.

**Tópicos relacionados:**

* [Caso de uso: Atualização de dados com base em um arquivo](../../automating/using/update-database-file.md)
* [Atualização de dados com base em um download automático de arquivo](../../automating/using/update-data-automatic-download.md)

## Configuração {#configuration}

1. Arraste e solte uma atividade **[!UICONTROL Update data]** no seu workflow.
1. Selecione e abra a atividade usando o botão ![](assets/edit_darkgrey-24px.png) das ações rápidas exibidas.
1. Especificar o **[!UICONTROL Operation type]** que será executado:

   * **[!UICONTROL Insert or update]**: inserir dados ou atualizá-los se já existirem registros no banco de dados.
   * **[!UICONTROL Insert only]**: inserir somente dados. Os registros que já existem não são atualizados. Se os critérios de reconciliação forem definidos, somente os registros não reconciliados serão adicionados.

      Marque a caixa **[!UICONTROL Generate an outbound transition for rejects]** se os dados importados contiverem determinados registros que já existem no banco de dados para evitar possíveis erros.

   * **[!UICONTROL Update]**: atualizar os dados dos registros que já existem somente no banco de dados.
   * **[!UICONTROL Delete]**: excluir dados.

   >[!NOTE]
   >
   >O campo **[!UICONTROL Batch size]** permite definir o tamanho máximo do lote para os dados dos quais se fará upload.

1. Na guia **[!UICONTROL Identification]**, especifique como identificar os registros no banco de dados:

   * **[!UICONTROL Using the targeting dimension]**: selecione a **[!UICONTROL Dimension to update]** e especifique as **[!UICONTROL Keys for finding records]**. Para mais informações, consulte [Targeting dimensions e recursos](../../automating/using/query.md#targeting-dimensions-and-resources).
   * Se os dados digitados corresponderem a um targeting dimension existente, selecione a opção **[!UICONTROL Using one or more links]**. Em seguida, selecione a **[!UICONTROL Dimension to update]**.

   Se o tipo de operação selecionado exigir uma atualização, você precisará usar chaves de reconciliação.

1. Na guia **[!UICONTROL Fields to update]**, especifique os campos nos quais a atualização será aplicada e, se necessário, adicione condições para que essa atualização seja realizada. Para isso, use a coluna **[!UICONTROL Taken into account if]**. As condições são aplicadas uma após a outra em ordem de lista. Use as setas à direita para alterar a ordem das atualizações. É possível usar o mesmo campo de destino várias vezes.

   É possível vincular campos automaticamente usando o botão ![](assets/wkf_magic_wand-24px.png). A vinculação automática detecta campos com o mesmo nome.

   Durante uma operação do tipo **[!UICONTROL Insert or update]**, você pode selecionar individualmente a operação a ser aplicada para cada campo. Para fazer isso, selecione o valor desejado na coluna **[!UICONTROL Operation]**.

   >[!NOTE]
   >
   >**Gerenciamento de atualizações** Os campos **[!UICONTROL lastModified]**, **[!UICONTROL modifiedBy]**, **[!UICONTROL created]** e **[!UICONTROL createdBy]** são atualizados automaticamente quando uma atividade de atualização de dados é executada, a menos que a configuração de cada um deles seja explicitamente executada na tabela de atualização de campo. A atualização só é efetuada nos registros em que tenha sido detectada pelo menos uma diferença. Se os valores forem iguais, nenhuma atualização será executada.

1. Se necessário, gerencie as [Transições](../../automating/using/activity-properties.md) de atividade para acessar as opções avançadas para a população de saída.

   Se você tiver selecionado **[!UICONTROL Insert only]** e os dados importados tiverem registros que já estão presentes no banco de dados, marque a caixa **[!UICONTROL Generate an outbound transition for the rejects]** para evitar possíveis erros.

1. Confirme a configuração da sua atividade e salve o fluxo de trabalho.
