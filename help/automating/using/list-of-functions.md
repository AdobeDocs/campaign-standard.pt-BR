---
title: Lista de funções
seo-title: Lista de funções
description: Lista de funções
seo-description: A ferramenta de edição de consulta permite usar funções avançadas para realizar filtragem complexa.
page-status-flag: nunca ativado
uuid: fd 50 fc 99-1 e 7 a -479 b-beb 7-1 f 246 b 419 d 46
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizando
content-type: reference
topic-tags: filtros de dados
discoiquuid: 3 cdbe 962-1 c 59-4 cd 8-b 29 e -36 aa 2562 fac 6
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 83be3f22f3508248f2a4666080a7207998093dc3

---


# Lista de funções{#list-of-functions}

## Sobre funções {#about-functions}

A ferramenta de edição de consulta permite usar funções avançadas para realizar filtragem complexa. Para fazer isso, a paleta de ferramentas contém o **[!UICONTROL Expression]** elemento que pode ser usado na área de trabalho. Mais informações sobre esse elemento são detalhadas em uma [seção específica](../../automating/using/advanced-expression-editing.md).

Esse elemento permite que você insira suas condições manualmente. Aqui, você pode usar as funções definidas nas seções a seguir.

Vários tipos de função estão disponíveis, dependendo dos resultados desejados e dos tipos de dados manipulados:

* Datas
* Geomarketing
* Valores numéricos
* Outras funções
* Agregados
* Manipulação de string
* Classificação

## Datas {#dates}

