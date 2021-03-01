---
solution: Campaign Standard
product: campaign
title: Introdução a processos e gerenciamento de dados
description: Automatize processos com workflows, gerencie dados e públicos, envie mensagens e muito mais.
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 13%

---


# Introdução a processos e gerenciamento de dados {#get-started-processes-data-management}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#workflow-activities">Atividades de fluxo de trabalho</a></p></td><td><img src="assets/do-not-localize/icon_activities.svg" width="60px"><p><a href="../../automating/using/workflow-created-query-with-complement.md">Casos de uso</a></p></td><td><img src="assets/do-not-localize/icon_filter.svg" width="60px"><p><a href="#filter-data">Filtrar dados</a></p></td>
<td><img src="assets/do-not-localize/icon_manage.svg" width="60px"><p><a href="#import-export-data">Importar/exportar dados</a></p></td></tr>
</table>

A Adobe Campaign oferta um ambiente gráfico abrangente que permite projetar processos complexos, incluindo segmentação, execução de campanhas, processamento de arquivos etc. Por exemplo, você pode usar um workflow para baixar um arquivo de um servidor, descompactá-lo e importar seus registros para o banco de dados do Adobe Campaign.

Um fluxo de trabalho também pode envolver usuários atribuindo tarefas ou fazendo com que eles aprovem tarefas executadas. Isso significa que você pode atribuir uma tarefa a um ou vários usuários para trabalhar com conteúdo ou especificar públicos alvos e aprovar provas antes de enviar a mensagem.

Workflows podem ser usados em contextos diferentes, como por exemplo:

* Definição de metas para gerenciar audiências ou enviar mensagens.
* Gestão de dados (ETL) para manipular dados.
* Importação de dados para o banco de dados de Campanhas.
* Processos técnicos, como limpeza do banco de dados, recuperação de informações de rastreamento etc.

## Atividades de fluxo de trabalho {#workflow-activities}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

Várias atividades estão disponíveis para ajudá-lo a criar seus workflows.

[As ](../../automating/using/about-targeting-activities.md) atividades de direcionamento permitem criar um ou mais targets definindo conjuntos e dividindo ou combinando esses conjuntos usando operações de interseção, união ou exclusão.

Com [atividades de execução](../../automating/using/about-execution-activities.md), coordene seu fluxo de trabalho e suas atividades, enquanto [o Canal atividade](../../automating/using/about-channel-activities.md) permite que você combine canais de comunicação Campaign Standard para criar workflows entre canais.

Finalmente, [o atividade](../../automating/using/about-data-management-activities.md) Gestão de dados permite manipular dados do banco de dados.

Leia mais:

* [Criação de um workflow](../../automating/using/building-a-workflow.md)
* [Execução de um fluxo de trabalho](../../automating/using/about-workflow-execution.md)
* [Práticas recomendadas do fluxo de trabalho](../../automating/using/best-practices-workflows.md)

## Filtrar dados {#filter-data}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

Aproveite o **editor de query** para filtrar dados do banco de dados e criar uma população para melhor público alvo dos recipient. O editor de query está disponível para executar várias ações no Campaign Standard: crie audiências de tipo de Query, defina públicos alvos de delivery ou populações nas atividades de fluxo de trabalho.

O editor de query vem com **filtros predefinidos e regras** para filtragem rápida e fácil. No entanto, você também pode usar os recursos de **edição avançada de expressão**. Isso permite que você insira manualmente as condições e use as funções para formar suas próprias regras.

Leia mais:

* [Edição de consultas](../../automating/using/editing-queries.md)
* [Edição de expressão avançada](../../automating/using/advanced-expression-editing.md)
* [Lista de funções](../../automating/using/list-of-functions.md)

## Importar/exportar dados {#import-export-data}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

O Campaign Standard vem com vários **recursos de gestão de dados** para importar e exportar dados.

[As atividades de gestão de dados de workflows ](../../automating/using/about-data-management-activities.md) permitem importar dados, executar atualizações em massa nos campos, receber ou enviar arquivos ou vincular dados não identificados aos recursos existentes.

Com [Templates de importação](../../automating/using/importing-data-with-import-templates.md), gerencie certos tipos de importação definidos pelos administradores por meio de funções de importação simplificadas.

[Exportar ](../../automating/using/exporting-logs.md) o log-let para exportar dados de log por meio de um fluxo de trabalho simples, permitindo que você analise os resultados das campanhas de marketing em suas próprias ferramentas de relatórios ou BI.

Utilize [Packages](../../automating/using/managing-packages.md) para trocar recursos entre diferentes instâncias de campanha, por exemplo, para replicar a configuração de uma instância ou para transferir dados de um servidor para outro, incluindo recursos personalizados.

Finalmente, [Exportar lista](../../automating/using/exporting-lists.md) permite exportar qualquer lista do Campaign Standard como, por exemplo, a lista de perfis de teste, a lista de endereços de email do quarentena etc.

Leia mais:

* [Importação e exportação de dados](../../automating/using/about-data-import-and-export.md)
* [Caso de uso: exportação / importação de recursos personalizados](../../automating/using/exporting-importing-custom-resources.md)

## Recursos adicionais

* [Vídeos de tutoriais de gestões de dados e processos](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/getting-started/create-workflow.html)
* [Workflows técnicos](../../administration/using/technical-workflows.md)
* [Introdução ao modelo de dados do Campaign Standard](../../developing/using/get-started-data-model.md)
