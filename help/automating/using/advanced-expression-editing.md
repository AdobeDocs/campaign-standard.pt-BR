---
title: Edição de expressões avançadas
seo-title: Edição de expressões avançadas
description: Edição de expressões avançadas
seo-description: O assistente da edição de consulta permite definir expressões avançadas.
page-status-flag: nunca ativado
uuid: a 635 f 999-27 ce -41 e 0-a 88 c -8 a 3882 e 31 efe
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizando
content-type: reference
topic-tags: filtros de dados
discoiquuid: 4375153 c -0621-4 d 4 c-bfcc -66 d 157 f 04 f 6 c
context-tags: Queryfilter, overview; público-alvo, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Advanced expression editing{#advanced-expression-editing}

## About advanced expression editing {#about-advanced-expression-editing}

Editar uma expressão envolve inserir manualmente condições para formar uma regra.

Esse modo permite usar funções avançadas. Essas funções permitem manipular os valores usados para realizar consultas específicas, como manipular datas, sequências, campos numéricos, classificação etc.

Também é possível usar variáveis de eventos durante a edição da expressão. For more on this, refer to the [Customizing activities with events variables](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) section.

É possível editar expressões para:

* Define a query, via the **[!UICONTROL Advanced mode]** option which is available when a rule is added.

   ![](assets/expression_editor_2.png)

* Edite uma expressão em um fluxo de trabalho. Por exemplo, para adicionar dados adicionais a uma atividade.
* Edite uma condição de visibilidade para definir como um bloco no editor de conteúdo HTML é exibido. Nesse caso, a expressão é editada no formato javascript e não oferece o uso de funções avançadas como padrão.

## Edit an expression {#edit-an-expression}

A edição de expressões avançadas permite definir manualmente uma expressão que corresponde especificamente às suas necessidades.

As expressões de edição podem ser usadas na janela Público-alvo ao criar um e-mail ou em uma atividade de consulta ao criar um fluxo de trabalho.

1. Access the expression editing window via one of the methods detailed in the [About advanced expression editing](../../automating/using/advanced-expression-editing.md#about-advanced-expression-editing) section. Envolve os seguintes elementos:

   * Um campo de entrada no qual a expressão é definida.
   * The list of available fields that can be used in the expression and correspond to the targeting dimension of the query (see [Targeting dimensions and resources](../../automating/using/query.md#targeting-dimensions-and-resources)).
   * A lista de funções disponíveis, classificada por categoria.
   ![](assets/expression_editor_1.png)

1. Edite a expressão inserindo uma expressão diretamente no campo correspondente ou usando as listas de campos e funções disponíveis.

   Clicar duas vezes em um campo ou uma expressão a adiciona à expressão na qual o cursor é posicionado.

   É possível usar variáveis de eventos dos fluxos de trabalho para criar uma expressão. For more on this, refer to the [Customizing activities with events variables](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) section.

1. Dê um nome específico à sua regra, se necessário. O nome inserido aparecerá como o nome da regra na área de trabalho do editor de consulta.

Editar uma expressão permite personalizar a expressão Públicos-alvo para direcionar sua população conforme necessário.

**Tópicos relacionados:**

* [Sintaxe de expressão](../../automating/using/advanced-expression-editing.md#expression-syntax)
* [Lista de funções](../../automating/using/list-of-functions.md)

## Expression Syntax {#expression-syntax}

### Standard syntax {#standard-syntax}

As expressões padrão são criadas de uma ou várias condições que respeitam os seguintes elementos de sintaxe:

* Each condition takes the form of **&lt;value1&gt; &lt;comparison operator&gt; &lt;value2&gt;** whereby:

   * **&lt; value 1 &gt;** é um campo ou uma função. For example **@created** for the date a profile was created or **Year(@created)** for the year a profile was created.
   * **&lt; operador de comparação &gt;** é um dos operadores listados na [seção Operadores](../../automating/using/advanced-expression-editing.md#comparison-operators) de comparação. This operator defines the comparison method between **&lt;value1&gt;** and **&lt;value2&gt;**.
   * **&lt; value 2 &gt;** é um campo, uma função ou um valor inserido manualmente.
   >[!NOTE]
   >
   >The **&lt;value1&gt;** and **&lt;value2&gt;** type data must be identical. For example, if **&lt;value1&gt;** is a date, then **&lt;value2&gt;** must also be a date.

* Se você quiser usar várias condições, elas poderão ser combinadas usando operadores lógicos.

   * **[!UICONTROL AND]**: duas condições são intersecionadas.
   * **[!UICONTROL OR]**: duas condições são combinadas.

Por exemplo:

```
Year(@created) = Year(GetDate()) AND Month(@created) = Month(GetDate())
```

Neste exemplo, os perfis cuja data de criação está no mês e ano atual são direcionados.

### JavaScript syntax {#javascript-syntax}

Ao definir as condições de visibilidade de um bloco de tipo de texto do editor de conteúdo HTML, é necessário usar uma expressão com a sintaxe do tipo javascript.

As expressões javascript são criadas de uma ou várias condições, e usam os seguintes elementos de sintaxe:

* Each condition takes the form of **&lt;context&gt; &lt;comparison operator&gt; &lt;value2&gt;** whereby:

   * **&lt; context &gt;** é um campo ou uma função que permite especificar o contexto. For example **context.profile.@email** for a profile's email address or **context.profile.firstName.length()** for the number of characters of a profile's first name.
   * **&lt; operador de comparação &gt;** é um dos operadores listados na [seção Operadores](../../automating/using/advanced-expression-editing.md#comparison-operators) de comparação. This operator defines the comparison method between **&lt;context&gt;** and **&lt;value2&gt;**.
   * **&lt; value 2 &gt;** é um campo, uma função ou um valor inserido manualmente.
   >[!NOTE]
   The **&lt;context&gt;** and **&lt;value2&gt;** type data must be identical. For example, if **&lt;context&gt;** is a date, then **&lt;value2&gt;** must also be a date.

* Se você quiser usar várias condições, elas poderão ser combinadas usando operadores lógicos.

   * **[!UICONTROL &&]**: duas condições são intersecionadas.
   * **[!UICONTROL ||]**: duas condições são combinadas.

Por exemplo:

```
context.profile.age > 21 && context.profile.firstName.length() > 0
```

In this example, profiles older than 21 years of age and whose first name has been provided (symbolized by the fact that the **firstName** field contains at least one character).

## Comparison operators {#comparison-operators}

Para algumas regras, o editor de consultas permite escolher um valor para definir sua condição.

As condições devem ser vinculadas a valores usando um dos seguintes operadores.

<table> 
 <thead> 
  <tr> 
   <th> Operator<br /> </th> 
   <th> Standard syntax<br /> </th> 
   <th> JavaScript syntax<br /> </th> 
   <th> Description<br /> </th> 
   <th> Example<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <span class="uicontrol">Igual a</span><br /> </td> 
   <td> =<br /> </td> 
   <td> ==<br /> </td> 
   <td> The first value must be completely identical to the second value.<br /> </td> 
   <td> <strong>@ Lastname = Martin</strong> recupera perfis cujo sobrenome é'Martin ', somente estes caracteres idênticos.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Maior que</span><br /> </td> 
   <td> &gt;<br /> </td> 
   <td> &gt;<br /> </td> 
   <td> The first value must categorically be more than the second value.<br /> </td> 
   <td> <strong>@ age &gt; 50</strong> recupera perfis que são mais antigos que "50", portanto "51", "52", etc.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Menor que</span><br /> </td> 
   <td> &lt;<br /> </td> 
   <td> &lt;<br /> </td> 
   <td> The first value must categorically be less than the second value.<br /> </td> 
   <td> <strong>@ criados &lt; daysago (100)</strong> recupera todos os perfis criados no banco de dados há menos de 100 dias.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Maior que ou igual a</span><br /> </td> 
   <td> &gt;=<br /> </td> 
   <td> &gt;=<br /> </td> 
   <td> The first value must be more than or equal to the second value.<br /> </td> 
   <td> <strong>@ age &gt; = 30</strong> recupera perfis com aged 0 anos ou mais.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Menor que ou igual a</span><br /> </td> 
   <td> &lt;=<br /> </td> 
   <td> &lt;=<br /> </td> 
   <td> The first value must be less than or equal to the second value.<br /> </td> 
   <td> <strong>@ age &lt; = 60</strong> recupera perfis com 60 ou menos.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Diferente </span><br /> </td> 
   <td> !=<br /> </td> 
   <td> !=<br /> </td> 
   <td> The first value must be different from the second value.<br /> </td> 
   <td> <strong>@ language!= English</strong> retrieves profiles that have not been defined as English speaking.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Contém</span><br /> </td> 
   <td> IN<br /> </td> 
   <td> N/A<br /> </td> 
   <td> The first value must contain the second value.<br /> </td> 
   <td> <strong>@ domínio IN email</strong>. Aqui, todos os nomes de domínio com o valor "email" são retornados no resultado. Consequently, the 'gmail.com' domain name will make up part of the returned results.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Curtir</span><br /> </td> 
   <td> LIKE<br /> </td> 
   <td> N/A<br /> </td> 
   <td> <span class="uicontrol">Curtir</span> é muito semelhante ao operador <span class="uicontrol">Contém</span> . It lets you insert a <span class="uicontrol">%</span> wild card character in the value that is being searched.<br /> </td> 
   <td> <strong>@ Lastname like Mart % n</strong>. Here, the substitution character <strong>%</strong> serves as a "joker" to find the name "Martin" in the hypothetical case that the spelling is not correct.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Não como</span><br /> </td> 
   <td> NOT<br /> </td> 
   <td> N/A<br /> </td> 
   <td> Is similar to <span class="uicontrol">Like</span>. Isso permite que você não recupere o valor inserido. Here too, the entered value must contain the <span class="uicontrol">%</span> wild card character.<br /> </td> 
   <td> <strong>@ Lastname NOT SMI % h</strong>. Aqui, os destinatários correspondem ao nome'Smi % h ' (so Smith etc.) are not returned as a result.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Está vazio</span><br /> </td> 
   <td> IS NULL<br /> </td> 
   <td> N/A<br /> </td> 
   <td> The first value must correspond to an empty value.<br /> </td> 
   <td> <strong>@ Mobilephone IS NULL</strong> recupera todos os perfis cujo número de telefone móvel não foi fornecido.<br /> </td> 
  </tr> 
 </tbody> 
</table>

