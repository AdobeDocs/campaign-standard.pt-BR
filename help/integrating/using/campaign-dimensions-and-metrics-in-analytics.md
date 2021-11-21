---
title: Dimensões e métricas do Campaign no Analytics
description: Saiba mais sobre as diferentes dimensões que você pode encontrar no Adobe Analytics para começar a rastrear seus deliveries de email pelo Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 6516c71a-efa8-4778-82bb-10615378f985
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 7%

---

# Dimensões e métricas do Campaign no Analytics{#campaign-dimensions-and-metrics-in-analytics}

A integração Adobe Campaign e Adobe Analytics permite rastrear o sucesso de seus deliveries de email diretamente no Adobe Analytics.

Campanha **[!UICONTROL dimensions]** Os encontrados no Analytics estão listados abaixo:

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
   <td> O nome interno da campanha, como visto no Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> Rótulo da campanha<br /> </td> 
   <td> O rótulo da campanha como visto no Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> ID de entrega<br /> </td> 
   <td> O nome interno do delivery, como visto no Campaign.<br /> Por exemplo, DM1 é um delivery recorrente agendado para enviar deliveries filho toda semana. DM2, DM3 e DM4 são enviados nas três primeiras semanas. A dimensão ID da entrega exibirá os resultados para cada delivery, especificamente DM1 para DM4. <br /> </td> 
  </tr> 
  <tr> 
   <td> Rótulo da entrega<br /> </td> 
   <td> O rótulo da entrega como visto no Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> ID de entrega executada<br /> </td> 
   <td> O nome interno do delivery, como visto no Campaign. Isso só afeta a entrega na execução no Campaign.<br /> Por exemplo, DM1 é um delivery recorrente agendado para enviar deliveries filho toda semana. DM2, DM3 e DM4 são enviados nas três primeiras semanas. A dimensão ID de delivery Executado exibirá os resultados das entregas executadas, ou seja, as entregas secundárias DM2, DM3 e DM4. <br /> </td> 
  </tr> 
  <tr> 
   <td> Rótulo de entrega executado<br /> </td> 
   <td> O rótulo da entrega como visto no Campaign. Isso só afeta a entrega na execução no Campaign.<br /> </td> 
  </tr> 
 </tbody> 
</table>

Campanha **[!UICONTROL metrics]** Os encontrados no Analytics estão listados abaixo:

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
   <td> Número de mensagens enviadas com êxito em relação ao número total de mensagens enviadas.<br /> </td> 
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
   <td> Total de erros acumulados durante o delivery e o processamento automático de retorno em relação ao número total de mensagens enviadas.<br /> </td> 
  </tr> 
  <tr> 
   <td> Abertura única<br /> </td> 
   <td> Número de recipients que abriram o delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clique único<br /> </td> 
   <td> Número de recipients que clicaram em um conteúdo em um delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Inscrições canceladas<br /> </td> 
   <td> Número de cliques no link unsubscription.<br /> </td> 
  </tr> 
 </tbody> 
</table>