As funções de data são usadas para manipular valores de data ou hora.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Nome</strong><br /> </td> 
   <td> <strong>Descrição</strong><br /> </td> 
   <td> <strong>Sintaxe</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Adddays</strong><br /> </td> 
   <td> Adiciona um número de dias a uma data<br /> </td> 
   <td> Adddays (&lt; data &gt;, &lt; número &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Addhours</strong><br /> </td> 
   <td> Adiciona um número de horas a uma data<br /> </td> 
   <td> Addhours (&lt; date &gt;, &lt; número &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Addminutes</strong><br /> </td> 
   <td> Adiciona vários minutos a uma data<br /> </td> 
   <td> Addminutes (&lt; data &gt;, &lt; número &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Addcher</strong><br /> </td> 
   <td> Adiciona vários meses a uma data<br /> </td> 
   <td> Addcher (&lt; data &gt;, &lt; número &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Addseconds</strong><br /> </td> 
   <td> Adiciona vários segundos a uma data<br /> </td> 
   <td> Addseconds (&lt; data &gt;, &lt; número &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Addyear</strong><br /> </td> 
   <td> Adiciona vários anos a uma data<br /> </td> 
   <td> Addyears (&lt; data &gt;, &lt; número &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Dateonly</strong><br /> </td> 
   <td> Retorna somente a data (com o tempo em 00:00)<br /> </td> 
   <td> Dateonly (&lt; date &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Dia</strong><br /> </td> 
   <td> Retorna o número que representa o dia da data<br /> </td> 
   <td> Dia (&lt; data &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Dayofyear</strong><br /> </td> 
   <td> Retorna um número representando o dia no ano da data<br /> </td> 
   <td> Dayofyear (&lt; date &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Daysago</strong><br /> </td> 
   <td> Retorna a data atual menos n dias<br /> </td> 
   <td> Daysago (&lt; número &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Daysagoint</strong><br /> </td> 
   <td> Retorna a data atual menos n dias (como um número inteiro aaaammdd)<br /> </td> 
   <td> Daysagoint (&lt; número &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Daysdiff</strong><br /> </td> 
   <td> Número de dias entre duas datas<br /> </td> 
   <td> Daysdiff (&lt; data final &gt;, &lt; data de início &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Daypaid</strong><br /> </td> 
   <td> Retorna a idade em dias de uma data<br /> </td> 
   <td> Dayvendidas (&lt; date &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Getdate</strong><br /> </td> 
   <td> Retorna a data atual do sistema do servidor<br /> </td> 
   <td> Getdate ()<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Hora</strong><br /> </td> 
   <td> Retorna a hora da data<br /> </td> 
   <td> Hora (&lt; data &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Hoursdiff</strong><br /> </td> 
   <td> Retorna o número de horas entre duas datas<br /> </td> 
   <td> Hoursdiff (&lt; data final &gt;, &lt; data de início &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Localtoutc</strong><br /> </td> 
   <td> Converte uma data e hora local em UTC<br /> </td> 
   <td> Localtoutc (&lt; data &gt;, &lt; Fuso horário &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Minuto</strong><br /> </td> 
   <td> Retorna os minutos da data<br /> </td> 
   <td> Minuto (&lt; data &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Minutesdiff</strong><br /> </td> 
   <td> Retorna o número de minutos entre duas datas<br /> </td> 
   <td> Minutesdiff (&lt; data final &gt;, &lt; data de início &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Mês</strong><br /> </td> 
   <td> Retorna o número que representa o mês da data<br /> </td> 
   <td> Mês (&lt; data &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Monthsago</strong><br /> </td> 
   <td> Retorna a data correspondente à data atual menos n meses<br /> </td> 
   <td> Monthsago (&lt; número &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Monthsdiff</strong><br /> </td> 
   <td> Retorna o número de meses entre duas datas<br /> </td> 
   <td> Monthsdiff (&lt; data final &gt;, &lt; data de início &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Monthsold</strong><br /> </td> 
   <td> Retorna a idade em meses de uma data<br /> </td> 
   <td> Monthvendidas (&lt; date &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Segundo</strong><br /> </td> 
   <td> Retorna os segundos da data<br /> </td> 
   <td> Segundo (&lt; data &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Mais antiga</strong><br /> </td> 
   <td> Retorna a data mais antiga </td> 
   <td> Mais antigas (&lt; Data &gt;, &lt; Data &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Secondsdiff</strong><br /> </td> 
   <td> Retorna o número de segundos entre duas datas<br /> </td> 
   <td> Secondsdiff (&lt; data final &gt;, &lt; data de início &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Subdias</strong><br /> </td> 
   <td> Subtrai um número de dias de uma data<br /> </td> 
   <td> Subdias (&lt; data &gt;, &lt; número &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Subhoras</strong><br /> </td> 
   <td> Subtrai um número de horas de uma data<br /> </td> 
   <td> Subhoras (&lt; data &gt;, &lt; número &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Subminutos</strong><br /> </td> 
   <td> Subtrai vários minutos de uma data<br /> </td> 
   <td> Subminutos (&lt; data &gt;, &lt; número &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Submeses</strong><br /> </td> 
   <td> Subtrai vários meses de uma data<br /> </td> 
   <td> Submeses (&lt; data &gt;, &lt; número &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Subsegundos</strong><br /> </td> 
   <td> Subtrai vários segundos de uma data<br /> </td> 
   <td> Subsegundos (&lt; data &gt;, &lt; número &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Subanos</strong><br /> </td> 
   <td> Subtrai vários anos de uma data<br /> </td> 
   <td> Subanos (&lt; data &gt;, &lt; número &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Todate</strong><br /> </td> 
   <td> Converte uma data + hora como uma data<br /> </td> 
   <td> Todate (&lt; date + time &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Todatetime</strong><br /> </td> 
   <td> Converte uma string em uma data + hora<br /> </td> 
   <td> Todatetime (&lt; string &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Todatetimewithtimezone</strong><br /> </td> 
   <td> Converte uma string em uma data + data e hora.<br /> Exemplo: Todatetimewithtimezone ("2019-02-19 08:09:00", "Ásia/Tehran")<br /> </td> 
   <td> Todatetimewithtimezone (&lt; string &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Truncdate</strong><br /> </td> 
   <td> Arredonda uma data + hora para o segundo mais próximo<br /> </td> 
   <td> Truncdate (@ lastmodified, &lt; número de segundos &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Truncdatetz</strong><br /> </td> 
   <td> Arredonda uma data + hora para determinada precisão, expresso em segundos<br /> </td> 
   <td> Truncdatetz (&lt; data &gt;, &lt; número de segundos &gt;, &lt; fuso horário &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Truncquarter</strong><br /> </td> 
   <td> Arredonda uma data para o trimestre<br /> </td> 
   <td> Trunctrimestre (&lt; date &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Trunctime</strong><br /> </td> 
   <td> Arredonda a parte de tempo até o segundo mais próximo<br /> </td> 
   <td> Trunctime (&lt; date &gt;, &lt; número de segundos &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Truncweek</strong><br /> </td> 
   <td> Arredonda uma data para a semana<br /> </td> 
   <td> Truncweek (&lt; date &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Truncyear</strong><br /> </td> 
   <td> Arredonda uma data + hora para o dia 1 º de janeiro do ano<br /> </td> 
   <td> Truncyear (&lt; date &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Weekday</strong><br /> </td> 
   <td> Retorna o número que representa o dia na semana da data<br /> </td> 
   <td> Weekday (&lt; date &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Ano</strong><br /> </td> 
   <td> Retorna o número que representa o ano da data<br /> </td> 
   <td> Ano (&lt; data &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Yearand Mês</strong><br /> </td> 
   <td> Retorna o número que representa o ano e o mês da data<br /> </td> 
   <td> Yearandmonth (&lt; date &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Yearsdiff</strong><br /> </td> 
   <td> Retorna o número de anos entre as duas datas<br /> </td> 
   <td> Yearsdiff (&lt; data final &gt;, &lt; data de início &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Yearsold</strong><br /> </td> 
   <td> Retorna a idade em anos de uma data<br /> </td> 
   <td> Yearsold (&lt; date &gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Geomarketing {#geomarketing}

As funções geomarketing são usadas para manipular valores geográficos.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Nome</strong><br /> </td> 
   <td> <strong>Descrição</strong><br /> </td> 
   <td> <strong>Sintaxe</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Distância</strong><br /> </td> 
   <td> Retorna a distância em quilômetros entre dois pontos definidos pela longitude e latitude (expresso em graus)<br /> </td> 
   <td> Distância (&lt; Longitude A &gt;, &lt; Latitude A &gt;, &lt; Longitude B &gt;, &lt; Latitude B &gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Numérico {#numerical}

As funções de valor numérico são usadas para converter texto em números.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Nome</strong><br /> </td> 
   <td> <strong>Descrição</strong><br /> </td> 
   <td> <strong>Sintaxe</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Abs</strong><br /> </td> 
   <td> Retorna o valor absoluto de um número<br /> </td> 
   <td> Abs (&lt; número &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Ceil</strong><br /> </td> 
   <td> Retorna o número inteiro mais baixo maior ou igual a um número<br /> </td> 
   <td> Ceil (&lt; número &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Floor</strong><br /> </td> 
   <td> Retorna o maior número inteiro maior ou igual a um número<br /> </td> 
   <td> Floor (&lt; número &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Maior</strong><br /> </td> 
   <td> Retorna o maior de dois números<br /> </td> 
   <td> Maior (&lt; número 1 &gt;, &lt; número 2 &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Menos</strong><br /> </td> 
   <td> Retorna o menor de dois números<br /> </td> 
   <td> Menos (&lt; número 1 &gt;, &lt; número 2 &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Mod</strong><br /> </td> 
   <td> Retorna o restante da divisão inteiro de n 1 em n 2<br /> </td> 
   <td> Mod (&lt; número 1 &gt;, &lt; número 2 &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Porcentagem</strong><br /> </td> 
   <td> Retorna a proporção de dois números expressos em porcentagem<br /> </td> 
   <td> Porcentagem (&lt; número 1 &gt;, &lt; número 2 &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Aleatório</strong><br /> </td> 
   <td> Retorna o valor aleatório<br /> </td> 
   <td> Random ()<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Round</strong><br /> </td> 
   <td> Arredondar um número para n decimal<br /> </td> 
   <td> Round (&lt; número &gt;, &lt; número de decimais &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Assinar</strong><br /> </td> 
   <td> Retorna o sinal do número<br /> </td> 
   <td> Sinal (&lt; número &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Todouble</strong><br /> </td> 
   <td> Converte um número inteiro em flutuante<br /> </td> 
   <td> Todouble (&lt; número &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToInt64</strong><br /> </td> 
   <td> Converte um flutuante em um número inteiro de 64 bits<br /> </td> 
   <td> Toint 64 (&lt; número &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Tointeger</strong><br /> </td> 
   <td> Converte um flutuante em um número inteiro<br /> </td> 
   <td> Tointeger (&lt; número &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Trunc</strong><br /> </td> 
   <td> Trunces n 1 a n 2 decimais<br /> </td> 
   <td> Trunc (&lt; n 1 &gt;, &lt; n 2 &gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Outros {#others}

Esta tabela contém as funções restantes disponíveis.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Nome</strong><br /> </td> 
   <td> <strong>Descrição</strong><br /> </td> 
   <td> <strong>Sintaxe</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Caso</strong><br /> </td> 
   <td> Retorna o valor 1 se a condição for verificada. Caso contrário, retorna valor 2<br /> </td> 
   <td> Case (when (&lt; condition &gt;, &lt; value 1 &gt;), Else (&lt; value 2 &gt;))<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Clearbit</strong><br /> </td> 
   <td> Exclui o sinalizador no valor<br /> </td> 
   <td> Clearbit (&lt; identifier &gt;, &lt; sinalizador &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Coalesce</strong><br /> </td> 
   <td> Retorna valor 2 se valor 1 for zero ou nulo; caso contrário retorna valor 1<br /> </td> 
   <td> Coalesce (&lt; value 1 &gt;, &lt; value 2 &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Decode</strong><br /> </td> 
   <td> Retorna valor 3 é valor 1 = valor 2; caso contrário retorna 4<br /> </td> 
   <td> Decode (&lt; value 1 &gt;, &lt; value 2 &gt;, &lt; value 3 &gt;, &lt; value 4 &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Else</strong><br /> </td> 
   <td> Retorna valor 1 (pode ser usado apenas como parâmetro da função case)<br /> </td> 
   <td> Else (&lt; value 1 &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Getemaildomain</strong><br /> </td> 
   <td> Extrai o domínio de um endereço de email<br /> </td> 
   <td> Getemaildomain (&lt; value &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Getmirrorurl</strong><br /> </td> 
   <td> Recupera o URL do servidor de página espelhada<br /> </td> 
   <td> Getmirrorurl (&lt; value &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Iif</strong><br /> </td> 
   <td> Retorna valor 1 se a expressão for verdadeira; caso contrário retorna valor 2<br /> </td> 
   <td> Iif (&lt; condition &gt;, &lt; value 1 &gt;, &lt; value 2 &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Isbitset</strong><br /> </td> 
   <td> Indica se o Sinalizador está no valor<br /> </td> 
   <td> Isbitset (&lt; identifier &gt;, &lt; sinalizador &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Isemptystring</strong><br /> </td> 
   <td> Retorna valor 2 se a sequência estiver vazia; caso contrário retorna valor 3<br /> </td> 
   <td> Isemptystring (&lt; string &gt;, &lt; value 2 &gt;, &lt; value 3 &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Nonull</strong><br /> </td> 
   <td> Retorna a string vazia se o argumento for NULL<br /> </td> 
   <td> Nonull (&lt; value &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Rowid</strong><br /> </td> 
   <td> Retorna o número da linha<br /> </td> 
   <td> Rowid<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Setbit</strong><br /> </td> 
   <td> Força o sinalizador no valor<br /> </td> 
   <td> Setbit (&lt; identifier &gt;, &lt; sinalizador &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Toboolean</strong><br /> </td> 
   <td> Converte um número em Booliano<br /> </td> 
   <td> Toboolean (&lt; número &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Quando</strong><br /> </td> 
   <td> Retorna o valor 1 se a expressão for verificada. Caso contrário, retorna valor 2 (pode ser usado apenas como parâmetro da função de caso)<br /> </td> 
   <td> Quando (&lt; condição &gt;, &lt; valor 1 &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Newuuid</strong><br /> </td> 
   <td> Retorna um novo UUID.<br /> </td> 
   <td> Newuuid<br /> </td> 
  </tr> 
 </tbody> 
</table>

## String {#string}

As funções de string são usadas para manipular um conjunto de strings.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Nome</strong><br /> </td> 
   <td> <strong>Descrição</strong><br /> </td> 
   <td> <strong>Sintaxe</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AllNonNull2</strong><br /> </td> 
   <td> Indica se todos os parâmetros não são nulos e não estão vazios<br /> </td> 
   <td> Allnonnull 2 (&lt; string &gt;, &lt; string &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AllNonNull3</strong><br /> </td> 
   <td> Indica se todos os parâmetros não são nulos e não estão vazios<br /> </td> 
   <td> Allnonnull 3 (&lt; string &gt;, &lt; string &gt;, &lt; string &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ASCII</strong><br /> </td> 
   <td> Retorna o valor ASCII do primeiro caractere na string<br /> </td> 
   <td> Ascii (&lt; string &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Char</strong><br /> </td> 
   <td> Retorna o caractere correspondente ao código "n" ASCII<br /> </td> 
   <td> Char (&lt; número &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Charindex</strong><br /> </td> 
   <td> Retorna a posição da string 2 na string 1<br /> </td> 
   <td> Charindex (&lt; string &gt;, &lt; string &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Datalength</strong><br /> </td> 
   <td> Retorna o número de caracteres em uma string<br /> </td> 
   <td> Datalength (&lt; String &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Getline</strong><br /> </td> 
   <td> Retorna a enésima linha (de 1 a n) da string<br /> </td> 
   <td> Getline (&lt; string &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Ifequals</strong><br /> </td> 
   <td> Retorna o terceiro parâmetro se os dois primeiros parâmetros forem iguais, caso contrário retorna o último parâmetro<br /> </td> 
   <td> Ifequals (&lt; string &gt;, &lt; string &gt;, &lt; string &gt;, &lt; string &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Ismemonull</strong><br /> </td> 
   <td> Indica se o memorando passado como parâmetro é nulo<br /> </td> 
   <td> Ismemonull (&lt; Memo &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Juxtwords</strong><br /> </td> 
   <td> Cônica as duas strings transmitidas como parâmetros. Um espaço é adicionado entre cada string no valor retornado.<br /> </td> 
   <td> Juxtwords (&lt; string &gt;, &lt; string &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>JuxtWords3</strong><br /> </td> 
   <td> Cônica as três strings transmitidas como parâmetros. Um espaço é adicionado entre cada string no valor retornado.<br /> </td> 
   <td> Juxtwords 3 (&lt; string &gt;, &lt; string &gt;, &lt; string &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Lpad</strong><br /> </td> 
   <td> Retorna a string concluída à esquerda<br /> </td> 
   <td> Lpad (&lt; string &gt;, &lt; número &gt;, &lt; caractère &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Esquerda</strong><br /> </td> 
   <td> Retorna os primeiros n caracteres da string<br /> </td> 
   <td> Left (&lt; string &gt;, &lt; número &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Comprimento</strong><br /> </td> 
   <td> Retorna o comprimento da string<br /> </td> 
   <td> Comprimento (&lt; string &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Lower</strong><br /> </td> 
   <td> Retorna a string em minúsculas<br /> </td> 
   <td> Lower (&lt; string &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Ltrim</strong><br /> </td> 
   <td> Remove espaços à esquerda da string<br /> </td> 
   <td> Ltrim (&lt; string &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Md5Digest</strong><br /> </td> 
   <td> Retorna uma representação hexadecimal da tecla MD 5 de uma string<br /> </td> 
   <td> Md 5 Compilação (&lt; string &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Memocontém</strong><br /> </td> 
   <td> Especifica se o memo contém a string transmitida como parâmetro<br /> </td> 
   <td> Memocontém (&lt; memo &gt;, &lt; string &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Rpad</strong><br /> </td> 
   <td> Retorna a string concluída à direita<br /> </td> 
   <td> Rpad (&lt; string &gt;, &lt; número &gt;, &lt; caractere &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Replace</strong><br /> </td> 
   <td> Substitui todas as ocorrências de um valor de string (segundo parâmetro) especificado por outro valor de string (terceiro parâmetro) em uma string (1 º parâmetro)<br /> </td> 
   <td> Replace (&lt; String &gt;, &lt; String &gt;, &lt; String &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Direita</strong><br /> </td> 
   <td> Retorna os últimos n caracteres da string<br /> </td> 
   <td> Right (&lt; string &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Rtrim</strong><br /> </td> 
   <td> Remove espaços à direita da string<br /> </td> 
   <td> Rtrim (&lt; string &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sha256Digest</strong><br /> </td> 
   <td> Calcula o hash padrão <strong>SHA 256</strong> para uma determinada string UTF 8<br /> </td> 
   <td> Sha 256 Compilação (&lt; String &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sha384Digest</strong><br /> </td> 
   <td> Calcula o hash padrão <strong>SHA 384</strong> para uma determinada string UTF 8<br /> </td> 
   <td> Sha 384 Compilação (&lt; String &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sha512Digest</strong><br /> </td> 
   <td> Calcula o hash padrão <strong>SHA 512</strong> para uma determinada string UTF 8<br /> </td> 
   <td> Sha 512 Compilação (&lt; String &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Inteligente</strong><br /> </td> 
   <td> Retorna a string com a primeira letra de cada palavra em maiúsculas<br /> </td> 
   <td> Inteligente (&lt; string &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Subsequência</strong><br /> </td> 
   <td> Extrai a subsequência de caracteres começando no caractere n 1 da string e com um comprimento n 2<br /> </td> 
   <td> Subsequência de caracteres (&lt; string &gt;, &lt; offset &gt;, &lt; length &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Tointlstring</strong><br /> </td> 
   <td> Converte o número em uma string<br /> </td> 
   <td> Tointlstring (&lt; número &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Tostring</strong><br /> </td> 
   <td> Converte o número em uma string<br /> </td> 
   <td> Tostring (&lt; número &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Upper</strong><br /> </td> 
   <td> Retorna a string em maiúsculas<br /> </td> 
   <td> Upper (&lt; string &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Virtuallink</strong><br /> </td> 
   <td> Retorna a chave externa de um link passado como um parâmetro se os outros dois parâmetros forem iguais<br /> </td> 
   <td> Virtuallink (&lt; número &gt;, &lt; número &gt;, &lt; número &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Virtuallinkstr</strong><br /> </td> 
   <td> Retorna a chave externa (texto) de um link passado como parâmetro se os outros dois parâmetros forem iguais<br /> </td> 
   <td> Virtuallinkstr (&lt; string &gt;, &lt; número &gt;, &lt; número &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>encryption_ aescbcdecrypt</strong><br /> </td> 
   <td> Descripts de um valor criptografado no formato HEX com prefixo "<strong>x</strong>" (1 º parâmetro) usando uma tecla no formato HEX (segunda parâmetro) e um vetor de inicialização no formato HEX (terceiro parâmetro)<br /> </td> 
   <td> encryption_ aescbcdecrypt (&lt; String &gt;, &lt; String &gt;, &lt; String &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>encryption_ aescbcencrypt</strong><br /> </td> 
   <td> Criptografos usando o algoritmo AES (modo de bloco CBC) uma string de caracteres (1 º parâmetro) com uma chave (segundo parâmetro) e um vetor de inicialização (terceiro parâmetro). A chave e o vetor de inicialização devem ser fornecidos em uma representação hexadecimal (começando por <strong>\ x</strong>). O resultado será hexadecimal sem o <strong>\ x</strong>.<br /> Observe que o tamanho da chave pode ser de 128 bits, 192 bits, 256 bits (16, 24, 32 caracteres hexadecimais), mas recomendamos usar 256 bits e um IV aleatório com o mesmo comprimento da chave.<br /> </td> 
   <td> encryption_ aescbcencrypt (&lt; String &gt;, &lt; String &gt;, &lt; String &gt;)<br /> Por exemplo: encryption_ aescbcencrypt (johndoe@example.com, "<strong>\ x 0123456789 ABCDEF 0123456789 ABCDEF</strong>", "<strong>\ x 0123456789 ABCDEFFEDCBA 9876543210</strong>")<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Agregados {#aggregates}

As funções de agregação só estão disponíveis ao [adicionar dados adicionais](../../automating/using/query.md#enriching-data) a partir **[!UICONTROL Query]** da atividade de um fluxo de trabalho.

As funções agregadas são usadas para executar cálculos em um conjunto de valores.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Nome</strong><br /> </td> 
   <td> <strong>Descrição</strong><br /> </td> 
   <td> <strong>Sintaxe</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Média</strong>, Média<br /> </td> 
   <td> Retorna a média em uma coluna numérica.<br /> </td> 
   <td> Avg (&lt; value &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Count</strong>, Count (exceto NULL)<br /> </td> 
   <td> Conta os valores não nulos em uma coluna.<br /> </td> 
   <td> Count (&lt; value &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Countall</strong>, Count All<br /> </td> 
   <td> Conta todos os valores (incluindo valores nulos e duplicatas).<br /> </td> 
   <td> Countall ()<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Contagem distinta,</strong>distinta e distinta<br /> </td> 
   <td> Conta os valores não nulos e distintos em uma coluna.<br /> </td> 
   <td> Contagem distinta (&lt; valor &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Máx</strong>., Máx.<br /> </td> 
   <td> Retorna o valor máximo em uma coluna numérica, de sequência ou de data.<br /> </td> 
   <td> Max (&lt; value &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Mín</strong>., Mín.<br /> </td> 
   <td> Retorna o valor mínimo em uma coluna numérica, de sequência ou de data.<br /> </td> 
   <td> Min (&lt; valor &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sum</strong>, Sum<br /> </td> 
   <td> Retorna a soma dos valores em uma coluna numérica.<br /> </td> 
   <td> Sum (&lt; value &gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Representação {#representation}

As funções de representação são usadas para ordenar valores.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Nome</strong><br /> </td> 
   <td> <strong>Descrição</strong><br /> </td> 
   <td> <strong>Sintaxe</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Desc</strong><br /> </td> 
   <td> Aplica uma classificação decrescente<br /> </td> 
   <td> Desc (&lt; value 1 &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Orderby</strong><br /> </td> 
   <td> Classifica o resultado na partição<br /> </td> 
   <td> Orderby (&lt; value 1 &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Partitionby</strong><br /> </td> 
   <td> Partições o resultado de uma consulta em uma tabela<br /> </td> 
   <td> Partitionby (&lt; value 1 &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Rownum</strong><br /> </td> 
   <td> Gera um número de linha com base na partição da tabela e em uma sequência de classificação. Essa função não é compatível com mysql<br /> </td> 
   <td> Rownum (partitionby (&lt; value 1 &gt;), orderby (&lt; value 1 &gt;))<br /> </td> 
  </tr> 
 </tbody> 
</table>

