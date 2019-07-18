---
title: Dimensões e métricas de campanha no Analytics
seo-title: Dimensões e métricas de campanha no Analytics
description: Dimensões e métricas de campanha no Analytics
seo-description: Saiba mais sobre as diferentes dimensões que podem ser encontradas no Adobe Analytics para começar a rastrear suas entregas de emails do Adobe Campaign.
page-status-flag: nunca ativado
uuid: effa 1028-66 b 2-4 bef-b 5 e 4-7319 dbb 23 d 5 d
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
discoiquuid: eb 3639 f 5-7246-46 c 4-8 ddb-da 9413 b 40 c 32
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Campaign dimensions and metrics in Analytics{#campaign-dimensions-and-metrics-in-analytics}

A integração do Adobe Campaign e do Adobe Analytics permite que você acompanhe o sucesso das entregas de email diretamente no Adobe Analytics.

Campaign **[!UICONTROL dimensions]** found in Analytics are listed below:

<table> 
 <thead> 
  <tr> 
   <th> Dimension<br /> </th> 
   <th> Definition<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Campaign ID<br /> </td> 
   <td> Campaign's internal name as seen in Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> Campaign label<br /> </td> 
   <td> Campaign's label as seen in Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivery ID<br /> </td> 
   <td> Nome interno da entrega como visto no Campaign.<br /> Por exemplo, DM 1 é uma entrega recorrente programada para enviar entregas secundárias todas as semanas. DM 2, DM 3 e DM 4 são enviados às três primeiras semanas. The Delivery ID dimension will then display the results for every delivery, namely DM1 to DM4. <br /> </td> 
  </tr> 
  <tr> 
   <td> Delivery label<br /> </td> 
   <td> Delivery's label as seen in Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> Executed delivery ID<br /> </td> 
   <td> Nome interno da entrega como visto no Campaign. Isso só diz respeito à entrega na execução no Campaign.<br /> Por exemplo, DM 1 é uma entrega recorrente programada para enviar entregas secundárias todas as semanas. DM 2, DM 3 e DM 4 são enviados às três primeiras semanas. The Executed delivery ID dimension will then display the results for the executed deliveries, namely the child deliveries DM2, DM3 and DM4. <br /> </td> 
  </tr> 
  <tr> 
   <td> Executed delivery label<br /> </td> 
   <td> Rótulo da entrega como visto no Campaign. This only concerns delivery in execution in Campaign.<br /> </td> 
  </tr> 
 </tbody> 
</table>

Campaign **[!UICONTROL metrics]** found in Analytics are listed below:

<table> 
 <thead> 
  <tr> 
   <th> Metric<br /> </th> 
   <th> Definition<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Clicked<br /> </td> 
   <td> Number of times a content was clicked in a delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivered<br /> </td> 
   <td> Number of messages successfully sent, in relation to the total number of sent messages.<br /> </td> 
  </tr> 
  <tr> 
   <td> Opened<br /> </td> 
   <td> Number of times a message was opened in a delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Sent<br /> </td> 
   <td> Total number of sends for the delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Total Bounces<br /> </td> 
   <td> Total of errors cumulated during delivery and automatic return processing in relation to the total number of sent messages.<br /> </td> 
  </tr> 
  <tr> 
   <td> Unique Open<br /> </td> 
   <td> Number of recipients who opened the delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Unique Click<br /> </td> 
   <td> Number of recipients who clicked on a content in a delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Unsubscribed<br /> </td> 
   <td> Number of clicks on the unsubscription link.<br /> </td> 
  </tr> 
 </tbody> 
</table>

