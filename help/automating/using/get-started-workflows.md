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
source-git-commit: 31f62227736daf4f215fcbe1cf7b0a0a8574cda3
workflow-type: tm+mt
source-wordcount: '506'
ht-degree: 30%

---

# Introdução a processos e gerenciamento de dados {#get-started-processes-data-management}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#workflow-activities">Atividades de fluxos de trabalho</a></p></td><td><img src="assets/do-not-localize/icon_activities.svg" width="60px"><p><a href="../../automating/using/workflow-created-query-with-complement.md">Casos de uso</a></p></td><td><img src="assets/do-not-localize/icon_filter.svg" width="60px"><p><a href="#filter-data">Filtrar dados</a></p></td>
<td><img src="assets/do-not-localize/icon_manage.svg" width="60px"><p><a href="#import-export-data">Importar/exportar dados</a></p></td></tr>
</table>

O Adobe Campaign oferece um ambiente gráfico abrangente que permite projetar processos complexos, incluindo segmentação, execução de campanha, processamento de arquivos etc. Você pode usar um fluxo de trabalho, por exemplo, para baixar um arquivo de um servidor, descompactá-lo e importar seus registros no banco de dados do Adobe Campaign.

Os workflows podem ser usados em contextos diferentes, por exemplo:

* Direcionamento para gerenciar públicos-alvo ou enviar mensagens.
* Gerenciamento de dados (ETL) para manipular dados.
* Importação de dados para o banco de dados do Campaign.
* Processos técnicos, como limpeza do banco de dados, recuperação de informações de rastreamento etc.

>[!IMPORTANT]
>
> a Adobe recomenda que os clientes não executem mais de 20 fluxos de trabalho ativos simultaneamente e priorizem e distribuam a execução do fluxo de trabalho ao longo do tempo. Para obter mais informações, consulte as práticas recomendadas fornecidas em [esta página](../../automating/using/best-practices-workflows.md).

## Atividades de fluxos de trabalho {#workflow-activities}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

Várias atividades estão disponíveis para ajudá-lo a projetar seus fluxos de trabalho.

[Atividades de direcionamento](../../automating/using/about-targeting-activities.md) O permite construir um ou mais targets definindo conjuntos e dividindo ou combinando esses conjuntos usando operações de interseção, união ou exclusão.

Com [Atividades de execução](../../automating/using/about-execution-activities.md), coordene o fluxo de trabalho e suas atividades, enquanto [Atividades de canal](../../automating/using/about-channel-activities.md) As permitem combinar canais de comunicação do Campaign Standard para criar workflows entre canais.

Por último, [Atividades de gestão de dados](../../automating/using/about-data-management-activities.md) permite manipular dados do banco de dados.

Leia mais:

* [Criação de um workflow](../../automating/using/building-a-workflow.md)
* [Execução de um fluxo de trabalho](../../automating/using/about-workflow-execution.md)
* [Práticas recomendadas de fluxo de trabalho](../../automating/using/best-practices-workflows.md)

## Filtrar dados {#filter-data}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

Aproveite o **editor de consulta** para filtrar dados do banco de dados e criar uma população para direcionar melhor seus recipients. O editor de consultas está disponível para executar várias ações no Campaign Standard: criar públicos do tipo Query, definir públicos-alvo de entrega ou populações em atividades de fluxo de trabalho.

O Editor de consultas vem com **regras e filtros predefinidos** para uma filtragem rápida e fácil. No entanto, também é possível usar **edição de expressão avançada** recursos. Isso permite inserir condições manualmente e usar funções para formar suas próprias regras.

Leia mais:

* [Edição de consultas](../../automating/using/editing-queries.md)
* [Edição de expressão avançada](../../automating/using/advanced-expression-editing.md)
* [Lista de funções](../../automating/using/list-of-functions.md)

## Importar/exportar dados {#import-export-data}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

Campaign Standard vem com vários **recursos de gerenciamento de dados** para importar e exportar dados.

[Atividades de gerenciamento de dados de workflows](../../automating/using/about-data-management-activities.md) O permite importar dados, executar atualizações em massa nos campos, receber ou enviar arquivos ou vincular dados não identificados aos recursos existentes.

Com [Importar modelos](../../automating/using/importing-data-with-import-templates.md), gerencie determinados tipos de importação definidos por administradores por meio de funções de importação simplificadas.

[Exportação de logs](../../automating/using/exporting-logs.md) permitem exportar dados de log por meio de um fluxo de trabalho simples, permitindo analisar os resultados de suas campanhas de marketing em seus próprios relatórios ou ferramentas de BI.

Aproveitar [Pacotes](../../automating/using/managing-packages.md) para trocar recursos entre diferentes instâncias do campaign, por exemplo, para replicar a configuração de uma instância ou para transferir dados de um servidor para outro, incluindo recursos personalizados.

Por último, [Exportação de listas](../../automating/using/exporting-lists.md) O permite exportar qualquer lista do Campaign Standard, como por exemplo, a lista de perfis de teste, a lista de endereços de email de quarentena etc.

Leia mais:

* [Importação e exportação de dados](../../automating/using/about-data-import-and-export.md)
* [Caso de uso: exportação/importação de recursos personalizados](../../automating/using/exporting-importing-custom-resources.md)

## Recursos adicionais

* [Vídeos tutoriais sobre processos e gerenciamento de dados](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/managing-processes-and-data/creating-a-workflow.html?lang=pt-BR)
* [Workflows técnicos](../../administration/using/technical-workflows.md)
* [Introdução ao modelo de dados do Campaign Standard](../../developing/using/get-started-data-model.md)
