---
title: Edição de consultas
description: Crie uma população com regras e filtros predefinidos.
page-status-flag: never-activated
uuid: a49c7739-a96c-45cb-9ac5-1ce299161a97
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: filtering-data
discoiquuid: 84306a1e-0d9f-44cc-88a7-36d7e5b4da1f
context-tags: queryFilter,overview;audience,main
internal: n
snippet: y
translation-type: ht
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e
workflow-type: ht
source-wordcount: '782'
ht-degree: 100%

---


# Edição de consultas{#editing-queries}

## Sobre o Editor de consultas {#about-query-editor}

O Editor de consultas é um assistente que permite filtrar os dados contidos no banco de dados do Adobe Campaign.

Use esse recurso para criar uma população e melhorar o direcionamento dos recipients usando as regras e os filtros predefinidos.

Várias funcionalidades de aplicativo o utilizam para:

* Criar **públicos** do tipo **Query**
* Definir os públicos alvo do **email**
* Definir as populações nas atividades de **fluxo de trabalho**

## interface do Editor de consultas {#query-editor-interface}

O Editor de consultas é composto de uma **paleta** e um **espaço de trabalho**.

![](assets/query_editor_overview.png)

### Paleta {#palette}

A paleta, localizada à esquerda do editor, tem duas guias com elementos divididos em blocos temáticos. Essas guias são:

* Os **atalhos**, disponíveis por padrão ou criados pelo administrador da instância. Eles contém campos, nós, agrupamentos, links 1-1, links 1-N e outros filtros predefinidos.
* O **Explorer** que permite acessar todos os campos disponíveis no recurso de público-alvo: nós, elementos de agrupamento, links (1-1 e 1-N).

Os elementos nas guias devem ser movidos para o espaço de trabalho para serem configurados e considerados para o query. Dependendo do targeting dimension selecionado (consulte [Targeting dimensions e recursos](../../automating/using/query.md#targeting-dimensions-and-resources)), você poderá:

* Selecionar públicos ou perfis individualmente
* Usar filtros predefinidos
* Definir regras simples para os campos escolhidos
* Definir regras avançadas para aplicar funções a campos específicos

### Espaço de trabalho {#workspace}

O espaço de trabalho é a zona central onde você pode configurar e combinar regras, públicos e filtros predefinidos adicionados da paleta.

Quando um elemento é movido da paleta para o espaço de trabalho, uma nova janela é aberta e você pode começar a [criação de consultas](#creating-queries).

## Criação de consultas {#creating-queries}

O Editor de consultas pode ser usado para definir um público ou um perfil de teste em uma mensagem, uma população em um fluxo de trabalho e para criar um público do tipo consulta.

As consultas podem ser definidas na janela **[!UICONTROL Audience]** ao criar um delivery ou em uma atividade **Consulta** ao criar um fluxo de trabalho.

1. Mova um elemento da paleta para o espaço de trabalho. A janela para editar a regra é aberta.

   * Para uma sequência ou um **campo** numérico, especifique o operador de comparação e o valor.

      ![](assets/query_editor_audience_definition2.png)

   * Para um **campo** de data ou de data e hora, você pode optar por definir uma data específica, um intervalo entre duas datas ou um período relativo à data de execução do query.

      ![](assets/query_editor_date_field.png)

   * Para um **campo** booliano, marque as caixas vinculadas aos valores possíveis do campo.
   * Para um campo de **agrupamento**, selecione o campo de agrupamento no qual deseja criar a regra e defina a condição do mesmo modo que para os outros campos.

      ![](assets/query_editor_audience_definition4.png)

   * Para um link **1-1** com outro recurso de banco de dados, selecione um valor diretamente na tabela direcionada.

      ![](assets/query_editor_audience_definition5.png)

   * Para um link **1-N** com outro recurso de banco de dados, você pode definir um subquery nos campos desse segundo recurso.

      Não é necessário especificar uma subcondição.

      Por exemplo, você só pode selecionar o operador **[!UICONTROL Exists]** nos logs de rastreamento do perfil e aprovar a regra. A regra retornará todos os perfis para os quais existem logs de rastreamento.

      ![](assets/query_editor_audience_definition6.png)

   * Para um **filtro predefinido**, insira ou selecione os elementos desejados de acordo com os critérios oferecidos.

      Os administradores podem criar filtros para facilitar as consultas complexas e repetitivas. Eles aparecerão no Editor de consultas na forma de regras pré-configuradas e limitarão as etapas a serem executadas pelo usuário.

      ![](assets/query-editor_filter_email-audience_filter.png)

1. Você pode especificar um nome para a regra. Ela será exibida como o nome de regra no espaço de trabalho. Se a regra não tiver nome, será exibida uma descrição automática das condições.
1. Para combinar os elementos do espaço de trabalho, faça o interbloqueio entre eles para criar grupos e/ou níveis de grupo diferentes. Você pode selecionar um operador lógico para combinar elementos no mesmo nível:

   * **[!UICONTROL AND]**: uma intersecção de dois critérios. Apenas os elementos correspondentes a cada critério são considerados.
   * **[!UICONTROL OR]**: uma união de dois critérios. Os elementos correspondentes a pelo menos um dos critérios são considerados.
   * **[!UICONTROL EXCEPT]**: critérios de exclusão. Os elementos correspondentes ao primeiro critério são considerados, a menos que também correspondam ao segundo critério.

1. Agora você pode calcular e pré-visualizar o número de elementos direcionados pelo query usando os botões ![](assets/count.png) e ![](assets/preview.png) da barra de ação.

   ![](assets/query_editor_combining_rules.png)

Se quiser modificar um elemento do query, clique no ícone de edição. A regra é aberta conforme configurada anteriormente, e você pode realizar os ajustes necessários.

Agora as consultas são criadas e definidas, e você pode criar uma população para personalizar melhor seus deliveries.

**Tópicos relacionados:**

* [Funções avançadas](../../automating/using/advanced-expression-editing.md)
* [Definição de filtros](../../developing/using/configuring-filter-definition.md)
* [Caso de uso: criar delivery por email uma vez por semana](../../automating/using/workflow-weekly-offer.md)
* [Caso de uso: criar um delivery segmentado na localização](../../automating/using/workflow-segmentation-location.md)
* [Caso de uso: criar deliveries com um complemento](../../automating/using/workflow-created-query-with-complement.md)
* [Caso de uso: workflow de redirecionamento enviando um novo delivery para não abridores](../../automating/using/workflow-cross-channel-retargeting.md)
