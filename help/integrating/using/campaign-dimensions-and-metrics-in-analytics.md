---
solution: Campaign Standard
product: campaign
title: Dimensões e métricas do Campaign no Analytics
description: Saiba mais sobre as diferentes dimensões que você pode encontrar no Adobe Analytics para o start que rastreia seus delivery de email da Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 7%

---


# Dimensões e métricas do Campaign no Analytics{#campaign-dimensions-and-metrics-in-analytics}

A integração entre a Adobe Campaign e a Adobe Analytics permite rastrear o sucesso dos delivery de email diretamente no Adobe Analytics.

Campanhas **[!UICONTROL dimensions]** encontradas no Analytics estão listadas abaixo:

<table> 
 <thead> 
  <tr> 
   <th> Dimensão<br /> </th> 
   <th> Definição<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> ID da campanha<br /> </td> 
   <td> Nome interno da campanha, como visto na Campanha<br /> </td> 
  </tr> 
  <tr> 
   <td> etiqueta da campanha<br /> </td> 
   <td> Etiqueta da campanha, conforme visto na Campanha<br /> </td> 
  </tr> 
  <tr> 
   <td> ID do delivery<br /> </td> 
   <td> Nome interno do delivery, como visto na Campanha.<br /> Por exemplo, DM1 é um delivery recorrente programado para enviar delivery filhos toda semana. DM2, DM3 e DM4 são enviados nas três primeiras semanas. A dimensão da ID do Delivery exibirá os resultados de cada delivery, a saber, DM1 para DM4. <br /> </td> 
  </tr> 
  <tr> 
   <td> Etiqueta do delivery<br /> </td> 
   <td> Etiqueta do delivery, conforme visto na Campanha<br /> </td> 
  </tr> 
  <tr> 
   <td> ID de delivery executada<br /> </td> 
   <td> Nome interno do delivery, como visto na Campanha. Isso só diz respeito ao delivery na execução na Campanhas.<br /> Por exemplo, DM1 é um delivery recorrente programado para enviar delivery filhos toda semana. DM2, DM3 e DM4 são enviados nas três primeiras semanas. A dimensão da ID de delivery Executada exibirá os resultados dos delivery executados, ou seja, os delivery filho DM2, DM3 e DM4. <br /> </td> 
  </tr> 
  <tr> 
   <td> Rótulo de delivery executado<br /> </td> 
   <td> Etiqueta do delivery, como visto na Campanha. Isso só diz respeito ao delivery na execução na Campanhas.<br /> </td> 
  </tr> 
 </tbody> 
</table>

Campanhas **[!UICONTROL metrics]** encontradas no Analytics estão listadas abaixo:

<table> 
 <thead> 
  <tr> 
   <th> Métrica<br /> </th> 
   <th> Definição<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Clicado<br /> </td> 
   <td> Número de vezes que um conteúdo foi clicado em um delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Entregue<br /> </td> 
   <td> Número de mensagens enviadas com êxito, em relação ao número total de mensagens enviadas.<br /> </td> 
  </tr> 
  <tr> 
   <td> Aberto<br /> </td> 
   <td> Número de vezes que uma mensagem foi aberta em um delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Sent<br /> </td> 
   <td> Número total de envios para o delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Total de rejeições<br /> </td> 
   <td> Total de erros acumulados durante o processamento de retorno automático e delivery em relação ao número total de mensagens enviadas.<br /> </td> 
  </tr> 
  <tr> 
   <td> Abertura exclusiva<br /> </td> 
   <td> Número de recipient que abriram o delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clique único<br /> </td> 
   <td> Número de recipient que clicaram em um conteúdo em um delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Inscrito<br /> </td> 
   <td> Número de cliques no link unsubscription.<br /> </td> 
  </tr> 
 </tbody> 
</table>

