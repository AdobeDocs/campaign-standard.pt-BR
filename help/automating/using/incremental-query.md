---
title: Consulta incremental
description: A atividade do Query incremental permite filtrar e extrair um preenchimento de elementos do banco de dados do Adobe Campaign.
page-status-flag: never-activated
uuid: 73b42422-e815-43ef-84c0-97c4433ccc98
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 80961e73-42ec-463a-8496-cff69fab0475
context-tags: incremental,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 87e0611fae0560aca276caa3c4cf793e9c095d72
workflow-type: tm+mt
source-wordcount: '614'
ht-degree: 1%

---


# Consulta incremental{#incremental-query}

## Descrição {#description}

![](assets/incremental.png)

A **[!UICONTROL Incremental query]** atividade permite filtrar e extrair um preenchimento de elementos do banco de dados do Adobe Campaign. Cada vez que essa atividade é executada, os resultados das execuções anteriores são excluídos. Isso permite que você público alvo somente elementos novos.

É possível definir **[!UICONTROL Additional data]** para a população direcionada por meio de uma guia dedicada. Esses dados são armazenados em colunas adicionais e só podem ser usados para o fluxo de trabalho em andamento.

A atividade usa a ferramenta do editor de query. Essa ferramenta é detalhada em uma seção [](../../automating/using/editing-queries.md#about-query-editor)dedicada.

## Contexto de utilização {#context-of-use}

Um evento **[!UICONTROL Incremental query]** deve estar vinculado a um evento **[!UICONTROL Scheduler]** para definir a frequência de execução do fluxo de trabalho e, portanto, o query.

A **[!UICONTROL Processed data]** guia, que é específica para essa atividade, permite que você visualização os resultados das execuções anteriores da atividade, se necessário.

A **[!UICONTROL Incremental query]** atividade pode ser usada para vários tipos de usos:

* Segmentação de indivíduos para definir o público alvo de uma mensagem, audiência etc.

* Exportação de dados.

   Você pode usar uma **[!UICONTROL Incremental query]** atividade para exportar regularmente novos registros em arquivos. Pode ser útil, por exemplo, se você quiser usar seus dados de log em ferramentas externas de relatórios ou BI. Um exemplo completo está disponível na seção [Exportar logs](../../automating/using/exporting-logs.md) .

**Tópicos relacionados**

* [Caso de uso: Query incremental dos assinantes de um serviço](../../automating/using/incremental-query-on-subscribers.md)

## Configuração {#configuration}

1. Arraste e solte uma **[!UICONTROL Incremental query]** atividade no seu fluxo de trabalho.
1. Selecione a atividade e abra-a usando o ![](assets/edit_darkgrey-24px.png) botão das ações rápidas que aparecem.
1. Se você quiser executar um query em um recurso diferente do perfil, vá para a guia atividade **[!UICONTROL Properties]** e selecione um **[!UICONTROL Resource]** e um **[!UICONTROL Targeting dimension]**.

   O **[!UICONTROL Resource]** permite refinar os filtros exibidos na paleta, enquanto o **[!UICONTROL Targeting dimension]**, contextual em relação ao recurso selecionado, corresponde ao tipo de população que você deseja obter (perfis identificados, delivery, dados vinculados ao recurso selecionado etc.).

1. Na **[!UICONTROL Target]** guia, execute seu query definindo e combinando regras.
1. Na **[!UICONTROL Processed data]** guia, escolha o modo incremental que deseja usar para as próximas execuções do fluxo de trabalho:

   * **[!UICONTROL Use the exclusion of the results of previous executions]**: os resultados das execuções anteriores para cada nova execução são excluídos.
   * **[!UICONTROL Use a date field]**: as execuções seguintes levam em conta apenas os resultados que tiverem o campo de data selecionado maior ou igual à data da última execução da **[!UICONTROL Incremental query]** atividade. Você pode selecionar qualquer campo de data pertencente ao recurso selecionado na **[!UICONTROL Properties]** guia. Esse modo tem melhor desempenho ao consultar grandes recursos, como dados de log.

      Após a primeira execução do fluxo de trabalho, você pode ver nesta guia a última data de execução que será usada para a próxima execução. Ele é atualizado automaticamente toda vez que o fluxo de trabalho é executado. Você ainda tem a possibilidade de substituir esse valor inserindo manualmente um novo para que ele se ajuste às suas necessidades.
   >[!NOTE]
   >
   >O **[!UICONTROL Use a date field]** modo permite mais flexibilidade dependendo do campo de data selecionado. Por exemplo, se o campo selecionado corresponde a uma data de modificação, o modo de campo de data permitirá que você recupere dados que foram atualizados recentemente, enquanto o outro modo simplesmente excluirá gravações que já foram direcionadas para uma execução anterior, mesmo que elas tenham sido modificadas desde a última execução do fluxo de trabalho.

   ![](assets/incremental_query_usedatefield.png)

1. É possível definir **[!UICONTROL Additional data]** para a população direcionada por meio de uma guia dedicada. Esses dados são armazenados em colunas adicionais e só podem ser usados para o fluxo de trabalho em andamento. Em particular, você pode adicionar dados das tabelas de banco de dados do Adobe Campaign vinculadas ao targeting dimension do query. Consulte a seção [Enriquecendo dados](../../automating/using/query.md#enriching-data) .
1. Confirme a configuração da atividade e salve o fluxo de trabalho.

## Enriquecimento de dados {#enriching-data}

Assim como para um query, você pode enriquecer os dados de um **[!UICONTROL Incremental query]**. Consulte a seção [Enriquecendo dados](../../automating/using/query.md#enriching-data) .
