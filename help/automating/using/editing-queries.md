---
title: Editar consultas
seo-title: Editar consultas
description: Editar consultas
seo-description: Crie uma população graças aos filtros e regras predefinidos.
page-status-flag: nunca ativado
uuid: a49c7739-a96c-45cb-9ac5-1ce299161a97
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: automatização
content-type: referência
topic-tags: filtragem de dados
discoiquuid: 84306a1e-0d9f-44cc-88a7-36d7e5b4da1f
context-tags: queryFilter,overview;audience,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 51d80fc9c683e39b9d08ba7d36b76b71a9dd1e8c

---


# Editar consultas{#editing-queries}

## Sobre o editor de consultas {#about-query-editor}

O editor de consultas é um assistente que permite filtrar os dados contidos no banco de dados do Adobe Campaign.

Esse recurso permite que você crie uma população para melhor direcioná-la aos destinatários graças aos filtros e regras predefinidos.

Várias funcionalidades do aplicativo o utilizam para:

* Criar **públicos-alvo do tipo de consulta** **de**
* Definir metas **de email**
* Definir populações em atividades **de fluxo de trabalho**

## Interface do editor de consultas {#query-editor-interface}

O editor de consultas é formado por uma **Paleta** e um **Espaço de trabalho**.

![](assets/query_editor_overview.png)

### Paleta {#palette}

A paleta, localizada no lado esquerdo do editor, é dividida em duas guias, que contêm elementos divididos em blocos temáticos. Essas guias são:

* Os **Atalhos**, disponíveis por padrão, ou criados pelo administrador da instância. Aqui você encontrará campos, nós, agrupamentos, links 1-1, links 1-N e outros filtros predefinidos.
* O **Explorer** que permite acessar todos os campos disponíveis no recurso de destino: nós, elementos de agrupamento, links (1-1 e 1-N).

Os elementos contidos nas guias devem ser movidos para o espaço de trabalho para serem configurados e levados em conta para a consulta. Dependendo da dimensão de definição de metas selecionada (consulte Dimensões e recursos [](../../automating/using/query.md#targeting-dimensions-and-resources)de definição de metas), é possível:

* Selecionar públicos-alvo ou perfis um a um
* Usar filtros predefinidos
* Definir regras simples para campos de sua escolha
* Definir regras avançadas que permitem aplicar funções a determinados campos

### Área de Trabalho {#workspace}

O espaço de trabalho é a zona central na qual você pode configurar e combinar regras, públicos-alvo e filtros predefinidos adicionados da paleta.

Quando um elemento é movido da paleta para o espaço de trabalho, uma nova janela é aberta e você pode iniciar a [Criação de consultas](#creating-queries).

## Criação de query {#creating-queries}

O editor de consultas pode ser usado para definir um público-alvo ou perfil de teste em uma mensagem, um preenchimento em um fluxo de trabalho e para criar um público-alvo do tipo de consulta.

As consultas podem ser definidas na **[!UICONTROL Audience]** janela ao criar uma entrega ou em uma atividade de **Consulta** ao criar um fluxo de trabalho.

1. Mova um elemento da paleta para o espaço de trabalho. A janela para editar a regra é aberta.

   * Para uma string ou **campo** numérico, especifique o operador de comparação e o valor.

      ![](assets/query_editor_audience_definition2.png)

   * Para um **campo** de data ou data e hora, você pode optar por definir uma data específica, um intervalo entre duas datas ou um período relativo à data de execução da consulta.

      ![](assets/query_editor_date_field.png)

   * Para um **campo** Booliano, marque as caixas vinculadas aos possíveis valores do campo.
   * Para um campo de **agrupamento** , selecione o campo de agrupamento no qual deseja criar a regra e defina a condição da mesma forma que para os outros campos.

      ![](assets/query_editor_audience_definition4.png)

   * Para um link de **1 a 1** com outro recurso de banco de dados, selecione um valor diretamente da tabela direcionada.

      ![](assets/query_editor_audience_definition5.png)

   * Para um link **1-N** com outro recurso de banco de dados, você pode definir uma subconsulta nos campos desse segundo recurso.

      Não é necessário especificar uma subcondição.

      Por exemplo, você só pode selecionar o **[!UICONTROL Exists]** operador nos registros de rastreamento de perfil e aprovar a regra. A regra retornará todos os perfis para os quais os logs de rastreamento existem.

      ![](assets/query_editor_audience_definition6.png)

   * Para um filtro **** predefinido, insira ou selecione os elementos desejados de acordo com os critérios oferecidos.

      Os administradores podem criar filtros para facilitar consultas complexas e repetitivas. Elas aparecerão no editor de consultas na forma de regras pré-configuradas e limitarão o número de etapas necessárias para serem executadas pelo usuário.

      ![](assets/query-editor_filter_email-audience_filter.png)

1. Você pode especificar um nome para sua regra. Isso é exibido como o nome da regra no espaço de trabalho. Se a regra não receber um nome, uma descrição automática das condições será exibida.
1. Para combinar os elementos do espaço de trabalho, interbloqueie-os entre si para criar grupos e/ou níveis de grupo diferentes. Você pode selecionar um operador lógico para combinar elementos no mesmo nível:

   * **[!UICONTROL AND]**: uma interseção de dois critérios. Só são tidos em conta os elementos que correspondem a cada critério.
   * **[!UICONTROL OR]**: uma união de dois critérios. São tidos em conta os elementos que correspondem a pelo menos um dos dois critérios.
   * **[!UICONTROL EXCEPT]**: critérios de exclusão. Os elementos que correspondem ao primeiro critério são tidos em conta, a menos que também correspondam ao segundo critério.

1. Agora você pode calcular e visualizar o número de elementos direcionados pela consulta usando os botões ![](assets/count.png) e ![](assets/preview.png) da barra de ações.

   ![](assets/query_editor_combining_rules.png)

Se você quiser modificar um elemento da consulta, clique no ícone de edição. A regra é aberta como foi configurada anteriormente e você pode realizar os ajustes necessários.

Suas consultas agora são criadas e definidas, permitindo que você crie uma população para personalizar melhor suas entregas.

**Tópicos relacionados:**

* [Funções avançadas](../../automating/using/advanced-expression-editing.md)
* [Definição de filtros](../../developing/using/configuring-filter-definition.md)
* [Caso de uso: Criar uma entrega de email uma vez por semana](../../automating/using/workflow-weekly-offer.md)
* [Caso de uso: Criação de uma entrega segmentada no local](../../automating/using/workflow-segmentation-location.md)
* [Caso de uso: Criação de entregas com um complemento](../../automating/using/workflow-created-query-with-complement.md)
* [Caso de uso: Fluxo de trabalho de redefinição de metas enviando uma nova entrega para não iniciantes](../../automating/using/workflow-cross-channel-retargeting.md)
