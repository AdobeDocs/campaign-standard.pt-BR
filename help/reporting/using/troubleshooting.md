---
title: Solução de problemas de relatórios dinâmicos
description: Encontre aqui perguntas comuns relacionadas aos Relatórios dinâmicos.
audience: reporting
content-type: reference
topic-tags: troubleshooting
feature: Reporting
role: Leader
level: Intermediate
exl-id: 0f99a109-2923-4e64-8131-80fcacf79c82
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '705'
ht-degree: 5%

---

# Solução de problemas{#troubleshooting}

Nesta seção, você pode encontrar perguntas comuns relacionadas aos Relatórios dinâmicos.

## Para aberturas exclusivas e cliques exclusivos, a contagem na linha de agregação não corresponde àquelas em linhas individuais {#unique-open-clicks-no-match}

Esse é um comportamento esperado.
Podemos usar o exemplo a seguir para explicar esse comportamento.

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
   <td align="center"> Dia 1<br /> </td> 
   <td align="center"> 2 + 1 = 3<br /> </td> 
   <td align="center"> 1 + 1 = 2<br /> </td> 
  </tr> 
  <tr> 
   <td align="center"> Dia 2<br /> </td> 
   <td align="center"> 3 + 0 = 3<br /> </td> 
   <td align="center"> 1 + 0 = 1<br /> </td> 
  </tr>
 </tbody> 
</table>

Para entender o número geral de aberturas exclusivas, precisamos somar as contagens de linha de **[!UICONTROL Unique Opens]** que nos dá o valor 3. Mas como o email foi direcionado para apenas 2 perfis, a taxa de abertura deve mostrar 150%.

Para não obter uma porcentagem superior a 100, a definição de **[!UICONTROL Unique Opens]** é mantido como o número de broadlogs exclusivos que foram abertos. Nesse caso, mesmo se P1 tiver aberto o email no Dia 1 e no Dia 2, suas aberturas exclusivas ainda serão 1.

Isso resultará na seguinte tabela:

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong></strong> <br /> </th> 
   <th align="center"> <strong>Aberturas</strong> <br /> </th> 
   <th align="center"> <strong>Aberturas exclusivas</strong> <br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> <strong> Day </strong><br /> </td> 
   <td align="center"> <strong> 6 </strong><br /> </td> 
   <td align="center"> <strong> 2</strong><br /> </td>
  </tr> 
  <tr> 
   <td align="center"> Dia 1<br /> </td> 
   <td align="center"> 3<br /> </td> 
   <td align="center"> 2<br /> </td>
  </tr> 
  <tr> 
   <td align="center"> Dia 2<br /> </td> 
   <td align="center"> 3<br /> </td> 
   <td align="center"> 1<br /> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>As contagens exclusivas são baseadas em um rascunho baseado em HLL, isso pode causar pequenas imprecisões em contagens grandes.

## Contagens abertas não correspondem à contagem Banco de dados {#open-counts-no-match-database}

Isso pode ser devido ao fato de que, as heurísticas são usadas no Dynamic Reporting para rastrear aberturas mesmo quando não podemos rastrear a variável **[!UICONTROL Open]** ação.

Por exemplo, se um usuário tiver desativado imagens em seu cliente e clicar em um link no email, a variável **[!UICONTROL Open]** não pode ser rastreado pelo banco de dados, mas o **[!UICONTROL Click]** o fará.

Por conseguinte, o **[!UICONTROL Open]** as contagens de logs de rastreamento podem não ter a mesma contagem no banco de dados.

Essas ocorrências são adicionadas como **&quot;um clique por email implica a abertura de um email&quot;**.

>[!NOTE]
>
>Como as contagens únicas são baseadas em um rascunho baseado em HLL, podem ocorrer pequenas inconsistências entre as contagens.

## Como as contagens de deliveries recorrentes/transacionais são calculadas? {#counts-recurring-deliveries}

Ao trabalhar com deliveries recorrentes e transacionais, as contagens serão atribuídas aos deliveries pai e filho.
Podemos ver o exemplo de um delivery recorrente chamado **R1** definido para ser executado todos os dias no dia 1 (RC1), no dia 2 (RC2) e no dia 3 (RC3).
Vamos supor que apenas uma única pessoa abriu todas as entregas secundárias várias vezes. Nesse caso, os deliveries secundários individuais recorrentes mostrarão a variável **[!UICONTROL Open]** contar como 1 para cada.
No entanto, como a mesma pessoa clicou em todos os deliveries, o delivery recorrente pai também terá **[!UICONTROL Unique open]** como 1.

Os relatórios devem ter a seguinte aparência:

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
   <td align="center"> <strong>R1</strong><br/> </td> 
   <td align="center"> <strong>100</strong><br/> </td> 
   <td align="center"> <strong>90º</strong><br/> </td> 
   <td align="center"> <strong>10º</strong><br/> </td> 
   <td align="center"> <strong>3</strong><br/> </td> 
  </tr> 
  <tr> 
   <td align="center"> RC1<br/> </td> 
   <td align="center"> 20º<br /> </td> 
   <td align="center"> 20º<br /> </td> 
   <td align="center"> 6<br /> </td> 
   <td align="center"> 1<br /> </td> 
  </tr>
    <tr> 
   <td align="center"> RC2<br /> </td> 
   <td align="center"> 40º<br /> </td> 
   <td align="center"> 30º<br /> </td> 
   <td align="center"> 2<br /> </td> 
   <td align="center"> 1<br /> </td> 
  </tr> 
    <tr> 
   <td align="center"> RC3<br /> </td> 
   <td align="center"> 40º<br /> </td> 
   <td align="center"> 40º<br /> </td> 
   <td align="center"> 2<br /> </td> 
   <td align="center"> 1<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Qual é o significado das cores na tabela dos meus relatórios? {#reports-color-signification}

As cores exibidas em seus relatórios são aleatorizadas e não podem ser personalizadas. Elas representam uma barra de progresso e são exibidas para ajudá-lo a destacar melhor o valor máximo atingido em seus relatórios.

No exemplo abaixo, a célula é da mesma cor, pois seu valor é 100%.

![](assets/troubleshooting_1.png)

Se você alterar a variável **[!UICONTROL Conditional formatting]** para personalizar, quando o valor atingir o limite superior, a célula ficará mais verde. Enquanto que, se atingir o limite inferior, ficará mais vermelho.

Por exemplo, aqui, definimos a variável **[!UICONTROL Upper limit]** a 500 e **[!UICONTROL Lower limit]** para 0.

![](assets/troubleshooting_2.png)

## Por que o valor N/A aparece nos meus relatórios?

![](assets/troubleshooting_3.png)

O valor **N/D** às vezes podem aparecer em seus relatórios dinâmicos. Isso pode ser exibido por três motivos:

* O delivery foi excluído e é mostrado aqui como **N/D** para não causar discrepância nos resultados.
* Ao arrastar e soltar a **[!UICONTROL Transactional Delivery]** para seus relatórios, o valor **N/D** pode aparecer como resultado. Isso acontece porque o relatório dinâmico obtém cada delivery mesmo que não seja transacional. Isso também pode acontecer ao arrastar e soltar a variável **[!UICONTROL Delivery]** para seu relatório, mas nesse caso, a variável **N/D** representará deliveries transacionais.
* Quando uma dimensão é usada com uma métrica que não está relacionada à dimensão. No exemplo abaixo, um detalhamento é adicionado com a variável **[!UICONTROL Tracking URL]** mesmo que a variável **[!UICONTROL Click]** é definida como 0 neste delivery.

   ![](assets/troubleshooting_4.png)

