---
title: Consulta incremental
description: A atividade de consulta incremental permite filtrar e extrair um preenchimento de elementos do banco de dados do Adobe Campaign.
page-status-flag: nunca ativado
uuid: 73b42422-e815-43ef-84c0-97c4433ccc98
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: automatização
content-type: referência
topic-tags: atividades de definição de metas
discoiquuid: 80961e73-42ec-463a-8496-cff69fab0475
context-tags: incremental,principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Consulta incremental{#incremental-query}

## Descrição {#description}

![](assets/incremental.png)

A **[!UICONTROL Incremental query]** atividade permite filtrar e extrair um preenchimento de elementos do banco de dados do Adobe Campaign. Cada vez que essa atividade é executada, os resultados das execuções anteriores são excluídos. Isso permite direcionar somente elementos novos.

É possível definir **[!UICONTROL Additional data]** para a população direcionada por meio de uma guia dedicada. Esses dados são armazenados em colunas adicionais e só podem ser usados para o fluxo de trabalho em andamento.

A atividade usa a ferramenta do editor de consultas. Essa ferramenta é detalhada em uma seção [](../../automating/using/editing-queries.md#about-query-editor)dedicada.

## Contexto de utilização {#context-of-use}

Um **[!UICONTROL Incremental query]** deve ser vinculado a um **[!UICONTROL Scheduler]** para definir a frequência de execução do fluxo de trabalho e, portanto, a consulta.

A **[!UICONTROL Processed data]** guia, que é específica para essa atividade, permite exibir quaisquer resultados das execuções anteriores da atividade, se necessário.

A **[!UICONTROL Incremental query]** atividade pode ser usada para vários tipos de usos:

* Segmentação de indivíduos para definir o destino de uma mensagem, público-alvo etc.
* Exportação de dados.

## Configuração {#configuration}

1. Arraste e solte uma **[!UICONTROL Incremental query]** atividade em seu fluxo de trabalho.
1. Selecione a atividade e abra-a usando o ![](assets/edit_darkgrey-24px.png) botão das ações rápidas que aparecem.
1. Se você deseja executar uma consulta em um recurso diferente do recurso de perfil, vá para a **[!UICONTROL Properties]** guia da atividade e selecione um **[!UICONTROL Resource]** e um **[!UICONTROL Targeting dimension]**.

   O **[!UICONTROL Resource]** permite refinar os filtros exibidos na paleta, enquanto o **[!UICONTROL Targeting dimension]**, contextual em relação ao recurso selecionado, corresponde ao tipo de população que você deseja obter (perfis identificados, entregas, dados vinculados ao recurso selecionado etc.).

1. Na **[!UICONTROL Target]** guia, execute sua consulta definindo e combinando regras.
1. Na **[!UICONTROL Processed data]** guia, escolha o modo incremental que deseja usar para as próximas execuções do fluxo de trabalho:

   * **[!UICONTROL Use the exclusion of the results of previous executions]**: os resultados das execuções anteriores para cada nova execução são excluídos.
   * **[!UICONTROL Use a date field]**: as execuções seguintes levam em conta apenas os resultados que tiverem o campo de data selecionado maior ou igual à data da última execução da **[!UICONTROL Incremental query]** atividade. Você pode selecionar qualquer campo de data pertencente ao recurso selecionado na **[!UICONTROL Properties]** guia. Esse modo tem melhor desempenho ao consultar grandes recursos, como dados de log.

      Após a primeira execução do fluxo de trabalho, você pode ver nesta guia a última data de execução que será usada para a próxima execução. Ele é atualizado automaticamente toda vez que o fluxo de trabalho é executado. Você ainda tem a possibilidade de substituir esse valor inserindo manualmente um novo para que ele se ajuste às suas necessidades.
   >[!NOTE]
   >
   >O **[!UICONTROL Use a date field]** modo permite mais flexibilidade dependendo do campo de data selecionado. Por exemplo, se o campo selecionado corresponde a uma data de modificação, o modo de campo de data permitirá que você recupere dados que foram atualizados recentemente, enquanto o outro modo simplesmente excluirá gravações que já foram direcionadas para uma execução anterior, mesmo que elas tenham sido modificadas desde a última execução do fluxo de trabalho.

   ![](assets/incremental_query_usedatefield.png)

1. É possível definir **[!UICONTROL Additional data]** para a população direcionada por meio de uma guia dedicada. Esses dados são armazenados em colunas adicionais e só podem ser usados para o fluxo de trabalho em andamento. Em particular, você pode adicionar dados das tabelas de banco de dados do Adobe Campaign vinculadas à dimensão de definição de metas da consulta. Consulte a seção Dados [](../../automating/using/query.md#enriching-data) enriquecedores.
1. Confirme a configuração da atividade e salve o fluxo de trabalho.

## Enriquecimento de dados {#enriching-data}

Assim como para uma consulta, você pode enriquecer os dados de uma **[!UICONTROL Incremental query]**. Consulte a seção Dados [](../../automating/using/query.md#enriching-data) enriquecedores.

## Exemplo: consulta incremental em assinantes de um serviço {#example--incremental-query-on-subscribers-to-a-service}

O exemplo a seguir mostra a configuração de uma **[!UICONTROL Incremental query]** atividade que filtra os perfis no banco de dados do Adobe Campaign que são inscritos no serviço **Running Newsletter** para enviar um email de boas-vindas contendo um código promocional.

O fluxo de trabalho é composto pelos seguintes elementos:

![](assets/incremental_query_example1.png)

* Uma **[!UICONTROL Scheduler]** atividade, para executar o fluxo de trabalho todas as segundas-feiras às 6 horas.

   ![](assets/incremental_query_example2.png)

* Uma **[!UICONTROL Incremental query]** atividade, que direciona todos os assinantes atuais durante a primeira execução, então somente os novos assinantes daquela semana durante as execuções a seguir.

   ![](assets/incremental_query_example3.png)

* Uma **[!UICONTROL Email delivery]** atividade. O fluxo de trabalho é executado uma vez por semana, mas você pode agregar os emails enviados e os resultados por mês, por exemplo, para gerar relatórios durante um período de um mês inteiro e não apenas uma única semana.

   Para fazer isso, escolha criar um **[!UICONTROL Recurring email]** aqui que agrupe os emails e os resultados **[!UICONTROL By month]**.

   Defina o conteúdo de seu email e insira o código promocional de boas-vindas.

   Para obter mais informações, consulte as seções Entrega [de](../../automating/using/email-delivery.md) email e [Definição de conteúdo](../../designing/using/personalization.md) de email.

Em seguida, inicie a execução do fluxo de trabalho. Todas as semanas, os novos assinantes receberão o email de boas-vindas com o código promocional.

## Exemplo: consulta incremental em registros de entrega {#example--incremental-query-on-delivery-logs}

Você pode usar uma **[!UICONTROL Incremental query]** atividade para exportar regularmente novos logs em arquivos. Pode ser útil, por exemplo, se você quiser usar seus dados de log em ferramentas externas de relatórios ou BI.

Um exemplo completo está disponível na seção [Exportar logs](../../automating/using/exporting-logs.md) .
