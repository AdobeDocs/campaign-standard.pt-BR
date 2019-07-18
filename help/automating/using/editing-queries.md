---
title: Edição de consultas
seo-title: Edição de consultas
description: Edição de consultas
seo-description: Crie uma população graças aos filtros e às regras predefinidos.
page-status-flag: nunca ativado
uuid: a 49 c 7739-a 96 c -45 cb -9 ac 5-1 ce 299161 a 97
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizando
content-type: reference
topic-tags: filtros de dados
discoiquuid: 84306 a 1 e -0 d 9 f -44 cc -88 a 7-36 d 7 e 5 b 4 da 1 f
context-tags: Queryfilter, overview; público-alvo, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Editing queries{#editing-queries}

## About query editor {#about-query-editor}

O editor de consulta é um assistente que permite filtrar dados contidos no banco de dados do Adobe Campaign.

Esse recurso permite que você crie uma população para direcionar melhor seus destinatários, graças aos filtros e às regras predefinidos.

Várias funcionalidades do aplicativo usam-a para:

* Create **Query** type **audiences**
* Define **email** targets
* Define populations in **workflow** activities

## Query editor interface {#query-editor-interface}

The query editor is made up of a **Palette** and a **Workspace**.

![](assets/query_editor_overview.png)

### Palette {#palette}

A paleta, localizada no lado esquerdo do editor, é dividida em duas guias, que contêm elementos divididos em blocos temáticos. Essas guias são:

* **Os Atalhos**, disponíveis por padrão ou criados pelo administrador da instância. Aqui, você encontrará campos, nós, agrupamentos, 1-1 links, links de 1 N e outros filtros predefinidos.
* **O Explorer** , que permite acessar todos os campos disponíveis no recurso de destino: nós, elementos de agrupamento, links (1-1 e 1-N).

Os elementos contidos nas guias devem ser movidos para a área de trabalho para serem configurados e considerados para a consulta. Depending on the targeting dimension selected (see [Targeting dimensions and resources](../../automating/using/query.md#targeting-dimensions-and-resources)), you can:

* Selecione públicos-alvo ou perfis um por um
* Usar filtros predefinidos
* Definir regras simples para campos de sua escolha
* Definir regras avançadas que permitem aplicar funções a certos campos

### Workspace {#workspace}

A área de trabalho é a zona central na qual é possível configurar e combinar regras, públicos-alvo e filtros predefinidos adicionados a partir da paleta.

When you move an element from the palette into the workspace, a new window opens and you can start [Creating queries](../../automating/using/editing-queries.md#creating-queries).

## Creating queries {#creating-queries}

O editor de consulta pode ser usado para definir um público-alvo ou perfil de teste em uma mensagem, uma população em um fluxo de trabalho e para criar um público-alvo de tipo de consulta.

Queries can be defined in the **[!UICONTROL Audience]** window while creating a delivery or in a **Query** activity while creating a workflow.

1. Mova um elemento da paleta até a área de trabalho. A janela para edição da regra é aberta.

   * For a string or numerical **field**, specify the comparison operator and the value.

      ![](assets/query_editor_audience_definition2.png)

   * For a date or date and time **field**, you can choose to define a specific date, a range between two dates, or a period relative to the query's execution date.

      ![](assets/query_editor_date_field.png)

   * For a Boolean **field**, check the boxes linked to the possible values for the field.
   * For a **grouping** field, select the grouping field on which you want to create the rule, then define the condition in the same way as for the other fields.

      ![](assets/query_editor_audience_definition4.png)

   * For a **1-1** link with another database resource, select a value directly from the table targeted.

      ![](assets/query_editor_audience_definition5.png)

   * For a **1-N** link with another database resource, you can define a sub-query on the fields of this second resource.

      Não é necessário especificar uma subcondição.

      For example, you can only select the **[!UICONTROL Exists]** operator on the profile tracking logs and approve the rule. A regra retornará todos os perfis para os quais existem registros de rastreamento.

      ![](assets/query_editor_audience_definition6.png)

   * For a **predefined filter**, enter or select the elements you like according to the criteria offered.

      Os administradores podem criar filtros para facilitar consultas complexas e repetitivas. Eles aparecerão no editor de consultas na forma de regras pré-definidas e limitarão o número de etapas necessárias para serem executadas pelo usuário.

      ![](assets/query-editor_filter_email-audience_filter.png)

1. Você pode especificar um nome para a regra. Isso é exibido como o nome da regra no espaço de trabalho. Se a regra não tiver um nome, uma descrição automática das condições será exibida.
1. Para combinar os elementos da área de trabalho, vincule-os uns em um outro para criar grupos diferentes e/ou níveis de grupos. Você pode selecionar um operador lógico para combinar elementos no mesmo nível:

   * **[!UICONTROL AND]**: uma interseção de dois critérios. Somente os elementos que correspondem cada critério são considerados.
   * **[!UICONTROL OR]**: uma união de dois critérios. Os elementos que correspondem ao pelo menos um dos dois critérios são considerados.
   * **[!UICONTROL EXCEPT]**: critérios de exclusão. Os elementos que corresponderem ao primeiro critério são levados em conta, a menos que também correspondam ao segundo critério.

1. You can now calculate and preview the number of elements targeted by your query using the ![](assets/count.png) and ![](assets/preview.png) buttons from the action bar.

   ![](assets/query_editor_combining_rules.png)

Se você quiser modificar um elemento da consulta, clique no ícone editar. A regra é aberta conforme foi configurada anteriormente e você pode executar quaisquer ajustes necessários.

Suas consultas agora são criadas e definidas, permitindo que você crie uma população para personalizar melhor suas entregas.

**Tópicos relacionados:**

* [Funções avançadas](../../automating/using/advanced-expression-editing.md)
* [Definição de filtros](../../developing/using/configuring-filter-definition.md)

