---
solution: Campaign Standard
product: campaign
title: Introdução a processos e gerenciamento de dados
description: Automatize processos com workflows, gerencie dados e públicos, envie mensagens e muito mais.
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
feature: Fluxos de trabalho
role: Arquiteto de dados
level: Iniciante
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 13%

---


# Introdução a processos e gerenciamento de dados {#get-started-processes-data-management}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#workflow-activities">Atividades de workflow</a></p></td><td><img src="assets/do-not-localize/icon_activities.svg" width="60px"><p><a href="../../automating/using/workflow-created-query-with-complement.md">Casos de uso</a></p></td><td><img src="assets/do-not-localize/icon_filter.svg" width="60px"><p><a href="#filter-data">Filtrar dados</a></p></td>
<td><img src="assets/do-not-localize/icon_manage.svg" width="60px"><p><a href="#import-export-data">Importar/exportar dados</a></p></td></tr>
</table>

O Adobe Campaign oferece um ambiente gráfico abrangente que permite projetar processos complexos, incluindo segmentação, execução de campanha, processamento de arquivos etc. Por exemplo, você pode usar um workflow para baixar um arquivo de um servidor, descompactá-lo e importar seus registros para o banco de dados do Adobe Campaign.

Um workflow também pode envolver usuários atribuindo tarefas ou fazendo com que eles aprovem tarefas realizadas. Isso significa que é possível atribuir uma tarefa a um ou vários usuários para trabalhar no conteúdo ou especificar alvos e aprovar provas antes de enviar a mensagem.

Os workflows podem ser usados em contextos diferentes, como por exemplo:

* Direcionamento para gerenciar públicos-alvo ou enviar mensagens.
* Gestão de dados (ETL) para manipular dados.
* Importação de dados para o banco de dados do Campaign.
* Processos técnicos, como limpeza do banco de dados, recuperação de informações de rastreamento etc.

## Atividades do workflow {#workflow-activities}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

Várias atividades estão disponíveis para ajudar você a projetar seus fluxos de trabalho.

[As ](../../automating/using/about-targeting-activities.md) atividades de direcionamento permitem criar um ou mais targets definindo conjuntos e dividindo ou combinando esses conjuntos usando operações de interseção, união ou exclusão.

Com [Execution activities](../../automating/using/about-execution-activities.md), coordene seu workflow e suas atividades, enquanto [Channel activities](../../automating/using/about-channel-activities.md) permitem combinar canais de comunicação do Campaign Standard para criar workflows entre canais.

Por fim, [Data management activities](../../automating/using/about-data-management-activities.md) permitem manipular dados do banco de dados.

Leia mais:

* [Criação de um workflow](../../automating/using/building-a-workflow.md)
* [Execução de um fluxo de trabalho](../../automating/using/about-workflow-execution.md)
* [Práticas recomendadas do fluxo de trabalho](../../automating/using/best-practices-workflows.md)

## Filtrar dados {#filter-data}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

Aproveite o **Editor de consultas** para filtrar dados do seu banco de dados e criar uma população para direcionar melhor seus recipients. O Editor de consultas está disponível para executar várias ações no Campaign Standard: crie públicos do tipo Query , defina targets de delivery ou populações em atividades de workflow.

O Editor de consultas vem com **filtros e regras predefinidos** para filtragem rápida e fácil. No entanto, também é possível usar os recursos de **edição de expressão avançada**. Isso permite inserir condições manualmente e usar funções para formar suas próprias regras.

Leia mais:

* [Edição de consultas](../../automating/using/editing-queries.md)
* [Edição de expressão avançada](../../automating/using/advanced-expression-editing.md)
* [Lista de funções](../../automating/using/list-of-functions.md)

## Importar/exportar dados {#import-export-data}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

O Campaign Standard vem com vários **data management capabilities** para importar e exportar dados.

[As ](../../automating/using/about-data-management-activities.md) atividades de gerenciamento de dados de fluxos de trabalho permitem importar dados, executar atualizações em massa nos campos, receber ou enviar arquivos ou vincular dados não identificados aos recursos existentes.

Com [Importar templates](../../automating/using/importing-data-with-import-templates.md), gerencie determinados tipos de importação definidos pelos administradores por meio de funções de importação simplificadas.

[Ao exportar ](../../automating/using/exporting-logs.md) a planilha, você exporta dados de log por meio de um fluxo de trabalho simples, o que permite analisar os resultados de suas campanhas de marketing em seus próprios relatórios ou ferramentas de BI.

Utilize [Pacotes](../../automating/using/managing-packages.md) para trocar recursos entre diferentes instâncias de campanha, por exemplo, para replicar a configuração de uma instância ou para transferir dados de um servidor para outro incluindo recursos personalizados.

Finalmente, [Exportar listas](../../automating/using/exporting-lists.md) permite exportar qualquer lista do Campaign Standard como, por exemplo, a lista de perfis de teste, a lista de endereços de email em quarentena, etc.

Leia mais:

* [Importação e exportação de dados](../../automating/using/about-data-import-and-export.md)
* [Caso de uso: exportação / importação de recursos personalizados](../../automating/using/exporting-importing-custom-resources.md)

## Recursos adicionais

* [Vídeos tutoriais sobre processos e gerenciamento de dados](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/getting-started/create-workflow.html)
* [Workflows técnicos](../../administration/using/technical-workflows.md)
* [Introdução ao modelo de dados do Campaign Standard](../../developing/using/get-started-data-model.md)
