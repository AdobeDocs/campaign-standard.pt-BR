---
title: Solução de problemas
description: Encontre aqui perguntas comuns relacionadas aos relatórios dinâmicos.
page-status-flag: nunca ativado
uuid: a84a18bd-4e33-466e-a6ce-d7008fe12746
contentOwner: comida
products: SG_CAMPAIGN/STANDARD
audience: relatório
content-type: referência
topic-tags: solução de problemas
discoiquuid: bbbb41c38-12c1-4625-85d5-69627e2f4b39
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Solução de problemas{#troubleshooting}

Nesta seção, você pode encontrar perguntas comuns relacionadas aos relatórios dinâmicos.

## Para abertos exclusivos e cliques exclusivos, a contagem na linha agregada não corresponde àqueles em linhas individuais {#unique-open-clicks-no-match}

Este é um comportamento esperado.
Podemos pegar o exemplo a seguir para explicar esse comportamento.

Um email é enviado para os perfis P1 e P2.

P1 abre o email duas vezes no primeiro dia e três vezes no segundo dia.

Enquanto isso, P2 abre o email uma vez no primeiro dia e não o abre novamente nos dias seguintes.
Esta é uma representação visual da interação dos perfis com o email enviado:

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Dia</strong><br /> </th> 
   <th align="center"> <strong>Aberturas</strong> <br /> </th> 
   <th align="center"> <strong>Aberturas</strong> exclusivas <br /> </th> 
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

Para entender o número total de aberturas únicas, precisamos somar as contagens de linhas das **[!UICONTROL Unique Opens]** quais nos dá o valor 3. Mas como o e-mail foi direcionado para apenas 2 perfis, a taxa de abertura deve mostrar 150%.

Para não obter uma porcentagem superior a 100, a definição de **[!UICONTROL Unique Opens]** é mantida como o número de publicações exclusivas que foram abertas. Nesse caso, mesmo se P1 abrir o email no Dia 1 e no Dia 2, suas aberturas exclusivas ainda serão 1.

Isso resultará na seguinte tabela:

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Dia</strong><br /> </th> 
   <th align="center"> <strong>Aberturas</strong> <br /> </th> 
   <th align="center"> <strong>Aberturas</strong> exclusivas <br /> </th> 
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

Isso pode ser devido ao fato de que as heurísticas são usadas em relatórios dinâmicos para rastrear aberturas, mesmo quando não é possível rastrear a **[!UICONTROL Open]** ação.

Por exemplo, se um usuário tiver desabilitado imagens em seu cliente e clicar em um link no email, o usuário não **[!UICONTROL Open]** poderá ser rastreado pelo banco de dados, mas o **[!UICONTROL Click]** fará.

Portanto, as contagens dos logs de **[!UICONTROL Open]** rastreamento podem não ter a mesma contagem no banco de dados.

Tais ocorrências são adicionadas como **"um clique de email implica uma abertura de email"**.

>[!NOTE]
>
>Como as contagens exclusivas são baseadas em um rascunho baseado em HLL, podem ocorrer pequenas inconsistências entre as contagens.

## Como são calculadas as contagens de entregas recorrentes/transacionais?

Ao trabalhar com entregas recorrentes e transacionais, as contagens serão atribuídas às entregas pai e filho.

Podemos pegar o exemplo de uma entrega recorrente chamada **R1** definida para ser executada todos os dias no dia 1 (RC1), no dia 2 (RC2) e no dia 3 (RC3).

Vamos supor que apenas uma única pessoa abriu todas as entregas secundárias várias vezes. Nesse caso, as entregas secundárias recorrentes individuais mostrarão a **[!UICONTROL Open]** contagem como 1 para cada entrega.

No entanto, como a mesma pessoa clicou em todas as entregas, a entrega recorrente pai também terá **[!UICONTROL Unique open]** 1.

Após a versão 19.2.1 do Adobe Campaign Standard, a definição de contagens **** exclusivas é alterada de **Número de pessoas únicas interagindo com a entrega** para **Número de mensagens únicas interagidas**.

Antes da versão 19.2.1 do Adobe Campaign Standard, os relatórios pareciam com o seguinte:

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Entrega</strong><br /> </th> 
   <th align="center"> <strong>Enviado</strong><br /> </th> 
   <th align="center"> <strong>Entregue</strong><br /> </th>
   <th align="center"> <strong>Aberturas</strong> <br /> </th> 
   <th align="center"> <strong>Aberturas</strong> exclusivas <br /> </th>
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> <strong>R1<br/> </td> 
   <td align="center"> <strong>100<br/> </td> 
   <td align="center"> <strong>90<br/> </td> 
   <td align="center"> <strong>10<br/> </td> 
   <td align="center"> <strong>1<br/> </td> 
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

Após a versão 19.2.1 do Adobe Campaign Standard, os relatórios são parecidos com o seguinte:

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Entrega</strong><br /> </th> 
   <th align="center"> <strong>Enviado</strong><br /> </th> 
   <th align="center"> <strong>Entregue</strong><br /> </th>
   <th align="center"> <strong>Aberturas</strong> <br /> </th> 
   <th align="center"> <strong>Aberturas</strong> exclusivas <br /> </th>
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

Por exemplo, aqui, definimos **[!UICONTROL Upper limit]** como 500 e **[!UICONTROL Lower limit**] como 0.

![](assets/troubleshooting_2.png)

## Por que o valor N/A aparece em meus relatórios?

![](assets/troubleshooting_3.png)

O valor **N/A** pode, às vezes, aparecer em seus relatórios dinâmicos. Isso pode ser exibido por dois motivos:

* A entrega foi excluída e é mostrada aqui como **N/A** para não causar discrepância nos resultados.
* Ao arrastar e soltar a **[!UICONTROL Transactional Delivery]** dimensão em seus relatórios, o valor **N/A** pode aparecer como resultado. Isso acontece porque o relatório dinâmico obtém cada entrega mesmo que não seja transacional.
Isso também pode acontecer quando você arrastar e soltar a **[!UICONTROL Delivery]** dimensão no relatório, mas, nesse caso, o valor **N/D** representará entregas transacionais.
