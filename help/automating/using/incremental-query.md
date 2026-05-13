---
title: Consulta incremental
description: A atividade Consulta incremental permite filtrar e extrair uma população de elementos do banco de dados do Adobe Campaign.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: incremental,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 18d6ffc0-cfc3-436e-8f0c-ea9c307541e4
TQID: https://experienceleague.adobe.com/pU8TR9TKVwM7-YcCHkxrSZ07UkBxE652McpBXxIp-Ik
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 614
ht-degree: 94%

---

# Consulta incremental{#incremental-query}

## Descrição {#description}

![](assets/incremental.png)

A atividade **[!UICONTROL Incremental query]** permite filtrar e extrair uma população de elementos do banco de dados do Adobe Campaign. Todas as vezes que essa atividade é executada, os resultados das execuções anteriores são excluídos. Isso permite direcionar somente elementos novos.

Você pode definir **[!UICONTROL Additional data]** para a população direcionada em uma guia dedicada. Esses dados são armazenados em colunas adicionais e só podem ser usados para o fluxo de trabalho em andamento.

A atividade usa a ferramenta Editor de consultas. Essa ferramenta é detalhada em uma [seção dedicada](../../automating/using/editing-queries.md#about-query-editor).

## Contexto de uso {#context-of-use}

Um evento **[!UICONTROL Incremental query]** deve estar vinculado a um evento **[!UICONTROL Scheduler]** para definir a frequência de execução do fluxo de trabalho e, portanto, do query.

A guia **[!UICONTROL Processed data]**, que é específica para essa atividade, permite visualizar os resultados das execuções anteriores da atividade, se necessário.

A atividade **[!UICONTROL Incremental query]** pode ser usada para várias finalidades:

* Segmentação de pessoas para definir o público-alvo ou o público de uma mensagem, etc.

* Exportação de dados.

  Você pode usar uma atividade **[!UICONTROL Incremental query]** para exportar regularmente novos logs em arquivos. Pode ser útil, por exemplo, se você quiser usar seus dados de log em ferramentas externas de BI ou geração de relatórios. Um exemplo completo está disponível na seção [Exportar logs](../../automating/using/exporting-logs.md).

**Tópicos relacionados**

* [Caso de uso: query incremental para assinantes de um serviço](../../automating/using/incremental-query-on-subscribers.md)

## Configuração {#configuration}

1. Arraste e solte uma atividade **[!UICONTROL Incremental query]** no seu fluxo de trabalho.
1. Selecione e abra a atividade usando o botão ![](assets/edit_darkgrey-24px.png) das ações rápidas exibidas.
1. Se você quiser executar uma consulta em um recurso diferente do perfil, vá para a guia **[!UICONTROL Properties]** da atividade e selecione um **[!UICONTROL Resource]** e um **[!UICONTROL Targeting dimension]**.

   O **[!UICONTROL Resource]** permite refinar os filtros exibidos na paleta, enquanto o **[!UICONTROL Targeting dimension]**, contextual em relação ao recurso selecionado, corresponde ao tipo de população que você gostaria de obter (perfis identificados, entregas, dados vinculados ao recurso selecionado, etc.).

1. Na guia **[!UICONTROL Target]**, execute a consulta definindo e combinando regras.
1. Na guia **[!UICONTROL Processed data]**, escolha o modo incremental que deseja usar para as próximas execuções do fluxo de trabalho:

   * **[!UICONTROL Use the exclusion of the results of previous executions]**: os resultados das execuções anteriores para cada nova execução são excluídos.
   * **[!UICONTROL Use a date field]**: as execuções seguintes levarão em conta apenas os resultados que tiverem o campo de data selecionado maior que ou igual à data da última execução da atividade **[!UICONTROL Incremental query]**. Você pode selecionar qualquer campo de data pertencente ao recurso selecionado na guia **[!UICONTROL Properties]**. Esse modo tem melhor desempenho ao consultar recursos grandes, como dados de log.

     Após a primeira execução do fluxo de trabalho, você poderá ver nesta guia a última data de execução que será usada para a próxima execução. Ela é atualizada automaticamente todas as vezes que o fluxo de trabalho é executado. Você ainda tem a possibilidade de substituir esse valor, inserindo manualmente um novo para que ele se ajuste às suas necessidades.

   >[!NOTE]
   >
   >O modo **[!UICONTROL Use a date field]** permite mais flexibilidade dependendo do campo de data selecionado. Por exemplo, se o campo selecionado corresponder a uma data de modificação, o modo de campo de data permitirá recuperar dados que foram atualizados recentemente, enquanto o outro modo simplesmente excluirá gravações que já foram direcionadas para uma execução anterior, mesmo que elas tenham sido modificadas desde a última execução do fluxo de trabalho.

   ![](assets/incremental_query_usedatefield.png)

1. Você pode definir **[!UICONTROL Additional data]** para a população direcionada em uma guia dedicada. Esses dados são armazenados em colunas adicionais e só podem ser usados para o fluxo de trabalho em andamento. Especificamente, você pode adicionar dados das tabelas do banco de dados do Adobe Campaign vinculadas à dimensão de direcionamento da consulta. Consulte a seção [Enriquecimento de dados](../../automating/using/query.md#enriching-data).
1. Confirme a configuração da sua atividade e salve o fluxo de trabalho.

## Enriquecimento de dados {#enriching-data}

Assim como para uma consulta, você pode enriquecer os dados de um **[!UICONTROL Incremental query]**. Consulte a seção [Enriquecimento de dados](../../automating/using/query.md#enriching-data).
