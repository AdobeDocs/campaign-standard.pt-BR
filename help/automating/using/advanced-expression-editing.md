---
title: Edição de expressão avançada
description: O assistente de edição de queries permite definir expressões avançadas.
page-status-flag: never-activated
uuid: a635f999-27ce-41e0-a88c-8a3882e31efe
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: filtering-data
discoiquuid: 4375153c-0621-4d4c-bfcc-66d157f04f6c
context-tags: queryFilter,overview;audience,main
internal: n
snippet: y
translation-type: ht
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e
workflow-type: ht
source-wordcount: '1091'
ht-degree: 100%

---


# Edição de expressão avançada{#advanced-expression-editing}

## Sobre a edição de expressão avançada {#about-advanced-expression-editing}

A edição de uma expressão envolve a inserção manual de condições para formar uma regra.

Esse modo permite usar funções avançadas. Essas funções permitem manipular os valores usados para realizar consultas específicas, como manipular datas, strings, campos numéricos, classificação etc.

Também é possível usar variáveis de eventos ao editar a expressão. Para obter mais informações, consulte a seção [Personalização de atividades com variáveis de eventos](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables).

É possível editar expressões para:

* Definir uma query, por meio da opção **[!UICONTROL Advanced mode]** que está disponível quando uma regra é adicionada.

   ![](assets/expression_editor_2.png)

* Editar uma expressão em um workflow. Por exemplo, para adicionar dados a uma atividade.
* Edite uma condição de visibilidade para definir como um bloco no editor de conteúdo HTML é exibido. Nesse caso, a expressão é editada no formato JavaScript e não oferece o uso de funções avançadas como padrão.

## Editar uma expressão {#edit-an-expression}

A edição de expressão avançada permite definir manualmente uma expressão que corresponde especificamente às suas necessidades.

A edição de expressões pode ser usada na janela Audience ao criar um email ou em uma atividade de Query ao criar um workflow.

