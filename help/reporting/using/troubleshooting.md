---
solution: Campaign Standard
product: campaign
title: Solução de problemas
description: Encontre aqui perguntas comuns relacionadas ao relatórios dinâmico.
audience: reporting
content-type: reference
topic-tags: troubleshooting
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 5%

---


# Solução de problemas{#troubleshooting}

Nesta seção, você pode encontrar perguntas comuns relacionadas ao relatórios dinâmico.

## Para abertos exclusivos e cliques exclusivos, a contagem na linha de agregação não corresponde àqueles em linhas individuais {#unique-open-clicks-no-match}

Este é um comportamento esperado.
Podemos pegar o exemplo a seguir para explicar esse comportamento.

Um email é enviado para os perfis P1 e P2.

P1 abre o email duas vezes no primeiro dia e três vezes no segundo dia.

Enquanto isso, o P2 abre o email uma vez no primeiro dia e não o abre novamente nos dias seguintes.
Esta é uma representação visual da interação dos perfis com o email enviado:

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Day</strong> <br /> </th> 
   <th align="center"> <strong>Aberturas</strong> <br /> </th> 
   <th align="center"> <strong>Aberturas exclusivas</strong> <br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> Day 1<br /> </td> 
   <td align="center"> 2 + 1 = 3<br /> </td> 
   <td align="center"> 1 + 1 = 2<br /> </td> 
  </tr> 
  <tr> 
   <td align="center"> Day 2<br /> </td> 
   <td align="center"> 3 + 0 = 3<br /> </td> 
   <td align="center"> 1 + 0 = 1<br /> </td> 
  </tr>
 </tbody> 
</table>

Para entender o número total de aberturas únicas, precisamos somar as contagens de linhas das **[!UICONTROL Unique Opens]** quais nos dá o valor 3. Mas como o e-mail foi direcionado para apenas 2 perfis, a taxa de Abertura deve apresentar 150%.

Para não obter uma porcentagem superior a 100, a definição de **[!UICONTROL Unique Opens]** é mantida como o número de publicações exclusivas que foram abertas. Nesse caso, mesmo se P1 abrir o email no Dia 1 e no Dia 2, suas aberturas exclusivas ainda serão 1.

Isso resultará na seguinte tabela:

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Day</strong> <br /> </th> 
   <th align="center"> <strong>Aberturas</strong> <br /> </th> 
   <th align="center"> <strong>Aberturas exclusivas</strong> <br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> Day 1<br /> </td> 
   <td align="center"> 6<br /> </td> 
   <td align="center"> 2<br /> </td>
  </tr> 
  <tr> 
   <td align="center"> Day 2<br /> </td> 
   <td align="center"> 3<br /> </td> 
   <td align="center"> 2<br /> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Contagens exclusivas são baseadas em um rascunho baseado em HLL, isso pode causar pequenas imprecisões em contagens grandes.

## Contagens abertas não correspondem à contagem do Banco de Dados {#open-counts-no-match-database}

Isso pode ser devido ao fato de que as heurísticas são usadas no Dynamic relatórios para rastrear aberturas, mesmo quando não é possível rastrear a **[!UICONTROL Open]** ação.

Por exemplo, se um usuário tiver desabilitado imagens em seu cliente e clicar em um link no email, o usuário não **[!UICONTROL Open]** poderá ser rastreado pelo banco de dados, mas o **[!UICONTROL Click]** fará.

Portanto, as contagens de **[!UICONTROL Open]** logs de rastreamento podem não ter a mesma contagem no banco de dados.

Tais ocorrências são adicionadas como **&quot;um clique de email implica uma abertura de email&quot;**.

>[!NOTE]
>
>Como as contagens únicas são baseadas em um rascunho baseado em HLL, podem ocorrer pequenas inconsistências entre as contagens.

## Como são calculadas as contagens de delivery recorrentes/transacionais? {#counts-recurring-deliveries}

Ao trabalhar com delivery recorrentes e transacionais, as contagens serão atribuídas aos delivery pai e filho.
Podemos pegar o exemplo de um delivery recorrente chamado **R1** definido para ser executado todos os dias no dia 1 (RC1), no dia 2 (RC2) e no dia 3 (RC3).
Vamos supor que apenas uma única pessoa abriu todos os delivery da criança várias vezes. Nesse caso, os delivery filhos recorrentes individuais mostrarão a **[!UICONTROL Open]** contagem como 1 para cada um.
No entanto, como a mesma pessoa clicou em todos os delivery, o delivery recorrente pai também terá **[!UICONTROL Unique open]** 1.

Os relatórios devem se parecer com o seguinte:

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Delivery</strong> <br /> </th> 
   <th align="center"> <strong>Sent</strong> <br /> </th> 
   <th align="center"> <strong>Entregue</strong> <br /> </th>
   <th align="center"> <strong>Aberturas</strong> <br /> </th> 
   <th align="center"> <strong>Aberturas exclusivas</strong> <br /> </th>
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> <strong>R1<br/> </td> 
   <td align="center"> <strong>100<br/> </td> 
   <td align="center"> <strong>90<br/> </td> 
   <td align="center"> <strong>10<br/> </td> 
   <td align="center"> <strong>3<br/> </td> 
  </tr> 
  <tr> 
   <td align="center"> RC1<br/> </td> 
   <td align="center"> 20<br /> </td> 
   <td align="center"> 20<br /> </td> 
   <td align="center"> 6<br /> </td> 
   <td align="center"> 1<br /> </td> 
  </tr>
    <tr> 
   <td align="center"> RC2<br /> </td> 
   <td align="center"> 40<br /> </td> 
   <td align="center"> 30<br /> </td> 
   <td align="center"> 2<br /> </td> 
   <td align="center"> 1<br /> </td> 
  </tr> 
    <tr> 
   <td align="center"> RC3<br /> </td> 
   <td align="center"> 40<br /> </td> 
   <td align="center"> 40<br /> </td> 
   <td align="center"> 2<br /> </td> 
   <td align="center"> 1<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Qual é a significação das cores na tabela dos meus relatórios? {#reports-color-signification}

As cores exibidas em seus relatórios são aleatórias e não podem ser personalizadas. Eles representam uma barra de progresso e são exibidos para ajudá-lo a destacar melhor o valor máximo alcançado em seus relatórios.

No exemplo abaixo, a célula tem a mesma cor, pois seu valor é 100%.

![](assets/troubleshooting_1.png)

Se você alterar **[!UICONTROL Conditional formatting]** para personalizado, quando o valor atingir o limite superior, a célula ficará mais verde. Enquanto que, se atingir o limite inferior, ele ficará mais vermelho.

Por exemplo, aqui, definimos **[!UICONTROL Upper limit]** para 500 e **[!UICONTROL Lower limit]** para 0.

![](assets/troubleshooting_2.png)

## Por que o valor N/A aparece em meus relatórios?

![](assets/troubleshooting_3.png)

O valor **N/A** pode, às vezes, aparecer em seus relatórios dinâmicos. Isso pode ser exibido por dois motivos:

* O delivery foi excluído e é mostrado aqui como **N/A** para não causar discrepância nos resultados.
* Ao arrastar e soltar a **[!UICONTROL Transactional Delivery]** dimensão em seus relatórios, o valor **N/A** pode aparecer como resultado. Isso acontece porque o relatório dinâmico obtém cada delivery mesmo que não seja transacional.
Isso também pode ocorrer ao arrastar e soltar a **[!UICONTROL Delivery]** dimensão no relatório, mas, nesse caso, o valor **N/D** representará delivery transacionais.
