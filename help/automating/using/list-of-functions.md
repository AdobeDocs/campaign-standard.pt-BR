---
solution: Campaign Standard
product: campaign
title: Lista de funções
description: A ferramenta de edição de query permite usar funções avançadas para fazer filtragens complexas.
audience: automating
content-type: reference
topic-tags: filtering-data
translation-type: tm+mt
source-git-commit: ef170f2282fcc46e36c90dada2083dea25b95f7c
workflow-type: tm+mt
source-wordcount: '1940'
ht-degree: 98%

---


# Lista de funções{#list-of-functions}

## Sobre funções {#about-functions}

A ferramenta de edição de query permite usar funções avançadas para fazer filtragens complexas. Para fazer isso, a paleta de ferramentas contém o elemento **[!UICONTROL Expression]** que pode ser usado no espaço de trabalho. Informações adicionais sobre esse elemento estão detalhadas em uma [seção específica](../../automating/using/advanced-expression-editing.md).

Esse elemento permite inserir as condições manualmente. Aqui, você pode usar as funções definidas nas seções a seguir.

Vários tipos de função estão disponíveis, dependendo dos resultados desejados e dos tipos de dados manipulados:

* Datas
* Geomarketing
* Valores numéricos
* Outras funções
* Agregados
* Manipulação de strings
* Classificação

