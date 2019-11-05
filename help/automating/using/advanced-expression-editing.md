---
title: Edição de expressão avançada
description: O assistente de edição de consulta permite definir expressões avançadas.
page-status-flag: nunca ativado
uuid: a635f999-27ce-41e0-a88c-8a3882e31efe
contentOwner: molviato
products: SG_CAMPAIGN/STANDARD
audience: automatização
content-type: referência
topic-tags: filtragem de dados
discoiquuid: 4375153c-0621-4d4c-bfcc-66d157f04f6c
context-tags: queryFilter,overview;audience,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Edição de expressão avançada{#advanced-expression-editing}

## Sobre a edição de expressões avançadas {#about-advanced-expression-editing}

A edição de uma expressão envolve a inserção manual de condições para formar uma regra.

Esse modo permite usar funções avançadas. Essas funções permitem manipular os valores usados para realizar consultas específicas, como manipular datas, sequências, campos numéricos, classificação etc.

Também é possível usar variáveis de eventos ao editar expressões. Para obter mais informações, consulte a seção [Personalizar atividades com variáveis](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) de eventos.

É possível editar expressões para:

* Defina uma consulta, por meio da **[!UICONTROL Advanced mode]** opção que está disponível quando uma regra é adicionada.

   ![](assets/expression_editor_2.png)

* Edite uma expressão em um fluxo de trabalho. Por exemplo, para adicionar dados adicionais a uma atividade.
* Edite uma condição de visibilidade para definir como um bloco no editor de conteúdo HTML é exibido. Nesse caso, a expressão é editada no formato JavaScript e não oferece o uso de funções avançadas como padrão.

## Editar uma expressão {#edit-an-expression}

A edição de expressão avançada permite definir manualmente uma expressão que corresponde especificamente às suas necessidades.

As expressões de edição podem ser usadas na janela Público-alvo ao criar um email ou em uma atividade de Consulta ao criar um fluxo de trabalho.

1. Acesse a janela de edição de expressão por meio de um dos métodos detalhados na seção [Sobre edição](../../automating/using/advanced-expression-editing.md#about-advanced-expression-editing) de expressões avançadas. Envolve os seguintes elementos:

   * Um campo de entrada no qual a expressão é definida.
   * A lista de campos disponíveis que podem ser usados na expressão e correspondem à dimensão de direcionamento da consulta (consulte Dimensões e recursos [de](../../automating/using/query.md#targeting-dimensions-and-resources)direcionamento).
   * A lista de funções disponíveis, classificadas por categoria.
   ![](assets/expression_editor_1.png)

1. Edite a expressão inserindo uma expressão diretamente no campo correspondente ou usando as listas de campos e funções disponíveis.

   Clicar duas vezes em um campo ou em uma expressão o adiciona à expressão na qual o cursor é colocado.

   É possível usar as variáveis de eventos de fluxos de trabalho para criar uma expressão. Para obter mais informações, consulte a seção [Personalizar atividades com variáveis](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) de eventos.

1. Dê um nome específico à sua regra, se necessário. O nome inserido será exibido como o nome da regra na área de trabalho do editor de consultas.

Editar uma expressão permite personalizar a expressão Públicos-alvo para direcionar sua população, conforme necessário.

**Tópicos relacionados:**

* [Sintaxe de expressão](../../automating/using/advanced-expression-editing.md#expression-syntax)
* [Lista de funções](../../automating/using/list-of-functions.md)

## Sintaxe de expressão {#expression-syntax}

### Sintaxe padrão {#standard-syntax}

As expressões padrão são compostas de uma ou várias condições que respeitam os seguintes elementos de sintaxe:

* Cada condição assume a forma de **&lt;valor1&gt; &lt;operador de comparação&gt; &lt;valor2&gt;** , em que:

   * **&lt;value1&gt;** é um campo ou uma função. Por exemplo, **@created** para a data em que um perfil foi criado ou **Year(@created)** para o ano em que um perfil foi criado.
   * **&lt;operador de comparação&gt;** é um dos operadores listados na seção operadores [de](../../automating/using/advanced-expression-editing.md#comparison-operators) comparação. Este operador define o método de comparação entre **&lt;value1&gt;** e **&lt;value2&gt;**.
   * **&lt;value2&gt;** é um campo, uma função ou um valor inserido manualmente.
   >[!NOTE]
   >
   >Os dados dos tipos **&lt;value1&gt;** e **&lt;value2&gt;** devem ser idênticos. Por exemplo, se **&lt;valor1&gt;** for uma data, **&lt;valor2&gt;** também deverá ser uma data.

* Se você quiser usar várias condições, elas poderão ser combinadas usando operadores lógicos.

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

* Cada condição assume a forma de **&lt;contexto&gt; &lt;operador de comparação&gt; &lt;valor2&gt;** , em que:

   * **&lt;context&gt;** é um campo ou uma função que permite especificar o contexto. Por exemplo, **context.profile.@email** para o endereço de email de um perfil ou **context.profile.firstName.length()** para o número de caracteres do nome de um perfil.
   * **&lt;operador de comparação&gt;** é um dos operadores listados na seção operadores [de](../../automating/using/advanced-expression-editing.md#comparison-operators) comparação. Este operador define o método de comparação entre **&lt;context&gt;** e **&lt;value2&gt;**.
   * **&lt;value2&gt;** é um campo, uma função ou um valor inserido manualmente.
   >[!NOTE]
   Os dados dos tipos **&lt;context&gt;** e **&lt;value2&gt;** devem ser idênticos. Por exemplo, se **&lt;contexto&gt;** for uma data, **&lt;valor2&gt;** também deverá ser uma data.

* Se você quiser usar várias condições, elas poderão ser combinadas usando operadores lógicos.

   * **[!UICONTROL &&]**: duas condições são cruzadas.
   * **[!UICONTROL ||]**: duas condições são combinadas.

Por exemplo:

```
context.profile.age > 21 && context.profile.firstName.length() > 0
```

Neste exemplo, perfis com mais de 21 anos e cujo nome foi fornecido (simbolizado pelo fato de o campo **firstName** conter pelo menos um caractere).

## Operadores de comparação {#comparison-operators}

Para algumas regras, o editor de consultas permite que você escolha um valor para definir sua condição.

As condições devem ser vinculadas aos valores usando um dos seguintes operadores.

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
   <td> <span class="uicontrol">Igual</span> a <br /> </td> 
   <td> =<br /> </td> 
   <td> ==<br /> </td> 
   <td> O primeiro valor deve ser completamente idêntico ao segundo.<br /> </td> 
   <td> <strong>@lastName = Martin</strong> recupera perfis cujo sobrenome é 'Martin', com apenas esses caracteres idênticos.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Maior que</span><br /> </td> 
   <td> &gt;<br /> </td> 
   <td> &gt;<br /> </td> 
   <td> O primeiro valor deve ser categoricamente maior que o segundo.<br /> </td> 
   <td> <strong>@age &gt; 50</strong> recupera perfis mais antigos que '50', portanto '51', '52' etc.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Menor que</span><br /> </td> 
   <td> &lt;<br /> </td> 
   <td> &lt;<br /> </td> 
   <td> O primeiro valor deve ser categoricamente menor que o segundo.<br /> </td> 
   <td> <strong>@created &lt; DaysAgo(100)</strong> recupera todos os perfis criados no banco de dados há menos de 100 dias.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Maior que ou igual a</span><br /> </td> 
   <td> &gt;=<br /> </td> 
   <td> &gt;=<br /> </td> 
   <td> O primeiro valor deve ser maior ou igual ao segundo.<br /> </td> 
   <td> <strong>@age &gt;= 30</strong> recupera perfis com mais de 30 anos.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Menor que ou igual</span> a <br /> </td> 
   <td> &lt;=<br /> </td> 
   <td> &lt;=<br /> </td> 
   <td> O primeiro valor deve ser menor ou igual ao segundo.<br /> </td> 
   <td> <strong>@age &lt;= 60</strong> recupera perfis com 60 anos ou menos.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Diferente </span><br /> </td> 
   <td> !=<br /> </td> 
   <td> !=<br /> </td> 
   <td> O primeiro valor deve ser diferente do segundo.<br /> </td> 
   <td> <strong>@idioma!= inglês</strong> recupera perfis que não foram definidos como inglês.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Contém</span><br /> </td> 
   <td> IN<br /> </td> 
   <td> N/A<br /> </td> 
   <td> O primeiro valor deve conter o segundo.<br /> </td> 
   <td> <strong>@domínio IN mail</strong>. Aqui, todos os nomes de domínio com o valor 'mail' são retornados no resultado. Consequentemente, o nome de domínio 'gmail.com' fará parte dos resultados retornados.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Curtir</span><br /> </td> 
   <td> CURTIR<br /> </td> 
   <td> N/A<br /> </td> 
   <td> <span class="uicontrol">Like</span> é muito semelhante ao operador <span class="uicontrol">Contains</span> . Permite inserir um caractere curinga <span class="uicontrol">%</span> no valor que está sendo pesquisado.<br /> </td> 
   <td> <strong>@lastName LIKE Mart%n</strong>. Aqui, o caractere de substituição <strong>%</strong> serve como "brincalhão" para encontrar o nome "Martin" no caso hipotético de a ortografia não estar correta.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Não é como</span><br /> </td> 
   <td>  NOT<br /> </td> 
   <td> N/A<br /> </td> 
   <td> Is similar to <span class="uicontrol">Like</span>. Isso permite que você não recupere o valor inserido. Here too, the entered value must contain the <span class="uicontrol">%</span> wild card character.<br /> </td> 
   <td> <strong>@lastName NOT Smi%h</strong>. Aqui, os destinatários correspondem ao nome 'Smi%h' (então Smith, etc.) não são retornados como resultado.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Está vazio</span><br /> </td> 
   <td> É NULO<br /> </td> 
   <td> N/A<br /> </td> 
   <td> O primeiro valor deve corresponder a um valor vazio.<br /> </td> 
   <td> <strong>@mobilePhone IS NULL</strong> recupera todos os perfis cujo número de telefone celular não foi fornecido.<br /> </td> 
  </tr> 
 </tbody> 
</table>

