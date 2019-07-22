---
title: Solução de problemas
seo-title: Solução de problemas
description: Solução de problemas
seo-description: Encontre aqui perguntas comuns relacionadas aos relatórios dinâmicos.
page-status-flag: nunca ativado
uuid: a 84 a 18 bd -4 e 33-466 e-a 6 ce-d 7008 fe 12746
contentOwner: beneat
products: SG_ CAMPAIGN/STANDARD
audience: relatórios
content-type: reference
topic-tags: solução de problemas
discoiquuid: bbb 41 c 38-12 c 1-4625-85 d 5-69627 e 2 f 4 b 39
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e0cbdfecde495d7c9f8bfa33dd5ee8598cdfe60a

---


# Troubleshooting{#troubleshooting}

Você pode encontrar nesta seção perguntas comuns relacionadas ao relatório dinâmico.

## For Unique opens and Unique clicks, the count in the aggregate row is not matching the ones in individual rows {#unique-open-clicks-no-match}

Esse é um comportamento esperado.
Podemos usar o seguinte exemplo para explicar esse comportamento.

Um email é enviado para perfis P 1 e P 2.

O P 1 abre o email duas vezes no primeiro dia e, em seguida, em tempo de árvore no segundo dia.

Considerando que P 2 abre o email uma vez no primeiro dia e não o abre novamente nos dias seguintes.
Esta é uma representação visual da interação dos perfis com o email enviado:

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Dia</strong><br /> </th> 
   <th align="center"> <strong>Aberturas</strong><br /> </th> 
   <th align="center"> <strong>Aberturas únicas</strong><br /> </th> 
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

To understand the overall number of unique opens, we need to sum up the row counts of **[!UICONTROL Unique Opens]** which gives us the value 3. Mas como o email foi direcionado para apenas 2 perfis, a taxa de Abertura deve mostrar 150%.

To not obtain percentage higher than 100, the definition of **[!UICONTROL Unique Opens]** is maintained to be the number of unique broadlogs that were opened. Nesse caso, mesmo se P 1 abrir o e-mail no Dia 1 e no Dia 2, sua abertura exclusiva ainda será 1.

Isso resultará na seguinte tabela:

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Dia</strong><br /> </th> 
   <th align="center"> <strong>Aberturas</strong><br /> </th> 
   <th align="center"> <strong>Aberturas únicas</strong><br /> </th> 
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
>Contagens únicas são baseadas em um rascunho baseado em HLL, isso pode causar pequenas imprecisões em grandes contagens.

## Open counts do not match the Database count {#open-counts-no-match-database}

This may be due to the fact that, heuristics are used in Dynamic reporting to track opens even when we can't track the **[!UICONTROL Open]** action.

For example, if a user has disabled images on their client and click on a link in the email, the **[!UICONTROL Open]** may not be tracked by the database but the **[!UICONTROL Click]** will.

Therefore, the **[!UICONTROL Open]** tracking logs counts may not have the same count in the database.

Such occurrences are added as **"an email click implies an email open"**.

>[!NOTE]
>
>Como as contagens únicas são baseadas em um rascunho baseado em HLL, é possível observar inconsistências menores entre as contagens.

## Como as contagens de entregas recorrentes/transacionais são calculadas?

Ao trabalhar com entregas recorrentes e transacionais, as contagens serão atribuídas às entregas pai e filho.

We can take the example of a recurring delivery named **R1** set to run every day on day 1 (RC1), day 2 (RC2) and day 3 (RC3).

Vamos supor que somente uma única pessoa abriu todas as entregas secundárias várias vezes. In this case, the individual recurring child deliveries will show the **[!UICONTROL Open]** count as 1 for each.

However, since the same person clicked on all the deliveries, the parent recurring delivery will also have **[!UICONTROL Unique open]** as 1.

After the Adobe Campaign Standard 19.2.1 release, the definition of **Unique counts** is changed from **Number of unique persons interacting with the delivery** to **Number of unique messages interacted**.

Antes da versão do Adobe Campaign Standard 19.2.1, os relatórios se pareciam como:

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Entrega</strong><br /> </th> 
   <th align="center"> <strong>Enviado</strong><br /> </th> 
   <th align="center"> <strong>Entregue</strong><br /> </th>
   <th align="center"> <strong>Aberturas</strong><br /> </th> 
   <th align="center"> <strong>Aberturas únicas</strong><br /> </th>
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

Após a versão do Adobe Campaign Standard 19.2.1, os relatórios se parecem com o seguinte:

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Entrega</strong><br /> </th> 
   <th align="center"> <strong>Enviado</strong><br /> </th> 
   <th align="center"> <strong>Entregue</strong><br /> </th>
   <th align="center"> <strong>Aberturas</strong><br /> </th> 
   <th align="center"> <strong>Aberturas únicas</strong><br /> </th>
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

## What is the colors' signification in my reports' table? {#reports-color-signification}

As cores exibidas em seus relatórios são aleatorizadas e não podem ser personalizadas. Representam uma barra de progresso e são exibidas para ajudá-lo a realçar melhor o valor máximo alcançado em seus relatórios.

No exemplo abaixo, a célula é da mesma cor, visto que seu valor é 100%.

![](assets/troubleshooting_1.png)

If you change the **Conditional formatting** to custom, when the value reaches the upper limit the cell will get greener. Se chegar ao limite inferior, ele será refeito.

For example, here, we set the **Upper limit** to 500 and **Lower limit** to 0.

![](assets/troubleshooting_2.png)