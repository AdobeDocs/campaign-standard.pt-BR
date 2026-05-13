---
title: Introdução a processos e gerenciamento de dados
description: Automatize processos com workflows, gerencie dados e públicos-alvos, envie mensagens e muito mais.
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
feature: Workflows
old-role: Data Architect
role: Developer
level: Beginner
exl-id: 26be942a-c252-458f-a590-eb235567ca67
TQID: https://experienceleague.adobe.com/iTJyQV-76oRhjJ4vDLKfSMpYTA27UcYt9UmVW-9YVq4
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
  - id: a658c786-869b-4194-a780-2594d663adda
subfeature_v2:
  - id: b5f0aaf4-1e48-400d-95ac-6eb3078cf22f
  - id: f5293531-9312-4099-bfa3-9e67df6a8750
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 520
ht-degree: 22%

---

# Introdução a processos e gerenciamento de dados {#get-started-processes-data-management}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#workflow-activities">Atividades do fluxo de trabalho</a></p></td><td><img src="assets/do-not-localize/icon_activities.svg" width="60px"><p><a href="../../automating/using/workflow-created-query-with-complement.md">Casos de uso</a></p></td><td><img src="assets/do-not-localize/icon_filter.svg" width="60px"><p><a href="#filter-data">Filtrar dados</a></p></td>
<td><img src="assets/do-not-localize/icon_manage.svg" width="60px"><p><a href="#import-export-data">Importar/exportar dados</a></p></td></tr>
</table>

O Adobe Campaign oferece um ambiente gráfico abrangente que permite projetar processos complexos, incluindo segmentação, execução de campanha, processamento de arquivos etc. Por exemplo, você pode usar um fluxo de trabalho para baixar um arquivo de um servidor, descompactá-lo e importar seus registros no banco de dados do Adobe Campaign.

Os fluxos de trabalho podem ser usados em contextos diferentes, por exemplo:

* Direcionamento para gerenciar públicos-alvo ou enviar mensagens.
* Gerenciamento de dados (ETL) para manipular dados.
* Importação de dados para o banco de dados do Campaign.
* Processos técnicos, como limpeza do banco de dados, recuperação de informações de rastreamento etc.

>[!IMPORTANT]
>
> A Adobe recomenda que os clientes não executem mais de 20 fluxos de trabalho ativos simultaneamente e priorizem e distribuam a execução do fluxo de trabalho ao longo do tempo. Para obter mais informações, consulte as práticas recomendadas fornecidas em [esta página](../../automating/using/best-practices-workflows.md).

## Atividades de fluxos de trabalho {#workflow-activities}

Várias atividades estão disponíveis para ajudá-lo a projetar seus fluxos de trabalho.

[As atividades de direcionamento](../../automating/using/about-targeting-activities.md) permitem criar um ou mais destinos definindo conjuntos e dividindo ou combinando esses conjuntos usando operações de interseção, união ou exclusão.

Com [Atividades de execução](../../automating/using/about-execution-activities.md), coordene o fluxo de trabalho e suas atividades, enquanto as [Atividades de canal](../../automating/using/about-channel-activities.md) permitem combinar canais de comunicação da Campaign Standard para criar fluxos de trabalho entre canais.

Finalmente, [as atividades de gerenciamento de dados](../../automating/using/about-data-management-activities.md) permitem manipular dados do seu banco de dados.

Leia mais:

* [Criação de um fluxo de trabalho](../../automating/using/building-a-workflow.md)
* [Execução de um fluxo de trabalho](../../automating/using/about-workflow-execution.md)
* [Práticas recomendadas de fluxo de trabalho](../../automating/using/best-practices-workflows.md)

## Filtrar dados {#filter-data}

Aproveite o **editor de consultas** para filtrar dados do banco de dados e criar uma população para direcionar melhor seus destinatários. O Editor de consultas está disponível para executar várias ações no Campaign Standard: criar públicos do tipo Query, definir públicos-alvo de entrega ou populações em atividades de fluxo de trabalho.

O Editor de Consultas vem com **regras e filtros predefinidos** para uma filtragem rápida e fácil. No entanto, você também pode usar os recursos de **edição de expressão avançada**. Isso permite inserir condições manualmente e usar funções para formar suas próprias regras.

Leia mais:

* [Edição de consultas](../../automating/using/editing-queries.md)
* [Edição de expressão avançada](../../automating/using/advanced-expression-editing.md)
* [Lista de funções](../../automating/using/list-of-functions.md)

## Importar/exportar dados {#import-export-data}

O Campaign Standard vem com vários **recursos de gerenciamento de dados** para importar e exportar dados.

[As atividades de gerenciamento de dados de fluxos de trabalho](../../automating/using/about-data-management-activities.md) permitem importar dados, executar atualizações em massa nos campos, receber ou enviar arquivos ou vincular dados não identificados aos recursos existentes.

Com os [Modelos de importação](../../automating/using/importing-data-with-import-templates.md), gerencie certos tipos de importação definidos por administradores por meio de funções de importação simplificadas.

[A exportação de logs](../../automating/using/exporting-logs.md) permite exportar dados de log por meio de um fluxo de trabalho simples, permitindo analisar os resultados de suas campanhas de marketing em seus próprios relatórios ou ferramentas de BI.

Aproveite os [Pacotes](../../automating/using/managing-packages.md) para trocar recursos entre diferentes instâncias da campanha, por exemplo, para replicar a configuração de uma instância ou transferir dados de um servidor para outro, incluindo recursos personalizados.

Finalmente, [Exportar listas](../../automating/using/exporting-lists.md) permite exportar qualquer lista do Campaign Standard como, por exemplo, a lista de perfis de teste, a lista de endereços de email de quarentena etc.

Leia mais:

* [Importação e exportação de dados](../../automating/using/about-data-import-and-export.md)
* [Caso de uso: exportação/importação de recursos personalizados](../../automating/using/exporting-importing-custom-resources.md)

## Recursos adicionais

* [Vídeos tutoriais sobre processos e gerenciamento de dados](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/managing-processes-and-data/creating-a-workflow.html?lang=pt-BR)
* [Fluxos de trabalho técnicos](../../administration/using/technical-workflows.md)
* [Introdução ao modelo de dados do Campaign Standard](../../developing/using/get-started-data-model.md)
