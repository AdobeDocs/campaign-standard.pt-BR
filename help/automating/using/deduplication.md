---
title: Eliminação de duplicação
description: A atividade Desduplicação-duplicada permite que você exclua duplicados nos resultados das atividades de entrada.
page-status-flag: never-activated
uuid: 11a22a9c-3bfe-4953-8a52-2f4e93c128fb
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: e7a5e1e7-4680-46c7-98b8-0a47bb7be2b8
context-tags: dedup,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 14%

---


# Eliminação de duplicação{#deduplication}

## Descrição {#description}

![](assets/deduplication.png)

A **[!UICONTROL Deduplication]** atividade permite excluir duplicados nos resultados das atividades de entrada.

## Contexto de utilização {#context-of-use}

A **[!UICONTROL Deduplication]** atividade é geralmente usada após atividades de definição de metas ou após a importação de um arquivo e antes das atividades que permitem o uso de dados direcionados.

Durante o desduplicação-duplicado, as transições de entrada são processadas separadamente. Por exemplo, se o perfil &#39;A&#39; estiver presente no resultado do query 1 e também no resultado do query 2, ele não será desduplicado.

Por conseguinte, é aconselhável que um desduplicação-duplicado tenha apenas uma transição de entrada. Para fazer isso, você pode combinar seus diferentes query usando atividades que correspondam às suas necessidades de direcionamento, como uma atividade de união, uma atividade de interseção etc. Por exemplo:

![](assets/dedup_bonnepratique.png)

**Tópicos relacionados**

* [Caso de uso: Identificação de duplicados antes de um delivery](../../automating/using/identifying-duplicated-before-delivery.md)
* [Caso de uso: Desduplicando os dados de um arquivo importado](../../automating/using/deduplicating-data-imported-file.md)

## Configuração {#configuration}

Para configurar uma atividade desduplicação-duplicada, é necessário inserir um rótulo, o método e os critérios desduplicação-duplicados, bem como as opções relacionadas ao resultado.

1. Arraste e solte uma **[!UICONTROL Deduplication]** atividade no seu fluxo de trabalho.
1. Selecione a atividade e abra-a usando o ![](assets/edit_darkgrey-24px.png) botão das ações rápidas que aparecem.

   ![](assets/deduplication_1.png)

1. Selecione o **[!UICONTROL Resource type]** objeto do desduplicação-duplicado:

   * **[!UICONTROL Database resource]** se o desduplicação-duplicado for realizado com dados que já existem na base de dados. Selecione o **[!UICONTROL Filtering dimension]** e o **[!UICONTROL Targeting dimension]**, dependendo dos dados que você deseja desduplicar. Por padrão, é desduplicação-duplicado nos **perfis**.
   * **[!UICONTROL Temporary resource]** se o desduplicação-duplicado for executado nos dados temporários do fluxo de trabalho: selecione os dados **[!UICONTROL Targeted set]** que contêm os dados a serem desduplicados. Esse caso de uso pode ser encontrado após a importação de um arquivo ou se os dados no banco de dados foram enriquecidos (com um código de segmento, por exemplo).

1. Selecione o **[!UICONTROL Number of unique records to keep]**. O valor padrão para esse campo é 1. O valor 0 permite manter todos os duplicados.

   Por exemplo, se os registros A e B forem considerados duplicados do registro Y e um registro C for considerado um duplicado do registro Z:

   * Se o valor do campo for 1: apenas os registros Y e Z são mantidos.
   * Se o valor do campo for 0: todos os registros são mantidos.
   * Se o valor do campo for 2: os registros C e Z são mantidos e dois registros de A, B e Y são mantidos, por acaso ou em função do método desduplicação-duplicado selecionado posteriormente.

1. Defina os **[!UICONTROL Duplicate identification]** critérios adicionando condições na lista fornecida. Especifique os campos e/ou expressões cujos valores idênticos permitem a identificação dos duplicados: endereço de email, nome, sobrenome etc. A ordem das condições permite que você especifique as condições para serem processadas primeiro.
1. Na lista suspensa, selecione a opção **[!UICONTROL Deduplication method]** a ser usada:

   * **[!UICONTROL Choose for me]**: seleciona aleatoriamente o registro a ser mantido fora das duplicatas.
   * **[!UICONTROL Following a list of values]**: permite definir uma prioridade de valor para um ou mais campos. Para definir os valores, selecione um campo ou crie uma expressão e adicione o(s) valor(s) à tabela apropriada. Para definir um novo campo, clique no botão **[!UICONTROL Add]** localizado acima da lista de valores.

      ![](assets/deduplication_2.png)

   * **[!UICONTROL Non-empty value]**: permite manter registros para os quais o valor da expressão selecionada não está vazio como uma prioridade.

      ![](assets/deduplication_3.png)

   * **[!UICONTROL Using an expression]**: isso permite manter os registros nos quais o valor da expressão inserida é o menor ou o maior.

      ![](assets/deduplication_4.png)

1. Se necessário, gerencie as [Transições](../../automating/using/activity-properties.md) de atividade para acessar as opções avançadas para a população de saída.
1. Confirme a configuração da atividade e salve o fluxo de trabalho.
