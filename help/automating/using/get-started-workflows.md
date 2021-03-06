---
title: Introdução a processos e gerenciamento de dados
description: Automatize processos com workflows, gerencie dados e públicos, envie mensagens e muito mais.
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
feature: Workflows
role: Data Architect
level: Beginner
exl-id: 26be942a-c252-458f-a590-eb235567ca67
source-git-commit: 6ca3ffe3ba2cf7629e511e4ba035b170b25ad79e
workflow-type: tm+mt
source-wordcount: '553'
ht-degree: 38%

---

# Introdução a processos e gerenciamento de dados {#get-started-processes-data-management}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#workflow-activities">Atividades de fluxos de trabalho</a></p></td><td><img src="assets/do-not-localize/icon_activities.svg" width="60px"><p><a href="../../automating/using/workflow-created-query-with-complement.md">Casos de uso</a></p></td><td><img src="assets/do-not-localize/icon_filter.svg" width="60px"><p><a href="#filter-data">Filtrar dados</a></p></td>
<td><img src="assets/do-not-localize/icon_manage.svg" width="60px"><p><a href="#import-export-data">Importar/exportar dados</a></p></td></tr>
</table>

O Adobe Campaign oferece um ambiente gráfico abrangente que permite projetar processos complexos, incluindo segmentação, execução de campanha, processamento de arquivos etc. Você pode usar um fluxo de trabalho, por exemplo, para baixar um arquivo de um servidor, descompactá-lo e importar seus registros no banco de dados do Adobe Campaign.

Um fluxo de trabalho também pode envolver usuários atribuindo tarefas ou fazendo com que eles aprovem tarefas realizadas. Isso significa que é possível atribuir uma tarefa a um ou vários usuários para trabalhar no conteúdo ou especificar alvos e aprovar provas antes de enviar a mensagem.

Os workflows podem ser usados em contextos diferentes, por exemplo:

* Direcionamento para gerenciar públicos ou enviar mensagens.
* Gerenciamento de dados (ETL) para manipular dados.
* Importação de dados para o banco de dados do Campaign.
* Processos técnicos, como limpeza do banco de dados, recuperação de informações de rastreamento etc.

>[!IMPORTANT]
>
> O Adobe recomenda que os clientes não executem mais de 20 workflows ativos simultaneamente e priorizem e distribuam a execução do workflow ao longo do tempo. Para obter mais informações, consulte as práticas recomendadas fornecidas em [esta página](../../automating/using/best-practices-workflows.md).

## Atividades de fluxos de trabalho {#workflow-activities}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

Várias atividades estão disponíveis para ajudar você a projetar seus fluxos de trabalho.

[Atividades de direcionamento](../../automating/using/about-targeting-activities.md) permite criar um ou mais targets definindo conjuntos e dividindo ou combinando esses conjuntos usando operações de interseção, união ou exclusão.

Com [Atividades de execução](../../automating/using/about-execution-activities.md)coordene seu fluxo de trabalho e suas atividades enquanto [Atividades de canal](../../automating/using/about-channel-activities.md) permite combinar canais de comunicação do Campaign Standard para criar fluxos de trabalho entre canais.

Por último, [Atividades de gestão de dados](../../automating/using/about-data-management-activities.md) permitem manipular dados do banco de dados.

Leia mais:

* [Criação de um workflow](../../automating/using/building-a-workflow.md)
* [Execução de um fluxo de trabalho](../../automating/using/about-workflow-execution.md)
* [Práticas recomendadas de fluxo de trabalho](../../automating/using/best-practices-workflows.md)

## Filtrar dados {#filter-data}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

Aproveite a **editor de consultas** para filtrar dados do banco de dados e criar uma população para direcionar melhor seus recipients. O Editor de consultas está disponível para executar várias ações no Campaign Standard: crie públicos do tipo Query , defina targets de delivery ou populações em atividades de workflow.

O Editor de consultas vem com **filtros e regras predefinidos** para filtragem rápida e fácil. No entanto, também é possível usar **edição de expressão avançada** recursos. Isso permite inserir condições manualmente e usar funções, para formar suas próprias regras.

Leia mais:

* [Edição de consultas](../../automating/using/editing-queries.md)
* [Edição de expressão avançada](../../automating/using/advanced-expression-editing.md)
* [Lista de funções](../../automating/using/list-of-functions.md)

## Importar/exportar dados {#import-export-data}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

Campaign Standard vem com vários **recursos de gerenciamento de dados** para importar e exportar dados.

[Atividades de gestão de dados de fluxos de trabalho](../../automating/using/about-data-management-activities.md) permite importar dados, executar atualizações em massa nos campos, receber ou enviar arquivo ou vincular dados não identificados aos recursos existentes.

Com [Importar modelos](../../automating/using/importing-data-with-import-templates.md), gerencie determinados tipos de importação definidos pelos administradores por meio de funções de importação simplificadas.

[Exportar logs](../../automating/using/exporting-logs.md) permite exportar dados de log por meio de um fluxo de trabalho simples, permitindo analisar os resultados de suas campanhas de marketing em seus próprios relatórios ou ferramentas de BI.

Aproveitamento [Pacotes](../../automating/using/managing-packages.md) para trocar recursos entre diferentes instâncias de campanha, por exemplo, para replicar a configuração de uma instância ou para transferir dados de um servidor para outro, incluindo recursos personalizados.

Por último, [Exportar listas](../../automating/using/exporting-lists.md) permite exportar qualquer lista do Campaign Standard, como, por exemplo, a lista de perfis de teste, a lista de endereços de email em quarentena, etc.

Leia mais:

* [Importação e exportação de dados](../../automating/using/about-data-import-and-export.md)
* [Caso de uso: exportação/importação de recursos personalizados](../../automating/using/exporting-importing-custom-resources.md)

## Recursos adicionais

* [Vídeos tutoriais sobre processos e gerenciamento de dados](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/managing-processes-and-data/creating-a-workflow.html?lang=pt-BR)
* [Workflows técnicos](../../administration/using/technical-workflows.md)
* [Introdução ao modelo de dados do Campaign Standard](../../developing/using/get-started-data-model.md)
