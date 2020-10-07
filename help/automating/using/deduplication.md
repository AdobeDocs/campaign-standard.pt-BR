---
title: Desduplicação
description: A atividade de Desduplicação permite excluir duplicados no(s) resultado(s) das atividades de entrada.
page-status-flag: never-activated
uuid: 11a22a9c-3bfe-4953-8a52-2f4e93c128fb
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: e7a5e1e7-4680-46c7-98b8-0a47bb7be2b8
context-tags: dedup,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 97%

---


# Desduplicação{#deduplication}

## Descrição {#description}

![](assets/deduplication.png)

A atividade de **[!UICONTROL Deduplication]** permite excluir duplicados no(s) resultado(s) das atividades de entrada.

## Contexto de uso {#context-of-use}

A atividade **[!UICONTROL Deduplication]** é geralmente usada após atividades de direcionamento ou após a importação de um arquivo e antes de atividades que permitem o uso de dados direcionados.

Durante a desduplicação, as transições de entrada são processadas separadamente. Por exemplo, se o perfil “A” estiver presente no resultado da consulta 1 e também no resultado da consulta 2, ele não será desduplicado.

Por conseguinte, é aconselhável que uma desduplicação tenha somente uma transição de entrada. Para fazer isso, combine as consultas usando atividades que correspondam às suas necessidades de direcionamento, como uma atividade de união, uma atividade de intersecção etc. Por exemplo:

![](assets/dedup_bonnepratique.png)

**Tópicos relacionados**

* [Caso de uso: Identificação de duplicados antes de um delivery](../../automating/using/identifying-duplicated-before-delivery.md)
* [Caso de uso: Desduplicando os dados de um arquivo importado](../../automating/using/deduplicating-data-imported-file.md)

## Configuração {#configuration}

Para configurar uma atividade de desduplicação, é necessário inserir um rótulo, o método e os critérios de desduplicação, bem como as opções relacionadas ao resultado.

1. Arraste e solte uma atividade **[!UICONTROL Deduplication]** no seu fluxo de trabalho.
1. Selecione e abra a atividade usando o botão ![](assets/edit_darkgrey-24px.png) das ações rápidas exibidas.

   ![](assets/deduplication_1.png)

1. Selecione o **[!UICONTROL Resource type]** no qual a desduplicação será realizada:

   * **[!UICONTROL Database resource]** se a desduplicação for realizada com dados que já existem na base de dados. Selecione a **[!UICONTROL Filtering dimension]** e a **[!UICONTROL Targeting dimension]**, dependendo dos dados que deseja desduplicar. Por padrão, a desduplicação é realizada nos **perfis**.
   * **[!UICONTROL Temporary resource]** se a desduplicação for realizada nos dados temporários do fluxo de trabalho: selecione o **[!UICONTROL Targeted set]** que contenha os dados que serão desduplicados. Esse caso de uso pode ser encontrado após a importação de um arquivo ou se os dados no banco de dados foram enriquecidos (com um código de segmento, por exemplo).

1. Selecione **[!UICONTROL Number of unique records to keep]**. O valor padrão para esse campo é 1. O valor 0 permite manter todas as duplicatas.

   Por exemplo, se os registros A e B forem considerados duplicatas do registro Y, e um registro C for considerado uma duplicata do registro Z:

   * Se o valor do campo for 1: somente os registros Y e Z são mantidos.
   * Se o valor do campo for 0: todos os registros são mantidos.
   * Se o valor do campo for 2: os registros C e Z são mantidos. Os dois registros de A, B e Y são mantidos por acaso ou dependendo do método de desduplicação selecionado posteriormente.

1. Defina os critérios de **[!UICONTROL Duplicate identification]** adicionando condições na lista fornecida. Especifique os campos e/ou expressões cujos valores idênticos permitem a identificação dos duplicados: endereço de email, nome, sobrenome etc. A ordem das condições permite especificar os que devem ser processados primeiro.
1. Na lista suspensa, selecione o **[!UICONTROL Deduplication method]** que será usado:

   * **[!UICONTROL Choose for me]**: seleciona aleatoriamente o registro que será mantido fora das duplicatas.
   * **[!UICONTROL Following a list of values]**: permite definir uma prioridade de valor para um ou mais campos. Para definir os valores, selecione um campo ou crie uma expressão e adicione o(s) valor(es) à tabela apropriada. Para definir um novo campo, clique no botão **[!UICONTROL Add]** localizado acima da lista de valores.

      ![](assets/deduplication_2.png)

   * **[!UICONTROL Non-empty value]**: permite manter registros para os quais o valor da expressão selecionada não está vazio como uma prioridade.

      ![](assets/deduplication_3.png)

   * **[!UICONTROL Using an expression]**: permite manter os registros nos quais o valor da expressão inserida é o menor ou o maior.

      ![](assets/deduplication_4.png)

1. Se necessário, gerencie as [Transições](../../automating/using/activity-properties.md) de atividade para acessar as opções avançadas para a população de saída.
1. Confirme a configuração da sua atividade e salve o fluxo de trabalho.
