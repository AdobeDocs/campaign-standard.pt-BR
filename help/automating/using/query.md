---
title: Consulta
description: A atividade do Query permite filtrar e extrair um preenchimento de elementos do banco de dados do Adobe Campaign.
page-status-flag: never-activated
uuid: b3c629fa-370e-481c-b347-fcf9f5a5e847
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 8d46ce28-0101-4f13-865a-2208ed6d6139
context-tags: query,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 87e0611fae0560aca276caa3c4cf793e9c095d72
workflow-type: tm+mt
source-wordcount: '1725'
ht-degree: 1%

---


# Consulta{#query}

## Descrição {#description}

![](assets/query.png)

A **[!UICONTROL Query]** atividade permite filtrar e extrair um preenchimento de elementos do banco de dados do Adobe Campaign. É possível definir **[!UICONTROL Additional data]** para a população direcionada por meio de uma guia dedicada. Esses dados são armazenados em colunas adicionais e só podem ser usados para o fluxo de trabalho em andamento.

A atividade usa a ferramenta do editor de query. Essa ferramenta é detalhada em uma seção [](../../automating/using/editing-queries.md#about-query-editor)dedicada.

**Tópicos relacionados:**

* [Amostras de query](../../automating/using/query-samples.md)
* [Caso de uso: Fluxo de trabalho de redefinição de metas enviando um novo delivery para não iniciantes](../../automating/using/workflow-cross-channel-retargeting.md)

## Contexto de utilização {#context-of-use}

A **[!UICONTROL Query]** atividade pode ser usada para vários tipos de usos:

* Segmentação de indivíduos para definir o público alvo de uma mensagem, audiência etc.
* Enriquecendo dados da tabela inteira do banco de dados do Adobe Campaign.
* Exportação de dados.

## Configuração {#configuration}

1. Arraste e solte uma **[!UICONTROL Query]** atividade no seu fluxo de trabalho.
1. Selecione a atividade e abra-a usando o ![](assets/edit_darkgrey-24px.png) botão das ações rápidas que aparecem. Por padrão, a atividade é pré-configurada para procurar perfis.
1. Se você quiser executar um query em um recurso diferente do perfil, vá para a guia atividade **[!UICONTROL Properties]** e selecione um **[!UICONTROL Resource]** e um **[!UICONTROL Targeting dimension]**.

   O **[!UICONTROL Resource]** permite refinar os filtros exibidos na paleta, enquanto o **[!UICONTROL Targeting dimension]**, contextual em relação ao recurso selecionado, corresponde ao tipo de população que você deseja obter (perfis identificados, delivery, dados vinculados ao recurso selecionado etc.).

   Para obter mais informações, consulte [Targeting dimension e recursos](#targeting-dimensions-and-resources).

1. Na **[!UICONTROL Target]** guia, execute seu query definindo e combinando regras.
1. É possível definir **[!UICONTROL Additional data]** para a população direcionada por meio de uma guia dedicada. Esses dados são armazenados em colunas adicionais e só podem ser usados para o fluxo de trabalho em andamento. Em particular, você pode adicionar dados das tabelas de banco de dados do Adobe Campaign vinculadas ao targeting dimension do query. Consulte a seção [Enriquecendo dados](#enriching-data) .

   >[!NOTE]
   >
   >Por padrão, a **[!UICONTROL Remove duplicate rows (DISTINCT)]** opção é marcada na guia **[!UICONTROL Advanced options]** do **[!UICONTROL Additional data]** query. Se a **[!UICONTROL Query]** atividade contiver muitos (de 100) dados adicionais definidos, é recomendável desmarcar essa opção por motivos de desempenho. Observe que desmarcar essa opção pode resultar na obtenção de duplicados, dependendo dos dados consultados.

1. Na **[!UICONTROL Transition]** guia, a **[!UICONTROL Enable an outbound transition]** opção permite que você adicione uma transição de saída após a atividade do query, mesmo que ela não recupere dados.

   O código de segmento de saída pode ser personalizado usando uma expressão padrão e variáveis de eventos (consulte [Personalização de atividades com variáveis](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables)de eventos).

1. Confirme a configuração da atividade e salve o fluxo de trabalho.

## Targeting dimension e recursos {#targeting-dimensions-and-resources}

Targeting dimension e recursos permitem definir em quais elementos um query será baseado para determinar o público alvo de um delivery.

Targeting dimension são definidos em target mapping. Para obter mais informações, consulte [esta seção](../../administration/using/target-mappings-in-campaign.md).

Targeting dimension e recursos são definidos ao criar um fluxo de trabalho, na **[!UICONTROL Properties]** guia de uma atividade de Query.

>[!NOTE]
>
>O targeting dimension também pode ser definido ao criar uma audiência (consulte [esta seção](../../audiences/using/creating-audiences.md)).

![](assets/targeting_dimension1.png)

Targeting dimension e recursos estão vinculados. Os targeting dimension disponíveis dependem, portanto, do recurso selecionado.

Por exemplo, para o Recurso **[!UICONTROL Profiles (profile)]**, os seguintes targeting dimension estarão disponíveis:

![](assets/targeting_dimension2.png)

Quando for **[!UICONTROL Deliveries (delivery)]**, a lista conterá os seguintes targeting dimension:

![](assets/targeting_dimension3.png)

Depois que o targeting dimension e o recurso são especificados, filtros diferentes ficam disponíveis no query.

Exemplo de filtros disponíveis para o **[!UICONTROL Profiles (profile)]** recurso:

![](assets/targeting_dimension4.png)

Exemplo de filtros disponíveis para o **[!UICONTROL Deliveries (delivery)]** recurso:

![](assets/targeting_dimension5.png)

Por padrão, o targeting dimension e o recurso são definidos para perfis públicos alvos. Entretanto, pode ser útil usar um recurso diferente do targeting dimension se você quiser procurar um registro específico em uma tabela distante.

Para obter mais informações, consulte este caso de uso: [Uso de recursos diferentes de targeting dimension](../../automating/using/using-resources-different-from-targeting-dimensions.md)

## Enriquecimento de dados {#enriching-data}

A **[!UICONTROL Additional data]** guia do **[!UICONTROL Query]**, **[!UICONTROL Incremental query]** e do **[!UICONTROL Enrichment]** atividade permite aprimorar os dados direcionados e transferir esses dados para as seguintes atividades de fluxo de trabalho, onde podem ser utilizados. Em particular, você pode adicionar:

* Dados simples
* Agregados
* Coleções

Para agregações e coleções, uma ID **[!UICONTROL Alias]** é automaticamente definida para fornecer uma ID técnica a uma expressão complexa. Esse alias, que deve ser exclusivo, permite que as agregações e coleções sejam facilmente encontradas depois. Você pode modificá-la para dar a ela um nome facilmente reconhecível.

>[!NOTE]
>
>Os aliases devem respeitar as seguintes regras de sintaxe: Apenas caracteres alfanuméricos e os caracteres &quot;_&quot; são autorizados. Os aliases fazem distinção entre maiúsculas e minúsculas. O alias deve ser start com o caractere &quot;@&quot;. O caractere imediatamente após &quot;@&quot; não deve ser numérico. Por exemplo: @myAlias_1 e @_1Alias estão corretos; considerando que @myAlias#1 e @1Alias estão incorretas.

Depois de adicionar quaisquer dados adicionais, você pode aplicar um nível de filtro adicional aos dados inicialmente direcionados criando condições com base nos dados adicionais definidos.

>[!NOTE]
>
>Por padrão, a **[!UICONTROL Remove duplicate rows (DISTINCT)]** opção é marcada na guia **[!UICONTROL Advanced options]** do **[!UICONTROL Additional data]** query. Se a **[!UICONTROL Query]** atividade contiver muitos (de 100) dados adicionais definidos, é recomendável desmarcar essa opção por motivos de desempenho. Observe que desmarcar essa opção pode resultar na obtenção de duplicados, dependendo dos dados consultados.

Um caso de uso sobre como personalizar um email com dados adicionais é apresentado [nesta seção](../../automating/using/personalizing-email-with-additional-data.md).

### Adicionar um campo simples {#adding-a-simple-field}

Ao adicionar um campo simples como dados adicionais, esse campo se torna diretamente visível na transição de saída da atividade. Isso permite que o usuário verifique, por exemplo, se os dados do query são os dados desejados.

1. Na **[!UICONTROL Additional data]** guia, adicione um novo elemento.
1. Na janela que é aberta, no **[!UICONTROL Expression]** campo, selecione um dos campos disponíveis diretamente no targeting dimension ou em uma das dimensões vinculadas. É possível editar expressões e usar funções ou cálculos simples (exceto agregações) dos campos de dimensão.

   Uma expressão **[!UICONTROL Alias]** será criada automaticamente se você editar uma  que não seja um caminho XPATH simples (por exemplo: &quot;Year(&lt;@bornDate>)&quot;). Se quiser, você pode modificá-la. Se você selecionar apenas um campo (por exemplo: &quot;@age&quot;), você não precisa definir um **[!UICONTROL Alias]**.

1. Selecione **[!UICONTROL Add]** para confirmar a adição do campo aos dados adicionais. Quando o query for executado, uma coluna adicional correspondente ao campo adicionado estará presente na transição de saída da atividade.

![](assets/enrichment_add_simple_field.png)

### Adicionar uma agregação {#adding-an-aggregate}

As Agregações permitem que os valores sejam calculados a partir de campos do targeting dimension ou de campos de dimensões vinculados ao targeting dimension. Por exemplo: a quantia média adquirida por um perfil.
Ao usar agregação com query, sua função pode retornar a zero, que é então considerado como NULL. Use a **[!UICONTROL Output filtering]** guia do query para filtrar o valor agregado:

* se quiser valores zero, você deve filtrar **[!UICONTROL is null]**.
* se você não quiser que valores zero filtrem **[!UICONTROL is not null]**.

Observe que, se você precisar aplicar a classificação na agregação, deverá filtrar valores zero ou o valor NULL será exibido como o maior número.

1. Na **[!UICONTROL Additional data]** guia, adicione um novo elemento.
1. Na janela que é aberta, selecione a coleção que deseja usar para criar sua agregação no **[!UICONTROL Expression]** campo.

   Um evento **[!UICONTROL Alias]** é criado automaticamente. Se desejar, você pode modificá-la voltando para a guia query **[!UICONTROL Additional data]** .

   A janela de definição de agregação é aberta.

1. Defina uma agregação na **[!UICONTROL Data]** guia. Dependendo do tipo de agregação selecionado, somente os elementos cujos dados são compatíveis estão disponíveis no **[!UICONTROL Expression]** campo. Por exemplo, uma soma só pode ser calculada com dados numéricos.

   ![](assets/enrichment_add_aggregate.png)

   É possível adicionar várias agregações para os campos da coleção selecionada. Certifique-se de definir rótulos explícitos para distinguir as diferentes colunas nos detalhes dos dados de saída da atividade.

   Você também pode alterar os aliases que são definidos automaticamente para cada agregação.

   ![](assets/enrichment_add_aggregate2.png)

1. Se necessário, é possível adicionar um filtro para limitar os dados considerados.

   Consulte a seção [Filtragem de dados](#filtering-added-data) adicionados.

1. Selecione **[!UICONTROL Confirm]** para adicionar agregações.

>[!NOTE]
>
>Não é possível criar uma expressão que contenha uma agregação diretamente do **[!UICONTROL Expression]** campo da **[!UICONTROL New additional data]** janela.

### Adicionar uma coleção {#adding-a-collection}

1. Na **[!UICONTROL Additional data]** guia, adicione um novo elemento.
1. Na janela que é aberta, selecione a coleção que deseja adicionar no **[!UICONTROL Expression]** campo. Um evento **[!UICONTROL Alias]** é criado automaticamente. Se desejar, você pode modificá-la voltando para a guia query **[!UICONTROL Additional data]** .
1. Selecione **[!UICONTROL Add]**. Uma nova janela é aberta, permitindo que você refine os dados de coleta que deseja exibir.
1. Na **[!UICONTROL Parameters]** guia, selecione **[!UICONTROL Collection]** e defina o número de linhas da coleção que deseja adicionar. Por exemplo, se você deseja obter as três compras mais recentes realizadas por cada perfil, digite &quot;3&quot; no **[!UICONTROL Number of lines to return]** campo.

   >[!NOTE]
   >
   >É necessário digitar um número maior ou igual a 1.

1. Na **[!UICONTROL Data]** guia, defina os campos da coleção que deseja exibir para cada linha.

   ![](assets/enrichment_add_collection.png)

1. Se desejar, você pode adicionar um filtro para limitar as linhas de coleta consideradas.

   Consulte a seção [Filtragem de dados](#filtering-added-data) adicionados.

1. Se desejar, você pode definir uma classificação de dados.

   Por exemplo, se você selecionou três linhas para retornar na guia **[!UICONTROL Parameters]** e deseja determinar as três compras mais recentes, é possível definir uma classificação decrescente no campo &quot;data&quot; da coleção que corresponde às transações.

1. Refer to the [Sorting additional data](#sorting-additional-data) section.
1. Selecione **[!UICONTROL Confirm]** para adicionar a coleção.

### Filtragem de dados adicionados {#filtering-added-data}

Ao adicionar uma agregação ou uma coleção, você pode especificar um filtro adicional para limitar os dados que deseja exibir.

Por exemplo, se você deseja processar apenas as linhas de coleta de transações com quantias de 50 dólares ou superiores, é possível adicionar uma condição no campo correspondente à quantia da transação na **[!UICONTROL Filter]** guia.

![](assets/enrichment_filter_data.png)

### Classificação de dados adicionais {#sorting-additional-data}

Ao adicionar uma agregação ou coleção aos dados de um query, você pode especificar se deseja aplicar uma classificação - ascendente ou descendente - com base no valor do campo ou da expressão definida.

Por exemplo, se você deseja salvar apenas a transação que foi realizada mais recentemente por um perfil, digite &quot;1&quot; no **[!UICONTROL Number of lines to return]** campo da guia **[!UICONTROL Parameters]** e aplique uma classificação decrescente no campo correspondente à data da transação por meio da **[!UICONTROL Sort]** guia.

![](assets/enrichment_sort_data.png)

### Filtrar os dados direcionados de acordo com dados adicionais {#filtering-the-targeted-data-according-to-additional-data}

Depois que você tiver adicionado dados adicionais, uma nova **[!UICONTROL Output filtering]** guia aparecerá no **[!UICONTROL Query]**. Essa guia permite que você aplique um filtro adicional aos dados inicialmente direcionados na **[!UICONTROL Target]** guia, levando em conta os dados adicionados.

Por exemplo, se você tiver direcionado todos os perfis que realizaram pelo menos uma transação e uma agregação calculando a quantia média de transação realizada para cada perfil tiver sido adicionada ao , você poderá refinar a população calculada inicialmente usando essa média. **[!UICONTROL Additional data]**

Para fazer isso, na **[!UICONTROL Output filtering]** guia, basta adicionar uma condição a esses dados adicionais.

![](assets/enrichment_output_filtering2.png)

![](assets/enrichment_output_filtering.png)