1. Acesse a janela de edição de expressões por meio de um dos métodos detalhados na seção [Sobre a edição de expressão avançada](../../automating/using/advanced-expression-editing.md#about-advanced-expression-editing). Envolve os seguintes elementos:

   * Um campo de entrada no qual a expressão é definida.
   * A lista dos campos disponíveis que podem ser usados na expressão e correspondem à dimensão de dimensionamento da query (consulte [Dimensão de dimensionamento e recursos](../../automating/using/query.md#targeting-dimensions-and-resources)).
   * A lista de funções disponíveis, classificadas por categoria.
   ![](assets/expression_editor_1.png)

1. Edite a expressão inserindo uma expressão diretamente no campo correspondente ou usando as listas de campos e funções disponíveis.

   Clicar duas vezes em um campo ou expressão adiciona-o à expressão em que o cursor está inserido.

   É possível usar variáveis de eventos de workflows para criar uma expressão. Para obter mais informações, consulte a seção [Personalização de atividades com variáveis de eventos](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables).

1. Dê um nome específico à sua regra, se necessário. O nome inserido será exibido como o nome da regra no espaço de trabalho do Editor de consultas.

A edição de uma expressão permite personalizar a expressão do Audiences para direcionar sua população conforme necessário.

**Tópicos relacionados:**

* [Sintaxe da expressão](../../automating/using/advanced-expression-editing.md#expression-syntax)
* [Lista de funções](../../automating/using/list-of-functions.md)

## Sintaxe da expressão {#expression-syntax}

### Sintaxe padrão {#standard-syntax}

As expressões padrão são formadas por uma ou várias condições que respeitam os seguintes elementos de sintaxe:

* Cada condição assume a forma de **&lt;value1> &lt;comparison operator> &lt;value2>** em que:

   * **&lt;value1>** é um campo ou uma função. Por exemplo, **@created** para a data em que um perfil foi criado ou **Year(@created)** para o ano em que um perfil foi criado.
   * **&lt;comparison operator>** é um dos operadores listados na seção [Operadores de comparação](../../automating/using/advanced-expression-editing.md#comparison-operators). Esse operador define o método de comparação entre **&lt;value1>** e **&lt;value2>**.
   * **&lt;value2>** é um campo, uma função ou um valor inserido manualmente.
   >[!NOTE]
   >
   >Os dados dos tipos **&lt;value1>** e **&lt;value2>** devem ser idênticos. Por exemplo, se **&lt;value1>** for uma data, **&lt;value2>** também deverá ser uma data.

* Se quiser usar várias condições, elas poderão ser combinadas usando operadores lógicos.

   * **[!UICONTROL AND]**: duas condições são cruzadas.
   * **[!UICONTROL OR]**: duas condições são combinadas.

Por exemplo:

```
Year(@created) = Year(GetDate()) AND Month(@created) = Month(GetDate())
```

Neste exemplo, os perfis cuja data de criação é no mês e ano atuais são direcionados.

### Sintaxe JavaScript {#javascript-syntax}

Ao definir as condições de visibilidade de um bloco de tipo de texto do editor de conteúdo HTML, você deve usar uma expressão com a sintaxe de tipo JavaScript.

As expressões JavaScript são constituídas por uma ou várias condições e usam os seguintes elementos de sintaxe:

* Cada condição assume a forma de **&lt;context> &lt;comparison operator> &lt;value2>** em que:

   * **&lt;context>** é um campo ou uma função que permite especificar o contexto. Por exemplo, **context.perfil.@email** para um endereço de email do perfil ou **context.perfil.firstName.length()** para o número de caracteres do nome do perfil.
   * **&lt;comparison operator>** é um dos operadores listados na seção [Operadores de comparação](../../automating/using/advanced-expression-editing.md#comparison-operators). Esse operador define o método de comparação entre **&lt;context>** e **&lt;value2>**.
   * **&lt;value2>** é um campo, uma função ou um valor inserido manualmente.
   >[!NOTE]
   Os dados dos tipos **&lt;context>** e **&lt;value2>** devem ser idênticos. Por exemplo, se **&lt;context>** for uma data, **&lt;value2>** também deverá ser uma data.

* Se quiser usar várias condições, elas poderão ser combinadas usando operadores lógicos.

   * **[!UICONTROL &&]**: duas condições são cruzadas.
   * **[!UICONTROL ||]**: duas condições são combinadas.

Por exemplo:

```
context.profile.age > 21 && context.profile.firstName.length() > 0
```

Neste exemplo, perfis com mais de 21 anos e cujo nome foi fornecido (simbolizado pelo fato de o campo **firstName** contém pelo menos um caractere).

## Operadores de comparação {#comparison-operators}

Para algumas regras, o Editor de consultas permite escolher um valor para definir sua condição.

As condições devem ser vinculadas a valores usando um dos operadores a seguir.

<table> 
 <thead> 
  <tr> 
   <th> Operador<br /> </th> 
   <th> Sintaxe padrão<br /> </th> 
   <th> Sintaxe JavaScript<br /> </th> 
   <th> Descrição<br /> </th> 
   <th> Exemplo<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <span class="uicontrol">Equal to</span> <br /> </td> 
   <td> =<br /> </td> 
   <td> ==<br /> </td> 
   <td> O primeiro valor deve ser completamente idêntico ao segundo.<br /> </td> 
   <td> <strong>@lastName = Martin</strong> recupera perfis cujo sobrenome é 'Martin', com apenas esses caracteres idênticos.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Greater than</span> <br /> </td> 
   <td> &gt;<br /> </td> 
   <td> &gt;<br /> </td> 
   <td> O primeiro valor deve ser categoricamente maior que o segundo.<br /> </td> 
   <td> <strong>@age &gt; 50</strong> recupera perfis mais antigos que '50', então '51', '52' etc.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Less than</span> <br /> </td> 
   <td> &lt;<br /> </td> 
   <td> &lt;<br /> </td> 
   <td> O primeiro valor deve ser categoricamente menor que o segundo.<br /> </td> 
   <td> <strong>@created &lt; DaysAgo(100)</strong> recupera todos os perfis criados no banco de dados há menos de 100 dias.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Greater than or equal to</span> <br /> </td> 
   <td> &gt;=<br /> </td> 
   <td> &gt;=<br /> </td> 
   <td> O primeiro valor deve ser maior que ou igual ao segundo valor.<br /> </td> 
   <td> <strong>@age &gt;= 30</strong> recupera perfis com 30 anos ou mais.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Less than or equal to</span> <br /> </td> 
   <td> &lt;=<br /> </td> 
   <td> &lt;=<br /> </td> 
   <td> O primeiro valor deve ser menor que ou igual ao segundo.<br /> </td> 
   <td> <strong>@age &lt;= 60</strong> recupera perfis com 60 anos ou menos.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Different </span> <br /> </td> 
   <td> !=<br /> </td> 
   <td> !=<br /> </td> 
   <td> O primeiro valor deve ser diferente do segundo.<br /> </td> 
   <td> <strong>@language != English</strong> recupera perfis que não foram definidos como falantes do inglês.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Contains</span> <br /> </td> 
   <td> IN<br /> </td> 
   <td> N/A<br /> </td> 
   <td> O primeiro valor deve conter o segundo.<br /> </td> 
   <td> <strong>@domain IN mail</strong>. Aqui, todos os nomes de domínios com o valor 'mail' são retornados no resultado. Consequentemente, o nome de domínio 'gmail.com' fará parte dos resultados retornados.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Like</span> <br /> </td> 
   <td> LIKE<br /> </td> 
   <td> N/A<br /> </td> 
   <td> <span class="uicontrol">Like</span> é muito semelhante ao operador <span class="uicontrol">Contains</span>. Permite inserir um caractere curinga <span class="uicontrol">%</span> no valor que está sendo pesquisado.<br /> </td> 
   <td> <strong>@lastName LIKE Mart%n</strong>. Aqui, o caractere de substituição <strong>%</strong> serve como "joker" para encontrar o nome "Martin" no caso hipotético de a ortografia não estar correta.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Not like</span> <br /> </td> 
   <td> NOT<br /> </td> 
   <td> N/A<br /> </td> 
   <td> É semelhante a <span class="uicontrol">Like</span>. Permite que você não recupere o valor inserido. Aqui o valor inserido também deve conter o caractere curinga <span class="uicontrol">%</span>.<br /> </td> 
   <td> <strong>@lastName NOT Smi%h</strong>. Aqui, os destinatários correspondem ao nome 'Smi%h' (então Smith, etc.) não são retornados como resultado.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Is empty</span> <br /> </td> 
   <td> IS NULL<br /> </td> 
   <td> N/A<br /> </td> 
   <td> O primeiro valor deve corresponder a um valor vazio.<br /> </td> 
   <td> <strong>@mobilePhone IS NULL</strong> recupera todos os perfis cujo número de telefone celular não foi fornecido.<br /> </td> 
  </tr> 
 </tbody> 
</table>

