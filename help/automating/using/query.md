---
solution: Campaign Standard
product: campaign
title: Query
description: A atividade Query permite filtrar e extrair uma população de elementos do banco de dados do Adobe Campaign.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: query,main
feature: Workflows
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '1761'
ht-degree: 93%

---


# Query{#query}

## Descrição {#description}

![](assets/query.png)

A atividade **[!UICONTROL Query]** permite filtrar e extrair uma população de elementos do banco de dados do Adobe Campaign. Você pode definir **[!UICONTROL Additional data]** para a população direcionada em uma guia dedicada. Esses dados são armazenados em colunas adicionais e só podem ser usados para o workflow em andamento.

A atividade usa a ferramenta Editor de consultas. Essa ferramenta é detalhada em uma [seção dedicada](../../automating/using/editing-queries.md#about-query-editor).

**Tópicos relacionados:**

* [Amostras de queries](../../automating/using/query-samples.md)
* [Caso de uso: workflow de redirecionamento enviando um novo delivery para não abridores](../../automating/using/workflow-cross-channel-retargeting.md)

## Contexto de uso {#context-of-use}

A atividade **[!UICONTROL Query]** pode ser usada para várias finalidades:

* Segmentação de indivíduos para definir o público-alvo ou o público de uma mensagem, etc.
* Enriquecimento dos dados da tabela do banco de dados do Adobe Campaign.
* Exportação de dados.

## Configuração {#configuration}

1. Arraste e solte uma atividade **[!UICONTROL Query]** no seu fluxo de trabalho.
1. Selecione e abra a atividade usando o botão ![](assets/edit_darkgrey-24px.png) das ações rápidas exibidas. Por padrão, a atividade é pré-configurada para procurar perfis.
1. Se você quiser executar um query em um recurso diferente do perfil, vá para a guia **[!UICONTROL Properties]** da atividade e selecione um **[!UICONTROL Resource]** e um **[!UICONTROL Targeting dimension]**.

   O **[!UICONTROL Resource]** permite refinar os filtros exibidos na paleta, enquanto o **[!UICONTROL Targeting dimension]**, contextual em relação ao recurso selecionado, corresponde ao tipo de população que você gostaria de obter (perfis identificados, deliveries, dados vinculados ao recurso selecionado, etc.).

   Para saber mais, consulte [Targeting dimensions e recursos](#targeting-dimensions-and-resources).

1. Na guia **[!UICONTROL Target]**, execute o query definindo e combinando regras.

   >[!NOTE]
   >
   >Ao direcionar um público-alvo, observe que a definição do público-alvo não é referenciada, mas **copiada** no query. Se você fizer qualquer alteração no público-alvo depois que ele tiver sido direcionado em um query, certifique-se de configurar o query novamente para considerar a nova definição.

1. Você pode definir **[!UICONTROL Additional data]** para a população direcionada em uma guia dedicada. Esses dados são armazenados em colunas adicionais e só podem ser usados para o workflow em andamento. Especificamente, você pode adicionar dados das tabelas do banco de dados do Adobe Campaign vinculadas ao targeting dimension do query. Consulte a seção [Enriquecimento de dados](#enriching-data).

   >[!NOTE]
   >
   >Por padrão, a opção **[!UICONTROL Remove duplicate rows (DISTINCT)]** está marcada nas **[!UICONTROL Advanced options]** da guia **[!UICONTROL Additional data]** do query. Se a atividade **[!UICONTROL Query]** contiver vários (de 100) dados adicionais definidos, é recomendável desmarcar essa opção para otimizar o desempenho. Observe que se essa opção for desmarcada, poderão ocorrer duplicatas, dependendo dos dados consultados.

1. Na guia **[!UICONTROL Transition]**, a opção **[!UICONTROL Enable an outbound transition]** permite adicionar uma transição de saída após a atividade de query, mesmo que ela não recupere dados.

   O código de segmento da transição de saída pode ser personalizado usando uma expressão padrão e variáveis de eventos (consulte [esta página](../../automating/using/customizing-workflow-external-parameters.md)).

1. Confirme a configuração da sua atividade e salve o fluxo de trabalho.

## Targeting dimensions e recursos {#targeting-dimensions-and-resources}

Os targeting dimensions e os recursos permitem definir em quais elementos um query se baseará para determinar o público alvo de um delivery.

Eles são configurados em [target mappings](../../administration/using/target-mappings-in-campaign.md) e são definidos ao criar um workflow, na guia **[!UICONTROL Properties]** de uma atividade Query .

>[!NOTE]
>
>O targeting dimension também pode ser definido ao criar um público-alvo (consulte [esta seção](../../audiences/using/creating-audiences.md)).

![](assets/targeting_dimension1.png)

Os targeting dimensions e os recursos estão vinculados. Os targeting dimensions disponíveis dependem, portanto, do recurso selecionado.

Por exemplo, para o recurso **[!UICONTROL Profiles (profile)]**, os seguintes targeting dimensions estarão disponíveis:

![](assets/targeting_dimension2.png)

No caso de **[!UICONTROL Deliveries (delivery)]**, a lista conterá os seguintes targeting dimensions:

![](assets/targeting_dimension3.png)

Depois que o targeting dimension e o recurso são especificados, filtros diferentes ficam disponíveis no query.

Exemplo de filtros disponíveis para o recurso **[!UICONTROL Profiles (profile)]**:

![](assets/targeting_dimension4.png)

Exemplo de filtros disponíveis para o recurso **[!UICONTROL Deliveries (delivery)]**:

![](assets/targeting_dimension5.png)

Por padrão, o targeting dimension e o recurso são definidos para direcionar perfis. Entretanto, convém usar um recurso diferente do targeting dimension se você quiser procurar um registro específico em uma tabela distante.

Para obter mais informações, consulte este caso de uso: [Uso de recursos diferentes de targeting dimensions](../../automating/using/using-resources-different-from-targeting-dimensions.md)

## Enriquecimento de dados {#enriching-data}

A guia **[!UICONTROL Additional data]** das atividades **[!UICONTROL Query]**, **[!UICONTROL Incremental query]** e **[!UICONTROL Enrichment]** permite enriquecer os dados direcionados e transferi-los para as seguintes atividades de fluxo de trabalho, onde podem ser utilizados. Você pode adicionar especificamente:

* Dados simples
* Agregados
* Coleções

Para agregações e coleções, um **[!UICONTROL Alias]** é automaticamente definido para atribuir uma ID técnica a uma expressão complexa. Esse alias, que deve ser exclusivo, permite que as agregações e coleções sejam facilmente encontradas depois. Você pode modificá-lo para atribuir a ele um nome facilmente reconhecível.

>[!NOTE]
>
>Os aliases devem respeitar as seguintes regras de sintaxe: apenas caracteres alfanuméricos e os caracteres “_” são autorizados. Os aliases diferenciam maiúsculas de minúsculas. O alias deve iniciar com o caractere “@”. O caractere imediatamente após “@” não deve ser numérico. Por exemplo: @myAlias_1 e @_1Alias estão corretos, ao contrário de @myAlias#1 e @1Alias.

Após adicionar dados adicionais, você poderá aplicar mais um nível de filtro aos dados inicialmente direcionados criando condições com base nos dados adicionais definidos.

>[!NOTE]
>
>Por padrão, a opção **[!UICONTROL Remove duplicate rows (DISTINCT)]** está marcada nas **[!UICONTROL Advanced options]** da guia **[!UICONTROL Additional data]** do query. Se a atividade **[!UICONTROL Query]** contiver vários (de 100) dados adicionais definidos, é recomendável desmarcar essa opção para otimizar o desempenho. Observe que se essa opção for desmarcada, poderão ocorrer duplicatas, dependendo dos dados consultados.

Um caso de uso sobre como personalizar um email com dados adicionais é apresentado em [this section](../../automating/using/personalizing-email-with-additional-data.md).

### Adição de um campo simples {#adding-a-simple-field}

Ao incluir um campo simples como dados adicionais, esse campo ficará diretamente visível na transição de saída da atividade. Isso permite que o usuário verifique, por exemplo, se os dados do query são os desejados.

1. Na guia **[!UICONTROL Additional data]**, adicione um novo elemento.
1. Na janela aberta, no campo **[!UICONTROL Expression]**, selecione um dos campos disponíveis diretamente no targeting dimension ou em uma das dimensões vinculadas. Você pode editar expressões e usar funções ou cálculos simples (exceto agregações) dos campos de dimensão.

   Um **[!UICONTROL Alias]** será automaticamente criado se você editar uma expressão diferente de um caminho XPATH simples (por exemplo: “Year(&lt;@birthDate>)”). Se quiser, você poderá modificá-lo. Se selecionar apenas um campo (por exemplo: “@age”), você não precisará definir um **[!UICONTROL Alias]**.

1. Selecione **[!UICONTROL Add]** para confirmar a inclusão do campo nos dados adicionais. Quando o query for executado, uma coluna adicional correspondente ao campo adicionado estará presente na transição de saída da atividade.

![](assets/enrichment_add_simple_field.png)

### Adição de uma agregação {#adding-an-aggregate}

As agregações permitem que os valores sejam calculados dos campos do targeting dimension ou das dimensões vinculadas ao targeting dimension. Por exemplo: o valor médio adquirido por um perfil.
Quando você usar a agregação com o query, sua função poderá retornar para zero, que será considerada como NULL. Use a guia **[!UICONTROL Output filtering]** do query para filtrar o valor agregado:

* se quiser valores zero, você deverá filtrar em **[!UICONTROL is null]**.
* se não quiser valores zero, você deverá filtrar em **[!UICONTROL is not null]**.

Observe que, se precisar aplicar a classificação na agregação, você deverá filtrar os valores zero, caso contrário, o valor NULL será exibido como o maior número.

1. Na guia **[!UICONTROL Additional data]**, adicione um novo elemento.
1. Na janela aberta, selecione a coleção que deseja usar para criar sua agregação no campo **[!UICONTROL Expression]**.

   Um evento **[!UICONTROL Alias]** é criado automaticamente. Se quiser, você poderá modificá-lo voltando para a guia **[!UICONTROL Additional data]** do query.

   A janela de definição da agregação é aberta.

1. Defina uma agregação na guia **[!UICONTROL Data]**. Dependendo do tipo de agregação selecionado, somente os elementos com dados compatíveis estarão disponíveis no campo **[!UICONTROL Expression]**. Por exemplo, uma soma só pode ser calculada com dados numéricos.

   ![](assets/enrichment_add_aggregate.png)

   Você pode adicionar várias agregações para os campos da coleção selecionada. Defina rótulos explícitos para distinguir as diferentes colunas nos detalhes dos dados de saída da atividade.

   Você também pode alterar os aliases definidos automaticamente para cada agregação.

   ![](assets/enrichment_add_aggregate2.png)

1. Se for necessário, você poderá adicionar um filtro para limitar os dados considerados.

   Consulte a seção [Filtragem dos dados adicionados](#filtering-added-data).

1. Selecione **[!UICONTROL Confirm]** para adicionar agregações.

>[!NOTE]
>
>Não é possível criar uma expressão contendo uma agregação diretamente do campo **[!UICONTROL Expression]** da janela **[!UICONTROL New additional data]**.

### Adição de uma coleção {#adding-a-collection}

1. Na guia **[!UICONTROL Additional data]**, adicione um novo elemento.
1. Na janela aberta, selecione a coleção que deseja adicionar ao campo **[!UICONTROL Expression]**. Um evento **[!UICONTROL Alias]** é criado automaticamente. Se quiser, você poderá modificá-lo voltando para a guia **[!UICONTROL Additional data]** do query.
1. Selecione **[!UICONTROL Add]**. Uma nova janela é aberta, para que você refine os dados de coleção que deseja exibir.
1. Na guia **[!UICONTROL Parameters]**, selecione **[!UICONTROL Collection]** e defina o número de linhas da coleção que deseja adicionar. Por exemplo, se você quiser obter as três compras mais recentes realizadas por cada perfil, digite “3” no campo **[!UICONTROL Number of lines to return]**.

   >[!NOTE]
   >
   >É necessário digitar um número maior ou igual a 1.

1. Na guia **[!UICONTROL Data]**, defina os campos da coleção que deseja exibir para cada linha.

   ![](assets/enrichment_add_collection.png)

1. Se desejar, você poderá adicionar um filtro para limitar as linhas da coleção consideradas.

   Consulte a seção [Filtragem dos dados adicionados](#filtering-added-data).

1. Se desejar, você poderá definir uma classificação de dados.

   Por exemplo, se você tiver selecionado três linhas a serem retornadas na guia **[!UICONTROL Parameters]** e quiser determinar as três compras mais recentes, poderá definir uma classificação decrescente no campo “date” da coleção que corresponde às transações.

1. Consulte a seção [Classificação de dados adicionais](#sorting-additional-data).
1. Selecione **[!UICONTROL Confirm]** para adicionar a coleção.

### Filtragem dos dados adicionados {#filtering-added-data}

Ao adicionar uma agregação ou uma coleção, você pode especificar um filtro adicional para limitar os dados que deseja exibir.

Por exemplo, se você quiser processar apenas as linhas da coleção das transações de 50 dólares e superiores, poderá adicionar uma condição no campo correspondente ao valor da transação da guia **[!UICONTROL Filter]**.

![](assets/enrichment_filter_data.png)

### Classificação de dados adicionais {#sorting-additional-data}

Ao adicionar uma agregação ou coleção aos dados de um query, você poderá especificar se deseja aplicar uma classificação crescente ou decrescente com base no valor do campo ou da expressão definida.

Por exemplo, se quiser salvar apenas a transação que foi executada mais recentemente por um perfil, digite “1” no campo **[!UICONTROL Number of lines to return]** da guia **[!UICONTROL Parameters]** e aplique uma classificação decrescente no campo correspondente à data da transação usando a guia **[!UICONTROL Sort]**.

![](assets/enrichment_sort_data.png)

### Filtragem dos dados direcionados de acordo com os dados adicionais {#filtering-the-targeted-data-according-to-additional-data}

Depois de incluir os dados adicionais, uma nova guia **[!UICONTROL Output filtering]** aparecerá no **[!UICONTROL Query]**. Essa guia permite aplicar um outro filtro aos dados inicialmente direcionados na guia **[!UICONTROL Target]**, considerando os dados adicionados.

Por exemplo, se você tiver direcionado todos os perfis que executaram pelo menos uma transação e uma agregação calculando o valor médio da transação realizado para cada perfil que foi adicionado aos **[!UICONTROL Additional data]**, você poderá refinar a população calculada inicialmente usando essa média.

Para isso, na guia **[!UICONTROL Output filtering]**, adicione uma condição a esses dados adicionais.

![](assets/enrichment_output_filtering2.png)

![](assets/enrichment_output_filtering.png)