>[!NOTE]
>
>Funções adicionais estão disponíveis em todas as atividades que permitem usar variáveis de eventos após chamar um fluxo de trabalho com parâmetros externos. Eles são detalhados [nesta seção](../../automating/using/customizing-workflow-external-parameters.md).

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
   <td> <strong>AddDays</strong><br /> </td> 
   <td> Adiciona um número de dias a uma data<br /> </td> 
   <td> AddDays(&lt;data&gt;, &lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddHours</strong><br /> </td> 
   <td> Adiciona um número de horas a uma data<br /> </td> 
   <td> AddHours(&lt;data&gt;, &lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddMinutes</strong><br /> </td> 
   <td> Adiciona um número de minutos a uma data<br /> </td> 
   <td> AddMinutes(&lt;data&gt;, &lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddMonths</strong><br /> </td> 
   <td> Adiciona um número de meses a uma data<br /> </td> 
   <td> AddMonths(&lt;data&gt;, &lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddSeconds</strong><br /> </td> 
   <td> Adiciona um número de segundos a uma data<br /> </td> 
   <td> AddSeconds(&lt;data&gt;, &lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddYears</strong><br /> </td> 
   <td> Adiciona um número de anos a uma data<br /> </td> 
   <td> AddYears(&lt;data&gt;, &lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DateOnly</strong><br /> </td> 
   <td> Retorna somente a data (com a hora 00:00)<br /> </td> 
   <td> DateOnly(&lt;data&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Day</strong><br /> </td> 
   <td> Retorna o número que representa o dia da data<br /> </td> 
   <td> Day(&lt;data&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DayOfYear</strong><br /> </td> 
   <td> Retorna o número que representa o dia no ano da data<br /> </td> 
   <td> DayOfYear(&lt;data&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DaysAgo</strong><br /> </td> 
   <td> Retorna a data atual menos n dias<br /> </td> 
   <td> DaysAgo(&lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DaysAgoInt</strong><br /> </td> 
   <td> Retorna a data atual menos n dias (como um número inteiro yyyymmdd)<br /> </td> 
   <td> DaysAgoInt(&lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DaysDiff</strong><br /> </td> 
   <td> Número de dias entre duas datas<br /> </td> 
   <td> DaysDiff(&lt;data final&gt;, &lt;data inicial&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DaysOld</strong><br /> </td> 
   <td> Retorna a idade em dias de uma data.<br /> </td> 
   <td> DaysOld(&lt;data&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>GetDate</strong><br /> </td> 
   <td> Retorna a data atual do sistema do servidor.<br /> </td> 
   <td> GetDate()<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Hour</strong><br /> </td> 
   <td> Retorna a hora da data.<br /> </td> 
   <td> Hour(&lt;data&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>HoursDiff</strong><br /> </td> 
   <td> Retorna o número de horas entre duas datas<br /> </td> 
   <td> HoursDiff(&lt;data final&gt;, &lt;data inicial&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>LocalToUTC</strong><br /> </td> 
   <td> Converte uma data e hora locais em UTC<br /> </td> 
   <td> LocalToUTC(&lt;data&gt;, &lt;Fuso horário&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Minute</strong><br /> </td> 
   <td> Retorna os minutos da data<br /> </td> 
   <td> Minute(&lt;data&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MinutesDiff</strong><br /> </td> 
   <td> Retorna o número de minutos entre duas datas<br /> </td> 
   <td> MinutesDiff(&lt;data final&gt;, &lt;data inicial&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Month</strong><br /> </td> 
   <td> Retorna o número que representa o mês da data<br /> </td> 
   <td> Month(&lt;data&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MonthsAgo</strong><br /> </td> 
   <td> Retorna a data correspondente à data atual menos n meses<br /> </td> 
   <td> MonthsAgo(&lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MonthsDiff</strong><br /> </td> 
   <td> Retorna o número de meses entre duas datas<br /> </td> 
   <td> MonthsDiff(&lt;data final&gt;, &lt;data inicial&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MonthsOld</strong><br /> </td> 
   <td> Retorna a idade em meses de uma data<br /> </td> 
   <td> MonthsOld(&lt;data&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Second</strong><br /> </td> 
   <td> Retorna os segundos da data<br /> </td> 
   <td> Second(&lt;data&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Oldest</strong><br /> </td> 
   <td> Retorna a data mais antiga </td> 
   <td> Oldest(&lt;Data&gt;, &lt;Data&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SecondsDiff</strong><br /> </td> 
   <td> Retorna o número de segundos entre duas datas<br /> </td> 
   <td> SecondsDiff(&lt;data final&gt;, &lt;data inicial&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SubDays</strong><br /> </td> 
   <td> Subtrai um número de dias a partir de uma data<br /> </td> 
   <td> SubDays(&lt;data&gt;, &lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SubHours</strong><br /> </td> 
   <td> Subtrai um número de horas a partir de uma data<br /> </td> 
   <td> SubHours(&lt;data&gt;, &lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SubMinutes</strong><br /> </td> 
   <td> Subtrai um número de minutos de uma data<br /> </td> 
   <td> SubMinutes(&lt;data&gt;, &lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SubMonths</strong><br /> </td> 
   <td> Subtrai um número de meses a partir de uma data<br /> </td> 
   <td> SubMonths(&lt;data&gt;, &lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SubSeconds</strong><br /> </td> 
   <td> Subtrai um número de segundos a partir de uma data<br /> </td> 
   <td> SubSeconds(&lt;data&gt;, &lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SubYears</strong><br /> </td> 
   <td> Subtrai um número de anos a partir de uma data<br /> </td> 
   <td> SubYears(&lt;data&gt;, &lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToDate</strong><br /> </td> 
   <td> Converte uma data + hora em uma data<br /> </td> 
   <td> ToDate(&lt;data + hora&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToDateTime</strong><br /> </td> 
   <td> Converte uma cadeia de caracteres em uma data + hora<br /> </td> 
   <td> ToDateTime(&lt;cadeia de caracteres&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToDateTimeWithTimezone</strong><br /> </td> 
   <td> Converte uma string em uma data + fuso horário.<br /> Exemplo: ToDateTimeWithTimezone ("2019-02-19 08:09:00", "Asia/Tehran")<br /> </td> 
   <td> ToDateTimeWithTimezone(&lt;cadeia de caracteres&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncDate</strong><br /> </td> 
   <td> Arredonda uma data e hora para o segundo mais próximo<br /> </td> 
   <td> TruncDate(@lastModified, &lt;número de segundos&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncDateTZ</strong><br /> </td> 
   <td> Arredonda uma data e hora para uma determinada precisão expressa em segundos<br /> </td> 
   <td> TruncDateTZ(&lt;data&gt;, &lt;número de segundos&gt;, &lt;fuso horário&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncQuarter</strong><br /> </td> 
   <td> Arredonda uma data para o trimestre<br /> </td> 
   <td> TruncQuarter(&lt;data&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncTime</strong><br /> </td> 
   <td> Arredonda a parte de horário para cima até o próximo segundo<br /> </td> 
   <td> TruncTime(&lt;data&gt;, &lt;número de segundos&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncWeek</strong><br /> </td> 
   <td> Arredonda uma data para a semana<br /> </td> 
   <td> TruncWeek(&lt;data&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncYear</strong><br /> </td> 
   <td> Arredonda uma data + hora para 1º de janeiro do ano<br /> </td> 
   <td> TruncYear(&lt;data&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>WeekDay</strong><br /> </td> 
   <td> Retorna o número que representa o dia na semana da data<br /> </td> 
   <td> WeekDay(&lt;data&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Year</strong><br /> </td> 
   <td> Retorna o número que representa o ano da data<br /> </td> 
   <td> Year(&lt;data&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>YearAnd Month</strong><br /> </td> 
   <td> Retorna o número que representa o ano e o mês da data.<br /> </td> 
   <td> YearAndMonth(&lt;data&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>YearsDiff</strong><br /> </td> 
   <td> Retorna o número de anos entre as duas datas<br /> </td> 
   <td> YearsDiff(&lt;data final&gt;, &lt;data inicial&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>YearsOld</strong><br /> </td> 
   <td> Retorna a idade em anos de uma data<br /> </td> 
   <td> YearsOld(&lt;data&gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Geomarketing {#geomarketing}

As funções de geomarketing são usadas para manipular valores geográficos.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Nome</strong><br /> </td> 
   <td> <strong>Descrição</strong><br /> </td> 
   <td> <strong>Sintaxe</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Distance</strong><br /> </td> 
   <td> Retorna a distância em quilômetros entre dois pontos definidos por sua longitude e latitude (expressa em graus)<br /> </td> 
   <td> Distance(&lt;Longitude A&gt;, &lt;Latitude A&gt;, &lt;Longitude B&gt;, &lt;Latitude B&gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Numerical {#numerical}

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
   <td> Abs(&lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Ceil</strong><br /> </td> 
   <td> Retorna o número inteiro mais baixo maior ou igual a um número<br /> </td> 
   <td> Ceil(&lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Floor</strong><br /> </td> 
   <td> Retorna o maior inteiro menor que ou igual a um número<br /> </td> 
   <td> Floor(&lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Greatest</strong><br /> </td> 
   <td> Retorna o maior número de dois números<br /> </td> 
   <td> Greatest(&lt;número 1&gt;, &lt;número 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Least</strong><br /> </td> 
   <td> Retorna o menor de dois números<br /> </td> 
   <td> Least(&lt;número 1&gt;, &lt;número 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Mod</strong><br /> </td> 
   <td> Retorna o resto da divisão do número inteiro de n1 por n2<br /> </td> 
   <td> Mod(&lt;número 1&gt;, &lt;número 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Percent</strong><br /> </td> 
   <td> Retorna a proporção de dois números expressos como uma porcentagem<br /> </td> 
   <td> Percent(&lt;número 1&gt;, &lt;número 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Random</strong><br /> </td> 
   <td> Retorna o valor aleatório<br /> </td> 
   <td> Random()<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Round</strong><br /> </td> 
   <td> Arredonda um número para decimais n<br /> </td> 
   <td> Round(&lt;número&gt;, &lt;número de decimais&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sign</strong><br /> </td> 
   <td> Retorna o sinal do número<br /> </td> 
   <td> Sign(&lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToDouble</strong><br /> </td> 
   <td> Converte um inteiro em um flutuante<br /> </td> 
   <td> ToDouble(&lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToInt64</strong><br /> </td> 
   <td> Converte um flutuante em um inteiro de 64 bits<br /> </td> 
   <td> ToInt64(&lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToInteger</strong><br /> </td> 
   <td> Converte um flutuante em um inteiro<br /> </td> 
   <td> ToInteger(&lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Trunc</strong><br /> </td> 
   <td> Corta o n1 para o decimal n2<br /> </td> 
   <td> Trunc(&lt;n1&gt;, &lt;n2&gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Outros {#others}

Essa tabela contém as funções restantes disponíveis.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Nome</strong><br /> </td> 
   <td> <strong>Descrição</strong><br /> </td> 
   <td> <strong>Sintaxe</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Case</strong><br /> </td> 
   <td> Retorna o valor 1 quando a condição é verificada. Caso contrário, retorna o valor 2<br /> </td> 
   <td> Case(When(&lt;condição&gt;, &lt;valor 1&gt;), Else(&lt;valor 2&gt;))<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ClearBit</strong><br /> </td> 
   <td> Exclui o Sinalizador no valor<br /> </td> 
   <td> ClearBit(&lt;identificador&gt;, &lt;sinalizador&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Coalesce</strong><br /> </td> 
   <td> Retorna o valor 2 se o valor 1 for zero ou nulo, caso contrário retorna o valor 1<br /> </td> 
   <td> Coalesce(&lt;valor 1&gt;, &lt;valor 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Decode</strong><br /> </td> 
   <td> Retorna o valor 3 quando valor 1 = valor 2; caso contrário, retorna 4<br /> </td> 
   <td> Decode(&lt;valor 1&gt;, &lt;valor 2&gt;, &lt;valor 3&gt;, &lt;valor 4&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Else</strong><br /> </td> 
   <td> Retorna o valor 1 (só pode ser usado como parâmetro da função case)<br /> </td> 
   <td> Else(&lt;valor 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>GetEmailDomain</strong><br /> </td> 
   <td> Extrai o domínio de um endereço de email<br /> </td> 
   <td> GetEmailDomain(&lt;valor&gt;)<br /> </td> 
  </tr>
  <tr> 
   <td> <strong>GetMirrorURL</strong><br /> </td> 
   <td> Recupera o URL do servidor da mirror page<br /> </td> 
   <td> GetMirrorURL(&lt;valor&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Iif</strong><br /> </td> 
   <td> Retorna o valor 1 quando a expressão é verdadeira; caso contrário, retorna o valor 2<br /> </td> 
   <td> Iif(&lt;condição&gt;, &lt;valor 1&gt;, &lt;valor 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>IsBitSet</strong><br /> </td> 
   <td> Indica se o Sinalizador está no valor<br /> </td> 
   <td> IsBitSet(&lt;identificador&gt;, &lt;sinalizador&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>IsEmptyString</strong><br /> </td> 
   <td> Retorna o valor 2 quando a string está vazia; caso contrário, retorna o valor 3<br /> </td> 
   <td> IsEmptyString(&lt;cadeia de caracteres&gt;, &lt;valor 2&gt;, &lt;valor 3&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>NoNull</strong><br /> </td> 
   <td> Retorna a cadeia de caracteres vazia se o argumento for NULL.<br /> </td> 
   <td> NoNull(&lt;valor&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>RowId</strong><br /> </td> 
   <td> Retorna o número da linha.<br /> </td> 
   <td> RowId<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SetBit</strong><br /> </td> 
   <td> Força o Sinalizador no valor.<br /> </td> 
   <td> SetBit(&lt;identificador&gt;, &lt;sinalizador&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToBoolean</strong><br /> </td> 
   <td> Converte um número em um booleano<br /> </td> 
   <td> ToBoolean(&lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>When</strong><br /> </td> 
   <td> Retorna o valor 1 quando a expressão é verificada. Caso contrário, retorna o valor 2 (só pode ser usado como parâmetro da função case)<br /> </td> 
   <td> When(&lt;condição&gt;, &lt;valor 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>newUUID</strong><br /> </td> 
   <td> Retorna um novo UUID.<br /> </td> 
   <td> newUUID<br /> </td> 
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
   <td> Indica se todos os parâmetros são não nulos e não estão vazios<br /> </td> 
   <td> AllNonNull2(&lt;cadeia de caracteres&gt;, &lt;cadeia de caracteres&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AllNonNull3</strong><br /> </td> 
   <td> Indica se todos os parâmetros são não nulos e não estão vazios<br /> </td> 
   <td> AllNonNull3(cadeia de caracteres&gt;, &lt;cadeia de caracteres&gt;, &lt;cadeia de caracteres&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ASCII</strong><br /> </td> 
   <td> Retorna o valor ASCII do primeiro caractere na cadeia de caracteres<br /> </td> 
   <td> Ascii(&lt;cadeia de caracteres&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Char</strong><br /> </td> 
   <td> Retorna o caractere correspondente ao código ASCII 'n'<br /> </td> 
   <td> Char(&lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Charindex</strong><br /> </td> 
   <td> Retorna a posição da cadeia de caracteres 2 na cadeia de caracteres 1<br /> </td> 
   <td> Charindex(&lt;cadeia de caracteres&gt;, &lt;cadeia de caracteres&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DataLength</strong><br /> </td> 
   <td> Retorna o número de caracteres em uma string<br /> </td> 
   <td> DataLength(&lt;Cadeia de caracteres&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>GetLine</strong><br /> </td> 
   <td> Retorna a linha enésima (de 1 a n) da cadeia de caracteres<br /> </td> 
   <td> GetLine(&lt;cadeia de caracteres&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>IfEquals</strong><br /> </td> 
   <td> Retorna o terceiro parâmetro quando os dois primeiros parâmetros são iguais; caso contrário, retorna o último parâmetro<br /> </td> 
   <td> IfEquals(&lt;cadeia de caracteres&gt;, &lt;cadeia de caracteres&gt;, &lt;cadeia de caracteres&gt;, &lt;cadeia de caracteres&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>IsMemoNull</strong><br /> </td> 
   <td> Indica se o memorando passado como parâmetro é nulo<br /> </td> 
   <td> IsMemoNull(&lt;Memorando&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>JuxtWords</strong><br /> </td> 
   <td> Concatena as duas strings transmitidas como parâmetros. Um espaço é adicionado entre cada string no valor retornado.<br /> </td> 
   <td> JuxtWords(&lt;cadeia de caracteres&gt;, &lt;cadeia de caracteres&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>JuxtWords3</strong><br /> </td> 
   <td> Concatena as três strings transmitidas como parâmetros. Um espaço é adicionado entre cada string no valor retornado.<br /> </td> 
   <td> JuxtWords3(&lt;cadeia de caracteres&gt;, &lt;cadeia de caracteres&gt;, &lt;cadeia de caracteres&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>LPad</strong><br /> </td> 
   <td> Retorna a cadeira de caracteres concluída à esquerda<br /> </td> 
   <td> LPad(&lt;cadeia de caracteres&gt;, &lt;número&gt;, &lt;caractere&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Left</strong><br /> </td> 
   <td> Retorna os primeiros n caracteres da cadeira de caracteres<br /> </td> 
   <td> Left(&lt;cadeia de caracteres&gt;, &lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Length</strong><br /> </td> 
   <td> Retorna o tamanho da string<br /> </td> 
   <td> Length(&lt;cadeia de caracteres&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Lower</strong><br /> </td> 
   <td> Retorna a cadeira de caracteres em minúsculas<br /> </td> 
   <td> Lower(&lt;cadeia de caracteres&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Ltrim</strong><br /> </td> 
   <td> Remove espaços à esquerda da cadeira de caracteres<br /> </td> 
   <td> Ltrim(&lt;cadeia de caracteres&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Md5Digest</strong><br /> </td> 
   <td> Retorna uma representação hexadecimal da chave MD5 de uma cadeira de caracteres<br /> </td> 
   <td> Md5Digest(&lt;cadeia de caracteres&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MemoContains</strong><br /> </td> 
   <td> Especifica se o memorando contém a cadeira de caracteres aprovada como um parâmetro<br /> </td> 
   <td> MemoContains(&lt;memorando&gt;, &lt;cadeia de caracteres&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>RPad</strong><br /> </td> 
   <td> Retorna a cadeira de caracteres concluída à direita<br /> </td> 
   <td> RPad(&lt;cadeia de caracteres&gt;, &lt;número&gt;, &lt;caractere&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Replace</strong><br /> </td> 
   <td> Substitui todas as ocorrências de um valor de string especificado (segundo parâmetro) por outro valor de string (terceiro parâmetro) em uma string (primeiro parâmetro)<br /> </td> 
   <td> Replace(&lt;Cadeia de caracteres&gt;, &lt;Cadeia de caracteres&gt;, &lt;Cadeia de caracteres&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Right</strong><br /> </td> 
   <td> Retorna os últimos n caracteres da cadeia de caracteres<br /> </td> 
   <td> Right(&lt;cadeia de caracteres&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Rtrim</strong><br /> </td> 
   <td> Remove espaços à direita da cadeira de caracteres<br /> </td> 
   <td> Rtrim(&lt;cadeia de caracteres&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sha256Digest</strong><br /> </td> 
   <td> Calcula o hash <strong>SHA256</strong> padrão para uma determinada string UTF8<br /> </td> 
   <td> Sha256Digest(&lt;Cadeia de caracteres&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sha384Digest</strong><br /> </td> 
   <td> Calcula o hash <strong>SHA384</strong> padrão para uma determinada string UTF8<br /> </td> 
   <td> Sha384Digest(&lt;Cadeia de caracteres&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sha512Digest</strong><br /> </td> 
   <td> Calcula o hash <strong>SHA512</strong> padrão para uma determinada string UTF8<br /> </td> 
   <td> Sha512Digest(&lt;Cadeia de caracteres&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Smart</strong><br /> </td> 
   <td> Retorna a cadeira de caracteres com a primeira letra de cada palavra em maiúsculas<br /> </td> 
   <td> Smart(&lt;cadeia de caracteres&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Substring</strong><br /> </td> 
   <td> Extrai a substring, começando no caractere n1 da string e com comprimento de n2<br /> </td> 
   <td> Substring(&lt;cadeia de caracteres&gt;, &lt;deslocamento&gt;, &lt;comprimento&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToIntlString</strong><br /> </td> 
   <td> Converte o número em uma cadeia de caracteres<br /> </td> 
   <td> ToIntlString(&lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToString</strong><br /> </td> 
   <td> Converte o número em uma cadeia de caracteres<br /> </td> 
   <td> ToString(&lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Upper</strong><br /> </td> 
   <td> Retorna a cadeia de caracteres em maiúsculas<br /> </td> 
   <td> Upper(&lt;cadeia de caracteres&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>VirtualLink</strong><br /> </td> 
   <td> Retorna a chave externa de um link passado como um parâmetro se os outros dois parâmetros forem iguais<br /> </td> 
   <td> VirtualLink(&lt;número&gt;, &lt;número&gt;, &lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>VirtualLinkStr</strong><br /> </td> 
   <td> Retorna a chave externa (texto) de um link passado como um parâmetro se os outros dois parâmetros forem iguais<br /> </td> 
   <td> VirtualLinkStr(&lt;cadeia de caracteres&gt;, &lt;número&gt;, &lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>encryption_aescbcDecrypt</strong><br /> </td> 
   <td> Descriptografa um valor criptografado no formato HEX com o prefixo "<strong>x</strong>" (primeiro parâmetro) usando uma chave no formato HEX (segundo parâmetro) e um vetor de inicialização no formato HEX (terceiro parâmetro)<br /> </td> 
   <td> encryption_aescbcDecrypt(&lt;Cadeia de caracteres&gt;, &lt;Cadeia de caracteres&gt;, &lt;Cadeia de caracteres&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>encryption_aescbcEncrypt</strong><br /> </td> 
   <td> Criptografa usando o algoritmo AES (modo de bloco CBC) uma string de caracteres (primeiro parâmetro) com uma chave (segundo parâmetro) e um vetor de inicialização (terceiro parâmetro). A chave e o vetor de inicialização devem ser fornecidos em uma representação hexadecimal (começando com <strong>\x</strong>). O resultado será hexadecimal sem o <strong>\x</strong>.<br /> Observe que o tamanho da chave pode ser de 128 bits, 192 bits, 256 bits (16, 24, 32 caracteres hexadecimais), mas recomendamos que você use 256 bits e um IV aleatório com o mesmo comprimento da chave.<br /> </td> 
   <td> encryption_aescbcEncrypt(&lt;Cadeia de caracteres&gt;, &lt;Cadeia de caracteres&gt;, &lt;Cadeia de caracteres&gt;)<br /> Por exemplo: encryption_aescbcEncrypt(johndoe@example.com, "<strong>\x0123456789ABCDEF0123456789ABCDEF</strong>", "<strong>\x0123456789ABCDEFFEDCBA9876543210</strong>")<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Agregados {#aggregates}

As funções de agregação só estão disponíveis ao [adicionar dados adicionais](../../automating/using/query.md#enriching-data) atividade **[!UICONTROL Query]** de um workflow.

As funções de agregação são usadas para realizar cálculos em um conjunto de valores.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Nome</strong><br /> </td> 
   <td> <strong>Descrição</strong><br /> </td> 
   <td> <strong>Sintaxe</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Avg</strong>, Average<br /> </td> 
   <td> Retorna a média em uma coluna numérica.<br /> </td> 
   <td> Avg(&lt;valor&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Count</strong>, Contagem (exceto NULL)<br /> </td> 
   <td> Conta os valores não nulos em uma coluna.<br /> </td> 
   <td> Count(&lt;valor&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>CountAll</strong>, Contar todos<br /> </td> 
   <td> Conta todos os valores (incluindo valores e duplicados nulos).<br /> </td> 
   <td> CountAll()<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Countdistinct</strong>, Distinct count<br /> </td> 
   <td> Conta os valores não nulos e distintos de uma coluna.<br /> </td> 
   <td> Countdistinct(&lt;valor&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Max</strong>, Máx<br /> </td> 
   <td> Retorna o valor máximo de uma coluna numérica, de string ou de data.<br /> </td> 
   <td> Max(&lt;valor&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Min</strong>, Mín<br /> </td> 
   <td> Retorna o valor mínimo de uma coluna numérica, de string ou de data.<br /> </td> 
   <td> Min(&lt;valor&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sum</strong>, Soma<br /> </td> 
   <td> Retorna a soma dos valores em uma coluna numérica.<br /> </td> 
   <td> Sum(&lt;valor&gt;)<br /> </td> 
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
   <td> Desc(&lt;valor 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>OrderBy</strong><br /> </td> 
   <td> Classifica o resultado dentro da partição<br /> </td> 
   <td> OrderBy(&lt;valor 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>PartitionBy</strong><br /> </td> 
   <td> Partições do resultado de um query em uma tabela<br /> </td> 
   <td> PartitionBy(&lt;valor 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>RowNum</strong><br /> </td> 
   <td> Gera um número de linha com base na partição da tabela e em uma sequência de classificação. Esta função não tem suporte para o MySQL<br /> </td> 
   <td> RowNum(PartitionBy(&lt;valor 1&gt;), OrderBy(&lt;valor 1&gt;))<br /> </td> 
  </tr> 
 </tbody> 
</table>

