---
title: Eliminação de duplicação
description: A atividade de Eliminação de Duplicados permite excluir duplicatas nos resultados das atividades de entrada.
page-status-flag: nunca ativado
uuid: 11a22a9c-3bfe-4953-8a52-2f4e93c128fb
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: automatização
content-type: referência
topic-tags: atividades de definição de metas
discoiquuid: e7a5e1e7-4680-46c7-98b8-0a47bb7be2b8
context-tags: desduplicação,principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Eliminação de duplicação{#deduplication}

## Descrição {#description}

![](assets/deduplication.png)

A **[!UICONTROL Deduplication]** atividade permite excluir duplicatas nos resultados das atividades de entrada.

## Contexto de utilização {#context-of-use}

A **[!UICONTROL Deduplication]** atividade é geralmente usada após atividades de definição de metas ou após a importação de um arquivo e antes de atividades que permitem o uso de dados direcionados.

Durante a desduplicação, as transições de entrada são processadas separadamente. Por exemplo, se o perfil 'A' estiver presente no resultado da consulta 1 e também no resultado da consulta 2, ele não será desduplicado.

Portanto, recomenda-se que a desduplicação tenha apenas uma transição de entrada. Para fazer isso, você pode combinar suas diferentes consultas usando atividades que correspondem às suas necessidades de direcionamento, como uma atividade de união, uma atividade de interseção etc. Por exemplo:

![](assets/dedup_bonnepratique.png)

## Configuração {#configuration}

Para configurar uma atividade de desduplicação, você deve inserir um rótulo, o método e os critérios de desduplicação, bem como as opções relacionadas ao resultado.

1. Arraste e solte uma **[!UICONTROL Deduplication]** atividade em seu fluxo de trabalho.
1. Selecione a atividade e abra-a usando o ![](assets/edit_darkgrey-24px.png) botão das ações rápidas que aparecem.

   ![](assets/deduplication_1.png)

1. Selecione o **[!UICONTROL Resource type]** objeto da desduplicação:

   * **[!UICONTROL Database resource]** se a desduplicação for realizada em dados que já existem no banco de dados. Selecione o **[!UICONTROL Filtering dimension]** e o **[!UICONTROL Targeting dimension]**, dependendo dos dados que você deseja desduplicar. Por padrão, a desduplicação é realizada nos **perfis**.
   * **[!UICONTROL Temporary resource]** se a desduplicação for realizada nos dados temporários do fluxo de trabalho: selecione os dados **[!UICONTROL Targeted set]** que contêm os dados a serem desduplicados. Esse caso de uso pode ser encontrado após a importação de um arquivo ou se os dados no banco de dados foram enriquecidos (com um código de segmento, por exemplo).

1. Selecione o **[!UICONTROL Number of unique records to keep]**. O valor padrão para esse campo é 1. O valor 0 permite manter todas as duplicatas.

   Por exemplo, se os registros A e B forem considerados duplicados do registro Y e um registro C for considerado uma duplicata do registro Z:

   * Se o valor do campo for 1: apenas os registros Y e Z são mantidos.
   * Se o valor do campo for 0: todos os registros são mantidos.
   * Se o valor do campo for 2: os registros C e Z são mantidos e dois registros de A, B e Y são mantidos, por acaso ou dependendo do método de desduplicação selecionado posteriormente.

1. Defina os **[!UICONTROL Duplicate identification]** critérios adicionando condições na lista fornecida. Especifique os campos e/ou as expressões cujos valores idênticos permitem a identificação das duplicatas: endereço de email, nome, sobrenome etc. A ordem das condições permite que você especifique as condições para serem processadas primeiro.
1. Na lista suspensa, selecione a opção **[!UICONTROL Deduplication method]** a ser usada:

   * **[!UICONTROL Choose for me]**: seleciona aleatoriamente o registro a ser mantido fora das duplicatas.
   * **[!UICONTROL Following a list of values]**: permite definir uma prioridade de valor para um ou mais campos. Para definir os valores, selecione um campo ou crie uma expressão e adicione o(s) valor(s) à tabela apropriada. To define a new field, click the **[!UICONTROL Add]** button located above the list of values.

      ![](assets/deduplication_2.png)

   * **[!UICONTROL Non-empty value]**: isso permite manter registros para os quais o valor da expressão selecionada não está vazio como prioridade.

      ![](assets/deduplication_3.png)

   * **[!UICONTROL Using an expression]**: isso permite manter os registros nos quais o valor da expressão inserida é o menor ou o maior.

      ![](assets/deduplication_4.png)

1. Se necessário, gerencie as [Transições](../../automating/using/executing-a-workflow.md#managing-an-activity-s-outbound-transitions) da atividade para acessar as opções avançadas para a população de saída.
1. Confirme a configuração da atividade e salve o fluxo de trabalho.

## Exemplo 1: Como identificar duplicatas antes de uma entrega {#example-1--identifying-duplicates-before-a-delivery}

O exemplo a seguir ilustra uma desduplicação que permite excluir as duplicatas de um destino antes de enviar um email. Isso significa que você evita enviar uma comunicação várias vezes para o mesmo perfil.

O fluxo de trabalho é composto de:

![](assets/deduplication_example_workflow.png)

* Um **[!UICONTROL Query]** que permite definir o destino do email. Aqui, o fluxo de trabalho direciona todos os perfis com idade entre 18 e 25 anos que estão no banco de dados do cliente por mais de um ano.

   ![](assets/deduplication_example_query.png)

* Uma **[!UICONTROL Deduplication]** atividade que permite identificar as duplicatas que vêm da consulta anterior. Neste exemplo, apenas um registro é salvo para cada duplicata. As duplicatas são identificadas usando o endereço de email. Isso significa que a entrega do email só pode ser enviada uma vez para cada endereço de email que esteja presente na definição de metas.

   O método de desduplicação selecionado é **[!UICONTROL Non-empty value]**. Isso permite garantir que, entre os registros mantidos em caso de duplicatas, seja dada prioridade àqueles em que foi fornecido o **nome** . Isso tornará mais coerente se o nome for usado nos campos de personalização do conteúdo de email.

   Além disso, uma transição extra é adicionada para manter as duplicatas e poder listá-las.

   ![](assets/deduplication_example_dedup.png)

* Um **[!UICONTROL Email delivery]** posicionado após a principal transição de saída da desduplicação. A configuração para entregas por email é detalhada na seção de entrega [por](../../automating/using/email-delivery.md) email.
* Uma **[!UICONTROL Save audience]** atividade realizada após a transição adicional da desduplicação para salvar as duplicatas em um público-alvo **Duplicado** . Esse público-alvo pode ser reutilizado para excluir diretamente seus membros de cada entrega de email.

## Exemplo 2: Desduplicando os dados de um arquivo importado {#example-2--deduplicating-the-data-from-an-imported-file}

Este exemplo mostra como desduplicar dados de um arquivo importado antes de carregar os dados no banco de dados. Esse procedimento melhora a qualidade dos dados carregados no banco de dados.

O fluxo de trabalho é composto de:

![](assets/deduplication_example2_workflow.png)

* Um arquivo que contém uma lista de perfis é importado usando uma **[!UICONTROL Load file]** atividade. Neste exemplo, o arquivo importado está no formato .csv e contém 10 perfis:

   ```
   lastname;firstname;dateofbirth;email
   Smith;Hayden;23/05/1989;hayden.smith@example.com
   Mars;Daniel;17/11/1987;dannymars@example.com
   Smith;Clara;08/02/1989;hayden.smith@example.com
   Durance;Allison;15/12/1978;allison.durance@example.com
   Lucassen;Jody;28/03/1988;jody.lucassen@example.com
   Binder;Tom;19/01/1982;tombinder@example.com
   Binder;Tommy;19/01/1915;tombinder@example.com
   Connor;Jade;10/10/1979;connor.jade@example.com
   Mack;Clarke;02/03/1985;clarke.mack@example.com
   Ross;Timothy;04/07/1986;timross@example.com
   ```

   Esse arquivo também pode ser usado como um arquivo de amostra para detectar e definir o formato das colunas. Na **[!UICONTROL Column definition]** guia, verifique se cada coluna do arquivo importado está configurada corretamente.

   ![](assets/deduplication_example2_fileloading.png)

* A **[!UICONTROL Deduplication]** activity. A desduplicação é realizada diretamente após a importação do arquivo e antes da inserção dos dados no banco de dados. Deve, por conseguinte, basear-se no **[!UICONTROL Temporary resource]** resultado da **[!UICONTROL Load file]** atividade.

   Neste exemplo, queremos manter uma única entrada por endereço de email exclusivo contido no arquivo. A identificação duplicada é, portanto, realizada na coluna de **email** do recurso temporário. No entanto, dois endereços de email são exibidos duas vezes no arquivo. Por conseguinte, serão consideradas duplicadas duas linhas.

   ![](assets/deduplication_example2_dedup.png)

* Uma **[!UICONTROL Update data]** atividade permite inserir os dados mantidos do processo de desduplicação no banco de dados. Somente quando os dados são atualizados é que os dados importados são identificados como pertencendo à dimensão do perfil.

   Aqui, gostaríamos de ver **[!UICONTROL Insert only]** os perfis que ainda não existem no banco de dados. Vamos fazer isso usando a coluna de email do arquivo e o campo de email da dimensão **Perfil** como a chave de reconciliação.

   ![](assets/deduplication_example2_writer1.png)

   Especifique os mapeamentos entre as colunas do arquivo a partir das quais deseja inserir os dados e os campos do banco de dados na **[!UICONTROL Fields to update]** guia.

   ![](assets/deduplication_example2_writer2.png)

Em seguida, inicie o fluxo de trabalho. Os registros salvos do processo de desduplicação são adicionados aos perfis no banco de dados.
